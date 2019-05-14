## confluence+postgres 를 docker-compose로 실행합니다.

# 환경준비
가. docker-ce 설치
나. docker-compose 설치

# 사전 조건
- confluence-data 폴더 생성
$> mkdir /opt/apps/atlassian/confluence-data

- postgres-data 폴더 생성
$> mkdir /opt/apps/database/postgres-data

# docker-compose 로 멀티 컨테이너 실행
1. docker-compose 파일을 다운로드 합니다.
wget 

2. vi docker-compose.yml 파일을 검토 하고 필요에 따라 커스터 마이즈 합니다.

3. docker-compose로 multi container를 실행 합니다.
$> docker-compose up -d

4. docker container를 확인 합니다.
$> docker ps

---
[root@wiki-vm confluence-docker-compose]# docker ps
CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                                          NAMES
dcbb2f9f96c2        atlassian/confluence-server:6.15.2   "/tini -- /entrypoin…"   27 minutes ago      Up 27 minutes       0.0.0.0:8091->8091/tcp, 0.0.0.0:80->8090/tcp   confluence
b1661f870ffe        postgres:10.4                        "docker-entrypoint.s…"   27 minutes ago      Up 27 minutes       0.0.0.0:5432->5432/tcp                         confluence-postgres
---
