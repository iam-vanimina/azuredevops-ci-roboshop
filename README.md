
**Azuredevops ci for roboshop application** 

**Roboshop Devop CI**

<img width="956" height="498" alt="image" src="https://github.com/user-attachments/assets/154d1b37-3414-4c88-959b-5bb6c8b4e8b1" />





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


<img width="951" height="440" alt="image" src="https://github.com/user-attachments/assets/1c224456-7ced-4467-b060-7224a8d21045" />


<img width="953" height="470" alt="image" src="https://github.com/user-attachments/assets/3af45447-0c4e-4a3b-9890-c638526fb099" />



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

<img width="945" height="466" alt="image" src="https://github.com/user-attachments/assets/0567519b-1f1b-42d4-b39c-0bee88f1f393" />

<img width="944" height="466" alt="image" src="https://github.com/user-attachments/assets/e973a0ee-06b3-4578-a839-6f230965148b" />

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

<img width="955" height="467" alt="image" src="https://github.com/user-attachments/assets/3d423363-bda5-4f7d-bcad-df66bdb13b9e" />

<img width="952" height="472" alt="image" src="https://github.com/user-attachments/assets/26460571-ecca-4407-9c1c-8890d9549c2e" />



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

<img width="959" height="472" alt="image" src="https://github.com/user-attachments/assets/59431233-7cf0-4251-9e21-baa26fe4b875" />

<img width="955" height="473" alt="image" src="https://github.com/user-attachments/assets/26d8941f-1caa-4a18-91f0-ae5da333753b" />



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

<img width="957" height="471" alt="image" src="https://github.com/user-attachments/assets/5ceff13d-fbe9-4999-995a-60f2e4e9e0ce" />

<img width="958" height="476" alt="image" src="https://github.com/user-attachments/assets/9f8fe5d0-717a-4582-9ff4-5077a0ca1cf9" />


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


<img width="959" height="447" alt="image" src="https://github.com/user-attachments/assets/3014b115-0f1a-4168-8ba6-1b9e8edcf62a" />

<img width="956" height="475" alt="image" src="https://github.com/user-attachments/assets/a7adafd8-fd14-4c33-aac2-2aaa2df46f0c" />


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

<img width="947" height="472" alt="image" src="https://github.com/user-attachments/assets/5db11835-7fd5-450c-9509-3478fcef29e2" />

<img width="957" height="469" alt="image" src="https://github.com/user-attachments/assets/61824c43-c805-4e0c-bd13-25595665c910" />


Jenkins server/azuredevops and jenkins agent/self runner agent.(build,SAST,Docker build image, push image ecr/acr/dockerhub 

registry,trivy scan/aws ecr scan/dockerhub image scan)

k8s cluster for deployment EKS/Docker desktop/AKS/GKS:

DEV,QA/UAT, Stage










----------------------------------------------------------------------------------------------------------------------------
Author: **Venkata Ram Vanimina**
