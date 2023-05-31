# WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
A LAMP stack is a group of open source software that is typically installed together in order to enable a server to host dynamic websites and web apps written in PHP. It consists of four components: Linux, Apache, MySQL, and PHP.
This project will try to implement .......

Steps to completion
1.	AWS Configuration
2.	Connecting to EC2 terminal
3.	Update package (Update && upgrade)
4.	Apache Installation
5.	Installing MySql
6.	Installing PhP
7.	Creating Virtual  Host for website using Apache
8.	Enabling PHP on website 

### 1. AWS Configuration / 	Connecting to EC2 terminal
We need a server and for the fact that most things are done in the cloud, we will ue a very effiv=ceint and cost effect cloud server on Amazon Web services(AWS). We will first 
- Create an Amazon AWS account
- Create and EC2 instance using ubuntu server(Linux)
![Screenshot (208)](https://github.com/ettebaDwop/project-1/assets/7973831/f85163db-be53-4be6-bb06-3e0683fff1be)

### 2. Update Ubuntu package
On connecting to the server, we would run the following commands:

 `sudo apt update`
 
 `sudo apt upgrade`

### 3. Apache Installation
To install Apache 2 run the commands:

   `sudo apt install apache2`

   `sudo systemctl status apache2`

![Screenshot (188)](https://github.com/ettebaDwop/project-1/assets/7973831/c646288d-8091-4816-87ee-97eb89f72309)

To access the apache2 page, type in the url into a web browser

   `http://13.40.229.97/:80`

![Screenshot (190)](https://github.com/ettebaDwop/project-1/assets/7973831/482681de-7f2c-481f-9fda-0306be04e6bc)


![ apache status](./image/apache-status.png)

[Linux Commands](https://www.hostinger.co.uk/tutorials/linux-commands)

### 4. Installing MySql
A Database Management System (DBMS) will need to be installed to be able to store and manage data for the website. MySQL is an RDBMS used within PHP environments
To install MYSQL:

   `sudo apt install mysql-server`

 check to see if mysql is installed, run command:
 
    `sudo mysql`

 ![Screenshot (192)](https://github.com/ettebaDwop/project-1/assets/7973831/e607519c-07c0-4c8e-a635-d37dd909643a)

A recommendation is to run a security script to lock down access to your database
    `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

To secure MySQL installation, run this command:

    `sudo mysql_secure_installation`
    
Test to see if you can log into mysql

    `sudo mysql -p`
    
 ![Screenshot (197)](https://github.com/ettebaDwop/project-1/assets/7973831/3a48fdbd-623c-4e5c-9543-f60b56871506)


### 5. Installing PhP
Installing  PHP in our setup that will process code to display dynamic content to the end user. 
To install PHP and its dependencies, run the command:

    `sudo apt install php libapache2-mod-php php-mysql`

confirm the installlation

    `php -v`

![Screenshot (199)](https://github.com/ettebaDwop/project-1/assets/7973831/ad3bb487-1b4f-44fd-9a05-f9a7506ecf3d)


### 6. Creating Virtual  Host for website using Apache
`sudo mkdir /var/www/projectlamp`

` sudo chown -R $USER:$USER /var/www/projectlamp`

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

```
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
To enable a new virtial host, run:

    `sudo a2ensite projectlamp`
    
It is recommended to disable Apache's default configuration so that our site would run. Thus command:

    `sudo a2dissite 000-default`
    
The next thing to do is reload Apache to apply all changes.

    `sudo systemctl reload apache2`
    
Open the website on the browser

http://<Public-IP-Address>:80
 
 
 
    
### 7. Enabling PHP on website 
To enable php, we have to change the order of execution. The reason for this is that the index.html file would always take precedence in the order of execution over an index.php file. Thus , we will edit the configutation file by running the command:

    `sudo vim /etc/apache2/mods-enabled/dir.conf`
    
Change the contents of the file to:

`<IfModule mod_dir.c>
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
 </IfModule>`
 
* Note here that the first file is index.php as opposed to index.html

Create a new file index.php in the root folder

    `vim /var/www/projectlamp/index.php`

Add the text below to the file to display the php page 

    `<?php 
       phpinfo();`

![Screenshot (193)](https://github.com/ettebaDwop/project-1/assets/7973831/d12e9f0a-c890-403a-958c-6a4f7ba40889)

