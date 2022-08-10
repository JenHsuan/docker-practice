FROM node:10-slim as prod
ENV NODE_ENV=production
EXPOSE 3000
WORKDIR /app
COPY package.json ./
RUN npm install --only=production && npm cache clean --force
COPY . .
CMD ["node", "./bin/www"]

FROM prod as dev
ENV NODE_ENV=development
EXPOSE 3000
RUN npm install --only=development
#Use Nodemon for development environment
CMD ["node_modules/nodemon/bin/nodemon.js",  "./bin/www", "--inspect=0.0.0.0:9229"]

FROM dev as test
ENV NODE_ENV=development
EXPOSE 3000
CMD ["npm", "test"]
