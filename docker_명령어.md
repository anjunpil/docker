1.DockerFile 로 새 이미지 생성
(DockerFile이 있는 위의 경로에서)
docker build . -f docker/Dockerfile

2.이미지로 컨테이너 생성 및 실행
docker run [만들 이미지 이름]

3.이미지로 컨테이너 실행
docker start [이미지 이름]

이미지 목록
docker images

이미지 삭제 -f 옵션 : 이미지가 생성한 컨테이너도 삭제
docker rmi  [-f] [이미지ID]

이미지 임포트(로컬 호스트로부터 images 생성)
docker load -i [path to image tar file]

이미지 익스포트(로컬 호스트에 저장)
docker save -o [file_name] [image name] 

이미지로 컨테이너 생성하고 bash로 실행 (호스트 파일시스템의 특정 경로를 컨테이너의 /data 디렉토리에 공유)
docker run -it -v [호스트 경로]:[컨테이너에서 접근할 경로] [이미지 이름] /bin/bash
docker run -it -v D:/grew_svn/2019:/data conda:rllab_robustRL /bin/bash


----------------------------------------------------
컨테이너 목록
docker ps (현재)
docker ps -a (전체)

컨테이너 모두 삭제(windows 에선 배치파일로 처리)
docker rm `docker ps -a -q`

컨테이너 종료
exit

컨테이너 실행(종료상태일 때)
docker start [컨테이너 ID]

컨테이너 종료하지 않고 나오기
Ctrl + P + Q

컨테이너에 다시들어가기(종료상태가 아닐 때)
docker attach [컨테이너 ID]

컨테이너 변경사항을 이미지에 저장
docker commit [컨테이너 ID] [리포지토리]:[태그]
docker commit [컨테이너 ID] conda:rllab_robustRL

컨테이너 홈 디렉토리의 .bashrc에 추가

vi .bashrc 로 들어가 확인

export PYTHONPATH=$PYTHONPATH:[container 경로]
export PYTHONPATH=$PYTHONPATH:[container 경로2]
