# Devops_Project

To automate the deployment process using Jenkins for Continuous Integration and Continuous Deployment (CI/CD) using Git, Jenkins, Ansible And Tomcat.

## 🏴 Purpose:

The primary goal of this project is to establish a seamless and automated process for building, testing, and deploying a Java web application. The use of Jenkins as the CI/CD orchestrator, Git for version control, and Ansible for configuration management enhances collaboration and guarantees consistency across different environments.

## ⏬ Key Features:

### 1. Continuous Integration (CI):

Jenkins is configured to monitor the Git repository for code changes.
Automated builds are triggered upon new commits to the repository.
Code compilation and execution of comprehensive tests are part of the CI pipeline.

### 2. Continuous Deployment (CD):

Jenkins orchestrates the deployment process by copying artifacts generated during the CI phase.
Ansible is employed for configuration management, ensuring that the application is deployed consistently on target servers.
Tomcat serves as the application server, and Ansible handles its installation, configuration, and service management.

### 3. Efficient Version Control:

Git is utilized for version control, offering a reliable and scalable way to manage code changes.
Branching strategies are implemented to facilitate development, testing, and production workflows.

## ☑️ Prerequisites

Before getting started, ensure you have the following installed:

### A. Jenkins Server:

- To setup jenkins refer to Jenkins repository ➡️(https://github.com/Rathodrahul3/Jenkins)
- Install git : `sudo yum install git -y `
  #### Maven Setup:
  - Download binary maven file from offical documentaion ➡️ [Maven](https://maven.apache.org/download.cgi)
  E.g `sudo wget https://dlcdn.apache.org/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz`
  - Extract file into opt folder : `sudo tar -xvzf apache-maven-3.8.8-bin.tar.gz -C /opt/`
  - Set environment variables to maven :-
  ```
       export M2_HOME=/opt/apache-maven-3.8.8
       export PATH=$PATH:$M2_HOME/bin
  ```
### B. Ansible Server:

- Installed Python3 and Ansible package.
- Create Ansible user and setup password.
- Give root previliages to ansible user.
- Enable password base authentication.
- Create directory /opt/ansible and change ownership to user.
- Write ansible playbook to copy file from anible server to application server.
- Generate ssh-keys to connect control node server without password.

### C. Application Server:

- Installed Python3 package.
- Create and setup same as ansible user and password.
- Give root previliages to ansible user.
- Enable password base authentication.
  #### Tomcat Setup:
  - To setup Tomcat refer to repository ➡️(https://github.com/Rathodrahul3/Tomcat-Setup)
  - Make sure Tomcat application user and ansible user same to aviod any error.
 
Now copy ssh-keys from ansible to tomcat server to setup ssh connection between them.

# ▶️ Set up CI/CD Pipeline.
- Login to jenkins and configure Maven path.
- We need to download some plugins.
  - A. Publish over ssh
  - B. Maven Integration.
- To configure Publish over ssh pulgin Navigate to manage jenkins then system scroll down u will find and Click on ssh add servers and do changes as per below Image.

  ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/56b74a82-98cf-4d79-a33e-3b5b33890dac)
  
- Now we ready to go setup job
- New item ➡️ maven project ➡️ add git repo and then add below details⤵️
 ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/fc016401-cf69-4aad-a294-b562c69ec395)

- Now in post build scetion select Send files or execute commands over SSH.
 ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/84f1d856-9eda-4c4e-8b93-1090b97fbf23)

- We need to add info accordingly and here we will not send exec command for that we will add another post build.
 ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/65749a46-b546-4c03-8d57-3ff9300d8742)

- To excute anible playbook here we need to give full path of file.
 ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/cff5211c-ce7a-443d-bc94-92c750b054ed)

- In build trigger add poll scm so that any changes made in repo the job will trigger and it will monitor repo at evry minute.
 ![image](https://github.com/Rathodrahul3/Devops_Project/assets/128371993/092bb468-4ed7-4c46-bc52-1d93f0148493)

# Usage
  1. Make changes to your code.
  2. Commit changes to the repository.
  3. Observe the automated CI/CD pipeline in action!

### You can access tomcat application server at (http://YOUR-SERVER-PUBLIC-IP:8080/Hello_World_warproject/)




