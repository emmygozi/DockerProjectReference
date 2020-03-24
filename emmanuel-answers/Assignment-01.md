### Using Containers for CLI Testing
1) Create get into the shell of containers using -it flag and cleanup after using --rm

- docker container run -it --rm centos:7 bash
- docker container run -it --rm ubuntu:14.4 bash

2) Create network, container without name but alias to show how DNS Round Robin
A technique to have dns with same name on the hosted on different ips on the server
- docker network create fruit
- docker container run -d --net fruit --net-alias search elasticsearch:2
- docker container run -d --net fruit --net-alias search elasticsearch:2
- docker container ls
- docker container run --rm --net fruit alpine nslookup search
- docker container run --rm --net fruit centos curl -s search:9200

The last command to search with `curl` shows different name outcomes

### Using Jekyll Assignment
- docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve
