# Docker Swarm

### Initialize Swarm
- docker swarm init

### Create service
- docker service create alpine ping 8.8.8.8

### Docker service list
- docker service ls
- docker service ps nameofcreatedservice

### Update service
- docker service update idnumber --replicas 3
desired number of replicas

### Remove Service
- docker service rm servicename