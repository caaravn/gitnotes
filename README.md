# githubnotes
-> Git/Github ---> it is source code management tool which helps you to manage the application code.
-> Git is local repository which is on you local machine.
-> Github is centralised repository were you need to login using username/passwd.
-> In github we can fork or import the code from other github
        Import -> it will copy the repository from one github account to another github account
        Fork   -> it will copy only specific branch master/main from one account to another account 

-> git init -> which helps to convert normal directory to git directory.(which initilise the git congiguration).

-> Git clone -> were we can download entire repository from github to local git
     git clone <github url>   (url -> github repo url)
     
     cd <reponame>  -> go inside directory
     
     vi filename    -> to create new file (esc->shift:->wq)

     LL            -> List
     
     git add .      -> . indicates all files
     git commit -m "message" -> (-m is message)
     git push origin branchname  ->push code to github.
     
     git status  -> to see the status before and after command exection for both add&commit.

     git pull origin branchname  -> It helps ypu to pull the latest code changes from github to local git

     git fetch                    -> It helps ypu to pull the latest code changes from github to local git from specific branch

-> git branching ---> Branching will helps developers to work parallely or samintaniously with out any dependency on each other.
         -> when we create any branch we get a default branch called "MAIN"
         Below are the branches were developers create depends on there project
             Stage  1) feature barnch-> were developer create and work on there code individually
             Stage  2) develop/dev/developement branch-> In this all developer code will merge and quality test happen 
             Stage  3) main or master branch (default branch)->were it contains final code application
             Stage  4) release branch -> code releasing to customer
             Stage  5) hotfix branch -> any minor and immediate change of code
             
         

     git branch <bname> --> to create branch 
     git checkout <bname>  -> switch from one to another branch
                Above two (OR) below one (same)
     git checkout -b <bname>  -> create and switch to that branch
     
     git branch -d <bname>    -> delete branch (-d delete)
     git branch    -> list the branches which are on local git
     git branch -a  -> it will list branches from both git and github. (-a   all branches)

-> git log  --> commit history display
   git log --oneline  shows commit history with less content

-> git diff <bname> <bname>     -> it will show diff b/w two branches
   git diff <commitid> <commitid>  -> it will show diff b/w two commit id's
   git show <commitid>   -> to see details info for commit id   

-> git merge --> combine two diff branches into single branch.
                  --> github->pullrequest->create pullrequest->merge request
   git checkout main
   git merge <main> <test>    -> it is merging test to main branch.  

-> git stash  --> to store current working directory temporarly 
            git stash      -> save the current work dir to stash
            git stash list -> show the list of saved items
            git stash apply -> to get back the save curent dir
            git stash drop  -> delete the saved items from stash

-> .gitignore  --> .gitignore file will helps to skip/avoid the unwanted files while pushing into github.
    vi .girignore --> *.log

-> git reset --> to undo the changes/// -> move from current state to previous state.(one step back)

-> git rebase --> when you are having multiple commits for same branch using rebase we make all those commits into single commit

   git reset <filename> 
   
   -> Setup git in Linux VM
    sudo yum install git -y
    ssh-keygen -> enter -> enter-> enter 
    to get key -> cat /home/ec2-user/.ssh/id_rsa.pub
    copy the key to github account in settings -> SSH option
    git clone <repo SSH URL> -> yes -> enter ---> it will start clone.

====================================================================================================================================================================================
# Maven

