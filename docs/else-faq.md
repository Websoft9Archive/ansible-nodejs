# FAQ

#### What is the default character set?
UTF-8

#### What is the Nginx vhost configuration file?
The Nginx vhost configuration file is the function for Nginx to manage multiple applications. It's path is: */etc/nginx/conf.d/default.conf*.
There have `server{ }` , each segment is corresponding to a application

#### What's different between YARN and NPM?

NPM and Yarn are two well-known JavaScript package managers.[Yarn](https://yarnpkg.com/en/) was developed by Facebook in attempt to resolve some of npm's shortcomings. Yarn isn't technically a replacement for npm since it relies on modules from the npm registry.

| npm | yarn |
| ---: | :--- |
| npm install | yarn |
| npm install react --save | yarn add react |
| npm uninstall react --save | yarn remove react |
| npm install react --save-dev | yarn add react --dev |
| npm update --save | yarn upgrade |

#### What's different Local install and Global install?
For local install, the module will be installed in the project folder, E.g. */data/wwwroot/project*  
For local install, the module will be installed in the node global modules folder: */usr/lib/node_modules*  
That means local install modules just can be required for your one project, and global install can be required for all projects.

#### Can I upgrade Node.JS and NPM version?
Yes,refer to the chapter [Upgrade](/solution-upgrade) of this documentation 

#### How to modify the path of example application?

coming soon..

#### Does the Node.js runtime support deploying multiple applications?

Yes

#### If there is no domain name, can I deploy LEMP?

Yes, visit Node.js application by *http://Internet IP:port*

#### What is the password for the database root user?

The password is stored in the server related file: `/credentials/password.txt`

#### Is there a web-base GUI database management tools?

Yes

#### How to delete 9Panel?

Please delete all files in 9Panel */data/apps/9panel* and keep an empty 9Panel folder

#### How to bind a domain name for your application?
Modify the **server_name** configuration item of VirtualHost template in the file `default.conf`

#### How to change the permissions of filesytem?

Change owner(group) or permissions like below:

```shell
chown -R nginx.nginx /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### How to set HTTP redirect to HTTPS automatically?

Insert these Rewrite rules in the file *server{ }* segment of [Nginx vhost configuration file](/stack-components.md#nginx)
```
 if ($scheme != "https") 
    {
    return 301 https://$host$request_uri;
    }
```
#### Which Nginx modules are installed by default by LEMP?

Use command `nginx -V` to list all modules

#### How to enable or disable Nginx module?

No

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers