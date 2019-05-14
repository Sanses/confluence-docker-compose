confluence 를 docker-compose로 실행합니다.

0. 사전 조건
## confluence-data 폴더 생성
- /opt/apps/atlassian/confluence-data

## postgres-data 폴더 생성
- /opt/apps/database/postgres-data


1. git 소스를 clone합니다.
git clone {git clone URL}

2. git 소스로 이동합니다.
cd confluence-docker-compose

3. docker-compose로 multi container를 실행 합니다.
docker-compose up -d
