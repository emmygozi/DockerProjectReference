# Docker Machine Commands

### Create virtual machine
- docker-machine create name1
- docker-machine create name2

### Configure your machine to listen to name1
- docker-machine env name1
- eval $(docker-machine env name1)
- docker info
Name should be name1 

### Docker swarm init
- docker swarm init
- docker swarm init --advertise-addr ip.number.shown.on.previous.command

### Join as Manager after init
- docker swarm join-token manager

### Join as Worker after init
- docker swarm join-token worker

### Join swarm as worker
open new terminal and type
- docker-machine ssh number2
copy swarm join command something like below
- docker swarm join --token SWMYGH-1-1aclevyuqxdhrasryt85wn0ka0nqps1ecmg4849f7i-c7v8xnyn6yx3mel1a0r94q28u 194.36.37.38.87
number2 is added as a worker

### Join swarm as manager
- docker node update --role manager number2

`OR`

### Promote node to manager
- docker node promote node-3 node-2

### Demote node to worker
- docker node demote node-3 node-2

### Start 2 replica services for nodes
- docker service create --replicas 2 alpine ping 8.8.8.8

### Increase or decrease the numbers of replicas in a swarm to scale
- docker service update <service-name> --replicas 10
note: to view service name, run docker service ls

### Check running service
- docker service ls
- docker node ls
- docker node ps node2

### Simple solution for unsetting name1 and all node
eval "$(docker-machine env -u)"

### check after unset
env | grep DOCKER

### Leave swarm 
- docker swarm leave 
on the node that you want it to leave

