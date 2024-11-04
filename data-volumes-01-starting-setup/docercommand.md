# Docker command under volumes chapter

## Build the image

`docker build -t feedback-node:volumes .`

## Run a container on the base of the image

`docker run --rm -d -v feedback:/app/feedback -p 3000:80 --name feedback-app feedback-node:volumes`

## Stop the container

`docker stop feedback-app`

## Show all retained volumes

`docker volume ls`
