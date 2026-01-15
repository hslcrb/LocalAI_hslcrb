+++
title = "LocalAI"
description = "무료 OpenAI, Anthropic 대안. 사용자의 올인원 완전한 로컬 AI 스택"
++
+++

**무료 OpenAI, Anthropic 대안. 사용자의 올인원 완전한 로컬 AI 스택** - 강력한 언어 모델, 자율 에이전트 및 문서 지능을 사용자의 하드웨어에서 **로컬**로 실행하세요.

**클라우드 없음, 제한 없음, 타협 없음.**

{{% notice tip %}}
**[⭐ GitHub에서 스타를 눌러주세요](https://github.com/mudler/LocalAI)** - 4만 개 이상의 스타를 기록 중이며 계속 성장하고 있습니다!

**OpenAI API의 드롭인 대체품** - 독립적으로 또는 완벽하게 함께 작동하는 모듈식 도구 모음입니다.

**[LocalAI](https://localai.io)**의 OpenAI 호환 API로 시작하고, **[LocalAGI](https://github.com/mudler/LocalAGI)**의 자율 에이전트로 확장하고, **[LocalRecall](https://github.com/mudler/LocalRecall)**의 시맨틱 검색으로 강화하세요 - 이 모든 것이 사용자의 하드웨어에서 로컬로 실행됩니다.

**오픈 소스** MIT 라이선스.
{{% /notice %}}

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/PDqYhB9nNHA?si=jUClTH7uuGMwMvFw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></center>

## 왜 LocalAI를 선택해야 하나요?

**OpenAI API 호환** - LocalAI의 모듈식 생태계와 함께 로컬에서 AI 모델을 실행하세요. 언어 모델부터 자율 에이전트 및 시맨틱 검색까지, 클라우드 없이 완전한 AI 스택을 구축하세요.

### 주요 기능

- **LLM 추론**: LocalAI는 무료이며 **오픈 소스**인 OpenAI 대안입니다. 소비자급 하드웨어에서 **로컬**로 **LLM**을 실행하고, **이미지**, **오디오** 등을 생성할 수 있습니다.
- **에이전트 우선**: 코딩 없이 로컬에서 실행되는 자율 AI 에이전트 플랫폼인 LocalAGI로 LocalAI를 확장하세요. 자율 에이전트를 쉽게 구축하고 배포하세요.
- **메모리 및 지식 베이스**: 시맨틱 검색 및 메모리 관리를 위한 로컬 REST API인 LocalRecall로 LocalAI를 확장하세요. AI 애플리케이션에 적합합니다.
- **OpenAI 호환**: OpenAI API의 드롭인 대체품입니다. 기존 애플리케이션 및 라이브러리와 호환됩니다.
- **GPU 필요 없음**: 소비자급 하드웨어에서 실행됩니다. 값비싼 GPU나 클라우드 서비스가 필요하지 않습니다.
- **다양한 모델**: LLM, 이미지 생성 및 오디오 모델을 포함한 다양한 모델 제품군을 지원합니다. 추론을 위한 여러 백엔드를 지원합니다.
- **개인정보 보호 중심**: 데이터를 로컬에 보관하세요. 어떤 데이터도 머신을 떠나지 않아 완벽한 프라이버시를 보장합니다.
- **쉬운 설정**: 간단한 설치 및 구성. 바이너리 설치, Docker, Podman, Kubernetes 또는 로컬 설치를 통해 몇 분 안에 시작할 수 있습니다.
- **커뮤니티 주도**: 활발한 커뮤니티 지원 및 정기 업데이트. LocalAI의 미래를 형성하는 데 기여하고 도움을 주세요.

## 빠른 시작

대부분의 사용자에게는 **Docker 설치 방식이 권장됩니다**:

```bash
docker run -p 8080:8080 --name local-ai -ti localai/localai:latest
```

전체 설치 지침은 [설치 가이드](/installation/)를 참조하세요.

## 시작하기

1. **[LocalAI 설치](/installation/)** - 설치 방법을 선택하세요 (Docker 권장)
2. **[빠른 시작 가이드](/getting-started/quickstart/)** - 설치 후 빠르게 시작하세요
3. **[모델 설치 및 실행](/getting-started/models/)** - AI 모델을 다루는 방법을 알아봅니다
4. **[직접 시도해 보기](/getting-started/try-it-out/)** - 예제와 사용 사례를 탐색해 봅니다

## 더 알아보기

- [사용 가능한 모델 탐색](https://models.localai.io)
- [모델 호환성](/model-compatibility/)
- [예제 시도해 보기](https://github.com/mudler/LocalAI-examples)
- [커뮤니티 참여하기](https://discord.gg/uJAeKSAGDy)
- [LocalAI Github 저장소 확인](https://github.com/mudler/LocalAI)
- [LocalAGI Github 저장소 확인](https://github.com/mudler/LocalAGI)
