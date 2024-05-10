## cli example

-------------------------------

### 1. Download an image from a registry
* 사용법
```
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```
* 예제
```
docker pull httpd
```

### 2. List images
* 사용법

```
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
* 예제

```
docker images
```

### 3. Create and run a new container from an image
* 사용법

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
* 예제

```
docker run httpd
docker run --name secondContainer httpd
docker run -p 8888:80 -v /Users/jk/wanted/docker-pro/lecture/1st:/usr/local/apache2/htdocs httpd
```
### 4. Start one or more stopped containers
* 사용법

```
docker start [OPTIONS] CONTAINER [CONTAINER...]
```
* 예제

```
docker start c8274d6a6273
```
### 5. Stop one or more running containers
* 사용법

```
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```
* 예제

```
docker stop 9b0f49de746c
docker stop -a
```
### 6. Fetch the logs of a container
* 사용법

```
docker logs [OPTIONS] CONTAINER
```
* 예제

```
docker logs second
docker logs second -f
```
### 7. Remove one or more containers
* 사용법

```
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```
* 예제

```
docker rm 6026ab9b44cc
docker rm second -f
```
### 8. Remove one or more images
* 사용법

```
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
* 예제

```
docker rmi 6026ab9b44cc
```
### 9. Execute a command in a running container
* 사용법

```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
* 예제

```
docker exec -it awesome_elion /bin/sh
```
### 10. Manage containers
* 사용법

```
docker container COMMAND
```
#### 10-1. Remove all stopped containers
* 사용법

```
docker container prune [OPTIONS]
```
* 예제

```
docker container prune
```
#### 10-2. Display a live stream of container(s) resource usage statistics
* 사용법

```
docker container stats [OPTIONS] [CONTAINER...]
```
* 예제

```
docker container stats
```
### 11. Manage images
* 사용법

```
docker image COMMAND
```

#### 11-1. Remove unused images
* 사용법

```
docker image prune [OPTIONS]
```
* 예제

```
docker image prune
```
#### 11-2. Display detailed information on one or more images
* 사용법

```
docker image inspect [OPTIONS]
```
* 예제

```
docker image inspect httpd
```
#### 11-3. Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
* 사용법

```
docker image tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```
* 예제

```
docker image tag my-httpd drumgrammer/my-httpd:latest
```
### 12. Upload an image to a registry
* 사용법

```
docker push [OPTIONS] NAME[:TAG]
```
* 예제

```
docker push drumgrammer/my-httpd:latest
```
### 13. Log in to a registry
* 사용법

```
docker login [OPTIONS] [SERVER]
```
* 예제

```
docker login
```
### 14. Log out from a registry
* 사용법

```
docker logout [SERVER]
```
* 예제

```
docker logout
```
### 15. Manage Docker
* 사용법

```
docker system COMMAND
```
#### 15-1. Remove unused data
* 사용법

```
docker system prune [OPTIONS]
```
* 예제

```
docker system prune
```

##  Dockerfile 활용

-------------------------------
#### 1.Dockerfile 예제
```
FROM httpd:latest
COPY  index.html /usr/local/apache2/htdocs/index.html
EXPOSE 80
```
#### 2. 이미지 만들기
```
docker build -t my-httpd .
```
#### 3. 도커파일로 생성된 이미지로 컨테이너 생성하기
```
docker run -d -p 8888:80 my-httpd
```



##### 출처 - [원티드 백엔드 프리온보딩 5월 강의 1주차 - 1](https://github.com/drum-grammer/docker-pro/blob/main/lecture/1st/cli.md)