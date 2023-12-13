# Automating Loadbalancer configuration with shell scripting

### Automating deployment of webservers

1. create 2 EC2 instance

![](img/01.3Instance.png)

2. Open port 8000 using the security group

![](img/02.InBoundRule.png)

3. ssh to the server to create the script and prepare to execute

![](img/03.Server1.png)
server 1

![](img/04.Server2.png)

4. open a file, paste the script provided

![](img/06.install_sh.png)

5. change permission and run the script

![](img/07.RunInstall.png)

*** the public_ip is the public ip of the server

![](img/08.FinishInstall.png)
The same process was ran for the 2 server

## Deployment of Nginx as a Load Balancer using shell

1. ssh to the server
![](img/09.Loadbal.png)

2. open a file, paste the provided script

3. grant exec permission to the script file

![](img/09.Loadbal.png)

4. test the script
![](img/11.testpage1.png)

![](img/11.testpage2.png)
