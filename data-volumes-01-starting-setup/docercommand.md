# Docker command under volumes chapter

## Build the image

`docker build -t feedback-node:volumes .`

## Run a container on the base of the image

`docker run --rm -d -v feedback:/app/feedback -p 3000:80 --name feedback-app feedback-node:volumes`

## Stop the container

`docker stop feedback-app`

## Show all retained volumes

`docker volume ls`

## Delete a volume / volumes

`docker volume rm VOL_NAME` / `docker volume prune`

## Add bind mount volume in the docker

`docker run --rm -d -v feedback:/app/feedback -v $(pwd):/app  -p 3000:80 --name feedback-app feedback-node:volumes`

But this command will not make the app work since the node modules (dependencies) would not remains in the docker because the source folder will copy into the container.

## Add another anonymous volume

To keep dependencies remaining in the container.

`docker run --rm -d -v feedback:/app/feedback -v $(pwd):/app -v /app/node_modules  -p 3000:80 --name feedback-app feedback-node:volumes`

This works because for volumes, the lonnger and more specific path wins.
