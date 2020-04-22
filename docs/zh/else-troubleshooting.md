# 故障处理

此处收集使用 Node.js 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### 如何查看错误日志？

日志文件路径为：`/data/logs`。检索关键词 **Failed** 或者 **error** 查看错误

#### How to NPM Prevent Permissions Errors
If you see an `EACCES` error when you try to install a package globally, read [this chapter](https://www.npmjs.com.cn/getting-started/fixing-npm-permissions/)

#### If npm is broken
Using Linux, please re-install npm：
```shell
curl -L https://www.npmjs.org/install.sh | sh
```

Using Windows, please download and re-install it。(remember [this note](https://www.npmjs.com.cn/troubleshooting/try-the-latest-stable-version-of-npm#upgrading-on-windows)).

#### Try clearing the npm cache
Sometimes npm's cache gets confused. You can reset it using:
```shell
npm cache clean
```
