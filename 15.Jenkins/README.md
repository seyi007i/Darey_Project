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


## 2. Source code Management Repository Integration

- configure webhook with jenkins public IP

This process create a continueous integration `Ci`

![](img/7.webhook.png)

![](img/7.webhook2.png)

packet delivery can also be verified

![](img/7.webhook_jenkins%20log.png)


## 3 Unit test with webhook
Continueous integration is when a code is push from the IDE, the push triggers the Jenkins to an action

1. create a free style project

2. set the repo url

3. check `GitHub hook trigger for GITScm polling` under the build trigger

![](img/jenkin%20freestyle.png)

4. Do a push from the IDE, it will trigger a build. find below the build log 

![](img/webhook%20jenkin%20freestyle.png)

## 3. jenkins pipeline for web application

1. Create a Jenkinsfile for the build

![](img/web_jenkinsfile.png)

2. create a `pipeline` project in jenkins
![](img/web%20pipe.png)

3. Automate the build process using webhook

![](img/9.pipe_website.png)

4. build log

![](img/9b%20script%20log.png)


## 5. Docker image creation and registry push

1. Setup a docker Ec2 instance. this can also be done on the Jenkins server

![](img/istall%20docker%20script.png)

2. Create a dockerfile to create the image

![](img/Dockerfile.png)

3. create and run jenkins scripts pipeline

![](img/push%20to%20hub.png)

4. push to the hub registry

![](img/hub-repo.png)


