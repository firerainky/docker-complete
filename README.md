# Learning Docker and Kubernetes from Udemy course

[First docker container example](https://www.udemy.com/course/docker-kubernetes-the-practical-guide/learn/lecture/22625196#overview)

- Start Docker if it's not started: `sudo dockerd`
- Build the container: `docker build .`, but this command is legacy nowadays in Docker 18.
- Run the container: `docker run -p 3000:3000 6114dadd34a9`
- List the containers: `docker ps`
- Stop the container: `docker stop $running_name$`, this operation will take a couple of seconds.