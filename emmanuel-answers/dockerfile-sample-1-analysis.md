# dockerfile-sample-1-analysis

### Steps
- cd dockerfile-sample-1
- docker image build -t customnginx .
this builds docker image in current location

`Note`: Keep the things that changes the most in your Dockerfile at the bottom and 
things that doesn't change at the top because docker uses hashes

It is best to build from an already existing image using the FROM

### Build Docker Assignment 2
- docker build -t testnode .
- docker container run --rm -p 80:3000 testnode
- docker tag testnode emmygozi/testing-node
- docker push emmygozi/testing-node
- docker image rm emmygozi/testing-node
- docker image ls
- docker container run --rm -p 80:3000 emmygozi/testing-node
- docker container run -d -p 80:3000 emmygozi/testing-node

### Named Volume Docker
- docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=true -v mysql-db:/var/lib/mysql mysql
Add -v and name-of-volume:/volumn/path to Docker
Check official image repo on docker to view volumn path
- docker volumn ls
- docker volumn inspect

### Run Postgres
- docker container run -d --name psql -v psql:/var/lib/postgresql/data -e POSTGRES_HOST_AUTH_METHOD=trust postgres:9.6.17
or with password
- docker container run -d --name psql -v psql:/var/lib/postgresql/data -e POSTGRES_PASSWORD=password postgres:9.6.17

### Keep Watching Logs Docker with -f
- docker container logs -f psql

### Stop Container
- 
