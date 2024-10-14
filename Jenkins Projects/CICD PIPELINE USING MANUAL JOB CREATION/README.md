# Jenkins CI/CD Pipeline with GitHub Webhook Integration

## Project Overview
This project demonstrates the implementation of a CI/CD pipeline using Jenkins with GitHub webhook integration. The pipeline includes automated builds, static code analysis using SonarQube, versioning and storage of artifacts in Nexus, and deployment of the application to a separate server.

---

**Documentation**: A Word document detailing the step-by-step approach to build the project and the results can be found [here](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/CICD%20PIPELINE%20USING%20JENKINS%20WITH%20MANUAL%20JOBS%20CREATION.docx).

## Features
- **Webhook-Triggered Builds**: Automatically triggers builds in Jenkins whenever code is pushed to the GitHub repository.
- **SonarQube Integration**: Performs static code analysis and ensures that code quality and security checks are met before moving further in the pipeline.
- **Nexus Artifact Storage**: Builds are stored in a Nexus repository for version control and future use.
- **Multi-Server Deployment**: The build occurs on one server, while the application is deployed on a separate server.
- **Automated Job Chaining**: Post-build actions automatically trigger subsequent jobs for deployment and testing.

## Source Code and Repository Ownership
- **Source Repository Owner**: The source code for this project was forked from [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms).
- **Modifications and Customizations**: The forked repository has been customized to implement a CI/CD pipeline, which includes additional integrations with SonarQube, Nexus, and deployment strategies.

---

## Pipeline Workflow
1. **Code Push**: Developers push code to the GitHub repository.
2. **Jenkins Trigger**: A webhook sends an HTTP POST request to Jenkins, which triggers the build job automatically.
3. **SonarQube Analysis**: Jenkins first runs a SonarQube analysis to check for code quality issues and potential bugs.
4. **Build and Package**: The code is built and packaged into a deployable artifact.
5. **Nexus Storage**: The artifact is stored in Nexus for version control and future deployments.
6. **Deploy to Node/Server**: The artifact is automatically deployed on a separate server, ensuring separation between build and deployment environments.
7. **Email Notification**: Once the job is completed, an email notification is sent to the development team with the build status and any relevant information.

---

## Detailed Setup Instructions

### 1. Forking the Repository
- Start by forking the original repository from [Original Repo Owner's GitHub](URL_TO_ORIGINAL_REPO).
- Clone your forked repository to make local changes.

### 2. Jenkins Job Configuration
- **Webhook Setup**: Configure a webhook in GitHub to notify Jenkins of any changes pushed to the repository.
- **Jenkins Job**:
  - Create a freestyle job in Jenkins and configure it to pull code from the forked GitHub repository.
  - Set up triggers for the job to start automatically upon receiving a webhook notification.
  - Integrate SonarQube for code quality analysis as the first step.
  - Configure Nexus to store build artifacts after a successful build.
  - Add post-build steps to deploy the artifact to the target server.

### 3. Deployment Configuration
- **Separate Server**: Set up a separate server (or node) for the deployment of the application. Jenkins can use SSH or an agent to deploy the artifact automatically after a successful build.
- **Automation**: Implement automatic deployment scripts using shell scripts, Ansible, or other tools to streamline the deployment process.

### 4. Nexus Setup
- Configure Nexus to act as the artifact repository, ensuring all built versions are stored securely and can be accessed for future deployments or rollbacks.

---

## Pipeline & Result ScreenShots
Feel free to add any images or diagrams that better illustrate the pipeline and workflow.

- **Jenkins Pipeline**:

  ![Jenkins Pipeline Diagram](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/pipeline1.png)

- **Commands used and Results**:

  ![Commands for sonarqube](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/Picture1.png)

  ![email notification](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/Picture2.png)

  ![Nexus repo Upload](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/Picture3.png)

  ![Nexus Repo Download](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20PIPELINE%20USING%20MANUAL%20JOB%20CREATION/Picture4.png)

---

## Tools & Technologies Used
- **Jenkins**: To automate the build and deployment process.
- **GitHub**: Source control management and integration with Jenkins via webhooks.
- **SonarQube**: To ensure code quality and security through static analysis.
- **Nexus**: Repository manager for storing and managing artifacts.
- **Separate Server Deployment**: The application is built on one system and deployed on a separate server to ensure an isolated deployment environment.

---

## Future Enhancements
- Had also Implemented Jenkins pipeline scripts (Jenkinsfile) for better pipeline management and version control.
- Improve SonarQube integration by setting up stricter quality gates.
- Use Kubernetes for containerized application deployment or Ansible for automated server provisioning.

---

## Acknowledgments
This project was built upon the source code provided by [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms), and I have added a CI/CD pipeline to enhance the development and deployment workflow.
