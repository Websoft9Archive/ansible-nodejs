# Initial Installation

If you have completed the Node.js deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:80 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for Node.js

## Node.js Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://Internet IP/9panel* to enter the boot page
   ![9panel](https://libs.websoft9.com/Websoft9/DocsPicture/en/9panel/9panelmain-websoft9.png)

2. You can get the basics of image, manage the database, access docs, and helpdesk from 9Panel

## Log in Database

Node.js runtime includes MongoDB and MySQL and their Web-GUI tools

* [Manage MySQL](/admin-mysql.md) 
* [Manage MongoDB](/admin-mongodb.md)

## Q&A

#### I can't visit the start page of Node.js?

Your TCP:80 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### What's 9Panel?

[9Panel](https://github.com/Websoft9/9panel) is an opensource component included in some image of Websoft9, it is powered by Websoft9. 9Panel is a set of HTML pages for quickly using image of Websoft9. You should delete all the files in 9Panel folder if you do not want to delete 9Panel