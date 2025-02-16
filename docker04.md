# docker 관리 명령어

### 도커 디스크 사용량 표시
```
docker system df
docker system df -v (or --verbose)  # 상세 표시
```
  
### 도커 디스크 정리
미사용(중지 상태) 컨테이너, 네트워크, 이미지(dangling or unused), 빌드 캐시 전부 제거
```
docker system prune
docker system prune --volumes  # 익명 저장소도 제거
```
