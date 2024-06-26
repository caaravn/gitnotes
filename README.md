Three tire application  

1. web tire (presentation layer) ---> frontend UI code ( html,css,js..)
2. 
3. app tire (logic code layer)  ---> banckend code (java, nodejs, python..)
4. 
5. Data base tire ----> (mysql, mangodb, nosql)


Backend end codes
 java
 nodejs
 python
 .net
 Ruby

Front end codes
 HTML
 CSS
 JAVA scripts
 Angular
 react.js

*Web servers:
   Apache HTTP server
   Apache tomcat (for java based application)
   NGINX
   ISS(microsoft)

Developer with code they keep dependencies and compilers in a file called build files like    pom.xml file       for java code
                                                                                             package.json file  for nodejs
                                                                                             requirement.txt    for python
                                                                                             project.json       for .net


==========================================================================================================================================================

Linux basic commands

COMANDS retated to packages
sudo yum insatll <package> -y  -----------> to install package
sudo su -                      -----------> to convert normal user to root user
sudo which <package>           -----------> to cross check package
sudo yum list installed        -----------> to check list of packages

COMANDS retated to directory(folder)
mkdir <folder name>           ------------> to create folder
ls or ll                      ------------> to see the list of folder
cd <folder name>              ------------> to get inside the folder
cd ..                         ------------> to get to previous folder
pwd                           -------------> to know the current directory were we are in

COMANDS retated to files
cat > <file name>              --------------> to create file
cat <file name>                --------------> for opening created file
                        (OR)
vi <file name>                ----------------> creating new file if it already not exist, otherwise opens existing file (creating and opening same command)
ecs :wq!                      -----------------> for coming out of the file
rm -rf                        -----------------> to remove or delete

========================================================================================================================================================
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

=============================================================================================================================================================================

# Maven

Maven Tool:
-> Maven is build automation tool
->Developer with code they keep dependencies and compilers in a file called build file like    pom.xml file       for java code
                                                                                               package.json file  for nodejs
                                                                                               requirement.txt    for python
                                                                                               project.json       for .net
          
