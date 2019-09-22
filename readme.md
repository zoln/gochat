# gochat 是一个im系统 

# architecture design 


# go run
```
go run -tags=etcd main.go -module logic
go run -tags=etcd main.go -module connect
go run -tags=etcd main.go -module task
```


```markdown
connect层
    bucket (bucket,减少锁竞争)
        room (房间)
            channel (会话)
    setOnline--->redis

task层
    getMsg--->redis
    sendMsg--->rpc call connect

ui层
    chat:
        用户注册  logic
            用户名,密码   sqllite
        用户登录  logic   sqllite
            login,return sessionId
```



