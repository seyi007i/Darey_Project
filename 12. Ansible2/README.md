## Ansible refactoring and static assigmnents

Refactoring is a general term in computer programming. it means making changes to the source code without charging expected behaviour of the software

#### Refactor ansible code 

1. make changes to the existing jenkins server

create a new directory called `ansible-config-artifact`

![](img/1a.png)
`sudo mkdir /home/ubuntu/ansible-config-artifact`

create new branch on git hub

![](img/04.new%20branch.png)


2. change permissions to the created directory
`chmod -R 0777 /home/ubuntu/ansible-config-artifact`
![](img/01.ansible-config-artifact.png)

3 Manage\Available, install `Copy-Artifact`

![](img/02.copy%20artifact%20to%20home%20directory.png)

4. create a new freestyle project

![](img/03.%20jenkin%20server%20artifact.png)


#### Configure uat webservers with a role webserver

1. setup a new directory called roles
2. create other sub folder using `ansible-galaxy init`

or create the folder manually

![](img/list%20folder.png)

create the below file structure


copy the below code in the static playbook

![](img/05.static%20assignment.png)

![](img/playbook1.png)

Push refactor to github

![](img/06.pushrefactor.png)

Unistall the wireshark installed in the previous project

![](img/07.connectionTest.png)

![](img/07.dev_yml%20a.png)

![](img/08.playbook.png)

![](img/09.uninstall-wireshark.png)


## Configure uat webservers with a role webserver

1. Lunch 2 fresh EC2 instances using RHEL 8 image
web1 and web2

create roles using ansible-galaxy or manually


![](img/12a.role.png)

Update playbook content


![](img/13%20playbook.png)

![](img/task_main.png)

![](img/static_uat.png)

![](img/)

run the playbook
cd /home/ubuntu/ansible-config-artifact

ansible-playbook -i /inventory/uat.yml playbooks/site.yaml
![](img/13%20playbook.png)

![](img/final.png)