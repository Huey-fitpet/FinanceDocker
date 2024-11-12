# 프로젝트 Docker 사용법

이 프로젝트는 Docker를 사용하여 쉽게 실행할 수 있습니다. 아래의 단계를 따라 주세요.

## 1. 프로젝트 클론

먼저, 프로젝트를 클론합니다. 터미널에서 다음 명령어를 입력하세요:

```
git clone <프로젝트_레포지토리_URL>
```

## 2. Docker 디렉토리로 이동

클론한 프로젝트 폴더로 이동한 후, `dockers` 폴더로 들어갑니다:

```
cd FinanceDocker/dockers
```

## 3. Docker Compose 실행

이제 Docker Compose를 사용하여 컨테이너를 실행합니다. 다음 명령어를 입력하세요:

```
docker-compose up -d
```

이 명령어는 백그라운드에서 컨테이너를 실행합니다.

## 4. 컨테이너 상태 확인

컨테이너가 정상적으로 실행되고 있는지 확인하려면 다음 명령어를 입력하세요:

```
docker ps
```

이제 프로젝트가 Docker를 통해 실행되고 있습니다. 추가적인 설정이나 사용법은 프로젝트 문서를 참조하세요.


### 설치 파일 업데이트
pip install에 추가 할 패키지가 있다면 아래 처럼 해주세요. 

## `requirements.txt` 업데이트

현재 설치된 패키지를 `requirements.txt` 파일로 추출하려면, docker container 환경 안에서 다음 명령어를 입력하세요:

```
pip freeze > requirements.txt
```

생성된 requirements.txt 중 필요한 패키지를 추가하거나 수정하려면 이 프로젝트의 `requirements.txt` 파일을 열고 원하는 패키지를 추가합니다. 예를 들어:

```
# 기존 패키지
numpy==1.21.0
pandas==1.3.0

# 추가할 패키지
requests==2.26.0
```

그리고 commit and push 해주시면 됩니다.


