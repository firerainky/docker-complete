FROM node

WORKDIR /app

COPY . /app

RUN npm config set registry=https://registry.npmmirror.com

RUN npm install

EXPOSE 80

CMD ["node", "server.js"] 

