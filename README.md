# 🚀 Static Website Deployment using Docker & Nginx

## 📌 Project Overview

This project demonstrates how to deploy a static website (HTML, CSS, JS) using Docker and Nginx. The website is containerized and served using the Nginx web server.

## 🛠️ Tech Stack

* Docker
* Nginx
* HTML, CSS, JavaScript
* Git & GitHub

## 📁 Project Structure

```
project/
│── index.html
│── style.css
│── images/
│── Dockerfile
│── README.md
```

## 🐳 Dockerfile

```
FROM nginx:latest
RUN rm -rf /usr/share/nginx/html/*
COPY . /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## ⚙️ Setup & Installation

### 1️⃣ Clone Repository

```
git clone <your-repo-url>
cd <repo-folder>
```

### 2️⃣ Build Docker Image

```
docker build -t mywebsite .
```

### 3️⃣ Run Docker Container

```
docker run -d -p 8080:80 mywebsite
```

### 4️⃣ Access Application 🌐

```
http://<your-ec2-public-ip>:8080
```

## 🔍 How It Works

* Docker builds an image using the Dockerfile
* Nginx serves static files from `/usr/share/nginx/html/`
* Port 80 (container) is mapped to 8080 (host)

## ⚠️ Common Issues & Fixes

### ❌ Container exits immediately

* Ensure correct Dockerfile
* Check logs using:

```
docker logs <container-id>
```

### ❌ Website not accessible

* Allow port 8080 in EC2 Security Group
* Verify container is running:

```
docker ps
```

### ❌ CSS not loading

* Check file paths in `index.html`
* Ensure files are copied correctly

## 🧠 Learning Outcomes

* Understand Docker image building
* Deploy static websites using Nginx
* Work with containers in a cloud environment
* Basic DevOps workflow (GitHub → EC2 → Docker)

## 📌 Future Enhancements

* CI/CD pipeline using Jenkins
* Reverse proxy setup with Nginx
* Deployment using Load Balancer
* Docker Compose integration

## 👨‍💻 Author

Avinash Mule
