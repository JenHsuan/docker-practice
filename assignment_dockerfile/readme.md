### Requirement

* wrap a node.js docker file

### Execute app with docker

```

docker build -t assignment1 .
docker run -p 80:3000 assignment1
docker run -d --init -p 8080:3000 assignment1

```

### Execute app with docker-compose

```

docker-compose up

```
