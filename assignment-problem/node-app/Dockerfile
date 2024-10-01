FROM node

WORKDIR /app

COPY package.json /app

RUN npm config set registry=https://registry.npmmirror.com

RUN npm install

COPY . /app

EXPOSE 3000

CMD ["node", "server.js"]