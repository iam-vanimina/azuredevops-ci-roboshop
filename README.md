
**Azuredevops ci for roboshop application** 

**Roboshop Devop CI**


<img width="950" height="470" alt="image" src="https://github.com/user-attachments/assets/c8f1435d-3ec1-4d06-8f6f-706662296d8d" />





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

<img width="957" height="475" alt="image" src="https://github.com/user-attachments/assets/55c93c77-feaa-4f54-a92e-59bc0a94dcb4" />

<img width="943" height="471" alt="image" src="https://github.com/user-attachments/assets/c6df4d66-3733-47c0-9ccf-403e8d6b4bbf" />


<img width="953" height="473" alt="image" src="https://github.com/user-attachments/assets/e47bc57d-2ed5-4213-9607-c2a676cf2353" />



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

<img width="935" height="468" alt="image" src="https://github.com/user-attachments/assets/50283414-d8c1-4f79-a7f3-b7dd427afbc0" />

<img width="958" height="473" alt="image" src="https://github.com/user-attachments/assets/734f2f09-bb39-4144-a09e-eafeb9faa960" />


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

<img width="955" height="476" alt="image" src="https://github.com/user-attachments/assets/06941ce6-98a8-4f51-84b2-375d7eebee4e" />

<img width="956" height="470" alt="image" src="https://github.com/user-attachments/assets/000a0b2b-eaa9-4cc9-9b45-782fe4b1e004" />



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

<img width="948" height="471" alt="image" src="https://github.com/user-attachments/assets/981a6fec-e9fc-4e86-8fb3-60153580ad31" />

<img width="958" height="470" alt="image" src="https://github.com/user-attachments/assets/21354f45-ec5d-4b79-83d7-999e86152017" />





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

<img width="953" height="477" alt="image" src="https://github.com/user-attachments/assets/0adf5742-cd0c-498a-b176-86036f1f95d9" />

<img width="952" height="475" alt="image" src="https://github.com/user-attachments/assets/a324fddf-1499-4940-8ebb-7bce9f0c2215" />


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

<img width="952" height="478" alt="image" src="https://github.com/user-attachments/assets/ce5a14bb-f214-4dcb-9293-7bce1df7f677" />

<img width="959" height="472" alt="image" src="https://github.com/user-attachments/assets/9ae5b5f5-979a-4600-8084-153707918d6f" />



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

<img width="959" height="469" alt="image" src="https://github.com/user-attachments/assets/42f03d2a-bf5a-4a04-a57f-186ac6d95bd5" />

<img width="954" height="479" alt="image" src="https://github.com/user-attachments/assets/e263fe1c-5cf6-4473-a181-d824106b60b3" />


Jenkins server/azuredevops and jenkins agent/self runner agent.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
In this roboshop ci project pushed the docker images to docker hub registry namespace vanimina to specific repository as per each microservice respectively.  Later on we will use these docker images for roboshop argocd deployments.

<img width="959" height="469" alt="image" src="https://github.com/user-attachments/assets/7b4e2d36-4d19-4bf1-b647-3251f915f489" />








----------------------------------------------------------------------------------------------------------------------------
Author: **Venkata Ram Vanimina**
