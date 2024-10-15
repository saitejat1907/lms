# Jenkins CI/CD Pipeline with GitHub Webhook Integration

## Project Overview
This project demonstrates the implementation of a CI/CD pipeline using Jenkins with GitHub webhook integration. The pipeline includes automated builds, static code analysis using SonarQube, versioning and storage of artifacts in Nexus, and deployment of the application on the same server.

## Features
- **Webhook-Triggered Builds**: Automatically triggers builds in Jenkins whenever code is pushed to the GitHub repository.
- **SonarQube Integration**: Performs static code analysis and ensures that code quality and security checks are met before moving further in the pipeline.
- **Nexus Artifact Storage**: Builds are stored in a Nexus repository for version control and future use.
- **Local Server Deployment**: The build and deployment occur on the same server, simplifying the infrastructure.
- **Automated Job Chaining**: Post-build actions automatically trigger subsequent jobs for deployment and testing.

## Source Code and Repository Ownership
- **Source Repository Owner**: The source code for this project was forked from [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms).
- **Modifications and Customizations**: The forked repository has been customized to implement a CI/CD pipeline that includes additional integrations with SonarQube, Nexus, and deployment strategies.

## Link to Documentation
For a detailed step-by-step approach to building the project, refer to the [Project Documentation](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Documentation.docx).

---

## Pipeline Workflow
1. **Code Push**: Developers push code to the GitHub repository.
2. **Jenkins Trigger**: A webhook sends an HTTP POST request to Jenkins, which triggers the build job automatically.
3. **SonarQube Analysis**: Jenkins first runs a SonarQube analysis to check for code quality issues and potential bugs.
4. **Build and Package**: The code is built and packaged into a deployable artifact.
5. **Nexus Storage**: The artifact is stored in Nexus for version control and future deployments.
6. **Deploy to Server**: The artifact is automatically deployed on the same server, ensuring a streamlined process.
7. **Email Notification**: Sends an email notification once the job is completed to inform the team of the build status.

---

## Jenkins Job Configuration
For the detailed configuration of the Jenkins job, you can find the setup instructions in the following link: [Jenkins Job Configuration](https://github.com/saitejat1907/lms/blob/main/Jenkinsfile).

---

## Detailed Setup Instructions

### 1. Forking the Repository
- Start by forking the original repository from [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms).
- Clone your forked repository to make local changes.

### 2. Jenkins Job Configuration
- **Webhook Setup**: Configure a webhook in GitHub to notify Jenkins of any changes pushed to the repository.
- **Jenkins Job**:
  - Create a new pipeline job in Jenkins and configure it to pull code from the forked GitHub repository.
  - Set up triggers for the job to start automatically upon receiving a webhook notification.
  - Integrate SonarQube for code quality analysis as the first step.
  - Configure Nexus to store build artifacts after a successful build.
  - Add post-build steps to deploy the artifact to the server.

### 3. Nexus Setup
- Configure Nexus to act as the artifact repository, ensuring all built versions are stored securely and can be accessed for future deployments or rollbacks.

---

## Images & Diagrams
Better illustrate the pipeline workflow and results.

- **Jenkins Pipeline**:

  ![Jenkins Pipeline Diagram](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/pipeline1.png)

- **Commands used and Results**:

  ![Jenkinsfile](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Images/Picture1.png)

  ![Console Output](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Images/Picture2.png)

  ![SonarQube Analysis](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Images/Picture3.png)

  ![Nexus Repo Storing Artifacts](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Images/Picture4.png)

  ![Pipeline Execution Result](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Images/Picture5.png)

---

## Tools & Technologies Used
- **Jenkins**: To automate the build and deployment process.
- **GitHub**: Source control management and integration with Jenkins via webhooks.
- **SonarQube**: To ensure code quality and security through static analysis.
- **Nexus**: Repository manager for storing and managing artifacts.

---


## Acknowledgments
This project was built upon the source code provided by [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms), and I have added a CI/CD pipeline to enhance the development and deployment workflow.
