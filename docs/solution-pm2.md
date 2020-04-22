# Using PM2

[PM2](https://github.com/Unitech/pm2) is a production process manager for Node.js applications with a built-in load balancer. It allows you to keep applications alive forever, to reload them without downtime and to facilitate common system admin tasks.PM2 is constantly assailed by [more than 1800 tests](https://travis-ci.org/Unitech/pm2).

## Install & Upgrade
```shell
# Install latest PM2 version
$ npm install pm2@latest -g

# Save process list, exit old PM2 & restore all processes
$ pm2 update
```
## Start An Application
You can start any application (Node.js, Python, Ruby, binaries in $PATH...) like that:
```shell
pm2 start app.js
```
Your app is now daemonized, monitored and kept alive forever. [More about Process Management]()

## Managing Applications

Once applications are started you can manage them easily:

![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/nodejs/pm2-list.png)

To list all running applications:
```shell
pm2 list
```

Managing apps is straightforward:
```shell
pm2 stop     <app_name|id|'all'|json_conf>
pm2 restart  <app_name|id|'all'|json_conf>
pm2 delete   <app_name|id|'all'|json_conf>
```

To have more details on a specific application:
```shell
pm2 describe <id|app_name>
```

To monitor logs, custom metrics, application information:
```shell
pm2 monit
```

## Log Management

To consult logs just type the command:
```shell
pm2 logs
```

Standard, Raw, JSON and formated output are available. Examples:
```shell
pm2 logs APP-NAME       # Display APP-NAME logs
pm2 logs --json         # JSON output
pm2 logs --format       # Formated output
pm2 flush               # Flush all logs
pm2 reloadLogs          # Reload all logs
```

## PM2 Modules

PM2 embeds a simple and powerful module system. Installing a module is straightforward:
```shell
pm2 install <module_name>
```

Here are some PM2 compatible modules (standalone Node.js applications managed by PM2):

- [**pm2-logrotate**](https://www.npmjs.com/package/pm2-logrotate) automatically rotate logs and limit logs size
- [**pm2-server-monit**](https://www.npmjs.com/package/pm2-server-monit) monitor the current server with more than 20+ metrics and 8 actions