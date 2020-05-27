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

-docker container rm webserver(이름) - container 삭제

- docker search ubuntu : ubuntu 찾기 ( star 가 많은것들 인기도가 높다)

- docker container run -it --name "test1" centos /bin/cal
 - i 는 input()  t는 tty standardout() - interactive한 대화형으로 받을 수 있다
 - centos 는 image 이름으로 실행 시킴
 - /bin/cal로 실행시켜라 (callender가 생성됨) bin은 기본명령

-docker container run -it --name "cosh" centos bash
 - linux를 실행시킴
 - whoami , exit, ls -al

- docker container run -it --name "ubuntush" ubuntu bash
 - ubuntu 실행
 - 종료 exit or ctrl p+q
 
 - run 실행시키기
 - -d(detach) 밖으로 나오기 (ctrl+ p,q) 하지만 container는 계속 작동중
 - exit() 는 완전히 container를 종료하고 나온다
 
 - attach - 현재 실행중인 container에 들어가는 것
 - stop  - container 죽이기
 
 - docker container exec - it ubuntush cat /etc/hosts
  - ubuntu container 안에 하나의 명령 cat /etc/hosts 만 실행해라
  
 - docker container port ubuntush
 - docker containrt rename ubuntush ub
  - 이름 변경
 
- docker container cp container-name: path client-path
 - container file을 줄 수 있다
- docker container cp container-name: path client-path
 - 내 파일을 container 에 줄 수 있다
  
- share directory(중요)
 - docker run -v localpath : container-path
 
 - docker stop `docker ps -q`
- docker ps -q 실행중인 container 의 ID를 달라

## docker - oracle ,Mysql

### oracle
<br>
#### 명령

- docker pull christophesurmont/oracle-xe-11g  - oracle image다운

- docker run -d -p 8080:8080 -p 1521:1521 christophesurmont/oracle-xe-11g
 - database 자체의 port  

- docker exec -it oracle bash
 -lsnrctl를 입력해서
 - oracle 서버로 들어간다
 
### mysql
<br>
#### 명령
- docker pull mysql:5.7
 - mysql 설치
 - 

- docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root1! --name mysql5 mysql:5.7
 - -e 환경변수 MYSQL_ROOT_PASSWORD =root1!(비밀번호 설정)
 - 띄어쓰기 주의
 - mysql:5.7 (mysql 에 태그도 입력해줘야한다 안그럼 오류남)
 
 - docker exec -it mysql5 bash
  - mysql bash로 들어가기
  - which mysql - mysql -위치알아보기
  - mysql -u root -p  - 비밀번호를 치고 들어가면 mysql로 들어갈 수 있음
  - show databese; - database들을 보여줌
  - use mysql - mysql을 사용하겠다
  - show tables;
  - select * from user;
  - select host,user from user;
  - quit - 종료
  

  
  
  
  
  
