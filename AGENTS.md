# 빌드 및 테스트 (Build and testing)

프로젝트의 빌드 및 테스트는 관련된 컴포넌트와 개발이 진행되는 플랫폼에 따라 다릅니다. 필요한 컨텍스트의 양이 많기 때문에 사용자가 요청하지 않는 한 프로젝트를 빌드하거나 테스트하지 않는 것이 좋습니다. 프로젝트를 빌드해야 하는 경우, 프로젝트 루트의 Makefile과 변경 사항의 영향을 받는 모든 백엔드의 Makefile을 검사하십시오. 또한, 컴포넌트를 빌드하거나 테스트하는 방법이 불분명할 때는 `.github/workflows`의 워크플로우를 참조로 사용할 수 있습니다. 기본 Makefile에는 Docker 내부 또는 외부 빌드를 위한 타겟이 포함되어 있습니다. 사용자가 이전에 선호도를 지정하지 않았다면 어느 것을 사용할지 물어보십시오.

## 특정 백엔드 빌드

사용자가 특정 플랫폼에 대해 특정 백엔드를 빌드하려는 경우를 가정해 보겠습니다. 예를 들어, ROCM/hipblas용 bark를 빌드하려는 경우:

- Makefile에는 작성 시점에 `generate-docker-build-target`으로 생성된 `docker-build-bark`와 같은 타겟이 있습니다. 최근에 추가된 백엔드는 새 타겟이 필요할 수 있습니다.
- 최소한 BUILD_TYPE, BASE_IMAGE build-args를 설정해야 합니다.
  - `.github/workflows/backend.yml`을 참조로 사용하십시오. `include` 작업 전략 매트릭스에 필요한 인수가 나열되어 있습니다.
  - l4t 및 cublas는 CUDA 메이저 및 마이너 버전도 필요합니다.
- 다음과 같이 명령어를 예쁘게 출력할 수 있습니다: `DOCKER_MAKEFLAGS=-j$(nproc --ignore=1) BUILD_TYPE=hipblas BASE_IMAGE=rocm/dev-ubuntu-24.04:6.4.4 make docker-build-bark`
- 사용자가 명령어를 실행하기를 원한다고 명시하지 않는 한, 명령어만 출력하십시오. 모든 에이전트 프런트엔드가 장시간 실행되는 작업을 잘 처리하는 것은 아니며 출력이 컨텍스트를 초과할 수 있기 때문입니다.
- 사용자가 hipblas 대신 AMD 또는 ROCM을, SYCL 대신 Intel을, l4t 또는 cublas 대신 NVIDIA를 빌드하라고 말할 수 있습니다. 모호한 경우 확인을 요청하십시오.
- 때로는 사용자가 `docker build`에 추가 매개변수(예: 크로스 플랫폼 빌드를 위한 `--platform` 또는 전체 로그를 보기 위한 `--progress`)를 추가해야 할 수도 있습니다. 이 경우 `docker build` 명령어를 직접 생성할 수 있습니다.

## 새로운 백엔드 추가

LocalAI에 새 백엔드를 추가할 때, 백엔드가 적절하게 빌드, 테스트 및 등록되도록 여러 파일을 업데이트해야 합니다. 다음은 `moonshine`과 같은 백엔드를 추가할 때 사용된 패턴을 기반으로 한 단계별 가이드입니다:

### 1. 백엔드 디렉토리 구조 생성

적절한 위치에 백엔드 디렉토리를 생성합니다:
- **Python 백엔드**: `backend/python/<backend-name>/`
- **Go 백엔드**: `backend/go/<backend-name>/`
- **C++ 백엔드**: `backend/cpp/<backend-name>/`

Python 백엔드의 경우 일반적으로 다음 파일이 필요합니다:
- `backend.py` - 기본 gRPC 서버 구현
- `Makefile` - 빌드 구성
- `install.sh` - 의존성 설치 스크립트
- `protogen.sh` - 프로토콜 버퍼 생성 스크립트
- `requirements.txt` - Python 의존성
- `run.sh` - 런타임 스크립트
- `test.py` / `test.sh` - 테스트 파일

### 2. `.github/workflows/backend.yml`에 빌드 구성 추가

지원하려는 각 플랫폼/GPU 유형에 대한 빌드 매트릭스 항목을 추가합니다. 참조를 위해 유사한 백엔드(예: `chatterbox`, `faster-whisper`)를 확인하십시오.

