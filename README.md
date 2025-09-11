# Three-Tier Application Deployment on AWS EKS

This project demonstrates the deployment of a **three-tier web application** (ReactJS, NodeJS, MongoDB) on **Amazon EKS (Elastic Kubernetes Service)** and use **Kubernetes for orchestration**, **AWS ALB for load balancing**.

---

## 🚀 Project Overview
- **Frontend:** ReactJS  
- **Backend:** NodeJS / Express  
- **Database:** MongoDB  
- **Orchestration:** Kubernetes on AWS EKS  
- **Load Balancer:** AWS Application Load Balancer (ALB)  
- **Containerization:** ECR  

The application follows the **three-tier architecture**:
1. **Presentation Layer (ReactJS)** – User interface  
2. **Application Layer (NodeJS)** – Business logic  
3. **Data Layer (MongoDB)** – Database  

---

## 🏗️ Architecture


```plaintext
        [ User ]
           |
     [ AWS ALB ]
           |
   -----------------
   |               |
[ReactJS]      [NodeJS API]  --->  [MongoDB]
(Frontend)     (Backend)          (Database)
   |               |
   -----------------
           |
       [ EKS Cluster ]
````

---

## 📦 Deployment Steps


### 1. Build Docker Images

```bash
docker build -t react-frontend ./frontend
docker build -t node-backend ./backend
docker build -t mongo-db ./database
```

### 2. Push Images to Amazon ECR

```bash
aws ecr create-repository --repository-name react-frontend
aws ecr create-repository --repository-name node-backend
aws ecr create-repository --repository-name mongo-db
```

Push images to ECR after login.

### 3. Deploy on EKS

Apply Kubernetes manifests:

```bash
kubectl apply -f k8s/frontend-deployment.yaml
kubectl apply -f k8s/backend-deployment.yaml
kubectl apply -f k8s/mongodb-deployment.yaml
kubectl apply -f k8s/services.yaml
```

---

## 🛠️ Tools & Technologies

* **AWS EKS** (Managed Kubernetes Service)
* **Kubernetes** (Deployment, Services, ConfigMaps, Secrets)
* **Docker** (Containerization)
* **AWS ALB** (Load Balancing)
* **MongoDB** (Database)
* **ReactJS / NodeJS** (Frontend & Backend)

---

## 🎯 Key Learnings

* Deploying and managing a **three-tier application** on **AWS EKS**
* Using **Kubernetes manifests** for deployments and services
* Leveraging **AWS ALB** for scalable and highly available architecture
* Hands-on experience with **cloud-native technologies, containerization, and orchestration**

---
