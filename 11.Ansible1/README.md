## Ansible Automate Project

### Install and configure ansible on ec2 instance

1. Update the Name tag on the Jenkins EC2 instance to Jenkins-Ansible

2. Create ansible-config-mgt in GitHub 
![](img/01.Github%20repo.png)

3. Install Ansible

![](img/01.install%20ansible.png)

![](img/02.version.png)

4. Configure jenkins build job to archive your repository content every time change is made
![](img/03.github%20repo.png)

5. create freestyle project ansible and point it to `ansible-config-mgt` repo 

configure webhook in githut and set webhook to trigger ansible build

![](img/04.testwebhook.png)

Configure a post-build job to save all `**` files

![](img/05.console%20output.png)

![](img/06.archive.png)

6. Clone the ansible repo on VSCode

![](img/07.clonegithub.png)

7. Create a directory called playbook and inventory
 
create common.yml file in the playbook and dev, stagging, uat and prod into the inventory playbook

![](img/08.directories.png)

8. setup ssh-agent and connect to the jenkins-ansible instance

![](img/09.addssh%20agent.png)

![](img/10.connect%20remotely%20to%20ansible.png)

9. update inventory/dev.yml

![](img/11.dev%20inventory.png)

10. Create playbooks/common.yml


![](img/12.playbook.png)

![](img/13.connect%20to%20instance%20vscode.png)

11. run ansible test

![](img/final.png)

![](img/wireshark.png)