-> using maven we are going to build the application code written by developers
-> Example after build java code it will generate target folder inside it we have .jar file (target/***.jar)
 Target folder:- folder where compiled or built artifacts are stored during the build process.
 
     This .jar file is called as Artifact/Package

     Same as above for .NET, PYTHON, NODEJS -------> We get .ZIP file.
                   for java web applications -------> we get .WAR file

-> maven is having lifecycle which contains diff stages/phases
     -> generate resource - Generate required de[pendencies to build application code using maven.
     -> Compile code -- convert code into binary language (machine readable)
     -> Unit test --- Maven will test internally diff test cases
     -> Package ---- Creating .jar file from the code (copying all the required code into .jar file)
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

Commands for building .war file without using jenkins

mvn clean install
ll
cd target
ll
wiil see .jar file
cd .. (for back)

**after creating the .jar file( artifact) we push the code to package repository tool like Nexus, jfrog**


======================================================================================================================================================================================
Jenkins:- 

Continious integration:
1> Code checkout ---> cloning repo and downloading repository and pushing back with same changes.
2> Build and unit test-----> Compile (from gb's to mb's) the code we use maven tool and generate war or jar file in the target folder
3> Code scan------> Sonarqube scans the code to find bugs, vurnabilities, static code and code related isses
4> Image build ----> With docker we create image

Continious deployment:
If the application successfully passes all tests and validations, it is deployed to the production environment.
As in the kubernetics cluster is created with nodes and in the nodes differtent servies of pods are created and inside the pods we 
have containers where image(package) is deployed into those containers.
Through port and ip address we can access the application in the browser.


 We have two types of pipe line 
 1. Scripted pipeline:- It provide lot of flexibility and control over the work flow.
                        This pipeline are used when you have complex build.
    
 2. Declarative pipeline:- It is more structured and simple syntax for defining pipeline.
                           As this is not best choise with complex logic.
       
 Jenkins pipeline (Declarative pipeline)
 
1)pipeline
2)Agent (any or VM name)
3)Stages
4)Stage
5)Steps

SCRIPT
=======

pipeline {
    agent any

    stages {
        stage('code checkout') {
            steps {
                // Get code from a GitHub repository
                git 'https://github.com/Renukadema/Calculator.git'
            }
        }
        stage('Maven Build') {
            steps {
                // Run Maven to build the project
                sh "mvn clean package"
            }
        }
        stage('SonarQube Analysis') {
            steps {
                // Run SonarQube analysis
                withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'sonar-token') {
                    sh "mvn clean verify sonar:sonar -Dsonar.projectKey=Calculator -Dsonar.projectName='Calculator'"
                }    
            } 
        }
        stage('Build docker') {
            steps {
                // Build Docker image
                sh 'docker build -t calculator . --file Dockerfile'
            }
        }
        stage('AWS Authentication') {
            steps {
                // Authenticate with AWS
                withAWS(region: 'ap-south-1', credentials: 'aws-credentials') {
                    sh "aws eks --region us-east-1 update-kubeconfig --name demo-eks"
                }
            }
        }
        stage('Kubernetes Setup') {
            steps {
                // Set up connection to Kubernetes cluster (if necessary)
                // withKubeConfig(credentialsId: 'K8S', clusterName: 'eks', serverUrl: 'https://B5FE4869B0809F47FCBB3CAE5F9E14D8.gr7.us-east-1.eks.amazonaws.com') {
                // }
            }
        }
        stage('Deploy app in kubernetes') {
            steps {
                // Deploy application in Kubernetes
                sh 'kubectl delete ns nginx'
                sh 'kubectl create namespace nginx'
                sh 'kubectl get ns'
                
                // Apply Kubernetes deployment and service configurations
                sh 'kubectl apply -f deployment.yaml -n nginx'
                sh 'kubectl apply -f service.yaml -n nginx'
                sh 'kubectl apply -f nginx-loadbalancer.yaml -n nginx'
            }
        }
        stage('verify') {
            steps {
                // Display cluster nodes and deployed pods
                sh 'kubectl get nodes'
                sh 'kubectl get pods -n nginx'
                sh 'kubectl get svc -n nginx'
            }
        }
    }
}


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

**java install**
sudo apt update
sudo apt install openjdk-11-jre


sudo adduser sonarqube   ---------> adding user
apt install unzip
sudo su - sonarqube      ----------> swiching to sonar user
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
unzip *
ls
chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
cd sonarqube-9.4.0.54424/bin/linux-x86-64/
./sonar.sh start
```

Hurray !! Now you can access the `SonarQube Server` on `http://<ip-address>:9000` 


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
=======================================================================================================================================================================================
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
    * sudo usermod -aG docker jenkins ---------------->  command adds the current user to the docker group, which allows you to run Docker commands without using sudo. Remember to log 
                                                         out and log back in for the group membership to take effect.

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
-> docker run -it --name <containername mywish> <imagename> /bin/bash ---> to create container and naming it
-> docker commit <containerid> <newinage mywish> ---- from this we can build new docker image from existing image
-> docker logs -f <containername> ----- to see container logs
-> docker exec -it <containername> sh  ------ to login into container 
-> exit ----> for coming out from container
-> docker stats <containername> ---- you can see the resource utilization cpu/ram/memory   
-> docker system prune ---- unused images/containers will be deleted
-> docker run -it --name <containername> --privileged=true --volumes-from <oldcontainer> <images> /bin/bash 

-> dcoker run -d --name mywish -p 8080:8080 "Imagename"    ---> command for deployment of image in container and accessing in browser through the given port

          -d-> want to run in detached mode
          -p-> for port 8080(this port we can access application in browser) :8080 (for container port)
          

**docker hub commands** 

docker run <ubantu>  -------> it will pull image from docker hub and creat container too

docker pull <ubantu> --------> it will only pull image from docker hub

=========================================================================================================================================================================================
Kubernetes:

Cluster > Nodes > Pods > Containers.

-> Popular kubernetics distributions

       -> Core Kubernetics 
       -> RED HATOpenshift
       -> Rancher
       -> EKS
       -> AKS
       -> GKE
       -> MiniKube (use for testing and practice in which master and worker node run on one machine)
       -> kubeadem


Kubernetics atchitecture:-

We are having two types of nodes in a cluster and each node has multiple pods in it.
   Note: Node is nothing but Virtual machine with ram, cpu and storage (eg. EC2 instance)

1. Master Node ----> It manges the worker node.
2. Worker Node ----> As application will deploy in pods of worker node only.


Master node:-
4 processes run every master node
   1> Api server ( Cluster gateway and acts as a gatekeeper for auth)
   2> Control manager  ( detects the cluster state changes )
   3> etcd  ( etcd is cluster brain and cluster changes get stored in the key value store )
   4> Scheduler  ( by this it schedules and knows where to put the new pod based on availability and requirement)
   
  
Worker node:-
Three process must be installed on every Worker node to manage the pods.
  1> Container Runtime ( Container run time manages container iside the pods)
  2> Kubelet ( After scheduler decides kubelet wiil create the pod, Interacts with both container and node)
  3) Kube proxy (critical role in enabling communication and networking between pods and services)

Architecture work flow-
1> we get a request to create the application pod
2> the request goes to API server and gets validated and updates info in etcd
3> and the request goes to scheduler which decides the suitable node to create the application pod and same updates info in etcd
4> Now kubelet will cteate the pod
5> After that kube proxy will enable the network rules for communication
             If pod gets crashed or any wrong happens
6> Now control manager identifies the incident and again inform to scheduler for replacement


what is kubernetes?
-> which helps you to deploy multiple applications as a containers, auto scaling and manage our applications.

What is kubernetes pod?
-> Running as a container on kubernete

**What is deployment in kubernetes?**
-> Deployment is nothing but converts application as a running container and it should manage the roll back machanism.

**what is kubernetes namespace?**
-> kubernetes namespace which helps you to seperate the multiple application deployments configurations.

**what is kubernetes services?**
-> Service load balancer ----- which manages the external acces to kubernetes service
                               feature of load balancer -> SSL, Virtual Hosting, Ingress Routing -> which helps to route the traffic to kubernetes services.
-> NodePort ---- which helps to access the application from external world and it expose the Node IP address
                <NodeIP>:<NodePort>
-> Cluster IP ---- exposes the service on each node based on internal IP address with in the cluster.
-> extral name-----

What is PV and PVC?
-> PV is persistent volumes stoages available for the cluster.
->PVC is persistent volume claim storages requested by user for storage which is bound to PV's.


kubectl is the command-line interface (CLI) tool used to interact with Kubernetes clusters. It is used such as deploying applications, managing pods, scaling deployments, inspecting cluster resources, and more. Below are commands.

-> Kubectl get nodes                       -> to see the nodes under kubernetes
-> kubectl get pods                        -> to see the pods running on cluster
-> kubectl get pods -o wide                -> detail info of pods
-> kubectl get deployments                 -> to get the list of deployments
-> kubectl get secrets                     -> to get the list of secrets
-> kubectl get ns                          -> to see list of namespaces
-> kubectl get svc                         -> to get the list of services
-> kubectl get cm                          -> to get the list of configmaps
-> kubectl get pv                          -> to get the list of persistent volumes
-> kubectl get pvc                         -> to get the list of persistent volume claims

-> kubectl create namespace <name>         -> to create namespace in kubernetes cluster
-> kubectl describe pod <podname>          -> to describe the pods and check the event logs
-> kubectl describe secret <name>          -> to see th full info secret
-> kubectl logs -f <podname>               -> to see the pod logs
-> kubectl logs -f <podname> -c <containername> -> to the application logs
-> kubectl delete pod <podname>             -> to restart the pod/container
-> kubectl edit deployment <deploymentname> -> to edit the deployment for local changes testing
-> kubectl exec -it <podname> /bin/bash          -> to get inside the pod(container)

  To execute and create. (note:- instead of appliying this comands manually we use jenkins tool to automate)
  for each and every yaml file we do the same command.
-> kubectl apply -f deployment.yaml         -> to execute/create the deployment
-> kubectl apply -f service.yaml            -> to execute/create the service

==============================================================================================================================================================
Office
-->kubectl -n sit3 get xxx
--> kubectl -n sit3 edit  xxx
--> kubectl -n sit3 logs -f  xxx
--> kubectl -n sit3 scale  xxx



--> kubectl -n sit3 get deployment---> for getting list of deployments in sit3 env
--> kubectl -n sit3 edit deployment <dep name>  ---> for editing any deployment of any env
--> kubectl -n sit3 logs -f <name of ms> ----> to check the logs of particular microservice
--> kubectl -n sit3 get sts   ------> to get the statefullset
--> kubectl -n sit3 edit deployment <sts name> ----> for editing any statefullset of any env
--> kubectl -n sit3 get pv   ------> to get the persistent volume
--> kubectl -n sit3 scale deployment <deplo name> -replicas=2  -----> to scaleup the pods


===============================================================================================================================================================
Namespaces:
      In kubernetics namespaces are a way to create virtual clusters within a physical cluster.They provide a way to divide cluster resources into logical
groups, enabling multiple teams or applications to coexist and operate independetly within the same kubernetics cluster.



Different YAML files. (Components/Kinds)

deployment.yaml *  --------> we create for deployment of application
        Below yaml files which we can include in deployment.yaml file or we can manintain saperate.
     -> replicaset.yaml -------> they automatically replace any pods that fail or are terminated (it is like duplicate or backup), basically count
pod.yaml*------------> we create for creating pods
service.yaml * --------> we create it because each and every pod( like frontend code pod, backend code pod, database pod) must communicate with each other to run the applicate
Ingress.yaml ---------> we create it to define how external HTTP and HTTPS traffic should be routed to services within the cluster
secret.yaml ----------> we create this file to store sensitive information, such as passwords, API keys, and other confidential data
configmap.yaml* -------> for external configuaration of application and it contains like "database_url"
persistentvolume.yaml(pv) --------> we create for persistent volumes stoages available for the cluster
persistentvolumeclaim.yaml------> 
ingress.yaml ------------> specifies rules that map HTTP or HTTPS routes to Kubernetes services (www.example.com) and traffic.
job.yaml     ------------->
namespace.yaml ----------> to seperate or partition the multiple application deployments configurations.
statefulset.yaml---------> Is used to manage stateful applications, such as databases, where each instance requires a stable, unique identity and stable storage.
role.yaml ---------->  



 
------->>*Deploy yaml file*

->Deployments manage the deployment and scaling of a set of pods, usually to run a stateless application.
->It includes specifications such as the container image, number of replicas.

apiVersion: apps/v1
kind: Deployment
metadata:
  name: <name of the deployment application that we are going to create>
  lables:
    app:my-web-app
spec:
  replicas: 3 ---> No. of pods
  selector:
    matchLabels:
      app: my-web-app
  template:
    metadata:
      labels:
        app: my-web-app
    spec:
      containers:
      - name: < name of the container>
        image: <docker image>
        ports:
        - containerPort: 80


----->>*Service yaml file*

->With this 
->Services provide network access to a set of pods, allowing them to communicate with each other and with external clients.
->It includes specifications for how to expose the pods, such as the port number and
 ->type of service (e.g., ClusterIP, NodePort, LoadBalancer, Ingress)
->Services can be used to load balance traffic across multiple pod replicas and enable external access to the application.

apiVersion: v1
kind: Service
metadata:
  name: my-web-app-service
spec:
  selector:
    app: my-web-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080 
  type: LoadBalancer


---->>*Configmap*

ConfigMaps are used to store configuration data in key-value pairs or as plain text

apiVersion: v1
kind: ConfigMap
metadata:
  name: my-configmap
data:
  # Define key-value pairs for your configuration data
  DATABASE_URL: "mysql://username:password@hostname:port/database"
  API_KEY: "your_api_key_here"
  LOG_LEVEL: "debug"

=======================================================================================================================================================================
aws eks update-kubeconfig --region us-east-1 --name demo-eks  -----> command for generating secret key of kubernetics which we should give in jenkins credencials 
cat <path>

Installation of EKS in linux server using EC2 instance

1>#Install AWS CLI
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" 
sudo yum install unzip
sudo unzip awscliv2.zip  
sudo ./aws/install
aws --version

2>#Install eksctl 
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
#Move the extracted binary to /usr/local/bin. 
sudo mv /tmp/eksctl /usr/local/bin
eksctl version

3>#Install Kubectl
sudo curl --silent --location -o /usr/local/bin/kubectl https://s3.us-west-2.amazonaws.com/amazon-eks/1.22.6/2022-03-09/bin/linux/amd64/kubectl
sudo chmod +x /usr/local/bin/kubectl
kubectl version --short --client

#Create EKS cluster using eksctl command

eksctl create cluster --name XXXX --region XXXX --nodegroup-name my-nodes --node-type t3.small --managed --nodes
===================================================================================================================================

=========================================================================================================================

S3 STORAGE
         It is a scable cloud storage service provided by amazon web servie for storing and retreving data.

AWS global wise division.
25 regions 
80 availability zones
Eg: In Mumbai region (Clustered data centers) we have 3 Availabity zones(AZ) (Isolated group of data centers)
1. North America(NA)
2. South America(SA)
3. Europe (EU)
4. Africa (AF)
5. Asia and Australia (AP) Asia pasific

Note : Bucket name should be unique but folder name can be same
Retreval fee (A fee for downloading)

As S3 can be use for hosting static websites 
Two types of websites we have

1. Dynamic website ---> In dynamic websites content changes based on users ( Instagram profiles of each person data is different)

2. Static website-----> But in static website content will be same for every person ( Enadu newspaper site)
                            Using FRONT END languages code we can host the content in static website
                              eg: HTML, CSS, JS, JQery, Angular, React, etc


STORAGE CLASSES

Each storage has different cost.

.Frequently accessed storage 
    ---->1) Standard storage ( stores greater than equal to 3 and above zones)
    ---->2) Reduced redundant storage

.Infrequently accessed storage
    -----> 3)Standard Infrequently accessed ( stores greater than equal to 3 and above zones)
    -----> 4)One zone infrequently accessed ( stores only in one zone)

.Archival storage
    ------> 5)Glacier (data stored in compression formate) ( stores greater than equal to 3 and above zones)
    ------> 6)Glacier deep archival (data stored in deep compression formate) ( stores greater than equal to 3 and above zones)

7. Intelligent (may be freq or infreq AWS decides)



S3 security:
1.Encryption  ------> for this security we have S3 SSE(Server side encryption)
2.Access permission ----> for this security we have
                            1. Bucket policy
                            2. ACL(Access control list)
                                   i)ACL at bucket level
                                   ii)ACL at object level
                            3.Presigned URL's   




=============================================================================================================================================================================
LAMDA function

Like s3 bucket ===> solves the problem of storage
like LAMDA function ====> Solves the problem of serverless

Note : ->EC2 and LAMBA both belongs to compute family but feature are some different
       ->Serverless computing on AWS allows developers to build and run applications and server without thinking about server. As AWS lamda is a key service in this model
          where you can upload your code and lambda automatically manages the execution, scaling and availability.
       

As in EC2 we need to mention IMAGE, INSTANCE TYPE, MEMORY REQ, CPU REQ, SECURITY
But in LAMDA  AWS will automatically will take the above details base on that, application you want to run.



                             



