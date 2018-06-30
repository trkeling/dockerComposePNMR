# 组合php+nginx+mysql+redis
- docker-compose 一键安装
- mysql和nginx连接php都是用的*.sock文件连接

## 项目目录
```
|
|-data
|	-etc
|		-nginx (nginx配置文件)
|	-usr
|		-local (php配置文件)
|	-var
|		-log (nginx日志)
|		-mysql (mysql存储目录)
|	-www (项目根目录)
|-php (phpDocker配置)
|	-Dockerfile (配置文件)
|-docker-compose-.yml 
```

## 安装步骤
```
1.docker-compose build
2.docker-compose up -d (这一步会启动docker)
```

## 注意事项
```
查看所有启动的容器的ip，项目里面redis的ip看这里(这里应该是用映射到本地的端口就可以了，但是目前还用不了。用客户端工具连是可以的，但是Laravel连接就报错。所用需要查看ip,不用本地映射端口)
docker inspect --format='{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $(docker ps -aq)

```
