# Docker command for networks chapter

```bash
docker build -t favorites-node .
docker run --rm -d -p 3000:3000 --name favorites favorites-node
docker run --rm -p 3000:3000 --name favorites favorites-node
```

In Docker, requests to outside web is not problem. Requests to local host machine can be resolved with `host.docker.internal`, which represents the host domain in source code.

Requests across containers can be resolved by using ip address or by using Docker network which is a much better method. If containers are in a same network, they can communicate with each other and IPs are automatically resolved.

`docker run --name mongodb -d mongo`

`docker inspect mongodb`

`docker container prune`: Remove all stopped containers

`docker network ls`: List all networks

```bash
docker run --name mongodb -d --network favorites-net mongo
docker run --rm -d -p 3000:3000 --network favorites-net --name favorites favorites-node
```
