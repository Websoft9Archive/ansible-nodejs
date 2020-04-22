---
sidebarDepth: 3
---

# 参数

Node.js 预装包包含 Node.js 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

接下来我们对路径信息进行准确的说明

### Node.js

除Node.js之外，本部署方案还包括：NPM,Yarn,PM2,Express等组件  

Node.JS 模块目录: */usr/lib/node_modules*  
Node.js 应用安装目录: */data/wwwroot*  
Express 示例目录: */data/wwwroot/express.example.com*  
Node.JS 日志文件: */root/.pm2/pm2.log*  

### Nginx

Nginx 虚拟主机配置文件：*/etc/nginx/conf.d/default.conf*  
Nginx 主配置文件： */etc/nginx/nginx.conf*  
Nginx 日志文件： */var/log/nginx*  
Nginx 伪静态规则目录： */etc/nginx/conf.d/rewrite*

**default.conf** 默认存在一个 [server（虚拟主机）](https://support.websoft9.com/docs/linux/zh/webs-nginx.html#虚拟主机) 配置项，对应的就是 **示例网站**
```
server {
    listen 80;
    server_name _;
    location / {
        proxy_pass  http://127.0.0.1:3000;
        proxy_redirect     off;
        proxy_set_header   Host             $host;
        proxy_set_header   X-Real-IP        $remote_addr;
        proxy_set_header   X-Forwarded-For  $proxy_add_x_forwarded_for;
        proxy_next_upstream error timeout invalid_header http_500 http_502 http_503 http_504;
        proxy_max_temp_file_size 0;
        proxy_connect_timeout      90;
        proxy_send_timeout         90;
        proxy_read_timeout         90;
        proxy_buffer_size          4k;
        proxy_buffers              4 32k;
        proxy_busy_buffers_size    64k;
        proxy_temp_file_write_size 64k;
   }
   include extra/*.conf;
}
```

> 有多少个网站，就需要在 default.conf 中增加同等数量的 server 配置项

### MongoDB

MongoDB 配置文件: */etc/mongod.conf*  
MongoDB 数据目录: */data/mongo*  
MongoDB 日志文件: */var/log/mongodb/mongod.log*

### MySQL

MySQL 安装目录: *usr/local/mysql*  
MySQL 配置文件: *etc/my.cnf*   
MySQL 数据目录：*/data/mysql*   
MySQL 日志文件: */var/log/mysql/mysqld.log*   
MySQL PIN: */run/mysqld/mysqld.pid*   
MySQL Socket: */var/lib/mysql/mysql.sock*

### Docker

本部署环境默认已安装Docker，Docker主要用于部署下面两个数据库可视化管理工具：

* phpMyAdmin on Docker，通过：*http://服务器公网IP:9090* 端口访问
* adminMongo on Docker，通过：*http://服务器公网IP:9091* 端口访问

## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

通过命令`netstat -tunlp`查看相关端口，下面列出本应用可能要用到的端口：

| 类型 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| TCP | 80/443 | Nginx, 通过 HTTP 访问 Express 框架 | 可选 |
| TCP | 9090 | 通过 HTTP 访问 phpMyAdmin | 可选 |
| TCP | 9091 | 通过 HTTP 访问 adminMongo | 可选 |
| TCP | 27017 |MongoDB 端口 | 可选 |
| TCP | 6379 | Redis 端口 | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

```shell
# Linux Version
lsb_release -a

# Node.js  Version
node -v

# PM2  Version
pm2 -V

# NPM version
npm -v

# yarn version
yarn --version

# MongoDB version
mongo --version

# Nginx version
nginx -v

# List Installed Nginx Modules
nginx -V

# MySQL version
mysql -V

# Redis version
redis-server -v

# Docker version
docker -v
```