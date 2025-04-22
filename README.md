# 🚀 Dockerized App Deployment to AWS EC2 via GitHub Actions


<img width="1268" alt="Screenshot 2025-04-22 at 4 33 32 PM" src="https://github.com/user-attachments/assets/b6888ba0-728e-4a4b-8038-89f36488d2c2" />


This project demonstrates how to automatically deploy a Dockerized web application to an Amazon EC2 instance using **GitHub Actions**.

The pipeline:
- Builds and runs a containerized app using Docker
- Transfers code from GitHub to EC2 using SCP
- Starts the app inside a Docker container on EC2
- Exposes it via port `80` to the public

---

## 🧱 Tech Stack

- **Amazon EC2 (Amazon Linux 2)** – Hosting the Docker container
- **Docker** – Containerizing the application
- **GitHub Actions** – CI/CD automation
- **SCP/SSH** – Secure file transfer and remote execution
- **Nginx or Static Web Server** – Serving HTML/CSS/JS content (based on your Dockerfile)

---
# Add Secrets to Github
<img width="1440" alt="Screenshot 2025-04-22 at 2 16 01 PM" src="https://github.com/user-attachments/assets/4c2ff5c6-d120-407c-ac27-1e457dd37d3c" />

# Github Actions
<img width="1440" alt="Screenshot 2025-04-22 at 2 30 29 PM" src="https://github.com/user-attachments/assets/087e67e8-0652-44b4-85a6-ac776041e10e" />

# Application
<img width="1440" alt="Screenshot 2025-04-22 at 2 32 11 PM" src="https://github.com/user-attachments/assets/9d2ba029-0a5e-487d-b362-b8d8b7f22de4" />


## 🛠️ How It Works

1. **Push to GitHub** – Any commit to the `main` branch triggers the workflow.
2. **GitHub Actions** – Executes a CI/CD pipeline:
    - Transfers code to EC2 via `appleboy/scp-action`
    - Remotely logs in via `appleboy/ssh-action`
    - Builds Docker image and runs the container
3. **EC2 Instance** – Runs your container and exposes your web app at:
