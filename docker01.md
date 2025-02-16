## 도커의 필요성

얼마 전에 도커를 학습할 때 계속 든 생각으로, '도커를 왜 사용해야 하지?'  
'상당히 복잡해보여서 학습 비용이 꽤 들 것 같은데, 그만한 가치가 있을까' 등이 있었다.  
하지만 요새 대부분의 기업에서 거의 필수로 사용하는 기술이라길래, 필요성에 대해서 조사해봤고 납득할만 했다.  
한글 자료가 별로 없지 않을까 걱정했지만, 의외로 잘 작성된 자료가 많아서 링크로 대신한다. ~~아직 이런 글을 작성할 내공이 없다.~~

[왜 굳이 도커(컨테이너)를 써야 하나요? 눈송이 서버의 한계를 넘어 컨테이너를 사용해야 하는 이유](https://www.44bits.io/ko/post/why-should-i-use-docker-container)  
[초보를 위한 도커 안내서 - 왜 이렇게 핫한가?](https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html#왜-이렇게-핫한가)  
  
아직 충분히 실습해보지 않았고 머리로만 이해한 정도라서, 실습하면서 익혀야겠다.  
  
## 도커 엔진 설치 및 설정  
도커 엔진은 서버(dockerd 대몬 프로세스), API, 클라이언트(CLI(command line interface))로 이뤄져 있다.  
구조: Docker CLI ↔ API ↔ Dockerd 대몬
  
[Docker Docs → Docker Engine → Istall → Ubuntu](https://docs.docker.com/engine/install/ubuntu/)  
한 O/S에 설치하는 방법도 몇 가지씩이나 된다.  
공식 홈페이지에서는 [Install using the apt repository] 방식을 추천하지만,  
지금은 [실습 가이드](https://subicura.com/2017/01/19/docker-guide-for-beginners-2.html)에 나온대로 [Install using the convenience script] 방식으로 진행한다.  
(※ 이 방식은 운영 환경에 적합하지 않다고 하니, 추후 본격적으로 사용하려면 apt 리포를 이용하는 게 낫겠다.)  
  
Preview script steps before running.  
You can run the script with the --dry-run option to learn what steps the script will run when invoked:  
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```
  
This example downloads the script from https://get.docker.com/ and runs it to install the latest stable release of Docker on Linux:  
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
Executing docker install script, commit: 7cae5f8b0decc17d6571f9f52eb840fbc13b2737
<...>
```
  
### sudo 없이 도커 사용하기  
사용자를 docker 그룹에 추가해서 sudo 없이 도커를 사용할 수 있도록 설정한다.
```bash
sudo usermod -aG docker $USER # 현재 접속중인 사용자를 docker 그룹에 추가
sudo usermod -aG docker 사용자명(bitnami 등) # 특정 사용자(bitnami 등)를 docker 그룹에 추가
```

##  

#### 참고 자료
[왜 굳이 도커(컨테이너)를 써야 하나요? 눈송이 서버의 한계를 넘어 컨테이너를 사용해야 하는 이유](https://www.44bits.io/ko/post/why-should-i-use-docker-container)  
[초보를 위한 도커 안내서 - 왜 이렇게 핫한가?](https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html#왜-이렇게-핫한가)  
[실습 가이드](https://subicura.com/2017/01/19/docker-guide-for-beginners-2.html)  
[Docker Docs → Docker Engine → Istall → Ubuntu](https://docs.docker.com/engine/install/ubuntu/)  
