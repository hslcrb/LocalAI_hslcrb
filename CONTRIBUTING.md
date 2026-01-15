# LocalAI 기여 가이드 (Contributing to LocalAI)

LocalAI 기여에 관심을 가져주셔서 감사합니다! 프로젝트 개선을 위한 여러분의 시간과 노력에 감사드립니다. 시작하기 전에 잠시 시간을 내어 다음 가이드라인을 검토해 주세요.

## 목차

- [시작하기](#시작하기)
  - [사전 요구 사항](#사전-요구-사항)
  - [개발 환경 설정](#개발-환경-설정)
- [기여하기](#기여하기)
  - [이슈 제보](#이슈-제보)
  - [풀 리퀘스트(PR) 생성](#풀-리퀘스트pr-생성)
- [코딩 가이드라인](#코딩-가이드라인)
- [테스트](#테스트)
- [문서화](#문서화)
- [커뮤니티 및 소통](#커뮤니티-및-소통)

## 시작하기

### 사전 요구 사항

- Golang [1.21]
- Git
- macOS/Linux

### 로컬 환경에서 개발 환경 설정 및 LocalAI 실행

1. 저장소 클론: `git clone https://github.com/go-skynet/LocalAI.git`
2. 프로젝트 디렉토리로 이동: `cd LocalAI`
3. 필요한 의존성 설치 ( https://localai.io/basics/build/#build-localai-locally 참조 )
4. LocalAI 빌드: `make build`
5. LocalAI 실행: `./local-ai`
6. 빌드 및 라이브 리로드(Live Reload): `make build-dev`

## 기여하기

누구나 기여할 수 있습니다! 시작하려면 다음 단계를 따르세요:

### 이슈 제보

버그를 발견하거나, 새로운 기능을 요청하거나, 문제를 겪고 있다면 [이슈 트래커](https://github.com/go-skynet/LocalAI/issues)를 확인하여 유사한 이슈가 이미 보고되었는지 확인해 주세요. 그렇지 않다면 [새로운 이슈를 생성](https://github.com/go-skynet/LocalAI/issues/new)하고 가능한 한 자세한 내용을 제공해 주세요.

### 풀 리퀘스트(PR) 생성

1. 저장소를 포크(Fork)합니다.
2. 설명이 포함된 이름으로 새 브랜치를 생성합니다: `git checkout -b [브랜치 이름]`
3. 변경 사항을 만들고 커밋합니다.
4. 포크한 저장소로 변경 사항을 푸시합니다: `git push origin [브랜치 이름]`
5. 여러분의 브랜치에서 메인 프로젝트의 `main` 또는 `master` 브랜치로 새 풀 리퀘스트를 생성합니다.
6. 풀 리퀘스트에 변경 사항에 대한 명확한 설명을 작성합니다.
7. 리뷰 과정에서 요청된 변경 사항을 반영합니다.
8. PR이 승인되면 메인 프로젝트에 병합됩니다.

## 코딩 가이드라인

- 현재 특별한 코딩 가이드라인은 없습니다. 코드가 테스트 가능한지 확인해 주세요. [`golangci-lint`](https://golangci-lint.run)와 같은 인기 있는 린트 도구가 도움이 될 수 있습니다.

## 테스트

`make test`는 현재 모든 모델을 처리할 수 없습니다. 새로운 기능이나 변경된 부분에 대해 반드시 테스트 케이스를 추가해 주세요.

### AIO 테스트 실행

All-In-One(AIO) 이미지에는 대부분의 엔드포인트가 올바르게 작동하는지 자동으로 확인하는 테스트 세트가 있습니다. 흐름은 다음과 같습니다:

```bash
# LocalAI 도커 이미지 빌드
make DOCKER_IMAGE=local-ai docker

# 해당 AIO 이미지 빌드
BASE_IMAGE=local-ai DOCKER_AIO_IMAGE=local-ai-aio:test make docker-aio

# AIO e2e 테스트 실행
LOCALAI_IMAGE_TAG=test LOCALAI_IMAGE=local-ai-aio make run-e2e-aio
```

## 문서화

문서 기여를 환영합니다. 새 PR을 열거나 새 이슈를 만들어 주세요. 문서는 `docs/` 아래에서 확인할 수 있습니다. https://github.com/mudler/LocalAI/tree/master/docs

### 갤러리 YAML 스키마

LocalAI는 다음 경로에서 갤러리 모델 YAML 파일에 대한 JSON 스키마를 제공합니다:

`core/schema/gallery-model.schema.json`

이 스키마는 내부 갤러리 모델 구성을 반영하며, 에디터(VS Code 등)에서 갤러리 파일을 만들거나 수정할 때 자동 완성과 유효성 검사, 인라인 문서를 활성화하는 데 사용할 수 있습니다.

YAML 언어 서버와 함께 사용하려면 갤러리 YAML 파일 상단에 다음 주석을 추가하세요:

```yaml
# yaml-language-server: $schema=../core/schema/gallery-model.schema.json
```

## 커뮤니티 및 소통

- Github 이슈 트래커를 통해 연락할 수 있습니다.
- [Discussion](https://github.com/go-skynet/LocalAI/discussions)에서 새로운 토론을 시작하세요.
- Discord 채널에 참여하세요 [Discord](https://discord.gg/uJAeKSAGDy)
