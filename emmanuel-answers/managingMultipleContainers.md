# Managing Multiple Containers

### Mysql Server Start, Stop and Remove
- docker container run -d -p 3308:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
- docker container logs db | grep "GENERATED ROOT PASSWORD"
- Copy generated root password
- docker container stop ID
- docker container rm (optionally add -f for force removal of running command)

### Apache Webserver Start, Stop and Remove
- docker container run -d --name webserver -p 8888:80 httpd
- docker container stop ID
- docker container rm (optionally add -f for force removal of running command)

### Nginx Start, Stop and Remove
- docker container run -d --name proxy -p 90:80 nginx
- docker container stop ID
- docker container rm (optionally add -f for force removal of running command)

### List all containers (Default shows running)
- docker container ls

### List all containers (Including stopped ones)
- docker container ls -a

### Start Already Created Container
- docker start container_id

### Test Containers from Commandline
- curl localhost
- curl localhost:8080

### Container Overview 
- docker container inspect

### List Docker Images
- docker image ls 

### List Processes Running inside a Container
- docker container top nginx

### View Container Json Config
- docker container inspect nginx

### Run containers without image
- docker container run -d --name nginx nginx
- docker container run -d --name mysql -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql

### See Container Port
- docker container port webhost

### View Container Stats
- docker container stats --help

### View Container Stats Streaming View for CPU View and Performance Monitoring
- docker container stats

### Getting a Shell Inside the Container
- docker container run -it --name proxy nginx bash
- List files in Bash Root; ls -al
- Exit; exit
NB: this exit the parent proxy and the child bash

### Getting a Shell Inside the Container Ubuntu
- docker container run -it --name ubuntu ubuntu
- apt-get update
- apt-get install -y curl
- Exit; exit
- Start Ubuntu; docker container start -ai ubuntu

### Starting a Shell Inside the Container that doesn't affect root process
- docker container exec -it nginx bash

### Pull alpine image a lightweight cammandline tool compared to ubuntu
- docker pull alpine
- Package Manager; apk