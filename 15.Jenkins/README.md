## Introduction to jenkins

#### How to install jenkins

1. setup an EC2 instance on AWS

2. Update the package repositories

`sudo apt update`

3. Install JDK

`sudo apt install default-jdk-headless`

![](img/03.apt%20update_install%20java.png)

4. install jenkins

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins


![](img/04.install%20jenkins.png)

5. check if jenkins has been installed

`sudo systemctl status jenkins`

![](img/05.jenkin%20status.png)

6. create inbound rule

![](img/06.sg.png)

7. setup the web console

input the jenkins server public ip with the port number on a browser

![](img/07.landing_page.png)

8. install suggested plugin

![](img/08.customize.png)

9. setup the credentials

10. log in to jenkins console

![](img/10.landingPage.png)
<<<<<<< HEAD


## 2. Source code Management Repository Integration

- configure webhook with jenkins public IP

This process create a continueous integration `Ci`

![](img/7.webhook.png)

![](img/7.webhook2.png)

packet delivery can also be verified

![](img/7.webhook_jenkins%20log.png)

## jenkins pipeline for web application

![](img/web%20pipe.png)

![](img/web_jenkinsfile.png)


![](img/9.pipe_website.png)

![](img/9b%20script%20log.png)



=======
>>>>>>> 30c063b397c1c559f7b9d02976b6d2eeb70ab56a
