FROM centos:7

#ENV NODE_VERSION "$NODE_VERSION"
ARG NODE_VERSION

EXPOSE 3000

WORKDIR /usr/src/app

RUN yum update -y

RUN yum install curl -y

RUN curl -sL https://rpm.nodesource.com/setup_${NODE_VERSION} | bash # for node version 10.x

RUN yum -y install nodejs

COPY package.json package-lock.json* ./

RUN npm install && npm cache clean --force

COPY . .

CMD [ "node", "./bin/www" ]
