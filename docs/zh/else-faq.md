# FAQ

#### 默认字符集是什么？
UTF-8

#### What's different between YARN and NPM?

[Yarn](https://yarnpkg.com/en/) 是在NPM之后推出的一个包管理解决方案

| npm | yarn |
| ---: | :--- |
| npm install | yarn |
| npm install react --save | yarn add react |
| npm uninstall react --save | yarn remove react |
| npm install react --save-dev | yarn add react --dev |
| npm update --save | yarn upgrade |

#### Nginx 虚拟主机配置文件是什么？

虚拟主机配置文件是 Nginx 用于管理多个网站的**配置段集合**，路径为：*/etc/nginx/conf.d/default.conf*。  
每个配置段的形式为： `server{ }`，有多少个网站就有多少个配置段

#### 如何修改示例网站根目录？

待续...

#### Node.js 环境是否支持部署多个网站？

支持。每增加一个网站，只需在[Nginx 虚拟主机配置文件](/zh/stack-components.md#nginx)中增加对应的 **server{ }** 即可。

#### 如果没有域名是否可以部署 Node.js 应用？

可以，访问`http://服务器公网IP:端口号` 即可

#### 数据库 root 用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### 是否有可视化的数据库管理工具？

有，内置phpMyAdmin 和 adminMongo

#### 如何删除9Panel?

删除 */data/apps/9panel* 下的所有数据即可，但需要保留文件夹

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R nginx.nginx /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```
#### 如果设置 HTTP 跳转到 HTTPS？

只需在网站对应的 server{} 配置段中增加规则即可：
```
 if ($scheme != "https") 
    {
    return 301 https://$host$request_uri;
    }
```

#### 如何启用或禁用 Nginx 模块？

不支持模块启用或关闭

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器