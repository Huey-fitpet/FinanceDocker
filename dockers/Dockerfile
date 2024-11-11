# Python 베이스 이미지 사용
FROM python:3.11-slim-bullseye


# 작업 디렉토리 설정
WORKDIR /app

# 시스템 패키지 및 MongoDB 클라이언트 설치
RUN apt-get update && apt-get install -y \
    gnupg \
    wget \
    git \
    && wget -qO - https://www.mongodb.org/static/pgp/server-7.0.asc | apt-key add - \
    && echo "deb http://repo.mongodb.org/apt/debian bullseye/mongodb-org/7.0 main" | tee /etc/apt/sources.list.d/mongodb-org-7.0.list \
    && apt-get update \
    && apt-get install -y mongodb-org-tools mongodb-org-shell \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# requirements.txt 복사 및 설치
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 애플리케이션 코드 복사
COPY . .

# 컨테이너를 계속 실행 상태로 유지
CMD ["tail", "-f", "/dev/null"]