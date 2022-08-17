# FROM ubuntu:18.04 as prod
# RUN apt-get update
# RUN apt-get install -y graphicsmagick
# RUN apt-get -y install nodejs
# RUN apt-get -y install npm
# WORKDIR /usr/src/app
# COPY package.json package-lock.json* ./
# RUN npm install && npm cache clean --force
# COPY . .
# CMD [ "node", "index.js" ]

FROM node:8

RUN apt-get update -y && apt-get install -y graphicsmagick

WORKDIR /app

COPY package.json ./

RUN npm install --only=production && npm cache clean --force

COPY . .

ENV CHARCOAL_FACTOR=0.1

CMD ["node", "index.js"]
