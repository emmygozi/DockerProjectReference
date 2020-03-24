# Docker Image

### Create Docker image tag off nginx official downloaded container using your docker repo name
make sure image nginx exits
- docker image tag nginx emmygozi/nginx

### Login to repo
- docker login
pass your details
If error connecting click on the docker desktop icon > preferences > Resources > PROXIES > webserver http = 8.8.8.8

### Push to Your Docker Repository
- docker image push emmygozi/nginx

### Create new tag off emmygozi/nginx
- docker image tag emmygozi/nginx emmygozi/nginx:testing

### Push new tag to emmygozi/nginx repository
- docker image push emmygozi/nginx:testing
