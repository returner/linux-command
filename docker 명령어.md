### remove containers
```bash
docker container rm -f $(docker container ls -aq)
```

### remove images
```bash
docker image rm -f $(docker image ls -f reference='diamol/*' -q)
```

### container 강제 삭제
```bash
docker container rm --force $(docker container ls --all --quiet)
```

### container 내부에 명령어 실행
```bash
docker container exec ### ls /usr/local/apache2/htdocs
```

### contaner 내부로 파일 복사
```bash
docker container cp index.html ###:/usr/local/apache2/htdocs/index2.html
```

### 백그라운드에서 실행하면서 이름을 지정하는 방법
```bash
docker container -d --name web-ping diamol/ch03-web-ping
```

### 도커의 환경변수값 세팅 or 변경
```bash
docker container run --env TARGET=google.com diamol/ch03-web-ping
```

### docker image build (끝에 . 이 있어야함 - 빌드 context가 현재 디렉터리라는 뜻)
```bash
docker image build --tag DOCKER_IMAGE_NAMe .
```

### docker image build history
```bash
docker image history web-ping
```

### 전체 이미지 목록
```bash
docker image ls
```

### 도커 시스템 용량등
```bash
docker system df
```

