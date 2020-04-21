# Initial Installation

If you have completed the Node.js deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:8161 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for Node.js

## Node.js Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://DNS:15672* or *http://Internet IP:15672*, you will enter installation wizard of Node.js
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rabbitmq/rabbitmq-login-websoft9.png)

2. Log in to Node.js web console([Don't have password?](/stack-accounts.md#rabbitmq))  
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rabbitmq/rabbitmq-bk-websoft9.png)

3. Set you new password from: 【Users】>【Admin】>【Permissions】>【Update this user】
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rabbitmq/rabbitmq-pw-websoft9.png)

> More useful Node.js guide, please refer to [Node.js Documentation](https://www.rabbitmq.com/documentation.html)

## Q&A

#### I can't visit the start page of Node.js?

Your TCP:15672 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Node.js service can't start? 