# lab-swarm-traefik
Findings from playing with swarm and traefik

Assuming you are in a shell on a node/computer where you are connected to a swarm, do the following.

Setup a network called "proxy".
```
docker network create --driver overlay proxy
```

Deploy traefik-proxy stack.
```
docker stack deploy --compose-file docker-compose.traefik.yml traefik-proxy
```
Deploy services stack.
```
docker stack deploy --compose-file docker-compose.services.yml services
```
