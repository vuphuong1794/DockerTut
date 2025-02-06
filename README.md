This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

<h1 align="center">Docker basic command</h1> 

## 1. DOCKER PULL
1) docker pull = Pull an image or a repository from a registry

## 2. LIST CONTAINERS, IMAGES
2) docker ps = Lists containers
3) docker ps -a = Lists running and stopped container
4) docker images = List images 
5) docker ps -aq = in ra tat ca containerID

## 3. START / STOP CONTAINER
6) docker start containerId = Start stopped containers
7) docker stop containerId = Stop one or more running containers

## 4. DOCKER RUN
8) docker run [OPTIONS] ${IMAGE_NAME}:${IMAGE_TAG} command
8) ex: docker run -it ubuntu:18.04 sh 
9) docker run image = Run a command in a new container || pulls image and starts container
10) docker run -d image = Run the command but can still continue writing other commands 
11) docker run -p Port:Port = Run a command on speciffic port
12) docker run image:version = Pull and run the container version you want

## 5. DOCKER DEBUGS
13) docker logs containerId = Fetch the logs of a container
14) docker exec -it containerId /bin/bash (ls, pwd, cd/, ls, env, exit ) = Check details information inside image

## 6. DOCKER NAME
15) docker run --name newName image = Run a command and change container name

## 7. REMOVE CONTAINER, IMAGE
16) docker rm containerId/Name = xoa container duoc chi dinh
16.1) docker rm -f containerId/Name = vua stop vua xoa container
17) docker rm $(docker ps -aq) = xoa het tat ca container
18) docker rm -f $(docker ps -aq) = xoa het tat ca container ke ca khi dang chay
              
## 8. FORMAT
19) docker ps --format=$FORMAT = format cho de nhin

## 9. VOLUMNS (duy trì dữ liệu bên trong container)
20) C:\website>docker run --name website -v "%CD%":/usr/share/nginx/html:ro -d -p 8080:80 nginx = ví dụ vể docker volumes sử dụng file index.html trong folder website thay vì file gốc của nginx
21) ví dụ lưu dữ liệu cho mongo
    + mkdir data (tạo folder lưu dữ liệu)
    + docker run -it -p 27017:27017 -v $(pwd)/data:/data/db --name mongo -d mongo
ví dụ khi container bị lỗi hay ngưng hoạt động hay db bị dừng thì dữ liệu vẫn được duy trì mà ko bị mất

## 10. REPLACE THE OLD CONTAINER
22) docker build -t imageName .
23) docker run -dp port:port imageName

## 11. SHARE THE APPLICATION
24) docker tag getting-started YOUR-USER-NAME/getting-started:tagname = Use the docker tag command to give the getting-started image a new name
25) docker push YOUR-USER-NAME/getting-started

