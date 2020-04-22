# Parameters

The Node.js deployment package contains a sequence software (referred to as "components") required for Node.js to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

Wave prepared more path details for your reference

### Node.js

Node.JS Global Modules Directory: */usr/lib/node_modules*  
Node.js applicaton root directory: */data/wwwroot*  
Express demo program: */data/wwwroot/express.example.com*  
Node.JS Log file: */root/.pm2/pm2.log*  

### Nginx

Nginx vhost configuration file: */etc/nginx/conf.d/default.conf*    
Nginx main configuration file: */etc/nginx/nginx.conf*   
Nginx logs file: */var/log/nginx*  
Nginx rewrite rules directory: */etc/nginx/conf.d/rewrite*    

**default.conf** includes one [server{}](https://support.websoft9.com/docs/linux/webs-nginx.html#vhost) configuration items whitch matched the **Example application**
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

> How many websites you need, you should add the same number of **server{ }** to **default.conf**

### MongoDB

MongoDB configuration file:  */etc/mongod.conf*  
MongoDB data directory: */data/mongo*  
MongoDB log file: */var/log/mongodb/mongod.log*  
MongoDB bin directory: */usr/bin*

### MySQL

MySQL installation directory: */usr/local/mysql*  
MySQL data directory: */data/mysql*  
MySQL configuration file: */etc/my.cnf*    
MySQL Web Management URL: *http://Internet IP:9090*

### Docker

This deployment solution installed Docker for run the following Web-GUI tools for database: 

* adminMongo on Docker for MongoDB, you can visit it by: *http://Internet IP:9090*
* phpMyAdmin on Docker for MySQL, you can visit it by: *http://Internet IP:9090*

### Redis

Redis configuration file: */etc/redis.conf*  
Redis data directory: */var/lib/redis*  
Redis logs file: */var/log/redis/redis.log*

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

You can run the cmd `netstat -tunlp` to list all used ports, and we list the following most useful ports for you:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 80/443 | Nginx for HTTP/HTTP  | Optional |
| TCP | 9090 | HTTP visit phpMyAdmin | Optional |
| TCP | 9091 | HTTP visit adminMongo | Optional |
| TCP | 27017 | MongoDB | Optional |
| TCP | 6379 | Redis | Optional |
| TCP | 3306 | MySQL | Optional |


## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

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