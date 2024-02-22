## Ansible dynamic assignments (include) and community roles

### ansible galaxy

Modify the github file structure. Create a new branch `dynamic-assignments`

![](img/01.NewBranch.png)

Create a new file `env-vars.yml`

![](img/02.addFile2DynamicDir.png)


![](img/02ab.directory.png)

In env-vars.yml,set your code to use `include_vars` variable with loop to iterate over the file for the inventory

![](img/03.env-vars.png)

Update site.yml

![](img/04.site.png)

### Update site.yml with dynamic assignments

Roles can be download from ansible galaxy. To download mysql role developed by geerlingguy

create a git hut branch `roles-feature`

![](img/6.git.png)

inside roles, directory create the new mysql role with `ansible-galaxy install geerlingguy.mysql` and remane the folder to mysql

![](img/7.ansible%20galaxy.png)

Set the configuration to use tooling website credentials

![](img/db%20connection.png)


Merge branch with remote master branch

![](img/8.merge.png)
![](img/9.merge.png)

### Setup load balancer

role can also be used to create load balancer. Apache and Nginx will be created

![](img/install%20apache.png)

![](img/install%20nginx.png)

create loadbalancers.yml

![](img/LByml.png)

Configure the site.yml to reference the loadbalancer

![](img/site.png)

run the playbook

![](img/run%20play.png)

![](img/play%20lb.png)

![](img/play2.png)

![](img/228.png)

![](img/36.png)

![](img/6.png)
