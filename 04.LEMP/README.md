# LEMP Project
### Linux, Nginx, MySQL, PHP

## Linux setup

The setup of the linux os was done on AWS. The OS is  `ubuntu`. Connection to the virtual box is done through SSH

![](img/01.ubuntu%20instance.png)

I login to the ubuntu instance on aws using `terminus`

![](img/02.Ubuntu%20cmd.png)

## Installing the Nginx websever

To install Nginx webserver, use the following commands
`sudo apt update`
`sudo apt install nginx`

![](img/03.sudo%20update.png)

![](img/04.install%20nginx.png)

When prompted, enter Y to confirm that you want to install nginx

To verify installation was successful
`sudo systemctl status nginx`

![](img/5.systemctl%20ngis.png)

#### Open port 80
How allow inbound traffic to server web page, port 80 must be open

![](img/06.port80.png)

To check if the web page can be access locally,
`curl http:\\hostname:80`
![](img/7.curllocalhost.png)

To test from the browser, use the public ip address

![](img/08.Niginx_WebPage.png)

## Installing MySql

MySql is the database management system to store and maintain data for the website

To install, use this command
`sudo apt install mysql-server`

![](img/09-installMySql.png)

To connect with the sql instance, type `sudo mysql`

![](img/10.mysql.png)

To change the root password, type this command
`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
`
![](img/11.ChangeRootpassword.png)

To harden mysql, run the following interactive script `$ sudo mysql_secure_installation
`
![](img/12.hardenSql.png)

Test connect to mysql with password
`sudo mysql -p`

![](img/13.testSQL.png)


## Installing PHP
`$ sudo apt install php-fpm php-mysql
`
![](img/14.install%20php.png)

### Configuring Nginx to use PHP processor

Create the rootweb directory
`$ sudo mkdir /var/www/projectLEMP` and change ownership to current user using variable `$USER`

![](img/15.mkdirChown.png)

Create bare-bones configuration using a editor
`$ sudo nano /etc/nginx/sites-available/projectLEMP
`
![](img/Snipaste_2023-10-21_02-33-17.png)

Activate configuration with the command below
`$ sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/
`
![](img/16.set%20new%20default.png)

Disable default Nginx host which is configure to listen to port 80

`sudo unlink /etc/nginx/sites-enabled/default
`
![](img/17.set%20NewFolderASNEWFILE.png)

Create html file in projectLEMP

![](img/18.NewHTML.png)

Reload page
![](img/19.NewlandingPage.png)

### Test PHP with Nginx

Create a info.php in projectLEMP directory
`$ nano /var/www/projectLEMP/info.php
`

`<?php
phpinfo();
`

![](img/20.info%20page.png)

php info page contains sensitive information, to remove the page, use
`sudo rm /var/www/your_domain/info.php
`
![](img/25.removeInfoPhp.png)

### Retrieving data from MySql database with PHP

Create new user

![](img/22.createNewUser.png)

create new db

![](img/21.dblist.png)

Insert rows to the table

![](img/23.createTable.png)

Creating dynamic content through php

![](img/24.todo.png)

Showing database content through php

![](img/26.finalPage.png)

