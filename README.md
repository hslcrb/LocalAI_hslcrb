<h1 align="center">
  <br>
  <img width="300" src="./core/http/static/logo.png"> <br>
<br>
</h1>

<p align="center">
<a href="https://github.com/go-skynet/LocalAI/fork" target="blank">
<img src="https://img.shields.io/github/forks/go-skynet/LocalAI?style=for-the-badge" alt="LocalAI forks"/>
</a>
<a href="https://github.com/go-skynet/LocalAI/stargazers" target="blank">
<img src="https://img.shields.io/github/stars/go-skynet/LocalAI?style=for-the-badge" alt="LocalAI stars"/>
</a>
<a href="https://github.com/go-skynet/LocalAI/pulls" target="blank">
<img src="https://img.shields.io/github/issues-pr/go-skynet/LocalAI?style=for-the-badge" alt="LocalAI pull-requests"/>
</a>
<a href='https://github.com/go-skynet/LocalAI/releases'>
<img src='https://img.shields.io/github/release/go-skynet/LocalAI?&label=Latest&style=for-the-badge'>
</a>
</p>

<p align="center">
<a href="https://hub.docker.com/r/localai/localai" target="blank">
<img src="https://img.shields.io/badge/dockerhub-images-important.svg?logo=Docker" alt="LocalAI Docker hub"/>
</a>
<a href="https://quay.io/repository/go-skynet/local-ai?tab=tags&tag=latest" target="blank">
<img src="https://img.shields.io/badge/quay.io-images-important.svg?" alt="LocalAI Quay.io"/>
</a>
</p>

<p align="center">
<a href="https://twitter.com/LocalAI_API" target="blank">
<img src="https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=X&logoColor=white&label=LocalAI_API" alt="Follow LocalAI_API"/>
</a>
<a href="https://discord.gg/uJAeKSAGDy" target="blank">
<img src="https://img.shields.io/badge/dynamic/json?color=blue&label=Discord&style=for-the-badge&query=approximate_member_count&url=https%3A%2F%2Fdiscordapp.com%2Fapi%2Finvites%2FuJAeKSAGDy%3Fwith_counts%3Dtrue&logo=discord" alt="Join LocalAI Discord Community"/>
</a>
</p>

<p align="center">
<a href="https://trendshift.io/repositories/5539" target="_blank"><img src="https://trendshift.io/api/badge/repositories/5539" alt="mudler%2FLocalAI | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</p>

