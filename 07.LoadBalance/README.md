# LOAD BALANCING WITH NGINX

### Create 2 instance of webserver

Using existing server from previous project.

Server is ubuntu with apache2 server while the second server is AWS linux with httpd

![](img/06.serverlist.png)

The web server are installed using scripts from previous project

![](img/05.serverInstallation.png)

the server home page was altered to indicate server 1 and server 2

![](img/04.server1Web.png)

![](img/03.server2Web.png)

![](img/06.serverlist.png)

Opening of `port 8000`

![](img/07.port8000.png)

![](img/08.listen8000.png)

![](img/09.port8000.png)


## Install Nginx load balancer

![](img/10.installNginx.png)

Check installation status

![](img/11.nginxStatus.png)

### configure load balancer

![](img/13.loadbalancer.png)

Test configuration

![](img/12.testnginx.png)

### Test loadbalancer on browser

load the load balancer IP on the browser
`13.53.176.144`

![](img/14.loadbalancer1.png)

![](img/14.loadbalancer2.png)