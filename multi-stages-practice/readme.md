```

docker build -t multistage --target prod . && docker run --init -p 3000:3000 multistage
docker build -t multistage:dev --target dev . && docker run --init -p 3000:3000 multistage:dev

```
