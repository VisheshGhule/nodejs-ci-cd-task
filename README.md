# 🚀 Task 2 – Jenkins CI/CD Pipeline for Node.js App

This project sets up a complete CI/CD pipeline using Jenkins running in Docker. The pipeline fetches code from GitHub, installs dependencies, runs tests, and simulates deployment for a Node.js application.

### 1. Jenkins Setup Instructions
Pull Jenkins Docker image and run:
```
docker run -d -p 8080:8080 --name jenkins jenkins/jenkins:lts
```
OR 
```
docker pull jenkins/jenkins:lts
```
<img width="619" height="316" alt="1" src="https://github.com/user-attachments/assets/2dbb3108-b7a4-402b-b2d7-3efca5cfdb7e" />
<img width="619" height="200" alt="Screenshot from 2025-08-05 10-40-37" src="https://github.com/user-attachments/assets/07bd5279-8987-4066-a12e-a36aecec2deb" />

## 


### 2. Unlock Jenkins
Visit http://localhost:8080, copy the password from:
```
docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
OR
```
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
<img width="1000" height="84" alt="Screenshot from 2025-08-05 10-41-19" src="https://github.com/user-attachments/assets/83eae16b-e64b-4f5b-81a5-f6c13252776b" />

## 

### 3. Install Suggested Plugins
- During setup, click "Install suggested plugins"
<img width="600" height="347" alt="Screenshot from 2025-08-05 10-41-55" src="https://github.com/user-attachments/assets/92d41646-a233-4a97-adcb-bdacf0219680" />

## 

### 4. Install Additional Plugin:
- Docker Pipeline
- Go to: Setting → Manage Jenkins → Manage Plugins → Available → Search Docker Pipeline → Install without restart

## 

### 5. Install Node.js Inside Jenkins Container
```
docker exec -u 0 -it jenkins bash

# Inside container
apt update
apt install -y curl
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install -y nodejs
node -v
npm -v
```

## 

### 6. Create Jenkins Job
- Go to Jenkins → New Item
- Name: nodejs-ci-cd-pipeline
- Type: Pipeline
- In Pipeline section:
- Definition: Pipeline script from SCM
- SCM: Git
- Repo URL: `https://github.com/VisheshGhule/nodejs-ci-cd-task.git`

## 

### 7. Here CI-CD runs successfully

<img width="1000" height="447" alt="Screenshot from 2025-08-05 13-23-04" src="https://github.com/user-attachments/assets/7c368f36-9fb8-4bd5-ab86-0d45d88c8b95" />

## 

<img width="1000" height="447" alt="Screenshot from 2025-08-05 13-25-16" src="https://github.com/user-attachments/assets/0e62149e-1a94-48ca-8f1c-dcfbf3f0f347" />

##  

<img width="1000" height="447" alt="Screenshot from 2025-08-05 13-26-16" src="https://github.com/user-attachments/assets/d8761f0f-d454-41de-a1e1-278c7a100a0a" />

##  

<img width="1000" height="447" alt="Screenshot from 2025-08-05 13-43-46" src="https://github.com/user-attachments/assets/f83c085e-d459-40da-bc66-9a30ddd1a223" />

<br><br><br>
<br><br><br>
<br><br><br>
<br><br><br>
<br><br><br>
<br><br><br>

---

# 🚀Task 1 - Node.js CI/CD Pipeline with GitHub Actions & DockerHub

This project was created for the DevOps Internship Task:  
**Automate Code Deployment Using CI/CD Pipeline (GitHub Actions)**

---

## ✅ Objective

Set up a CI/CD pipeline that:
- Automatically builds a Docker image from a Node.js app
- Pushes the image to DockerHub
- Runs every time code is pushed to the `main` branch

---

## 🛠 Technologies Used

- Node.js (Express app)
- Docker
- GitHub
- GitHub Actions
- DockerHub

---

## 📦 What I Did Step-by-Step

### 1. **Created a Simple Node.js App**
- Built a small Express.js app (`index.js`)
- Added `package.json` with `express` dependency

### 2. **Dockerized the Application**
- Wrote a `Dockerfile` to:
  - Use Node.js Alpine image
  - Install dependencies
  - Run the app on port 3000

### 3. **Pushed the Project to GitHub**
- Created a GitHub repo named `nodejs-ci-cd-task`
- Pushed all local project files using Git

### 4. **Created GitHub Actions Workflow**
- Added a workflow file at `.github/workflows/main.yml`
- The workflow:
  - Triggers on push to `main`
  - Builds Docker image
  - Pushes image to DockerHub

### 5. **Added GitHub Secrets**
- `DOCKER_USERNAME`: my DockerHub username
- `DOCKER_PASSWORD`: DockerHub access token (not password)

### 6. **Triggered the Pipeline**
- Made a small change (like editing `README.md`)
- GitHub Actions ran automatically and:
  - ✅ Built the Docker image
  - ✅ Logged in to DockerHub
  - ✅ Pushed the image successfully
 
  <img width="1366" height="554" alt="Screenshot from 2025-08-04 16-44-34" src="https://github.com/user-attachments/assets/f25e0261-3ba1-49ea-8cea-39dc4267fe63" />
  <img width="1365" height="567" alt="Screenshot from 2025-08-04 16-48-10" src="https://github.com/user-attachments/assets/7d5f2c9d-43d0-4c9e-8c1e-f83e9a833c84" />

---

## 📥 DockerHub Image

You can find the built image here:  
🔗 [https://hub.docker.com/r/visheshghule/nodejs-demo-app](https://hub.docker.com/r/visheshghule/nodejs-demo-app)

---

## 📂 Repository Link

🔗 [https://github.com/VisheshGhule/nodejs-ci-cd-task](https://github.com/VisheshGhule/nodejs-ci-cd-task)

---

## 🙏 Thank You

This project helped me understand:
- CI/CD using GitHub Actions
- Docker image build/push workflow
- Automation using GitHub Secrets and DockerHub