**파일 내 배치:**
- CPU 빌드: 다른 CPU 빌드 뒤에 추가 (예: `cpu-chatterbox` 뒤)
- CUDA 12 빌드: 다른 CUDA 12 빌드 뒤에 추가 (예: `gpu-nvidia-cuda-12-chatterbox` 뒤)
- CUDA 13 빌드: 다른 CUDA 13 빌드 뒤에 추가 (예: `gpu-nvidia-cuda-13-chatterbox` 뒤)

**필요할 수 있는 추가 빌드 유형:**
- ROCm/HIP: `build-type: 'hipblas'`와 `base-image: "rocm/dev-ubuntu-24.04:6.4.4"` 사용
- Intel/SYCL: `build-type: 'intel'` 또는 `build-type: 'sycl_f16'`/`sycl_f32`와 `base-image: "intel/oneapi-basekit:2025.3.0-0-devel-ubuntu24.04"` 사용
- L4T (ARM): `build-type: 'l4t'`와 `platforms: 'linux/arm64'`, `runs-on: 'ubuntu-24.04-arm'` 사용

### 3. `backend/index.yaml`에 백엔드 메타데이터 추가

**3a단계: 메타 정의 추가**

`## metas` 섹션(약 2-300행 부근)에 YAML 앵커 정의를 추가합니다. `diffusers`나 `chatterbox`와 같은 유사한 백엔드를 템플릿으로 사용하십시오.

**3b단계: 이미지 항목 추가**

유사한 백엔드의 패턴에 따라 파일 끝에 이미지 항목을 추가합니다. `latest`(운영) 및 `master`(개발) 태그를 모두 포함하십시오.

### 4. Makefile 업데이트

새 백엔드의 빌드 및 테스트를 지원하기 위해 Makefile을 여러 곳에서 업데이트해야 합니다:

**4a단계: `.NOTPARALLEL`에 추가**

병렬 실행 충돌을 방지하기 위해 `.NOTPARALLEL` 라인(약 2행 부근)에 `backends/<backend-name>`을 추가합니다:

```makefile
.NOTPARALLEL: ... backends/<backend-name>
```

**4b단계: `prepare-test-extra`에 추가**

테스트 준비를 위해 `prepare-test-extra` 타겟(약 312행 부근)에 백엔드를 추가합니다:

```makefile
prepare-test-extra: protogen-python
	...
	$(MAKE) -C backend/python/<backend-name>
```

**4c단계: `test-extra`에 추가**

테스트 실행을 위해 `test-extra` 타겟(약 319행 부근)에 백엔드를 추가합니다:

```makefile
test-extra: prepare-test-extra
	...
	$(MAKE) -C backend/python/<backend-name> test
```

**4d단계: 백엔드 정의 추가**

백엔드 정의 섹션(약 428-457행 부근)에 백엔드 정의 변수를 추가합니다. 형식은 백엔드 유형에 따라 다릅니다:

**루트 컨텍스트를 사용하는 Python 백엔드** (`faster-whisper`, `bark` 등):
```makefile
BACKEND_<BACKEND_NAME> = <backend-name>|python|.|false|true
```

**`./backend` 컨텍스트를 사용하는 Python 백엔드** (`chatterbox`, `moonshine` 등):
```makefile
BACKEND_<BACKEND_NAME> = <backend-name>|python|./backend|false|true
```

**Go 백엔드**:
```makefile
BACKEND_<BACKEND_NAME> = <backend-name>|golang|.|false|true
```

**4e단계: Docker 빌드 타겟 생성**

docker-build 타겟을 생성하기 위한 eval 호출을 추가합니다(약 480-501행 부근):

```makefile
$(eval $(call generate-docker-build-target,$(BACKEND_<BACKEND_NAME>)))
```

**4f단계: `docker-build-backends`에 추가**

`docker-build-backends` 타겟(약 507행 부근)에 `docker-build-<backend-name>`을 추가합니다:

```makefile
docker-build-backends: ... docker-build-<backend-name>
```

**컨텍스트 결정 방법:**

- 백엔드가 `backend/python/<backend-name>/`에 있고 워크플로우 파일에서 `./backend`를 컨텍스트로 사용하면, `./backend` 컨텍스트를 사용하십시오.
- 백엔드가 `backend/python/<backend-name>/`에 있지만 워크플로우 파일에서 `.`을 컨텍스트로 사용하면, `.` 컨텍스트를 사용하십시오.
- 정확한 컨텍스트를 결정하려면 유사한 백엔드를 확인하십시오.

