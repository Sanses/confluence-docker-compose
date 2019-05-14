# confluence+postgres 를 docker-compose로 실행합니다.



## 환경준비
1. docker-ce 설치
2. docker-compose 설치

## 사전 조건
1. confluence-data 폴더 생성
- mkdir /opt/apps/atlassian/confluence-data

2. postgres-data 폴더 생성
- mkdir /opt/apps/database/postgres-data

## docker-compose 로 멀티 컨테이너 실행
1. docker-compose 파일을 다운로드 합니다.
- wget https://raw.githubusercontent.com/Sanses/confluence-docker-compose/master/docker-compose.yml

2. docker-compose 파일을 검토 하고 필요에 따라 커스터 마이즈 합니다.
- vi docker-compose.yml 

3. docker-compose로 multi container를 실행 합니다.
- docker-compose up -d

4. docker container를 확인 합니다.
- docker ps

[root@wiki-vm workspace]# docker ps
CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                                          NAMES
dcbb2f9f96c2        atlassian/confluence-server:6.15.2   "/tini -- /entrypoin…"   About an hour ago   Up About an hour    0.0.0.0:8091->8091/tcp, 0.0.0.0:80->8090/tcp   confluence
b1661f870ffe        postgres:10.4                        "docker-entrypoint.s…"   About an hour ago   Up About an hour    0.0.0.0:5432->5432/tcp                         confluence-postgres


## confluence 환경 설정
http://{your ip}


### DB 설정 정보 참고
- db hosts : postgresql
- db name : confluencedb
- db port : 5342
- db user : dbuser
- db passwd : dbpassword
