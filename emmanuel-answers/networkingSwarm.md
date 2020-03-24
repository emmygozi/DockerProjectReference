# Network 
`Do this on node1 - leader node in your swarm`

### Create docker overlay network
- docker network create networkname --driver overlay
allows containers connected to it (including swarm service containers) to communicate

### Connect psql to mydrupal overlay network
- docker service create --name psql --network mydrupal -e POSTGRES_PASSWORD=mypass postgres
database running on node1

### Connect drupal to mydrupal overlay network
- docker service create --name drupal --network mydrupal -p 80:80 drupal
drupal running on node2
- docker service ls
- docker service ps drupal
- docker network inspect mydrupal

### How do they talk with each other?
