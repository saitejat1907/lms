# Dockerized E-Commerce Application with Versioning

## Project Overview
This project involves dockerizing an e-commerce web application primarily built using HTML. Different versions of the application were created, containerized using Docker, and tested by running containers from each version. All Docker images were tagged with version numbers and pushed to Docker Hub for storage and easy retrieval.

## Features
- **Versioning of Docker Images**: Each version of the application was built and tagged with a version number, allowing for easy tracking and deployment of specific versions.
- **Containerization**: The application was containerized using Docker, simplifying the deployment process.
- **Docker Hub Integration**: Docker images were pushed to Docker Hub, enabling version control and easier sharing.
- **Testing Multiple Versions**: Different versions of the application were tested by running containers from each image, ensuring consistency and compatibility.

## Link to Documentation
For a detailed step-by-step approach to building the project, refer to the [Project Documentation](https://github.com/saitejat1907/lms/blob/main/Jenkins%20Projects/CICD%20Pipeline%20Jenkins%20Script/Documentation.docx).

## Docker Hub
The Docker images for the different versions of the e-commerce application are available on Docker Hub:

- **Version 1.0**: [Version 1.0 Summer collection Image on Docker Hub](https://hub.docker.com/layers/saiteja19799/ecomm/v3-Summer/images/sha256-7d4a43d844c9f31e16482e6d500dc844ff53449b56fa78ac9c2cf903e7fe470b?context=repo)
- **Version 2.0**: [Version 2.0 spring collection on Docker Hub](https://hub.docker.com/layers/saiteja19799/ecomm/v2-spring/images/sha256-30b81e379fa18d2e81e8c45a3acf0fd017cf4b8784f154a2fb08e97ba3afec64?context=repo)
- **Version 3.0**: [Version 3.0 fall collection Image on Docker Hub](https://hub.docker.com/layers/saiteja19799/ecomm/v1-fall/images/sha256-e98d18d823db472ca828330f4319e3cf7bdb3b7a0dcc5ec9020ba138b06dcb51?context=repo)

---

## Setup Instructions

### 1. Clone the Repository
Fork the original repository and clone it to your local machine.

```bash
git clone https://github.com/saitejat1907/ecomm
```
## Build and Run Docker Containers for Different Versions

### Version 1.0

1. **Build the Docker image for version 1.0:**
   ```bash
   docker build -t <your-dockerhub-username>/app:v1.0 .
   ```
### Version 2.0

2. **Build the Docker image for version 2.0:**
   ```bash
   docker build -t <your-dockerhub-username>/app:v2.0 .
   ```
### Version 3.0

3. **Build the Docker image for version 3.0:**
   ```bash
   docker build -t <your-dockerhub-username>/app:v3.0 .
   ```
---
### Run the Docker container for version 1.0:

```bash
docker run -d -p 8080:80 --name app_v1 <your-dockerhub-username>/app:v1.0
```
---

### Verify the running container:

```bash
docker ps
```
---
### Check the application in your browser:
Open [http://localhost:8080](http://localhost:8080) to view version 1.0 of the application.


### Versioning Strategy
Each time the code was updated, the corresponding Docker image was built with a new version tag:

- **Version 1.0** was the initial release.
- **Version 2.0** includes minor updates and bug fixes.
- **Version 3.0** adds new features to enhance the application.

By tagging each Docker image with a specific version number, you can easily switch between versions and roll back if necessary.

---
### Future Enhancements
- Automate the versioning process using a CI/CD pipeline.
- Implement a testing framework to automatically verify each version of the application.
- Containerize the backend of the application and connect it with the frontend using Docker Compose.

---

### Acknowledgments
This project is based on the e-commerce application template. The Dockerization and versioning process were customized to fit the project's requirements, focusing on easy deployment and version control via Docker Hub.

