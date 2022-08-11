# ARG vs ENV
* ARG: build phase
* ENV: running phase (container)

# Pass ARG to Dockfile
* Dockerfile

```

ARG NODE_VERSION
RUN curl -sL https://rpm.nodesource.com/setup_${NODE_VERSION} | bash # for node version 10.x

```

* build command

```

docker build --build-arg NODE_VERSION="10.x" .

```

# Pass environment variables inside the Docker container
## 1. Pass env file in docker-compose.yml

* .env

```

NODE_VERSION=10.x

```

* docker-compose.yml

```

web:
    env_file: .env

```

* docker container (node.js)

```

console.log(process.env.NODE_VERSION)


```

* command

```

docker-compose up --build

```

## 2. envsubst

## References


* [活用 ENV 與 ARG](https://ithelp.ithome.com.tw/articles/10251549)
* [How to use environment variables in docker-compose?](https://stackoverflow.com/questions/29377853/how-to-use-environment-variables-in-docker-compose)
* [利用 Linux 指令 envsubst 產生設定檔](https://myapollo.com.tw/zh-tw/linux-command-envsubst/)
* [使用 envsubst 替換整份環境變數](https://medium.com/@SiegeSailor/%E4%BD%BF%E7%94%A8-envsubst-%E6%9B%BF%E6%8F%9B%E7%92%B0%E5%A2%83%E8%AE%8A%E6%95%B8-8c2826996fd5)
