#### docker  - single container 에 대한 명령을 수행하는 client

#### docker-compose yaml file을 기반으로 multi container를 관리할 수 있는 client

## COPY - 파일을 복사하는 명령어
## RUN - 실행하는 명령어 ,RUN 명령은 image layer를 만들어냄
## ADD - 파일을 이미지에 추가
#### ex)
- ADD hello-entrypoint.sh /entrypoint.sh
- ADD hello-dir /hello-dir
- ADD zlib-1.2.8.tar.gz /
- ADD hello.zip /
- ADD http://example.com/hello.txt /hello.txt
- ADD *.txt /root/

밑에 5개는 모두 같은 image를 가리킴

- nginx:latest
- nginx@sha256:50cf965a6e08ec5784009d0fccb380fc479826b6e0e65684d9879170a9df8566
- library/nginx:latest
- docker.io/library/nginx:latest
- index.docker.io/library/nginx:latest


CMD : 컨테이너가 실행될 때 명령어 및 인자값 전달하여 실행,
 단 docker run 명령에 쉘 명령어 및 인자값 전달할 경우 CMD에 작성된 명령어와 인자값은 무시됨
 
#### CMD
- 명령과 인자값이 변경될 수 있고, 컨테이너에서 명령 설정하지 않을 시 CMD에 기재된 명령을 기본값으로 실행
#### ENTRYPOINT
- 명령 수정이 불가능하여 사용자에 의해 변경되지 않고 고정적으로 실행될 명령은 ENTRYPOINT를 사용하는것이 좋음 

