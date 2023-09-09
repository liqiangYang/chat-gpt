docker registry liqiangyang/chatgpt

# docker 安装
```shell
yum -y install docker
systemctl enable docker.service
systemctl start docker.service
docker login
```

# v2ray
```shell
docker run -d --name v2ray -v /data/app/conf/v2ray.json:/etc/v2ray/config.json -p 31560:31560 v2fly/v2fly-core run -c /etc/v2ray/config.json 
```

```shell
docker build --platform linux/amd64 -t chatgpt:0609-amd64 .
```

```shell
docker tag chatgpt:0609-amd64 liqiangyang/chatgpt:0609-amd64
docker push liqiangyang/chatgpt:0609-amd64
```

run
```shell
docker run -d --name chatgpt --restart on-failure --network=host -e PANDORA_TOKENS_FILE=/data/app/conf/gpt.json -e PANDORA_SERVER=0.0.0.0:8888 -v /data/app/conf/gpt.json:/data/app/conf/gpt.json liqiangyang/chatgpt:0615
```

update restart
```shell
docker update --restart on-failure chatgpt
```


access token
```json
{
    "user": {
        "id": "user-1G02Rt1WRZ9P33Hyoz6Gbb2p",
        "name": "杨立强",
        "email": "nishuihan.yang@gmail.com",
        "image": "https://lh3.googleusercontent.com/a/AAcHTtcc69BnhI1Gq-Ay8bO1OEQgYjl4HC5qztUJ1wtBhKUs=s96-c",
        "picture": "https://lh3.googleusercontent.com/a/AAcHTtcc69BnhI1Gq-Ay8bO1OEQgYjl4HC5qztUJ1wtBhKUs=s96-c",
        "idp": "google-oauth2",
        "iat": 1688020541,
        "mfa": false,
        "groups": [],
        "intercom_hash": "a51145f08c0915968707d037f3a903665166e2980ef8a4c52d2e66cc5ed7c214"
    },
    "expires": "2023-07-29T06:39:31.847Z",
    "accessToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6Ik1UaEVOVUpHTkVNMVFURTRNMEZCTWpkQ05UZzVNRFUxUlRVd1FVSkRNRU13UmtGRVFrRXpSZyJ9.eyJodHRwczovL2FwaS5vcGVuYWkuY29tL3Byb2ZpbGUiOnsiZW1haWwiOiJuaXNodWloYW4ueWFuZ0BnbWFpbC5jb20iLCJlbWFpbF92ZXJpZmllZCI6dHJ1ZX0sImh0dHBzOi8vYXBpLm9wZW5haS5jb20vYXV0aCI6eyJ1c2VyX2lkIjoidXNlci0xRzAyUnQxV1JaOVAzM0h5b3o2R2JiMnAifSwiaXNzIjoiaHR0cHM6Ly9hdXRoMC5vcGVuYWkuY29tLyIsInN1YiI6Imdvb2dsZS1vYXV0aDJ8MTExMTQwMDgzMDQ0MDA0NjA3ODYyIiwiYXVkIjpbImh0dHBzOi8vYXBpLm9wZW5haS5jb20vdjEiLCJodHRwczovL29wZW5haS5vcGVuYWkuYXV0aDBhcHAuY29tL3VzZXJpbmZvIl0sImlhdCI6MTY4ODAyMDU0MSwiZXhwIjoxNjg5MjMwMTQxLCJhenAiOiJUZEpJY2JlMTZXb1RIdE45NW55eXdoNUU0eU9vNkl0RyIsInNjb3BlIjoib3BlbmlkIHByb2ZpbGUgZW1haWwgbW9kZWwucmVhZCBtb2RlbC5yZXF1ZXN0IG9yZ2FuaXphdGlvbi5yZWFkIG9yZ2FuaXphdGlvbi53cml0ZSJ9.BlinvPD23Bl9CFH11-DEUzEJkwoTO3CwNO2t9qaHmDrxpPioZ0D3jYmH6INDWzwwc3wfI0aMICwAncdAzYWF8IBww1RP7Q0p3808fD7Etrj72U0z4bJlqaUZ0trButLXpwoXYiR1Luav2wJ92Nk35A-Cpx8ynNG5Rt9S01FwdllOgPtecdUBo5K5iUGIAnGubo5BLb7CtdtCZ1SRXovolh-wlMaOfTbvcEKQx2oAsoXSlryYsH_Rso6eIC-P6bWSGpiAjsU4wK5cl_QzAZ6luG6p7x8WI4qu9e6cQ_gherip1nWrzic90880xbMbZEqOJ4IJbtIia5FMaa0V0_OIcQ",
    "authProvider": "auth0"
}
```
```shell
curl https://chat.openai.com/api/auth/session
# vi /data/app/www/chatgpt/access_token.json
```