### References
- `https://github.com/docker/libnetwork/blob/master/docs/design.md`

### Commands
- `docker version`
- `docker info`
- `docker network ls`
- `docker network inspect <network ID>`

### Bridge networking
- `docker network create -d bridge --subnet 10.0.0.1/24 <network name>`
- `sudo apt-get install bridge-utils`
- `brctl show`
- `ip link show`
- `docker run -dt --name c1 --network <network name> alpine sleep 1d`
- `docker run -dt --name c2 --network <network name> alpine sleep 1d`
- `docker exec -it c1 sh`
- `docker exec -it c2 sh`
- `docker run -d --name web1 --network <network name> -p 5000:8080 <image name>`

### Overlay networking
- `docker swarm init`
- `docker swarm join --token <token> ip:port`
- `docker node ls`
- `docker network create -d overlay <network name>`
- `docker service create --name <service name> --network <network name> --replica 2 sleep 1d`
- `docker service ps <service name>`