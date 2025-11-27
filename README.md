# ✅ **README.md (Final Version — DiscoverDollar DevOps Assignment)**


# Discover Dollar — DevOps Engineer Intern Assignment  
MEAN Stack Application | Docker | Docker Compose | CI/CD | Nginx | Cloud Deployment

## 👤 Candidate Details
**Name:** Hari Om  
**Position Applied:** DevOps Engineer Intern  
**Assignment Date:** 27 November 2025  

---

# 📌 Project Overview  
This repository contains the complete DevOps assignment for Discover Dollar.  
The task involves containerizing, deploying, and automating CI/CD for a full-stack **MEAN application**.

The project includes:

- Dockerfiles for **frontend** and **backend**
- **MongoDB** container or native installation option
- **Docker Compose** for multi-container orchestration
- **GitHub Actions CI/CD** pipeline
- **Nginx reverse proxy** on port 80
- Cloud deployment on an Ubuntu VM (AWS / Azure / GCP)

---

# 📂 Project Structure  


.
├── backend/
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── Dockerfile
│   ├── package.json
│   └── src/
│
├── nginx/
│   └── nginx.conf
│
├── .github/workflows/
│   └── ci-cd.yml
│
├── docker-compose.yml
├── deploy.sh
└── README.md



---

# 🐳 Docker Setup

## 🔹 Backend Dockerfile  
Located in `/backend/Dockerfile`

Build:
```bash
docker build -t backend-image ./backend
````

## 🔹 Frontend Dockerfile

Located in `/frontend/Dockerfile`

Build:

```bash
docker build -t frontend-image ./frontend
```

---

# ⚙️ Docker Compose Deployment

Start all services:

```bash
docker compose up -d
```

Included services:

* `mongo`
* `backend`
* `frontend`
* `nginx` (reverse proxy)

Stop containers:

```bash
docker compose down
```

---

# 🌐 Nginx Reverse Proxy

Nginx routes:

* `/` → Angular frontend
* `/api/` → Node.js backend

Config file: `nginx/nginx.conf`

---

# 🚀 CI/CD Pipeline (GitHub Actions)

Pipeline features:

* Auto-build Docker images
* Push to Docker Hub
* SSH into Ubuntu VM
* Pull new images and restart containers

Workflow file:
`.github/workflows/ci-cd.yml`

Triggered on:

```
push to: main
```

---

# 🖥 Cloud Deployment (Ubuntu VM)

### Install Docker

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
```

### Install Compose Plugin

```bash
sudo apt install -y docker-compose-plugin
```

### Clone your project

```bash
git clone https://github.com/Hari99-ai/discoverdollar-devops-assignment.git deploy
cd deploy
docker compose up -d
```

---

# 📝 How CI/CD Works

1. You push code → GitHub triggers workflow
2. Pipeline builds backend + frontend Docker images
3. Pushes images to Docker Hub
4. SSH into VM
5. Pulls updated images
6. Restarts containers with zero downtime

---

# 📸 Required Screenshots (Add During Submission)

* Docker images built
* Docker Hub image repository
* GitHub Actions successful workflow run
* VM running containers (`docker ps`)
* Working frontend UI in browser
* Nginx reverse proxy working

---

# 🔐 Secrets Used in GitHub Actions

Add in:
**Settings → Secrets → Actions**

| Secret               | Description                |
| -------------------- | -------------------------- |
| `DOCKERHUB_USER`     | Docker Hub Username        |
| `DOCKERHUB_TOKEN`    | Docker Hub Access Token    |
| `VM_HOST`            | VM public IP               |
| `VM_USER`            | SSH user (ubuntu/ec2-user) |
| `VM_SSH_PRIVATE_KEY` | PEM key content            |

---

# ✔ Final Notes

* Do **NOT** delete your cloud VM; it may be needed for the next round.
* You may stop the instance when not in use.
* Ensure your Docker Hub repositories are set to **public** for easier access.

---

# 🙌 Thank You


If you want:  
✅ I can generate a **perfect GitHub description**  
✅ I can create a **wiki page**  
✅ I can generate **screenshots list**  
Just tell me!
```
