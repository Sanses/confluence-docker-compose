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


# confluence 환경 설정
http://{your ip}
