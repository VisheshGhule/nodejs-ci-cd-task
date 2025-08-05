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

