# 🧾 Expensy — End-to-End DevOps Deployment

## Overview

Expensy is a full-stack expense tracking application featuring a Node.js backend and a Next.js frontend. This project demonstrates an end-to-end DevOps deployment pipeline, including containerization, CI/CD, monitoring, and secure deployment in a cloud environment.

---

## 🚀 DevOps Workflow

### 🐳 Containerization

- Both backend and frontend are containerized using Docker.
- A `docker-compose.yaml` file is provided for local development.
- Environment variables are securely managed via `.env` files.

---

### ⚙️ CI/CD Pipeline

- CI/CD is handled using GitHub Actions.
- Main stages include:
  - Linting and building the code
  - (Optional) Automated testing
  - Docker image creation and push to Docker Hub
  - Manual approval step for deployment

---

### 📈 Monitoring with Prometheus & Grafana

- **Prometheus** scrapes application and system metrics.
- **Grafana** dashboards provide visual insights into:
  - CPU and memory usage
  - Pod status
  - Custom app metrics via `/metrics` endpoint
- Monitoring tools run inside the Kubernetes cluster.

---

## 🔐 Security Overview

- **Secrets Management:**  
  All sensitive data is stored in Kubernetes Secrets.

- **Access Control:**  
  IAM roles are used to manage access to cloud resources.

- **TLS Encryption:**  
  TLS is used for secure communication between components.

- **Network Policies:**  
  Access between services is restricted by security groups and policies.

- **Secure Images:**  
  Only official base images are used and scanned for vulnerabilities.

---

## ✅ Compliance Summary

- **Data Protection:**  
  User data is encrypted at rest and in transit using cloud provider tools.

- **User Rights:**  
  The app supports complete user data deletion to align with GDPR principles.

- **Log Retention:**  
  Monitoring logs are retained only for the development/testing lifecycle.

- **Traceability:**  
  CI/CD workflows record every deployment step, providing full auditability.

- **Code Transparency:**  
  All configurations are version-controlled in a public repository.

---

## 🧪 Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/devops.expensy
   cd devops.expensy
Create .env files for frontend and backend:

Backend: DATABASE_URI, REDIS_PASSWORD, etc.

Frontend: prefixed with NEXT_PUBLIC_

Run the app locally:

bash
Copiar código
docker-compose up --build
📡 Deployment (Production)
Set up a Kubernetes cluster (e.g., AWS EKS)

Apply Kubernetes manifests:

bash
Copiar código
kubectl apply -f k8s/
Access the frontend and monitoring dashboards via LoadBalancer endpoints.

🧠 Author
Built by Gabriel Arias Karausch as part of the DevOps Bootcamp Final Project.
