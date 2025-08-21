# n8n Docker Setup

이 저장소는 n8n 워크플로 자동화 도구를 Docker로 실행하기 위한 설정입니다.

## 현재 상태 확인

```bash
# 실행 중인 컨테이너 확인
docker ps

# Docker Compose 서비스 상태 확인
docker-compose ps
```

## n8n 사용법

### 1. 컨테이너 시작 (이미 실행 중인 경우 생략)
```bash
# 백그라운드에서 실행
docker-compose up -d

# 로그 확인하며 실행
docker-compose up
```

### 2. n8n 웹 인터페이스 접속
- 브라우저에서 `http://localhost:5678` 접속
- 기본 인증 정보:
  - 사용자명: `admin`
  - 비밀번호: `n8n123!`

### 3. 컨테이너 중지
```bash
# 컨테이너 중지
docker-compose down

# 데이터까지 삭제 (주의!)
docker-compose down -v
```

### 4. 로그 확인
```bash
# 실시간 로그 확인
docker-compose logs -f

# n8n 컨테이너만 로그 확인
docker-compose logs -f n8n
```

## 설정 정보

- **포트**: 5678 (HTTP)
- **데이터베이스**: SQLite (로컬 파일)
- **데이터 저장소**: `./n8n-data` 디렉토리
- **타임존**: Asia/Seoul

## 중요 참고사항

1. `n8n-data` 디렉토리에는 워크플로, 실행 기록, 데이터베이스가 저장됩니다.
2. 이 디렉토리는 `.gitignore`에 포함되어 있어 Git에 추가되지 않습니다.
3. 데이터 백업이 필요한 경우 `n8n-data` 디렉토리를 별도로 백업하세요.