### 5. 검증 체크리스트

새 백엔드를 추가한 후 다음 사항을 확인하십시오:

- [ ] 백엔드 디렉토리 구조가 필요한 모든 파일과 함께 완료됨
- [ ] 원하는 모든 플랫폼에 대해 `.github/workflows/backend.yml`에 빌드 구성이 추가됨
- [ ] `backend/index.yaml`의 `## metas` 섹션에 메타 정의가 추가됨
- [ ] 모든 빌드 변형(latest + master)에 대해 `backend/index.yaml`에 이미지 항목이 추가됨
- [ ] 워크플로우 파일과 index.yaml 사이의 태그 접미사가 일치함
- [ ] Makefile이 6가지 필수 변경 사항(`.NOTPARALLEL`, `prepare-test-extra`, `test-extra`, 백엔드 정의, docker-build 타겟 eval, `docker-build-backends`)으로 업데이트됨
- [ ] YAML 구문 오류 없음 (린터로 확인)
- [ ] Makefile 구문 오류 없음 (린터로 확인)
- [ ] 유사한 백엔드의 패턴을 따름 (예: 전사 백엔드인 경우 `faster-whisper` 패턴을 따름)

### 6. 예시: Python 백엔드 추가

참조를 위해 `moonshine`이 추가되었을 때:
- **생성된 파일**: `backend/python/moonshine/{backend.py, Makefile, install.sh, protogen.sh, requirements.txt, run.sh, test.py, test.sh}`
- **워크플로우 항목**: 3개의 빌드 구성 (CPU, CUDA 12, CUDA 13)
- **인덱스 항목**: 1개의 메타 정의 + 6개의 이미지 항목 (cpu, cuda12, cuda13 × latest/master)
- **Makefile 업데이트**: 
  - `.NOTPARALLEL` 라인에 추가됨
  - `prepare-test-extra` 및 `test-extra` 타겟에 추가됨
  - `BACKEND_MOONSHINE = moonshine|python|./backend|false|true` 추가됨
  - docker-build 타겟 생성을 위한 eval 추가됨
  - `docker-build-backends`에 `docker-build-moonshine` 추가됨

# 코딩 스타일

- 프로젝트에는 다음 `.editorconfig`가 적용되어 있습니다:

```
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.go]
indent_style = tab

[Makefile]
indent_style = tab

[*.proto]
indent_size = 2

[*.py]
indent_size = 4

[*.js]
indent_size = 2

[*.yaml]
indent_size = 2

[*.md]
trim_trailing_whitespace = false
```

- 코드가 무엇을 하는지가 아니라 왜 그렇게 하는지를 설명하기 위해 주석을 제한적으로 사용하십시오. 주석은 코드를 읽어서 추론하기 어려운 컨텍스트를 추가하는 데 사용됩니다.
- 현대적인 Go를 선호하십시오. 예: `interface{}`가 아닌 `any` 사용

# 로깅

slog와 동일한 API를 갖춘 로깅을 위해 `github.com/mudler/xlog`를 사용하십시오.

# llama.cpp 백엔드

llama.cpp 백엔드(`backend/cpp/llama-cpp/grpc-server.cpp`)는 업스트림 HTTP 서버(`llama.cpp/tools/server/server.cpp`)를 gRPC에 맞게 조정한 것입니다. `llama.cpp/tools/server/server-context.cpp`의 동일한 기본 서버 인프라를 사용합니다.

## 빌드 및 테스트

- llama.cpp 백엔드 컴파일 테스트: `make backends/llama-cpp`
- 백엔드는 메인 빌드 프로세스의 일부로 빌드됩니다.
- 빌드 구성에 대해서는 `backend/cpp/llama-cpp/Makefile`을 확인하십시오.

## 아키텍처

- **grpc-server.cpp**: gRPC 서버 구현, HTTP 서버 패턴을 gRPC에 맞게 조정
- 공유 서버 인프라 사용: `server-context.cpp`, `server-task.cpp`, `server-queue.cpp`, `server-common.cpp`
- gRPC 서버는 HTTP 서버의 기능을 미러링하지만 HTTP 대신 gRPC를 사용합니다.

## 업스트림 llama.cpp 업데이트 시 일반적인 문제

