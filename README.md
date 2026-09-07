
**Azuredevops ci for roboshop application** 

**Roboshop Devop CI**







Roboshop project:
=================

Developers brings the requirements like which programming language using and which tests need to be
include and docker base image required for the application and ecr repo name and helm deployment and 
kuberenetes deploymentetc.

**Micro services in roboshop:**
==========================
**frontend:**
=========
**frontend --- JavaScript ---- runtime environment --- nodejs**

 **frontend microservice using Azure devops**

**backend:**
=======
****user   -------  JavaScript ---- runtime environment --- nodejs****

**catalogue ----  JavaScript ---- runtime environment --- nodejs**

**cart    ------  JavaScript ---- runtime environment --- nodejs**

**shipping -----  Java   ---- runtime environment --- JRE**

**payments -----  Python**

**dispatch -----  Go**

  
**databases:**
=========
redis

mangodb

mysql

rabbitmq

*=========================================*
#                                         #
#  **Micro services:**                    #
#                                         #
*==========================================*

**frontend:**
=====

github/git repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/frontend ( sourcecode folder,azure-pipelines.yml/Jenkinsfile,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages npm install,npm test,gitleaks,sonarqube vulernability test,docker build,docker image trivy test,
and push image to ecr/acr/dockerhub registry ) ---> agent (nodejs)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/frontend-argocd.git (helm folder for eks deployment with 
user ecr/dockhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)


**frontend Infra:**






Jenkins server and jenkins nodejs agent/Azuredevops with self runner.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registery,trivy scan/aws ecr scan/dockerhub image scan)


k8s cluster for deployment EKS/Docker desktop/AKS/GKS:


DEV,QA/UAT, Stage

**user:**
====
github/git repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/user ( sourcecode folder,azure-pipelines.yml/Jenkinsfile,Dockerfile)
ci : Jenkins server/Azuredevops with self runner (pipeline stages npm install,npm test,gitleaks,sonarqube vulernability test,docker build,docker image trivy test and push image to ecr/acr/dockerhub registry ) ---> agent (nodejs)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/user-argocd.git (helm folder for eks deployment with 
user ecr/dockhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**user Infra:**



Jenkins server and jenkins nodejs agent/Azuredevops with self runner.(build,SAST,Docker build image, push image ecr/acr/dockerhub ecr/acr/dockerhub registery,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage

catalogue:
=========
github repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/catalogue ( sourcecode folder,Jenkinsfile/azure-pipelines.yml,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages npm install,npm test,gitleaks,sonarqube vulernability test,docker build,docker image trivy test and push image to ecr/acr/dockerhub registry ) ---> agent (nodejs)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/catalogue-argocd.git (helm folder for eks deployment with 
user ecr/dockhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**catalogue Infra:**





Jenkins server and jenkins nodejs agent/Azuredevops with self runner.(build,SAST,Docker build image, push image ecr/acr/dockerhub registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage

cart:
====
github repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/cart ( sourcecode folder,Jenkinsfile/azure-pipelines.yml,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages npm install,npm test,gitleaks,sonarqube vulernability test,docker build,docker image trivy test and push image to ecr/acr/dockerhub registry) ---> agent (nodejs)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/cart-argocd.git (helm folder for eks deployment with 
user ecr/dockhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**cart Infra:**





Jenkins server and jenkins nodejs agent/Azuredevops with self runner.(build,SAST,Docker build image, push image ecr/acr/dockerhub registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS


DEV,QA/UAT, Stage

shipping:
========
github repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/shipping ( sourcecode folder,Jenkinsfile/azure-pipelines.yml,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages Java install,gitleaks,sonarqube vulernability test,docker build,docker image trivy test,
and push image to ecr/acr/dockerhub registry ) ---> agent (Java)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/shipping-argocd.git (helm folder for eks deployment with user ecr/dockhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**shipping Infra:**



Jenkins server/azuredevops and jenkins agent/self runner agent.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registery,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage

payment:
========
github repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/payment ( sourcecode folder,Jenkinsfile/azure-pipelines.yml,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages python install,gitleaks,sonarqube vulernability test,docker build,docker image trivy test,
and push image to ecr/acr/dockerhub registry ) ---> agent (python insatll)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/payment-argocd.git (helm folder for eks deployment with user ecr/docker hub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**payment Infra:**





Jenkins server/azuredevops and jenkins agent/self runner agent.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage


**dispatch:**
========
github repo for CI: https://vaniminadevops@dev.azure.com/vaniminadevops/roboshop/_git/dispatch ( sourcecode folder,Jenkinsfile/azure-pipelines.yml,Dockerfile)
ci : Jenkins server/Azuredevops with self runner(pipeline stages go install,gitleaks,sonarqube vulernability test,docker build,docker image trivy test,
and push image to ecr/acr/dockerhub registry ) ---> agent (go install)
dynamic analysis source code test (DAST) uses veracode tool
github repo for delivery/deployment:  https://github.com/iam-vanimina/dispatch-argocd.git (helm folder for eks/k8s deployment with user ecr/dockerhub/acr image with required version in manifest/deploymnt image, networkpolicy,hpa,values)

**dispatch Infra:**




Jenkins server/azuredevops and jenkins agent/self runner agent.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage










----------------------------------------------------------------------------------------------------------------------------
Author: **Venkata Ram Vanimina**
