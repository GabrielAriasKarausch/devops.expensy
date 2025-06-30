FROM node:18-alpine

WORKDIR /app

RUN apk add --no-cache bash

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8706

CMD ["npx", "ts-node-dev", "--respawn", "--transpile-only", "src/server.ts"]
