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
  E.g `sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.2/binaries/apache-maven-3.9.2-bin.tar.gz`
  - Extract file into opt folder : `sudo tar -xvzf apache-maven-3.9.2-bin.tar.gz -C /opt/`
  - Set environment variables to maven :-
  ```
       export M2_HOME=/opt/apache-maven-3.9.2
       export PATH=$PATH:$M2_HOME/bin
  ```
### B. Ansible Server:

- Installed Python3 and Ansible package.
- Create Ansible user and setup password.
- Give root previliages to ansible user.
- Enable password base authentication.
- Generate ssh-keys to connect control node server without password.

### C. Application Server:

- Installed Python3 package.
- Create and setup same as ansible user and password.
- Give root previliages to ansible user.
- Enable password base authentication.
  #### Tomcat Setup:
  - To setup Tomcat refer to repository ➡️(https://github.com/Rathodrahul3/Tomcat-Setup)
  - Make sure Tomcat application user and ansible user same to aviod any error.