Maven Tool:
-> Maven is build automation tool
->developer keep dependencies and compilers in pom.xml file
-> using maven we are going to build the application code written by developers
-> After build it will generate target folder and .jar file inside init (target/***.jar)
-> maven is having lifecycle which contains diff stages/phases
     -> generate resource - Generate required de[pendencies to build application code using maven.
     -> Compile code -- convert code into binary language (machine readable)
     -> Unit test --- Maven will test internally diff test cases
     -> Package ---- Creating .jar file from the code (copying all the required code into jar)
     -> install ----- Install the .jar on maven server
     -> Deploy ----- Deploy is ntg but upload/deploy the dependencies and .jar files to maven repository.
     -> Clean ----- Claen the existing .jar file and recreate new .jar file.
-> When we download and install maven
     -> .M2 folder ---- were it containes entire configuration of maven.
         settings.xml ---- Maven repo URL then username/password.
         pom.xml ---- when we execute maven commnd will simply follow the pom.xml file
     -> Using single command we can execute the entire maven lifecycle
         mvn clean install
-> Download and install maven in windows/Linux
Windows:
    -> https://phoenixnap.com/kb/install-maven-windows (Installation steps)
    -> https://maven.apache.org/download.cgi (download maven package)
Linux:
   -> Sudo yum install maven -y
   -> maven -version

-> Make sure execute maven command were the POM file is.
Sample Repo: https://github.com/Renukadema/Calculator.git 

=====================================================================================================================================================================================

What is Docker?
Docker is light weight container, were you can build and run your application on docker.
Docker is very fast in build and running application.
Docker will only support single application deployment.

-> hardware-==> kernel OS----->Docker engine---->Application
-> Install docker on linux machine
    *  yum install docker -y  (Install docker on our VM).
    *  systemctl start docker  (will start the docker service).
    *  systemctl enable docker (if we stop the VM docker service also will stop and once VM is start automatically it will start the docker service as well).
    *  systemctl restart docker (to restart the docker service).

-> Docker engine ---> which containes docker config and which heps to run the docker service
-> Docker Repository --> were you can store the docker images (here we can do pull/push mechanism)
-> Docker images -> we can build docker image using docker file 
-> Dockerfile ---> Group of instructions

Docker Commands:
-> **Docker info** ---- we can see the config/details about docker
-> **Docker images** ---- to see list of docker images
-> **Docker rmi <imagename>** --- to delete specific docker image
-> **Docker build -t <imagename> .** ----to build docker image from dockerfile

-> docker ps --- it will show the running containers
-> docker ps -a -- it will show both stop and running containers.
--> docker start <containerid>  ------> to start the container
-> docker stop <containerid>  ------> to stop the container
-> docker rm <containername> --- delete docker container (make sure container should be in stop state)
-> docker run -it --name <containername> <imagename> /bin/bash ---> to create container and naming it
-> docker commit <containerid> ---- from this we can build new docker image from existing image
-> docker logs -f <containername> ----- to see container logs
-> docker exec -it <containername> sh  ------ to login into container 
-> exit ----> for coming out from container
-> docker stats <containername> ---- you can see the resource utilization cpu/ram/memory   
-> docker system prune ---- unused images/containers will be deleted
-> docker run -it --name <containername> --privileged=true --volumes-from <oldcontainer> <images> /bin/bash 

**docker hub commands** 

docker run <ubantu>  -------> it will pull image from docker hub and creat container too

docker pull <ubantu> --------> it will only pull image from docker hub



======================================================================================================================================================================================

# Jenkins-notes
**Download and install jenkins on linux**

-> sudo dnf update -y                     ----------------------> for updating any dipendenciess
-> sudo dnf install java-17-amazon-corretto -y
-> sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
-> sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key 
-> sudo dnf install jenkins -y
-> sudo systemctl enable jenkins
-> sudo systemctl start jenkins
-> open your web browser and access Jenkins by navigating to:
         http://your_amazon_linux_instance_ip:8080
-> sudo cat /var/lib/jenkins/secrets/initialAdminPassword

-> new item -> name -> pipeline -> pipeline script -> apply -> save -> Build Now -> logs -> console output.

 Sample pipeline code

 refer in ----> Jenkinsfile (same repo)
======================================================================================================================================================================================

**SonarQube** -> Security tool - https://techexpert.tips/sonarqube/sonarqube-scanner-installation-ubuntu-linux/ 
-To scan our code in the repository.
-Sonar Qube will helps us to find the bugs, vurnabilities and code related issues.
-Sonar report will be uploaded to Sonar Hub
-Reports will assigned to developers.

->**download and install SonarQube on linux **

->wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip?_gl=1*1k01es0*_gcl_au*NDcxMDQ0MTA2LjE3MDQ4NTA0NTg.*_ga*MzQ3NDcyODQ5LjE3MDQ4NTA0NTg.*_ga_9JZ0GZ5TC6*MTcxMTAwMzk3Ny45LjEuMTcxMTAwNDAwMS4zNi4wLjA.

->sudo mv sonarqube-10.4.1.88267.zip\?_gl\=1\*1k01es0\*_gcl_au\*NDcxMDQ0MTA2LjE3MDQ4NTA0NTg.\*_ga\*MzQ3NDcyODQ5LjE3MDQ4NTA0NTg.\*_ga_9JZ0GZ5TC6\*MTcxMTAwMzk3Ny45LjEuMTcxMTAwNDAwMS4zNi4wLjA. sonar.zip

-> sudo unzip sonar.zip

-> cd sonarqube-10.4.1.88267/bin/linux-x86-64/
   -> ll
   ->  sudo ./sonar.sh start
   ->  sudo yum install maven -y (to setup java on this)
   ->  sudo ./sonar.sh start
   ->  sudo ./sonar.sh stop
   ->  sudo ./sonar.sh start
Use IP Address of VM with PORT number
http://IPAddress:9000/         (9000 --- default port for Sonar)
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
-> **Download and install sonar on Ubuntu**

sudo mkdir /downloads/sonarqube -p
sudo cd /downloads/sonarqube
sudo wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.2.0.1873-linux.zip
sudo unzip sonar-scanner-cli-4.2.0.1873-linux.zip
sudo mv sonar-scanner-4.2.0.1873-linux /opt/sonar-scanner
sudo vi /opt/sonar-scanner/conf/sonar-scanner.properties
         sonar.host.url=http://localhost:9000
         sonar.sourceEncoding=UTF-8

sudo vi /etc/profile.d/sonar-scanner.sh
        #/bin/bash
        export PATH="$PATH:/opt/sonar-scanner/bin"

sudo reboot
sudo source /etc/profile.d/sonar-scanner.sh

sonar-scanner -v

===================================================================================================================================================================================

**Helm**
-> Using helm we are creating packages (.tgz) 
-> Using helm we can install, upgrade, and deploy our application on Kubernetes Cluster.
-> Helm package/helm chart both are same.
-> Helm Folder Structure 
    -> helm -> whatsapp -> chart.yaml
                        -> Values.yaml
                        -> templates folder -> service.yaml
                                               deployment.yaml
                                               database.yaml
                                               secrets

-> Helm create whatsapp (it will create hel folder structure)
-> helm lint whatsapp   (to verify the folder structure or syntax for helm)
-> helm package whatsapp (it will generate .tgz file)
-> helm install whatsapp whatsapp-1.0.0.tgz (it will install chart on our cluster for first time)
-> helm upgrade --install whatsapp whatsapp-1.0.0.tgz (upgrade/second time installation od same chart with new version)
-> helm ls
-> helm uninstall whatsapp (delete/uninstall the chart from cluster).

Install helm on linux VM:
- sudo curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
- sudo chmod 700 get_helm.sh
- sudo ./get_helm.sh

=========================================================================================================================================================================================


  ====
