# 服务启停

使用由Websoft9提供的 Node.js 部署方案，可能需要用到的服务如下：

## Node.js

```shell
sudo systemctl start rabbitmq-server
sudo systemctl stop rabbitmq-server
sudo systemctl restart rabbitmq-server
sudo systemctl status rabbitmq-server

# you can use this debug mode if Node.js service can't run
rabbitmq-server console
```