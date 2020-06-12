# confluence+postgresql 를 docker-compose로 실행합니다.



## 환경준비
0. root 계정으로 설치 합니다.
1. docker-ce 설치
- 참고 : https://docs.docker.com/install/linux/docker-ce/centos/
2. docker-compose 설치
- 참고 : https://docs.docker.com/compose/install/

## 사전 조건
1. confluence-data 폴더 생성 (confluece application 입니다.)
- mkdir -p /opt/apps/atlassian/confluence-data

2. postgres-data 폴더 생성 (postgres db data 입니다.)
- mkdir -p /opt/apps/database/postgres-data

3. SSL 인증서
- certbot-auto certonly --cert-name wiki.iisanse.com -d wiki.iisanse.com

## docker-compose 로 멀티 컨테이너 실행
1. docker-compose 파일을 다운로드 합니다.
- git clone https://github.com/Sanses/confluence-docker-compose.git
- cd confluence-docker-compose
- cp /etc/letsencrypt/live/wiki.iisanse.com/fullchain.pem ssl
- cp /etc/letsencrypt/live/wiki.iisanse.com/privkey.pem ssl

2. docker-compose 파일을 검토 하고 필요에 따라 커스터 마이즈 합니다.
- vi docker-compose.yml 

3. docker-compose로 multi container를 실행 합니다.
- docker-compose up -d --build

4. docker container를 확인 합니다.
- docker ps


## confluence 환경 설정
https://wiki.iisanse.com


## DB 설정 정보 참고
- db hosts : postgresql
- db name : confluencedb
- db port : 5432
- db user : dbuser
- db passwd : dbpassword

## 참고
confluence를 이전 할 경우 대상 환경에 docker-compose파일로 container를 실행하고,
confluence-data, postgres-data 데이터를 대상환경에 복제해 주면 기존환경 그대로 이용 가능합니다.