> :bulb: 도움말 - [❓자주 묻는 질문(FAQ)](https://localai.io/faq/) [💭토론](https://github.com/go-skynet/LocalAI/discussions) [:speech_balloon: Discord](https://discord.gg/uJAeKSAGDy) [:book: 문서 웹사이트](https://localai.io/)
>
> [💻 빠른 시작](https://localai.io/basics/getting_started/) [🖼️ 모델](https://models.localai.io/) [🚀 로드맵](https://github.com/mudler/LocalAI/issues?q=is%3Aissue+is%3Aopen+label%3Aroadmap) [🛫 예제](https://github.com/mudler/LocalAI-examples) 사용해보기:
> [![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/localaiofficial_bot)

[![테스트](https://github.com/go-skynet/LocalAI/actions/workflows/test.yml/badge.svg)](https://github.com/go-skynet/LocalAI/actions/workflows/test.yml)[![빌드 및 릴리스](https://github.com/go-skynet/LocalAI/actions/workflows/release.yaml/badge.svg)](https://github.com/go-skynet/LocalAI/actions/workflows/release.yaml)[![컨테이너 이미지 빌드](https://github.com/go-skynet/LocalAI/actions/workflows/image.yml/badge.svg)](https://github.com/go-skynet/LocalAI/actions/workflows/image.yml)[![의존성 업데이트](https://github.com/go-skynet/LocalAI/actions/workflows/bump_deps.yaml/badge.svg)](https://github.com/go-skynet/LocalAI/actions/workflows/bump_deps.yaml)[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/localai)](https://artifacthub.io/packages/search?repo=localai)

**LocalAI**는 무료이며 오픈 소스인 OpenAI 대안입니다. LocalAI는 로컬 AI 추론을 위한 OpenAI(Elevenlabs, Anthropic 등) API 사양과 호환되는 드롭인 대체 REST API 역할을 합니다. 소비자급 하드웨어에서 로컬 또는 온프레미스로 여러 모델 제품군을 지원하여 LLM 실행, 이미지 생성, 오디오 생성 등을 할 수 있게 해줍니다. GPU가 필요하지 않습니다. [Ettore Di Giacinto](https://github.com/mudler)에 의해 만들어지고 유지 관리됩니다.


## 📚🆕 Local Stack 제품군

🆕 LocalAI는 이제 함께 작동하도록 설계된 포괄적인 AI 도구 제품군의 일부입니다:

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://github.com/mudler/LocalAGI">
        <img src="https://raw.githubusercontent.com/mudler/LocalAGI/refs/heads/main/webui/react-ui/public/logo_2.png" width="300" alt="LocalAGI 로고">
      </a>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/mudler/LocalAGI">LocalAGI</a></h3>
      <p>OpenAI의 Responses API를 드롭인 대체하고 고급 에이전트 기능이 강화된 강력한 로컬 AI 에이전트 관리 플랫폼입니다.</p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <a href="https://github.com/mudler/LocalRecall">
        <img src="https://raw.githubusercontent.com/mudler/LocalRecall/refs/heads/main/static/localrecall_horizontal.png" width="300" alt="LocalRecall 로고">
      </a>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/mudler/LocalRecall">LocalRecall</a></h3>
      <p>AI 에이전트를 위한 영구 메모리 및 저장 기능을 제공하는 REST-ful API 및 지식 베이스 관리 시스템입니다.</p>
    </td>
  </tr>
</table>

## 스크린샷 / 비디오

### 유튜브 비디오

<h1 align="center">
  <br>
  <a href="https://www.youtube.com/watch?v=PDqYhB9nNHA" target="_blank"> <img width="300" src="https://img.youtube.com/vi/PDqYhB9nNHA/0.jpg"> </a><br>
<br>
</h1>


### 스크린샷

| 대화 인터페이스 | 오디오 생성 |
| --- | --- |
| ![스크린샷 2025-03-31 12-01-36 LocalAI - Talk](./docs/assets/images/screenshots/screenshot_tts.png) | ![스크린샷 2025-03-31 12-01-29 LocalAI - Generate audio with voice-en-us-ryan-low](./docs/assets/images/screenshots/screenshot_tts.png) |

| 모델 개요 | 이미지 생성 |
| --- | --- |
| ![스크린샷 2025-03-31 12-01-20 LocalAI - Models](./docs/assets/images/screenshots/screenshot_gallery.png) | ![스크린샷 2025-03-31 12-31-41 LocalAI - Generate images with flux 1-dev](./docs/assets/images/screenshots/screenshot_image.png) |

| 채팅 인터페이스 | 홈 |
| --- | --- |
| ![스크린샷 2025-03-31 11-57-44 LocalAI - Chat with localai-functioncall-qwen2 5-7b-v0 5](./docs/assets/images/screenshots/screenshot_chat.png) | ![스크린샷 2025-03-31 11-57-23 LocalAI API - c2a39e3 (c2a39e3639227cfd94ffffe9f5691239acc275a8)](./docs/assets/images/screenshots/screenshot_home.png) |

| 로그인 | 스웜(Swarm) |
| --- | --- |
|![스크린샷 2025-03-31 12-09-59 ](./docs/assets/images/screenshots/screenshot_login.png) | ![스크린샷 2025-03-31 12-10-39 LocalAI - P2P 대시보드](./docs/assets/images/screenshots/screenshot_p2p.png) |

## 💻 빠른 시작

> ⚠️ **참고:** `install.sh` 스크립트는 현재 LocalAI의 대대적인 변경 사항으로 인해 문제가 발생할 수 있으며, 설치가 중단되거나 잘못 구성될 수 있습니다. [이슈 #8032](https://github.com/mudler/LocalAI/issues/8032)가 해결될 때까지 Docker 설치(아래 참조) 또는 수동 바이너리 설치를 사용해 주세요.

설치 스크립트 실행:

```bash
# 기본 설치
curl https://localai.io/install.sh | sh
```

더 많은 설치 옵션은 [설치 옵션](https://localai.io/installation/)을 참조하세요.

### macOS 다운로드:

<a href="https://github.com/mudler/LocalAI/releases/latest/download/LocalAI.dmg">
  <img src="https://img.shields.io/badge/Download-macOS-blue?style=for-the-badge&logo=apple&logoColor=white" alt="macOS용 LocalAI 다운로드"/>
</a>

> 참고: DMG 파일은 Apple에 의해 서명되지 않아 격리된 것으로 표시될 수 있습니다. 해결 방법은 https://github.com/mudler/LocalAI/issues/6268을 참조하세요. 수정 사항은 여기서 추적됩니다: https://github.com/mudler/LocalAI/issues/6244

### 컨테이너 (Docker, podman, ...)

> **💡 Docker Run vs Docker Start**
> 
> - `docker run`은 새 컨테이너를 생성하고 시작합니다. 동일한 이름의 컨테이너가 이미 존재하면 이 명령은 실패합니다.
> - `docker start`는 이전에 `docker run`으로 생성된 기존 컨테이너를 시작합니다.
> 
> 이전에 LocalAI를 실행한 적이 있고 다시 시작하려면 다음을 사용하세요: `docker start -i local-ai`

#### CPU 전용 이미지:

```bash
docker run -ti --name local-ai -p 8080:8080 localai/localai:latest
```

#### NVIDIA GPU 이미지:

```bash
# CUDA 13.0
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-gpu-nvidia-cuda-13

# CUDA 12.0
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-gpu-nvidia-cuda-12

# NVIDIA Jetson (L4T) ARM64
# CUDA 12 (Nvidia AGX Orin 및 유사 플랫폼용)
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-nvidia-l4t-arm64

# CUDA 13 (Nvidia DGX Spark용)
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-nvidia-l4t-arm64-cuda-13
```

#### AMD GPU 이미지 (ROCm):

```bash
docker run -ti --name local-ai -p 8080:8080 --device=/dev/kfd --device=/dev/dri --group-add=video localai/localai:latest-gpu-hipblas
```

#### Intel GPU 이미지 (oneAPI):

```bash
docker run -ti --name local-ai -p 8080:8080 --device=/dev/dri/card1 --device=/dev/dri/renderD128 localai/localai:latest-gpu-intel
```

#### Vulkan GPU 이미지:

```bash
docker run -ti --name local-ai -p 8080:8080 localai/localai:latest-gpu-vulkan
```

#### AIO 이미지 (미리 다운로드된 모델 포함):

```bash
# CPU 버전
docker run -ti --name local-ai -p 8080:8080 localai/localai:latest-aio-cpu

# NVIDIA CUDA 13 버전
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-aio-gpu-nvidia-cuda-13

# NVIDIA CUDA 12 버전
docker run -ti --name local-ai -p 8080:8080 --gpus all localai/localai:latest-aio-gpu-nvidia-cuda-12

# Intel GPU 버전
docker run -ti --name local-ai -p 8080:8080 localai/localai:latest-aio-gpu-intel

# AMD GPU 버전
docker run -ti --name local-ai -p 8080:8080 --device=/dev/kfd --device=/dev/dri --group-add=video localai/localai:latest-aio-gpu-hipblas
```

AIO 이미지 및 미리 다운로드된 모델에 대한 자세한 정보는 [컨테이너 문서](https://localai.io/basics/container/)를 참조하세요.

모델 로드 방법:

```bash
# 모델 갤러리에서 (사용 가능한 모델은 `local-ai models list`, WebUI의 모델 탭 또는 https://models.localai.io 방문하여 확인)
local-ai run llama-3.2-1b-instruct:q4_k_m
# Hugging Face에서 직접 phi-2 모델로 LocalAI 시작
local-ai run huggingface://TheBloke/phi-2-GGUF/phi-2.Q8_0.gguf
# Ollama OCI 레지스트리에서 모델 설치 및 실행
local-ai run ollama://gemma:2b
# 구성 파일에서 모델 실행
local-ai run https://gist.githubusercontent.com/.../phi-2.yaml
# 표준 OCI 레지스트리(예: Docker Hub)에서 모델 설치 및 실행
local-ai run oci://localai/phi-2:latest
```

> ⚡ **자동 백엔드 감지**: 갤러리나 YAML 파일에서 모델을 설치할 때, LocalAI는 시스템의 GPU 기능(NVIDIA, AMD, Intel)을 자동으로 감지하고 적절한 백엔드를 다운로드합니다. 고급 구성 옵션은 [GPU 가속](https://localai.io/features/gpu-acceleration/#automatic-backend-detection)을 참조하세요.

자세한 내용은 [💻 시작하기](https://localai.io/basics/getting_started/index.html)를 참조하세요. 로드맵 항목 및 향후 개선 사항에 관심이 있다면 [여기에서 로드맵으로 표시된 이슈](https://github.com/mudler/LocalAI/issues?q=is%3Aissue+is%3Aopen+label%3Aroadmap)를 확인할 수 있습니다.

## 📰 최신 프로젝트 뉴스

- 2025년 12월: [동적 메모리 자원 회수기](https://github.com/mudler/LocalAI/pull/7583), [여러 GPU에 대한 모델 자동 피팅(llama.cpp)](https://github.com/mudler/LocalAI/pull/7584), [Vibevoice 백엔드 추가](https://github.com/mudler/LocalAI/pull/7494)
- 2025년 11월: UX 주요 개선. 그 중: [URL을 통한 모델 가져오기](https://github.com/mudler/LocalAI/pull/7245) 및 [다중 채팅 및 기록](https://github.com/mudler/LocalAI/pull/7325)
- 2025년 10월: 🔌 룩업 외부 도구를 사용한 에이전트 기능을 위해 [모델 컨텍스트 프로토콜 (MCP)](https://localai.io/docs/features/mcp/) 지원 추가
- 2025년 9월: MacOS 및 Linux용 새 런처 애플리케이션, Mac 및 Nvidia L4T 장치용 많은 백엔드까지 지원 확장. 모델: MLX-Audio, WAN 2.2 추가. WebUI 개선 및 Python 기반 백엔드에 휴대용 Python 환경 포함.
- 2025년 8월: MLX, MLX-VLM, Diffusers 및 llama.cpp가 이제 Mac M1/M2/M3+ 칩에서 지원됩니다 (갤러리에서 `development` 접미사 포함): https://github.com/mudler/LocalAI/pull/6049 https://github.com/mudler/LocalAI/pull/6119 https://github.com/mudler/LocalAI/pull/6121 https://github.com/mudler/LocalAI/pull/6060
- 2025년 7월/8월: 🔍 [rf-detr](https://github.com/roboflow/rf-detr)을 특징으로 하는 [객체 탐지](https://localai.io/features/object-detection/)가 API에 추가되었습니다.
- 2025년 7월: 모든 백엔드가 메인 바이너리 외부로 마이그레이션되었습니다. LocalAI는 이제 더 가볍고 작아졌으며, 모델을 실행하는 데 필요한 백엔드를 자동으로 다운로드합니다. [릴리스 노트 읽기](https://github.com/mudler/LocalAI/releases/tag/v3.2.0)
- 2025년 6월: [백엔드 관리](https://github.com/mudler/LocalAI/pull/5607)가 추가되었습니다. 주의: 다음 릴리스부터 extras 이미지는 더 이상 사용되지 않습니다! [백엔드 관리 PR](https://github.com/mudler/LocalAI/pull/5607)을 읽어보세요.
- 2025년 5월: llama.cpp 백엔드에서 [오디오 입력](https://github.com/mudler/LocalAI/pull/5466) 및 [리랜킹(Reranking)](https://github.com/mudler/LocalAI/pull/5396), [Realtime API](https://github.com/mudler/LocalAI/pull/5392), Gemma, SmollVLM 및 더 많은 멀티모달 모델 지원(갤러리에서 사용 가능).
- 2025년 5월: 중요: 이미지 이름 변경 [릴리스 보기](https://github.com/mudler/LocalAI/releases/tag/v2.29.0)
- 2025년 4월: 브랜드 리뉴얼, WebUI 개선
- 2025년 4월: [LocalAGI](https://github.com/mudler/LocalAGI) 및 [LocalRecall](https://github.com/mudler/LocalRecall)이 LocalAI 제품군 스택에 합류했습니다.
- 2025년 4월: WebUI 전면 개편, AIO 이미지 업데이트
- 2025년 2월: 백엔드 정리, 파괴적 변경 사항, 새 백엔드(kokoro, OutelTTS, faster-whisper), Nvidia L4T 이미지
- 2025년 1월: LocalAI 모델 릴리스: https://huggingface.co/mudler/LocalAI-functioncall-phi-4-v0.3, diffusers의 SANA 지원: https://github.com/mudler/LocalAI/pull/4603
- 2024년 12월: stablediffusion.cpp 백엔드(ggml) 추가 ( https://github.com/mudler/LocalAI/pull/4289 )
- 2024년 11월: Bark.cpp 백엔드 추가 ( https://github.com/mudler/LocalAI/pull/4287 )
- 2024년 11월: API의 음성 활동 감지(**VAD**) 모델 추가: https://github.com/mudler/LocalAI/pull/4204
- 2024년 10월: 예제가 [LocalAI-examples](https://github.com/mudler/LocalAI-examples)로 이동되었습니다.
- 2024년 8월: 🆕 FLUX-1, [P2P 익스플로러](https://explorer.localai.io)
- 2024년 7월: 🔥🔥 🆕 P2P 대시보드, LocalAI 페더레이션 모드 및 AI 스웜: https://github.com/mudler/LocalAI/pull/2723. P2P 글로벌 커뮤니티 풀: https://github.com/mudler/LocalAI/issues/3113
- 2024년 5월: 🔥🔥 탈중앙화 P2P llama.cpp: https://github.com/mudler/LocalAI/pull/2343 (peer2peer llama.cpp!) 👉 문서 https://localai.io/features/distribute/
- 2024년 5월: 🔥🔥 분산 추론: https://github.com/mudler/LocalAI/pull/2324
- 2024년 4월: Reranker API: https://github.com/mudler/LocalAI/pull/2121

로드맵 항목: [이슈 목록](https://github.com/mudler/LocalAI/issues?q=is%3Aissue+is%3Aopen+label%3Aroadmap)

## 🚀 [기능](https://localai.io/features/)

- 🧩 [백엔드 갤러리](https://localai.io/backends/): OCI 이미지로 구동되며 즉시 백엔드를 설치/제거할 수 있습니다. 완전히 맞춤화 가능하며 API 중심입니다.
- 📖 [GPT를 통한 텍스트 생성](https://localai.io/features/text-generation/) (`llama.cpp`, `transformers`, `vllm` ... [:book: 그 외 더보기](https://localai.io/model-compatibility/index.html#model-compatibility-table))
- 🗣 [텍스트-오디오 변환](https://localai.io/features/text-to-audio/)
- 🔈 [오디오-텍스트 변환](https://localai.io/features/audio-to-text/) (`whisper.cpp`를 이용한 오디오 전사)
- 🎨 [이미지 생성](https://localai.io/features/image-generation)
- 🔥 [OpenAI와 유사한 도구 API](https://localai.io/features/openai-functions/) 
- 🧠 [벡터 데이터베이스용 임베딩 생성](https://localai.io/features/embeddings/)
- ✍️ [제약된 문법(Constrained grammars)](https://localai.io/features/constrained_grammars/)
- 🖼️ [Hugging Face에서 직접 모델 다운로드](https://localai.io/models/)
- 🥽 [비전 API](https://localai.io/features/gpt-vision/)
- 🔍 [객체 탐지](https://localai.io/features/object-detection/)
- 📈 [리랜커(Reranker) API](https://localai.io/features/reranker/)
- 🆕🖧 [P2P 추론](https://localai.io/features/distribute/)
- 🆕🔌 [모델 컨텍스트 프로토콜 (MCP)](https://localai.io/docs/features/mcp/) - 외부 도구를 사용한 에이전트 기능 및 [LocalAGI의 에이전트 기능](https://github.com/mudler/LocalAGI)
- 🔊 음성 활동 감지 (Silero-VAD 지원)
- 🌍 통합 WebUI!

## 🧩 지원되는 백엔드 및 가속

LocalAI는 여러 가속 옵션과 함께 광범위한 AI 백엔드를 지원합니다:

### 텍스트 생성 및 언어 모델
| 백엔드 | 설명 | 가속 지원 |
|---------|-------------|---------------------|
| **llama.cpp** | C/C++ 기반 LLM 추론 | CUDA 12/13, ROCm, Intel SYCL, Vulkan, Metal, CPU |
| **vLLM** | PagedAttention을 사용한 빠른 LLM 추론 | CUDA 12/13, ROCm, Intel |
| **transformers** | HuggingFace transformers 프레임워크 | CUDA 12/13, ROCm, Intel, CPU |
| **exllama2** | GPTQ 추론 라이브러리 | CUDA 12/13 |
| **MLX** | Apple Silicon LLM 추론 | Metal (M1/M2/M3+) |
| **MLX-VLM** | Apple Silicon 비전-언어 모델 | Metal (M1/M2/M3+) |

### 오디오 및 음성 처리
| 백엔드 | 설명 | 가속 지원 |
|---------|-------------|---------------------|
| **whisper.cpp** | C/C++ 기반 OpenAI Whisper | CUDA 12/13, ROCm, Intel SYCL, Vulkan, CPU |
| **faster-whisper** | CTranslate2를 사용한 빠른 Whisper | CUDA 12/13, ROCm, Intel, CPU |
| **bark** | 텍스트-오디오 생성 | CUDA 12/13, ROCm, Intel |
| **bark-cpp** | Bark의 C++ 구현 | CUDA, Metal, CPU |
| **coqui** | 1100개 이상의 언어를 지원하는 고급 TTS | CUDA 12/13, ROCm, Intel, CPU |
| **kokoro** | 경량 TTS 모델 | CUDA 12/13, ROCm, Intel, CPU |
| **chatterbox** | 상용 등급 TTS | CUDA 12/13, CPU |
| **piper** | 빠른 신경망 TTS 시스템 | CPU |
| **kitten-tts** | Kitten TTS 모델 | CPU |
| **silero-vad** | 음성 활동 감지 | CPU |
| **neutts** | 음성 복제 기능이 있는 텍스트-음성 변환 | CUDA 12/13, ROCm, CPU |
| **vibevoice** | 음성 복제 기능이 있는 실시간 TTS | CUDA 12/13, ROCm, Intel, CPU |
| **pocket-tts** | 경량 CPU 기반 TTS | CUDA 12/13, ROCm, Intel, CPU |

### 이미지 및 비디오 생성
| 백엔드 | 설명 | 가속 지원 |
|---------|-------------|---------------------|
| **stablediffusion.cpp** | C/C++ 기반 Stable Diffusion | CUDA 12/13, Intel SYCL, Vulkan, CPU |
| **diffusers** | HuggingFace 확산 모델 | CUDA 12/13, ROCm, Intel, Metal, CPU |

### 특화된 AI 작업
| 백엔드 | 설명 | 가속 지원 |
|---------|-------------|---------------------|
| **rfdetr** | 실시간 객체 탐지 | CUDA 12/13, Intel, CPU |
| **rerankers** | 문서 리랜킹 API | CUDA 12/13, ROCm, Intel, CPU |
| **local-store** | 벡터 데이터베이스 | CPU |
| **huggingface** | HuggingFace API 통합 | API 기반 |

### 하드웨어 가속 매트릭스

| 가속 유형 | 지원되는 백엔드 | 하드웨어 지원 |
|-------------------|-------------------|------------------|
| **NVIDIA CUDA 12** | 모든 CUDA 호환 백엔드 | Nvidia 하드웨어 |
| **NVIDIA CUDA 13** | 모든 CUDA 호환 백엔드 | Nvidia 하드웨어 |
| **AMD ROCm** | llama.cpp, whisper, vllm, transformers, diffusers, rerankers, coqui, kokoro, bark, neutts, vibevoice, pocket-tts | AMD 그래픽 |
| **Intel oneAPI** | llama.cpp, whisper, stablediffusion, vllm, transformers, diffusers, rfdetr, rerankers, exllama2, coqui, kokoro, bark, vibevoice, pocket-tts | Intel Arc, Intel iGPU |
| **Apple Metal** | llama.cpp, whisper, diffusers, MLX, MLX-VLM, bark-cpp | Apple M1/M2/M3+ |
| **Vulkan** | llama.cpp, whisper, stablediffusion | 크로스 플랫폼 GPU |
| **NVIDIA Jetson (CUDA 12)** | llama.cpp, whisper, stablediffusion, diffusers, rfdetr | ARM64 임베디드 AI (AGX Orin 등) |
| **NVIDIA Jetson (CUDA 13)** | llama.cpp, whisper, stablediffusion, diffusers, rfdetr | ARM64 임베디드 AI (DGX Spark) |
| **CPU 최적화** | 모든 백엔드 | AVX/AVX2/AVX512, 양자화 지원 |

### 🔗 커뮤니티 및 통합

맞춤형 컨테이너 빌드 및 배포:
- https://github.com/sozercan/aikit

WebUI:
- https://github.com/Jirubizu/localai-admin
- https://github.com/go-skynet/LocalAI-frontend
- QA-Pilot(GitHub 코드 저장소의 빠른 이해와 탐색을 위해 LocalAI LLM을 활용하는 대화형 채팅 프로젝트) https://github.com/reid41/QA-Pilot

에이전트 라이브러리:
- https://github.com/mudler/cogito

MCP:
- https://github.com/mudler/MCPs

모델 갤러리:
- https://github.com/go-skynet/model-gallery

음성:
- https://github.com/richiejp/VoxInput

기타:
- Helm 차트 https://github.com/go-skynet/helm-charts
- VSCode 확장 프로그램 https://github.com/badgooooor/localai-vscode-plugin
- Langchain: https://python.langchain.com/docs/integrations/providers/localai/
- 터미널 유틸리티 https://github.com/djcopley/ShellOracle
- 로컬 스마트 어시스턴트 https://github.com/mudler/LocalAGI
- Home Assistant https://github.com/sammcj/homeassistant-localai / https://github.com/drndos/hass-openai-custom-conversation / https://github.com/valentinfrlch/ha-gpt4vision
- Discord 봇 https://github.com/mudler/LocalAGI/tree/main/examples/discord
- Slack 봇 https://github.com/mudler/LocalAGI/tree/main/examples/slack
- Shell-Pilot(Linux 또는 MacOS 시스템에서 순수 쉘 스크립트를 통해 LocalAI 모델을 사용하여 LLM과 상호 작용) https://github.com/reid41/shell-pilot
- Telegram 봇 https://github.com/mudler/LocalAI/tree/master/examples/telegram-bot
- 또 다른 Telegram 봇 https://github.com/JackBekket/Hellper
- 자동 문서화 https://github.com/JackBekket/Reflexia
- 코드와 문서를 컨텍스트로 하여 이슈에 답변하는 Github 봇 https://github.com/JackBekket/GitHelper
- Github Actions: https://github.com/marketplace/actions/start-localai
- 예제: https://github.com/mudler/LocalAI/tree/master/examples/
  

### 🔗 리소스

- [LLM 미세 조정 가이드](https://localai.io/docs/advanced/fine-tuning/)
- [로컬에서 빌드하는 방법](https://localai.io/basics/build/index.html)
- [Kubernetes에 설치하는 방법](https://localai.io/basics/getting_started/index.html#run-localai-in-kubernetes)
- [LocalAI를 통합한 프로젝트](https://localai.io/docs/integrations/)
- [How-to 섹션](https://io.midori-ai.xyz/howtos/) (커뮤니티 관리)

## :book: 🎥 [미디어, 블로그, 소셜](https://localai.io/basics/news/#media-blogs-social)

- [LocalAI(SUSE)로 Visual Studio Code 실행하기](https://www.suse.com/c/running-ai-locally/)
- 🆕 [Jetson Nano Devkit에서 LocalAI 실행하기](https://mudler.pm/posts/local-ai-jetson-nano-devkit/)
- [Pulumi를 사용하여 AWS EKS에서 LocalAI 실행하기](https://www.pulumi.com/blog/low-code-llm-apps-with-local-ai-flowise-and-pulumi/)
- [AWS에서 LocalAI 실행하기](https://staleks.hashnode.dev/installing-localai-on-aws-ec2-instance)
- [문서에 답변하는 팀 및 OSS 프로젝트용 슬랙봇 개발](https://mudler.pm/posts/smart-slackbot-for-teams/)
- [LocalAI와 k8sgpt의 만남](https://www.youtube.com/watch?v=PKrDNuJ_dfE)
- [LangChain, LocalAI, Chroma, GPT4All을 사용하여 로컬에서 문서에 대한 질의응답하기](https://mudler.pm/posts/localai-question-answering/)
- [LocalAI와 함께 k8sgpt를 사용하는 튜토리얼](https://medium.com/@tyler_97636/k8sgpt-localai-unlock-kubernetes-superpowers-for-free-584790de9b65)

## 인용 (Citation)

이 저장소나 데이터가 프로젝트에 도움이 되었다면 다음을 인용해 주세요:

```
@misc{localai,
  author = {Ettore Di Giacinto},
  title = {LocalAI: The free, Open source OpenAI alternative},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/go-skynet/LocalAI}},
```

## ❤️ 후원사

> LocalAI가 유용하다고 생각하시나요?

[후원자나 스폰서](https://github.com/sponsors/mudler)가 되어 프로젝트를 지원해 주세요. 웹사이트 링크와 함께 로고가 여기에 표시됩니다.

CI 비용을 지원해 주시는 관대한 스폰서들과 [스폰서 목록](https://github.com/sponsors/mudler)에 큰 감사를 드립니다:

<p align="center">
  <a href="https://www.spectrocloud.com/" target="blank">
    <img height="200" src="https://github.com/user-attachments/assets/72eab1dd-8b93-4fc0-9ade-84db49f24962">
  </a>
  <a href="https://www.premai.io/" target="blank">
    <img height="200" src="https://github.com/mudler/LocalAI/assets/2420543/42e4ca83-661e-4f79-8e46-ae43689683d6"> <br>
  </a>
</p>

### 개인 스폰서

프로젝트에 기여해 주신 개인 스폰서분들께 특별히 감사드립니다. 전체 목록은 [Github](https://github.com/sponsors/mudler) 및 [buymeacoffee](https://buymeacoffee.com/mudler)에서 확인할 수 있으며, 특히 아낌없는 지원을 해주신 [drikster80](https://github.com/drikster80)님께 감사드립니다. 모두 감사합니다!

## 🌟 스타 기록 (Star history)

[![LocalAI Star history Chart](https://api.star-history.com/svg?repos=go-skynet/LocalAI&type=Date)](https://star-history.com/#go-skynet/LocalAI&Date)

## 📖 라이선스

LocalAI는 [Ettore Di Giacinto](https://github.com/mudler/)가 만든 커뮤니티 주도 프로젝트입니다.

MIT - Author Ettore Di Giacinto <mudler@localai.io>

## 🙇 감사의 말

LocalAI는 커뮤니티에서 이미 제공하는 훌륭한 소프트웨어의 도움 없이는 구축될 수 없었을 것입니다. 감사합니다!

- [llama.cpp](https://github.com/ggerganov/llama.cpp)
- https://github.com/tatsu-lab/stanford_alpaca
- 초기 아이디어를 제공한 https://github.com/cornelk/llama-go
- https://github.com/antimatter15/alpaca.cpp
- https://github.com/EdVince/Stable-Diffusion-NCNN
- https://github.com/ggerganov/whisper.cpp
- https://github.com/rhasspy/piper

## 🤗 기여자

이것은 커뮤니티 프로젝트입니다. 기여자분들께 특별히 감사드립니다! 🤗
<a href="https://github.com/go-skynet/LocalAI/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=go-skynet/LocalAI" />
</a>
