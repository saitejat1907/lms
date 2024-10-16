# Dockerized 3-Tier Application with Backend, Frontend, and Postgres Database

## Project Overview
This project demonstrates a Dockerized 3-tier architecture for an application consisting of a Postgres database, a Node.js backend, and a React frontend. The backend and frontend have been containerized using Docker, and the respective Docker images are stored on Docker Hub. The Postgres database is used to store the application's data.

## Features
- **Dockerized 3-Tier Application**: Each tier of the application (frontend, backend, and database) is containerized using Docker.
- **Postgres Database**: A Postgres container is used for data persistence.
- **Docker Hub**: The Docker images for both the backend and frontend are available on Docker Hub for easy access and deployment.

## Application Architecture
1. **Postgres Database**: Used as the data layer to store application data.
2. **Backend (Node.js)**: A Node.js backend that handles business logic and API requests. It communicates with the Postgres database.
3. **Frontend (React)**: A React application built using Vite, served via Nginx. It provides the user interface for interacting with the backend.

---

## Docker Hub
The Docker images for both the backend and frontend are available on Docker Hub:

- **Backend Docker Image**: [Backend Image on Docker Hub](https://hub.docker.com/repository/docker/saiteja19799/lms/general)
- **Frontend Docker Image**: [Frontend Image on Docker Hub](https://hub.docker.com/repository/docker/saiteja19799/lms-fe/general)

---

## Setup Instructions

### 1. Clone the Repository
Fork the original repository and clone it to your local machine.

```bash
git clone https://github.com/yourusername/your-forked-repo.git
```

### 2. Build and Run Docker Containers
To build and run the Docker containers for the backend and frontend, follow the steps below:

#### Backend:
```bash
docker build -t yourusername/backend-image .
docker run -p 8080:8080 yourusername/backend-image
```
#### Frontend:
```bash
docker build -t yourusername/frontend-image .
docker run -p 80:80 yourusername/frontend-image
```
### 3. Postgres Database Setup
You can run the Postgres database container using the following command:

```bash
docker run --name postgres-db -e POSTGRES_PASSWORD=yourpassword -d postgres
```

---

- **Database Configuration**:

  ![Database Configuration](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture1.png)

- **Building Backend Image**:

  ![Building Backend Image](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture2.png)

- **Creating a container f0r Backend LMS**:

  ![Creating a container f0r Backend LMS](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture3.png)

- **Testing Backend Image**:

  ![Testing Backend Image](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture4.png)

- **Backend Image Testing Result**:

  ![Backend Image Testing Result](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture5.png)

- **Building Frontend Image**:

  ![Database Configuration](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture6.png)

- **Frontend Image Testing Result**:

  ![Database Configuration](https://github.com/saitejat1907/lms/blob/main/Docker%20Projects/LMS%20APPLICATION%20DOCKERIZATION/Images/Picture7.png)

---

### Future Enhancements
- Implement a Jenkins pipeline to automate the build and deployment of the Docker images.
- Add monitoring and logging for Docker containers.
- Implement Kubernetes for container orchestration.

---

### Acknowledgments
This project was based on the source code from [Original Repo Owner's GitHub](https://github.com/ravi2krishna/lms), with additional modifications to create a Dockerized 3-tier application.
