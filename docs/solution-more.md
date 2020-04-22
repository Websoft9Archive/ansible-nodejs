# More

Each of the following solutions has been proven to be effective and we hope to be helpful to you.

## Domain binding

The precondition for binding a domain is that LEMP can accessed by domain name.

Nonetheless, from the perspective of server security and subsequent maintenance considerations, the **Domain Binding** step cannot be omitted.

LEMP domain name binding steps:

1. Connect your Cloud Server
2. Modify [Nginx vhost configuration file](/stack-components.md#nginx), change the **server_name**'s value to your domain name
   ```text
   server
   {
   listen 80;
   server_name www.example.com;  # 此处修改为你的域名
   index index.html index.htm index.php;
   root  /data/wwwroot/www.example.com;
   ...
   }
   ```
3. Save it and restart [Nginx Service](/admin-services.md#nginx)


## Use Rewrite

Rewrite was enabled by default on Node.js runtime, three steps to use rewrite for your application:

1.  Add a new rewirte rules configuration file(e.g. wordpress.conf) to the directory:  */etc/nginx/conf.d/rewrite* on your Server
2.  Edit the **server{ }** segment of your [Nginx vhost configuration file](/stack-components.md#nginx), include your rewirte rules configuration file
   ```text
   server
   {
   listen 80;
   server_name yourdomain.com;  # modify it to your domain
   ...
   }
   ```
3. Save it, then [Restart Nginx service](/admin-services.md#nginx)

## Rest MySQL *root* password

1. Connect to your Cloud Server by SSH
2. Run the below command
   ```
   sudo git clone https://github.com/Websoft9/linux.git; cd linux/Mysql_ResetPasswd_Script;sudo sh reset_mysql_password.sh
   ```