## eCommerce with Github Action

### Project Setup
1. create a git repo `ecommerce-app`

![](img/1.create%20repo.png)

2. Inside the repo, create 2 dir. `api` and `webapp`

![](img/2.%20api_webapp_workflow%20dir.png)

### Initialize GitHub Actions

3. Initialize the git repo created
4. Create `.github/workflow` dir in the repo

### backend API setup

5. In the api folder, setup nodejs code

![](img/3.backend%20api%20setup.png)

### Frontend web application setup

6. In the webapp folder, setup `react` application

![](img/4.%20webapp.png)

### Continuous Integration workflow

7. Install dependencies, run test and build the appication

![](img/5.ci-1.png)
![](img/6.ci-2.png)

### Docker Integration

8. Create Dockerfile for both the api and the front end

![](img/7.dockersetup.png)

9. build docker application
![](img/8.gitopsrun.png)
![](img/9.dockerfile_run.png)

### Deploy to Cloud

10. configure Github action to deploy the docker image

![](img/11.buildDockerCi.png)

setup secret in the github setting

![](img/12.secret.png)

push the image to docker hub

![](img/13.push%20docker.png)

workflow run

![](img/14.githubaction%20run.png)

view image on docker hub

![](img/15.Docker%20repo.png)

Pull the image to Ec2 instance with docker runing

![](img/16.ec2_pull.png)

![](img/17.image%20ls.png)

run docker image

![](img/18.docker%20run.png)

