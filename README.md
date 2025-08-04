
# 🚀 Node.js CI/CD Pipeline with Jenkins & DockerHub

This project demonstrates a complete CI/CD pipeline for a Node.js web application using **Jenkins**, **Docker**, and **DockerHub**. Every code push triggers an automated workflow that builds the app, runs tests, creates a Docker image, and pushes it to DockerHub.

---

## 📦 Project Structure

```
.
├── Screenshots/
    ├── 1-Jenkins-Dashboard.png
    ├── 2-Build-Status-Output
    ├── 3-Pipeline_Stages
    ├── 4-Dockerhub-Image
    ├── 5-Browser-Output
├── Dockerfile
├── index.js
├── package.json
└── README.md
```

---

## 🛠️ Tech Stack / Tools Used

| Tool            | Purpose                                    |
|-----------------|---------------------------------------------|
| **Node.js**     | Runtime environment for the web app         |
| **Jenkins**     | CI/CD automation engine                     |
| **Docker**      | Containerization of the application         |
| **DockerHub**   | Remote container image registry             |
| **GitHub**      | Source code repository                      |
| **Jenkins Pipeline (Groovy)** | CI/CD logic in pipeline-as-code       |

---

## 🔧 Jenkins Pipeline Flow

1. **Clone Repository** – Fetch latest code from GitHub
2. **Install Dependencies** – Run `npm install`
3. **Build Docker Image** – Create image using `Dockerfile`
4. **Login to DockerHub** – Secure login using Jenkins credentials
5. **Push to DockerHub** – Upload the image to DockerHub registry

---

## 🐳 Dockerfile Overview

```dockerfile
# Use the official Node.js 18 image from Docker Hub as the base image
FROM node:18

# Set the working directory inside the container to /app
# All subsequent commands will be run from this directory
WORKDIR /app

# Copy all files from the current local directory to the working directory in the container
COPY . .

# Install all dependencies defined in package.json
RUN npm install

# Expose port 3000 to allow external access to the app
EXPOSE 3000

# Define the command to run the application
# In this case, run index.js using Node.js
CMD ["node", "index.js"]
```

---

## 🔐 Secure Credentials

Secrets like DockerHub username and password are stored in Jenkins using:
- **Credentials ID**: `dockerhub-creds-id`
- Managed via: `Manage Jenkins → Credentials → Global → Add Credentials`

---

## 🚀 How to Run the App Locally

```bash
git clone https://github.com/yourusername/TASK-1-NodeJs_CI-CD_Pipeline.git
cd TASK-1-NodeJs_CI-CD_Pipeline
npm install
node index.js
```

Visit: [http://localhost:3000](http://localhost:3000)

---

## 🌐 How to Run the App with Docker

```bash
docker build -t sohel7866/nodejs-demo-app .
docker run -p 3000:3000 sohel7866/nodejs-demo-app
```

---

## 💡 What You Learned

- How to write a basic Node.js web app
- How to write a Dockerfile to containerize the app
- How to build a full Jenkins Pipeline with Docker steps
- How to securely store credentials in Jenkins
- How to push Docker images to DockerHub
- How to automate CI/CD workflows end-to-end

---

## 📸 Screenshots

### 1. Jenkins Dashboard
![Jenkins Dashboard](screenshots/1-Jenkins-Dashboard.png)

### 2. Build Status Output
![Build Status](screenshots/2-Build-Status-Output.png)

### 3. Pipeline Stages
![Pipeline Stages](screenshots/3-Pipeline_Stages.png)

### 4. DockerHub Image
![DockerHub](screenshots/4-Dockerhub-Image.png)

### 5. Application Running
![Browser Output](screenshots/5-Browser-Output.png)

---

## 🔗 Useful Links

- [Jenkins Official Site](https://www.jenkins.io/)
- [DockerHub](https://hub.docker.com/)
- [Your GitHub Repo](https://github.com/Sohel9146/TASK-1-NodeJs_CI-CD_Pipeline)

---

## 👨‍💻 Author

**Sohel Shaikh**  
DevOps Intern | Passionate about automation and CI/CD pipelines

---

## 🏁 License

This project is for educational purposes only.
