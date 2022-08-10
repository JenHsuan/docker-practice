ARG: build phase
* Dockerfile

```

ARG NODE_VERSION
RUN curl -sL https://rpm.nodesource.com/setup_${NODE_VERSION} | bash # for node version 10.x

```

* build command

```

docker build --build-arg NODE_VERSION="10.x" .

```

ENV: running phase
