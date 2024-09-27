FROM node

WORKDIR /usr/src/app

RUN npm install

COPY package*.json .

RUN npm ci

COPY . .

EXPOSE 80

CMD ["node", "server.js"]