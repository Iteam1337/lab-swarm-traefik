# lab-swarm-traefik
Findings from playing with swarm and traefik

## Setup swarm

Setup a number of centos 7.4 servers. Run the "centos.sh" init script from https://github.com/Iteam1337/init-scripts/

## Setup proxy + services

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
docker stack deploy --compose-file docker-compose.services.yml lab
```
You can run the stack deploy commands over and over again if you have made changes to your .yml files.

## See for yourself

Traefik: http://swarm.lab.zengarden.se:5001/dashboard/#/

Services:
http://whoami.swarm.lab.zengarden.se/
http://nginx.swarm.lab.zengarden.se/
