+++
title = "개요 (Overview)"
weight = 1
toc = true
description = "LocalAI란 무엇인가?"
tags = ["입문자"]
categories = [""]
url = "/docs/overview"
author = "Ettore Di Giacinto"
icon = "info"
+++


LocalAI는 로컬에서 AI 모델을 실행하기 위한 완벽한 AI 스택입니다. 사용자의 데이터를 비공개적이고 안전하게 유지하면서 OpenAI의 API를 드롭인 대체할 수 있도록 단순하고 효율적이며 접근 가능하게 설계되었습니다.

## 왜 LocalAI인가요?

오늘날의 AI 지형에서 프라이버시, 제어권 및 유연성은 무엇보다 중요합니다. LocalAI는 다음과 같은 방식으로 이러한 요구를 충족합니다:

- **프라이버시 우선**: 데이터가 사용자의 머신을 떠나지 않습니다.
- **완전한 제어권**: 사용자의 하드웨어에서 사용자의 조건에 따라 모델을 실행하세요.
- **오픈 소스**: MIT 라이선스이며 커뮤니티 주도로 개발됩니다.
- **유연한 배포**: 노트북부터 서버까지, GPU 유무에 관계없이 배포 가능합니다.
- **확장성**: 필요에 따라 새로운 모델과 기능을 추가할 수 있습니다.

## 핵심 컴포넌트

LocalAI는 단순한 도구 그 이상입니다. 하나의 완전한 생태계입니다:

1. **[LocalAI Core](https://github.com/mudler/LocalAI)**
   - OpenAI 호환 API
   - 다중 모델 지원 (LLM, 이미지, 오디오)
   - 에이전트 기능을 위한 모델 컨텍스트 프로토콜 (MCP)
   - GPU 필요 없음
   - 네이티브 바인딩을 통한 빠른 추론
   - [Github 저장소](https://github.com/mudler/LocalAI)

2. **[LocalAGI](https://github.com/mudler/LocalAGI)**
   - 자율 AI 에이전트
   - 코딩 불필요
   - WebUI 및 REST API 지원
   - 확장 가능한 에이전트 프레임워크
   - [Github 저장소](https://github.com/mudler/LocalAGI)

3. **[LocalRecall](https://github.com/mudler/LocalRecall)**
   - 시맨틱 검색
   - 메모리 관리
   - 벡터 데이터베이스
   - AI 애플리케이션에 적합
   - [Github 저장소](https://github.com/mudler/LocalRecall)

## 시작하기

LocalAI는 여러 가지 방법으로 설치할 수 있습니다. 가장 쉬운 설정을 제공하고 모든 플랫폼에서 작동하는 **Docker 설치 방식이 대부분의 사용자에게 권장됩니다**.

### 권장: Docker 설치

LocalAI를 시작하는 가장 빠른 방법은 Docker를 사용하는 것입니다:

```bash
docker run -p 8080:8080 --name local-ai -ti localai/localai:latest
```

Docker, macOS, Linux, Kubernetes 및 소스 빌드를 포함한 전체 설치 지침은 [설치 가이드](/installation/)를 참조하세요.

## 주요 기능

- **텍스트 생성**: 다양한 LLM을 로컬에서 실행
- **이미지 생성**: Stable Diffusion을 사용하여 이미지 생성
- **오디오 처리**: 텍스트-음성 변환(TTS) 및 음성-텍스트 변환(STT)
- **비전 API**: 이미지 이해 및 분석
- **임베딩**: 벡터 데이터베이스 지원
- **함수 호출**: OpenAI 호환 함수 호출(Function Calling)
- **MCP 지원**: 에이전트 기능을 위한 모델 컨텍스트 프로토콜 지원
- **P2P**: 분산 추론 기능

## 커뮤니티 및 지원

LocalAI는 커뮤니티 주도 프로젝트입니다. 다음과 같은 활동에 참여할 수 있습니다:

- [Discord 커뮤니티](https://discord.gg/uJAeKSAGDy) 참여
- [GitHub 저장소](https://github.com/mudler/LocalAI) 확인
- 프로젝트 기여
- 사용 사례 및 예제 공유

## 다음 단계

시작할 준비가 되셨나요? 다음 단계들을 추천합니다:

1. **[LocalAI 설치](/installation/)** - [Docker 설치](/installation/docker/)(권장) 또는 다른 방법 선택
2. [사용 가능한 모델 탐색](https://models.localai.io)
3. [모델 호환성](/model-compatibility/)
4. [예제 시도해 보기](https://github.com/mudler/LocalAI-examples)
5. [커뮤니티 참여하기](https://discord.gg/uJAeKSAGDy)
6. [LocalAI Github 저장소 확인](https://github.com/mudler/LocalAI)
7. [LocalAGI Github 저장소 확인](https://github.com/mudler/LocalAGI)


## 라이선스

LocalAI는 MIT 라이선스를 따르며, [Ettore Di Giacinto](https://github.com/mudler)에 의해 만들어지고 유지 관리됩니다.
