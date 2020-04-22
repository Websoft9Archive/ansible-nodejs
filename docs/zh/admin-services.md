# 服务启停

使用由Websoft9提供的 Node.js 部署方案，可能需要用到的服务如下：

## PM2

```shell
systemctl start pm2-root
systemctl stop pm2-root
systemctl restart pm2-root
systemctl status pm2-root
```

## Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```

## MongoDB

```shell
systemctl start mongod
systemctl stop mongod
systemctl restart mongod
systemctl status mongod
```

## MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

## Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```

## Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```