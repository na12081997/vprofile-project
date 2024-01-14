# End to End Continuous Integration - Continous Deployment of Java Project using Jenkins and docker

# Continuous Integration using Jenkins - Java 

## Tools Used
- **IDE:** Visual Studio Code
- **Code Commit:** Git
- **Version Control System:** GitHub
- **Continuous Integration Server:** Jenkins
- **Code Analysis:** Checkmate with SonarQube Scanner Plugin
- **Code Analysis Report:** SonarQube Server
- **Code Build:** Maven
- **Artifact Repository Server:** Nexus
- **Notification:** Slack
- **Cloud:** AWS (EC2 Server)
- **staging Branch:** cicd-Jenkins
- **Production Branch:** Prod

## Flow of Execution

1. **Code Changes:**
   - Developers make code changes and commit them via Git to the GitHub repository.

2. **Jenkins Trigger:**
   - Jenkins, hosted on an AWS EC2 instance, monitors the GitHub repository for changes.
   - When changes are detected, Jenkins initiates the continuous integration process.

3. **Unit Testing:**
   - Jenkins starts with unit tests using JUnit before the code build step.

4. **Code Analysis:**
   - Checkmate tool with SonarQube Scanner Plugin analyzes the code.
   - Analysis results are published as reports on the SonarQube server hosted on an AWS EC2 instance.

5. **Quality Gates:**
   - The code is evaluated against quality gates criteria on the SonarQube server.

6. **Code Build with Maven:**
   - If the code passes quality gates, Maven builds the code.
   - Dependencies are downloaded from the Nexus server hosted on an AWS EC2 instance during the build process.

7. **Artifact Repository:**
   - The built artifact is sent to the artifact repository on the Nexus server hosted on an AWS EC2 instance.

8. **Slack Notifications:**
   - Slack notifications are sent at each stage of the continuous integration process.
   - Failure notifications are sent in case of any issues.

9. **Success Notification:**
   - Once the build is successfully completed, a success notification is sent via Slack.

## Setting Up the Environment

1. **Install Visual Studio Code:**
   - [Download Visual Studio Code](https://code.visualstudio.com/)

2. **Configure Git:**
   - Set up Git and configure it with your GitHub account.

3. **Jenkins Configuration:**
   - Install and configure Jenkins on an AWS EC2 instance.
   - Set up Jenkins to monitor your GitHub repository.

4. **SonarQube Server:**
   - Install and configure SonarQube server on an AWS EC2 instance.
   - Set up SonarQube Scanner in Jenkins.

5. **Maven Installation:**
   - [Download and Install Maven](https://maven.apache.org/download.cgi)

6. **Nexus Server:**
   - Install and configure Nexus server on an AWS EC2 instance.

7. **Slack Integration:**
   - Set up a Slack workspace and integrate it with Jenkins for notifications.

8. **AWS EC2 Server:**
   - If using AWS, host Jenkins, SonarQube, and Nexus servers on EC2 instances.

## Notes
- Update Jenkinsfile, pom.xml, and other configuration files as per your project requirements.
- Ensure that necessary plugins and permissions are set in Jenkins.
- Customize Slack notifications to fit your team's needs.
- Regularly update dependencies and review quality gate criteria.


# Continuous Deployment using jenkins and docker - Java Project

This repository contains a Java project with continuous deployment implemented using Jenkins, Docker, and other related tools.

## Tools Used

- **IDE:** Visual Studio Code
- **Code Commit:** Git
- **Version Control System:** GitHub
- **Continuous Integration Server:** Jenkins
- **Code Analysis:** Checkmate with SonarQube Scanner plugin
- **Code Analysis Report:** SonarQube Server
- **Code Build:** Maven
- **Notification:** Slack
- **AWS Cloud:**
  - EC2 Server
  - Docker
  - Amazon ECR (Elastic Container Registry)
  - Amazon CLI
  - Amazon ECS (Elastic Container Service)

## Flow of Execution

1. **Code Changes:**
   - Developer makes code changes, commits, and pushes to GitHub repository.

2. **Continuous Integration with Jenkins:**
   - Jenkins automatically fetches the latest code commit.
   - Unit tests using JUnit are executed before the code build step.

3. **Code Analysis:**
   - Code is analyzed using Checkmate tool with SonarQube Scanner plugin.
   - Test results are published as reports in the SonarQube Server.
   - Quality gates criteria are checked in the SonarQube Server.

4. **Code Build with Maven:**
   - If the code passes quality gates, Maven is used to build the Java application.

5. **Docker Image Build:**
   - Tomcat Docker image is built with the application artifact.
   - Docker image is published to Amazon ECR (Elastic Container Registry).

6. **Deployment to Amazon ECS:**
   - Using Amazon CLI, the Docker image is deployed to Amazon ECS (Elastic Container Service).
   - ECS fetches the latest image from ECR and runs the application.

7. **Slack Notifications:**
   - Slack notifications are sent during each stage of the continuous deployment process.
   - Failure notifications are sent in case of any issues.

8. **Success Notification:**
   - Once the build is successfully completed, a success notification is sent via Slack.

## Prerequisites

Ensure you have the following tools installed and configured:
- Docker
- Maven
- Jenkins
- SonarQube Server
- Amazon CLI

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repository.git


## Reference:

1. Sourcecode for this project is used from the public repository.
