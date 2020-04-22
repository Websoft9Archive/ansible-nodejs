# Node.js 应用示例（集）

## Ghost

### 关于Ghost

Ghost(ghost.org)是由WordPress前员工创建，系统基于Node.JS开发的开源内容管理系统（CMS），界面简洁、现代、美观，代码优雅。继承了WordPress的一些特征，如短代码、固定链接、在线主题修改等，去掉了WordPress复杂的部分，显得更为简洁，官方的Marketplace可以提供大量免费或付费的精美主题。

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/ghost/ghostui.jpg)

### 获取Ghost镜像
镜像需要与服务器配套使用，获取Websoft9的镜像有两种方式： 
* 方式一：若没有可用的云服务器，登录主流云厂商的云市场，找到由Websoft9提供的“Ghost博客系统”相关免费镜像，点击“购买”（同时会配套购买云服务器，若只打算试用请选择“**按量**”方式购买，实现按小时使用，接近免费） 
* 方式二：若有可用的云服务器，登录到云厂商的控制面板，找到可用的云服务器，通过关机-&gt;更换系统盘（重装镜像）,在更换过程中选取云市场镜像，获取本镜像

### 验证Ghost

待镜像购买或更换完成后，镜像会自动安装到配套的云服务器上，当云服务实例处于“运行中”后，通过浏览器访问网址 http://服务器公网IP/， 正常会出现Ghost前台界面： ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/ghost/ghost-bootpage-websoft9.png)

如果浏览器访问以上网址没有任何反应，请检查您的安全组设置，确保80端口是开放的。

### Ghost官方支持资源

* 文档：[https://docs.ghost.org/docs](https://docs.ghost.org/docs)
* FAQ：[https://ghost.org/pricing/#faq](https://ghost.org/pricing/#faq)