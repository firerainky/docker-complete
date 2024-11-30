# Docker command for multi container module

Dockerfile for backend:

```bash
FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["npm", "start"]
```

Dockerfile for frontend:

```bash
FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["npm", "start"]
```

```bash
# My pre-course try
docker build -t backend-node .
docker build -t frontend-react .

docker network create todo-net

docker run -d --name mongodb -v $(pwd)/data:/data/db -e MONGO_INITDB_ROOT_PASSWORD_FILE=.env mongo
docker run -d --rm --name backend --network todo-net -v $(pwd):/app:ro -v /app/node_modules backend-node
docker run -d --rm --name front --network todo-net -v $(pwd):/app:ro -v /app/node_modules frontend-node
```
