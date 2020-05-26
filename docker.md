## docker

- os는 아니다
- linux에서 왔지만 하나의 프로세스
- on-premises  회사에 서버실을 두고 사용(보안-인트라넷에 많이 사용) /데이터 전달받을 때 firewall 있음 , 특정 포트를 열어서



- load balancing

- immutable ,stateless

- linux Base* (linux virtual box를 설치해야 한다)



## docker terms

- docker image and container
- docker engine(deamon) - 실제 운영을 담당

- docker client(docker 바깥쪽 부팅 나는 window로 부팅)
- docker host OS (바깥쪽 os 나는 window)
- docker machine - docker 안쪽 애들
- docker compose - run 할 때 한번에 run할 수 있게함
- docker registry

## docker container

directory ip 공유

## docker Image

app,libs,middleware,os,nw,etc



## docker principle

- namespace  ex) python 3.7 python 3.8

- docker0 NIC

## 명령어



- docker verison  : 버전 확인

- docker --help : 도움말

- docker run hello-world

- docker machine ls - 오류 ㅜ

- docker cotainer run ubuntu:latest  /bin/echo 'Hello world'

- docker ps - 현재 실행중인 container 

- docker system df - image , container 상태들을 알려준다

- docker container run --name webserver -d -p 80 :80 nginx 
 - 이름은 webserver 로 -d (background명령 배경으로 돔) -p(port) 80(1) 내 pc포트 80(2) nginx 의 포트 

-


