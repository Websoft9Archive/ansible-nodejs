#### 包含组件

1. Node.js
2. Nginx
3. mysql
4. mongodb
5. redis

#### 参数说明

+ mongodb_ver: 3.0    #mongodb版本(可选3.0/3.2/3.4/3.6/4.0)
+ mysqlver: 56        # mysql版本(可选55/56/57)
+ mysql_password: 123456 # mysql 默认密码
+ remote: no  # 是否开启mysql远程
+ nodejs_ver: 11  # Node.js版本(可选6/8/10/11)



注意事项:文档第4步骤中新增步骤: pm2 startup 