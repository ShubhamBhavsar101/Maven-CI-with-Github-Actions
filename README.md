

# 🚀 Maven CI/CD with GitHub Actions

This project demonstrates how to set up **Continuous Integration (CI)** and **Continuous Deployment (CD)** for a Maven project using **GitHub Actions**, **Docker Hub**, and **AWS EC2**.

---

## 📋 Steps Overview

### ✅ CI Pipeline (Continuous Integration)

1. Go to the **Actions** tab in your GitHub repository and select **Configure with Maven**.
2. GitHub Actions will:
   - Checkout the current repository.
   - Set up Maven and package the application into a `.jar` file.
3. A **Docker image** will be built using the provided `Dockerfile`.
4. The image will be **pushed to Docker Hub** using credentials stored as GitHub **Variables** and **Secrets**.

---

### ✅ CD Pipeline (Continuous Deployment)

1. Configure an **EC2 instance** as a **self-hosted GitHub runner**.
2. Create a `Maven-CD.yaml` workflow file for deployment to the EC2 instance.
3. In the deployment job:
   - Pull the latest Docker image from Docker Hub.
   - Stop and remove any existing Docker containers (if running).
   - Run a new container, exposing ports `80:8080`.

---

## 🔥 How to See it in Action

1. Push to the `main` branch or create a pull request targeting the `main` branch.
2. The **Maven CI** workflow will trigger automatically, build the Docker image, and push it to Docker Hub.
3. After the CI workflow succeeds, the **Maven CD** workflow will start.
4. The latest Docker image will be pulled and deployed to the EC2 instance.
5. Access your running application via:

   ```
   http://[EC2-PUBLIC-IP]
   ```

> **Note:** The application inside the container runs on port `8080`, but it's mapped to port `80` on the EC2 instance for easy access.

---

## 📦 Tech Stack

- **Maven** (Build Tool)
- **Docker** (Containerization)
- **Docker Hub** (Container Registry)
- **GitHub Actions** (CI/CD Pipelines)
- **AWS EC2** (Deployment Target)

---

## 📜 Prerequisites

- A GitHub repository.
- Docker Hub account.
- An AWS EC2 instance (Ubuntu/any Linux).
- Proper security group settings for EC2 (allow inbound HTTP on port 80).

---

## 📌 Additional Notes

- Make sure Docker is installed and running on the EC2 instance.
- Ensure the GitHub Runner service on EC2 has access to Docker (use the right user permissions).
- Secrets such as `DOCKER_USERNAME` and `DOCKER_PASSWORD` must be properly configured in the GitHub repository settings.
