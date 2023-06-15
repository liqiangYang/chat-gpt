docker registry liqiangyang/chatgpt

```shell
docker build --platform linux/amd64 -t chatgpt:0609-amd64 .
```

```shell
docker tag chatgpt:0609-amd64 liqiangyang/chatgpt:0609-amd64
docker push liqiangyang/chatgpt:0609-amd64
```

run
```shell
docker run -d --name chatgpt --restart on-failure --network=host -e PANDORA_TOKENS_FILE=/data/app/www/chatgpt/access_token.json -e PANDORA_SERVER=0.0.0.0:8888 -v /data/app/www/chatgpt/access_token.json:/data/app/www/chatgpt/access_token.json liqiangyang/chatgpt:0615
```

update restart
```shell
docker update --restart on-failure chatgpt
```