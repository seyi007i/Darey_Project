# Client Server Architecture using MySql DB

## Create two instances of servers on Linux

I spin existing server used in LEMP class as the server, while `mysql-client` was setup on my local ubuntu server

![](img/04.ExistingServer.png)
 
 ![](img/01.installMySql_client.png)

 ## Connect MySql client to MySql server

 `open port 3306`
 ![](img/03.Port3306.png)

 #### Modify mysql configuration file to accept remote connection

 open `sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf 
` in an editor
change the `bind-address to 0.0.0.0` ie any ip

![](img/05.AcceptRemoteCon.png)

Restart MySql server to effect the change

![](img/06.restartMySql.png)

#### Connect remotely to MySql server

use this command to connect
mysql -u `<username>` -p -h `<server ip address>`

![](img/07.remoteConnection.png)