업스트림 변경 후 컴파일 오류를 수정할 때:
1. HTTP 서버(`server.cpp`)가 동일한 변경 사항을 어떻게 처리하는지 확인하십시오.
2. 새 공용 API 또는 getter 메서드를 찾으십시오.
3. 비공개 멤버에 액세스하는 대신 필요한 데이터의 복사본을 저장하십시오.
4. 새 시그니처와 일치하도록 함수 호출을 업데이트하십시오.
5. `make backends/llama-cpp`로 테스트하십시오.

## HTTP 서버와의 주요 차이점

- gRPC는 gRPC 서비스 메서드가 포함된 `BackendServiceImpl` 클래스를 사용합니다.
- HTTP 서버는 HTTP 핸들러가 포함된 `server_routes`를 사용합니다.
- 둘 다 동일한 `server_context` 및 태스크 큐 인프라를 사용합니다.
- gRPC 메서드: `LoadModel`, `Predict`, `PredictStream`, `Embedding`, `Rerank`, `TokenizeString`, `GetMetrics`, `Health`

## 도구 호출 파싱 유지 관리

JSON/XML 도구 호출 파싱 기능을 작업할 때는 항상 llama.cpp를 참조 구현 및 업데이트로 확인하십시오:

### XML 파싱 변경 사항 확인

1. **XML 형식 정의 검토**: `xml_tool_call_format` 구조체 변경 사항은 `llama.cpp/common/chat-parser-xml-toolcall.h`를 확인하십시오.
2. **파싱 로직 검토**: 파싱 알고리즘 업데이트는 `llama.cpp/common/chat-parser-xml-toolcall.cpp`를 확인하십시오.
3. **형식 프리셋 검토**: 새 XML 형식 프리셋은 `llama.cpp/common/chat-parser.cpp`를 확인하십시오 (`xml_tool_call_format form` 검색).
4. **모델 목록 검토**: XML 파싱을 사용하는 `COMMON_CHAT_FORMAT_*` 열거형 값은 `llama.cpp/common/chat.h`를 확인하십시오:
   - `COMMON_CHAT_FORMAT_GLM_4_5`
   - `COMMON_CHAT_FORMAT_MINIMAX_M2`
   - `COMMON_CHAT_FORMAT_KIMI_K2`
   - `COMMON_CHAT_FORMAT_QWEN3_CODER_XML`
   - `COMMON_CHAT_FORMAT_APRIEL_1_5`
   - `COMMON_CHAT_FORMAT_XIAOMI_MIMO`
   - 새로 추가된 모든 형식

### 모델 구성 옵션

항상 LocalAI에서 지원해야 하는 새 모델 구성 옵션이 있는지 `llama.cpp`를 확인하십시오:

1. **서버 컨텍스트 확인**: 새 매개변수는 `llama.cpp/tools/server/server-context.cpp`를 검토하십시오.
2. **채팅 파라미터 확인**: `common_chat_params` 구조체 변경 사항은 `llama.cpp/common/chat.h`를 검토하십시오.
3. **서버 옵션 확인**: 명령줄 인수 변경 사항은 `llama.cpp/tools/server/server.cpp`를 검토하십시오.
4. **확인할 옵션 예시**:
   - `ctx_shift` - 컨텍스트 시프팅 지원
   - `parallel_tool_calls` - 병렬 도구 호출
   - `reasoning_format` - 추론 형식 옵션
   - 모든 새 플래그 또는 매개변수

### 구현 가이드라인

1. **기능 패리티**: 항상 llama.cpp의 구현과 기능 패리티를 목표로 하십시오.
2. **테스트 커버리지**: llama.cpp의 동작과 일치하는 새 기능에 대한 테스트를 추가하십시오.
3. **문서화**: 새 형식이나 옵션을 추가할 때 관련 문서를 업데이트하십시오.
4. **하위 호환성**: 변경 사항이 기존 기능을 손상시키지 않도록 하십시오.

### 모니터링할 파일

- `llama.cpp/common/chat-parser-xml-toolcall.h` - 형식 정의
- `llama.cpp/common/chat-parser-xml-toolcall.cpp` - 파싱 로직
- `llama.cpp/common/chat-parser.cpp` - 형식 프리셋 및 모델별 핸들러
- `llama.cpp/common/chat.h` - 형식 열거형 및 매개변수 구조체
- `llama.cpp/tools/server/server-context.cpp` - 서버 구성 옵션
