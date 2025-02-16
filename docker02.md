# docker container run (= docker run)
도커 이미지로부터 새 컨테이너를 생성하고 실행하는 명령어  
(단, 로컬에 이미지가 없으면 일단 원격 repository에서 pull(다운로드)부터 실행 후)
  
```
docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]
(container는 생략 가능해서 보통 생략)
```
  	
### docker run options

|option|description|
|---|---|
|-d, --detach|컨테이너를 백그라운드에서(대몬으로) 실행하고 컨테이너 ID 출력|
|-e, --env|환경 변수 설정|
|-p, --publish|호스트 포트에 컨테이너 포트 연결 (network)|
|-v, --volume|호스트와 컨테이너의 저장 공간 연결 (Bind mount)|
|-i, --interactive|STDIN(표준 입력. 키보드) 열어놓기|
|-t, --tty|가상-TTY(입출력 드라이버) 할당|
|--link|다른 컨테이너에 연결|
|--name|컨테이너에 이름 할당|
|--rm|프로세스 종료시 '컨테이너' 및 연결된 익명 저장 공간 자동 삭제 (이미지 삭제 아님)|
