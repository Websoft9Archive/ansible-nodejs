# Deploy Your Node.JS Application

Please follow the steps below before deploying the application to remove the sample program.

## Pre-condition

1. Delete the process of pm2 sample program
   ```
   pm2 delete 0
   ```   
2. Save the modification
   ```
   pm2 save
   ```
3. Delete the folder of program
   ```
   rm -rf /data/wwwroot/project
   ```

## Deployment

Following are the steps for adding your Node.js Applicaton:

1. Upload your Node.js application to the directory: */data/wwwroot* e.g. assume folder name is **myapps**
2. Using putty to log in Linux,then go the myapps directory and install the node.js application dependency package
    ```
    cd /data/wwwroot/myapps
    npm install
    ```
3. Modify the database configuration file if necessary

4. Come back to the myapps directory and start up the index.js or app.js.Using the `pm2 list` command to show the state of application,if the application is “online” means is runing OK
    ```
    cd /data/wwwroot/myapps
    pm2 start index.js 
    pm2 list
    ```

5. Then you shoul save the process of application and make it boot automatically start
    ```
    pm2 save 
    sudo pm2 startup 
    pm2 save
    ```

6. Add a new reverse proxy conf file of Ngnix.(Like the /etc/nginx/sites-available/default below).Please make sure using the correct port(The default port is 3000)
    ```
    server {
            listen 80 default_server;
            server_name _;
            location / {
            proxy_pass http://127.0.0.1:3000;
            proxy_set_header Host $host;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            }
    }
    ```

7. Restart Nginx
   ```
    systemctl restart nginx.service
   ```


