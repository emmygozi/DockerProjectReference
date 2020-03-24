### Show Networks
- docker network ls

### Inspect a Network
- docker network inspect (networkname -)bridge

### Create a Network
- docker network create my_app_net

### Network Help
- docker network --help 
- docker network create --help 

### Connect to New Application
- docker network connect my_app_net_ID container_specified_ID
press tab for autocompletion
`Important`: To add a container to bridge network by default,
publish the port with the -p on create.

### Create Two Containers on Same Network and Ping Each Other Using DNS
- docker container run -d --name my_nginx --network my_app_net  nginx
- docker container run -d --name new_nginx --network my_app_net  nginx
- docker container exec -it my_nginx bash
- apt-get update
- apt-get install inetutils-ping
- exit
- docker container exec -it new_nginx bash
- apt-get update
- apt-get install inetutils-ping
- exit
- docker container exec -it my_nginx ping new_nginx

`What it solves`? 
It solves the problem of changinging IP address by using the dns as hostname



