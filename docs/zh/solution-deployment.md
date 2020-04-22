# 安装网站

在 Node.js 环境上安装一个网站（应用），也就是我们常说的增加一个虚拟主机。

全局上看，只需三个步骤：**上传网站代码** + **运行NPM命令** + [**虚拟机主机配置文件**](/zh/stack-components.md#nginx) **中增加 server{} 配置段**

> server{} 又称之为虚拟主机配置段，每个网站必定在 default.conf 中对应唯一的 server{}。

## 准备

安装网站之前，请了解如下几个要点，做好准备工作

*  虚拟机主机配置文件：*/etc/nginx/conf.d/default.conf* 
*  连接工具：使用 WinSCP 连接服务器，它包含文件管理、运行命令两方面功能
*  域名：若需要使用域名，请确保备案后的域名成功解析到服务器IP
*  数据库：网站安装向导过程中可能需要使用 [MongoDB](/zh/admin-mongodb.md) 和 [MySQL](/zh/admin-mysql.md) 数据库

有一个全局认知并完成准备工作之后，我们开始部署网站

## 删除示例

本部署方案默认已经安装并启动了[Express框架](https://www.expressjs.com.cn/)，我们先删除它：

1. 运行 `npm list` 查询正在运行的Node.js程序
   ```
   ┌────┬────────────────────┬──────────┬──────┬───────────┬──────────┬──────────┐
   │ id │ name               │ mode     │ ↺    │ status    │ cpu      │ memory   │
   ├────┼────────────────────┼──────────┼──────┼───────────┼──────────┼──────────┤
   │ 0  │ www                │ fork     │ 0    │ online    │ 0.1%     │ 48.7mb   │
   ```
2. 运行 `pm2 delete 0` 删除程序
3. 运行 `pm2 save`
4. 删除项目文件夹 `rm -rf /data/wwwroot/express.example.com`
5. 删除初始化
   ```
   //delete the PM2 init script
   pm2 unstartup systemd

   //delete the have been saved PM2 file of process
   rm -rf /root/.pm2
   ```


## 安装Express

下面我们还原Express的安装过程：

1. 创建目录
   ```
   mkdir myapp
   cd myapp
   ```
2. 创建Express应用骨架
   ···
   npx express-generator
   ···
3. 安装依赖包
   ```
   npm install
   ```
4. 启动应用程序，通过：*http://服务器公网IP:3000* 访问应用
   ```
   DEBUG=myapp:* npm start
   ```

> 你也可以使用pm2管理应用程序


## 常见问题

#### 访问刚安装的网站，页面显示 “没有权限...” ？

运行一条修改文件权限的命令
~~~
chown -R nginx.nginx /data/wwwroot
~~~

#### 修改 default.conf 文件之后，Nginx 服务无法启动？

一般是 server{ } 中虚拟主机的目录位置不正确导致

#### 新增网站不可访问，且导致其他网站都不可访问？

一般是 server{ } 中虚拟主机的目录位置不正确导致 Nginx 无法启动

#### 打开新增的网站，显示404错误？

一般是网站目录下没有 index.php 或 index.html 等默认首页导致

#### 新增的网站，显示 500 Internal Server Error？

程序代码错误，需要查看程序的日志文件