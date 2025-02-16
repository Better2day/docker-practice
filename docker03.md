# docker 기본 명령어

### 이미지 다운로드
```
docker pull name[:tag]
eg. docker pull node:22.14.0
```

### 이미지 목록 표시
```
docker images
```

### 컨테이너 목록 표시  
```
docker ps     실행중인 컨테이너 목록 표시
docker ps -a  실행 후 종료된 컨테이너 목록까지 표시
```
cf. 컨테이너는 종료되어도 삭제되지 않고 남아있어서, 다시 시작할 수도 있다.

### 컨테이너 시작
```
docker start containerID(or containerName)
```
containerID는 띄어쓰기로 구분해서 여러 개를 동시에 중지 가능  
cf. 컨테이너ID는 복사 후 붙여넣어도 되지만, 다른 컨테이너ID와 중복되지 않는다면 ID의 앞글자 몇 자만 적어도 된다.  
eg. docker stop b5f (원래 ID가 b5fd009f3fab일 때)  

### 컨테이너 중지
```
docker stop containerID(or containerName)  실행중인 컨테이너 중지
```
containerID는 띄어쓰기로 구분해서 여러 개를 동시에 중지 가능  
cf. 컨테이너ID는 복사 후 붙여넣어도 되지만, 다른 컨테이너ID와 중복되지 않는다면 ID의 앞글자 몇 자만 적어도 된다.  
eg. docker stop b5f (원래 ID가 b5fd009f3fab일 때)  

### 컨테이너 제거
```
docker rm containerID  종료된 컨테이너 제거
```
containerID는 띄어쓰기로 구분해서 여러 개를 동시에 제거 가능  

제거할 컨테이너가 많을 때는 아래처럼 옵션을 이용해서 쉽게 제거 가능  
```
docker rm $(docker ps -a -q -f status=exited)
  
(※ 이 명령은 윈도우 터미널의 경우 PowerShell에서만 가능하고, Command Prompt(cmd)에서는 오류 발생  
    Command Prompt에서 제거하려면 docker system prune 명령어 사용)
```
-q, --quiet: 컨테이너ID만 출력  
-f, --filter: 조건에 해당하는 컨테이너만 필터링 (위 예에서는 '종료' 상태인 컨테이너만)  
-n 숫자: 가장 최근에 생성된 n개의 컨테이너를 필터링  
  
### 이미지 삭제
```
docker rmi imageID
```

  
### 컨테이너 로그 표시
```
docker logs containerID
docker logs containerID --tail 10  (로그가 길 경우) 로그 마지막 10줄만 표시
```
  
### 컨테이너 명령어 실행
```
docker exec -it containerID command
eg. docker exec -it b5f /bin/bash
```
