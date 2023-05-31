# WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
A LAMP stack is a group of open source software that is typically installed together in order to enable a server to host dynamic websites and web apps written in PHP¹³. It consists of four components: Linux, Apache, MySQL, and PHP.
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
### 2. Update Ubuntu package
On connecting to the server, we would run the following commands:

 `sudo apt update`
 
 `sudo apt upgrade`

### 3. Apache Installation
To install Apache 2 run the commands:

` sudo apt install apache2`

`sudo systemctl status apache2`

![ apache status](./image/apache-status.png)

[Linux Commands](https://www.hostinger.co.uk/tutorials/linux-commands)

### 4. Installing MySql

### Installing PhP
### Creating Virtual  Host for website using Apache
### Enabling PHP on website 

