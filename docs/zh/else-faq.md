# FAQ

#### 如何以调试模式启动Node.js服务？

```
systemctl stop rabbitmq-server
rabbitmq-server console
```

#### 是否可以通过命令行修改Node.js后台密码？

可以，`rabbitmqctl change_password  admin newpassword`

#### 如果没有域名是否可以部署 Node.js？

可以，访问`http://服务器公网IP` 即可

#### 是否可以修改Node.js的源码路径？

不可以

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器