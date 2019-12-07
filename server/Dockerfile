FROM node:12.12.0-alpine

WORKDIR /usr/local/issues-server
COPY dist/ /usr/local/issues-server
COPY src/environment/development.env /usr/local/issues-server/.env
COPY db/ /usr/local/issues-server/db
COPY package.json /usr/local/issues-server
COPY package-lock.json /usr/local/issues-server

RUN npm install

EXPOSE 8000

CMD [ "npm", "run", "start:docker" ]
