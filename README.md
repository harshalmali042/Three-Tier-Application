Perfect 👍 Let’s give your project a **unique name** and a professional **README.md** file for GitHub.

---

### ✅ Unique Project Name

**TriKube**
(*Three-Tier + Kubernetes*)
👉 Clear, professional, and meaningful. It shows that your project is a **three-tier app deployed on Kubernetes (EKS)**.

---

### 📄 `README.md` file

````markdown
# TriKube – Three-Tier Application Deployment on AWS EKS

This project demonstrates the deployment of a **scalable three-tier web application** (ReactJS, NodeJS, MongoDB) on **Amazon EKS (Elastic Kubernetes Service)**. It highlights the use of **Kubernetes for orchestration**, **AWS ALB for load balancing**, and best practices in cloud-native application deployment.

---

## 🚀 Project Overview
- **Frontend:** ReactJS  
- **Backend:** NodeJS / Express  
- **Database:** MongoDB  
- **Orchestration:** Kubernetes on AWS EKS  
- **Load Balancer:** AWS Application Load Balancer (ALB)  
- **Containerization:** Docker  

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

### 1. Clone Repository

```bash
git clone https://github.com/harshalmali042/There-tier-application.git
cd There-tier-application
```

### 2. Build Docker Images

```bash
docker build -t react-frontend ./frontend
docker build -t node-backend ./backend
docker build -t mongo-db ./database
```

### 3. Push Images to Amazon ECR

```bash
aws ecr create-repository --repository-name react-frontend
aws ecr create-repository --repository-name node-backend
aws ecr create-repository --repository-name mongo-db
```

Push images to ECR after login.

### 4. Deploy on EKS

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

