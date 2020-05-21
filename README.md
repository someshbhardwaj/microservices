# microservices
Currency Conversion System in AWS, Google Cloud and Azure
## Software Pre-requisite or Tools
1. Java 8+
2. Eclipse - Recent Version
3. Maven
4. Git
5. Docker desktop
6. Kubernetes
7. ELB CLI
8. Google Cloud Account
9. AWS Account
10. Azue Account
11. Account in hub.docker
12. Actual code to deploy (Download the one given by me. It also has needed scripts)

## Basic Step:
1. Once you have a working code.
2. Make its image using command >>>> mvn clean install
3. Upload the image in the docker (it needs docker account)
4. Deploy using kubernetes
5. As per respective clouds the commands will change.

## Docker Images of currency-exchange microservice
![hub.docker account](https://github.com/someshbhardwaj/microservices/blob/master/Docker_Hub_Code_Image.png)
## Few commands which might be useful for anyone

__Make Kubernetes Cluster and connect with them__

1. Create a cluster in the Google cloud (give name and choose features u want in the cluster)
2. Connect with the cluster from Local PC console (goto the kubernetes cluster pager -> Select cluster -> Select "connect" option copy the command and run in ur consle.

kubectl set image deployment currency-exchange currency-exchange=somesh0905/currency-exchange:0.0.1-RELEASE

__Steps to create image and push to hub.docker.com and deploy in Google Cloud__

0. Goto The Root directory of the code
1. To create image
2. Change code and in pom.xml change the version of the code.
3. mvn clean install
4. docker push <hub.docker.com user if>/<application name>:<Tag Release>
   docker push somesh0905/currency-exchange:0.0.1-RELEASE
5. kubectl apply -f deployment.yaml

__Validate the execution of commands__
1. docker images
2. kubectl get all			//get the external ip   example 35.232.160.148 and port 8080
3. Goto the google Cloud console
4. watch -n 0.1 curl 35.232.160.148:8080/hello-world

   watch -n 0.1 curl 35.232.160.148:8080/<url in the code or api in the code>

## NOTE
Please keep in mind, it takes money to keep running in the cloud (AWS/Azure or Google Cloud)

__TIP: As deployment consumes money. Once you have learnt how to deploy please free all deployed resources.__

