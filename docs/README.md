# LocalAI 웹사이트

LocalAI 문서 웹사이트

## 요구 사항
이 프로젝트에서 Docsy 테마 컴포넌트는 다른 모듈 의존성과 함께 Hugo 모듈로 가져옵니다:

```bash
$ hugo mod graph
hugo: collected modules in 566 ms
hugo: collected modules in 578 ms
github.com/google/docsy-example github.com/google/docsy@v0.5.1-0.20221017155306-99eacb09ffb0
github.com/google/docsy-example github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1
github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1 github.com/twbs/bootstrap@v4.6.2+incompatible
github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1 github.com/FortAwesome/Font-Awesome@v0.0.0-20220831210243-d3a7818c253f
```

SCSS를 편집하고 게시하려면 `PostCSS`를 설치해야 합니다:

```bash
npm install
```

## 로컬에서 웹사이트 실행하기

사이트를 로컬에서 빌드하고 실행하려면 최신 `extended` 버전의 [Hugo](https://gohugo.io)가 필요합니다.
사용자의 개발 환경에 Hugo를 설치하는 방법에 대한 자세한 내용은 [시작하기](https://www.docsy.dev/docs/getting-started/#prerequisites-and-installation) 가이드를 참조하세요.

사이트 저장소의 작업 복사본이 준비되면 저장소 루트 폴더에서 다음을 실행하세요:

```
hugo server
```

## 로컬에서 컨테이너 실행하기

[Docker](https://docs.docker.com/) 컨테이너 내에서 docsy-example을 실행할 수 있습니다. 컨테이너는 `docsy-example` 폴더에 바인딩된 볼륨과 함께 실행됩니다. 이 방식은 Windows 및 Mac의 경우 [Docker Desktop](https://www.docker.com/products/docker-desktop)을, Linux의 경우 [Docker Compose](https://docs.docker.com/compose/install/)만 설치하면 되며 다른 의존성은 필요하지 않습니다.

1. 도커 이미지 빌드

   ```bash
   docker-compose build
   ```

1. 빌드된 이미지 실행

   ```bash
   docker-compose up
   ```

   > 참고: `docker-compose up --build` 명령어로 두 명령을 한 번에 실행할 수 있습니다.

1. 서비스가 작동하는지 확인합니다.

   웹 브라우저를 열고 주소창에 `http://localhost:1313`을 입력합니다.
   그러면 로컬 인스턴스의 docsy-example 홈페이지가 열립니다. 이제 docsy 예제를 변경할 수 있으며, 변경 사항은 저장 후 브라우저에 즉시 반영됩니다.

### 정리 (Cleanup)

Docker Compose를 중지하려면 터미널 창에서 **Ctrl + C**를 누르세요.

생성된 이미지를 제거하려면 다음을 실행하세요:

```console
docker-compose rm
```
더 자세한 내용은 [Docker Compose 문서](https://docs.docker.com/compose/gettingstarted/)를 참조하세요.

## 문제 해결 (Troubleshooting)

웹사이트를 로컬에서 실행할 때 다음과 같은 오류가 발생할 수 있습니다:

```
➜ hugo server

INFO 2021/01/21 21:07:55 Using config file: 
Building sites … INFO 2021/01/21 21:07:55 syncing static files to /
Built in 288 ms
Error: Error building site: TOCSS: failed to transform "scss/main.scss" (text/x-scss): resource "scss/scss/main.scss_9fadf33d895a46083cdd64396b57ef68" not found in file cache
```

이 오류는 Hugo의 extended 버전을 설치하지 않은 경우 발생합니다.
Hugo 설치 방법은 사용자 가이드의 [이 섹션](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-hugo)을 참조하세요.

또는 다음과 같은 오류가 발생할 수 있습니다:

```
➜ hugo server

Error: failed to download modules: binary with name "go" not found
```

이 오류는 시스템에 `go` 프로그래밍 언어가 설치되어 있지 않은 경우 발생합니다.
Go 설치 방법은 사용자 가이드의 [이 섹션](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-go-language)을 참조하세요.
