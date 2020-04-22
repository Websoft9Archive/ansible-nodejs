# Troubleshooting

We collect the most common troubleshooting of using Node.js for your reference:

#### How can I use the logs?

You can find the keywords **Failed** or **error** from the logs directory: `/data/logs`

#### Nginx service restart error
Please make sure the `default.conf` is correct for you, and you can track and analyze log files from _/var/log/nginx_

#### How to NPM Prevent Permissions Errors
If you see an `EACCES` error when you try to install a package globally, read [this chapter](https://www.npmjs.com.cn/getting-started/fixing-npm-permissions/)

#### If npm is broken
please re-install npm  

```shell
curl -L https://www.npmjs.org/install.sh | sh
```

#### Try clearing the npm cache
Sometimes npm's cache gets confused. You can reset it using:
```shell
npm cache clean
```