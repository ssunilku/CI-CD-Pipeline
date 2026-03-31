

---

# 🚀 Ultimate End-to-End CI/CD Pipeline (GitOps)

This repository features a production-grade **CI/CD Pipeline** that implements modern DevOps best practices. It bridges the gap between **Continuous Integration (CI)** and **Continuous Delivery (CD)** using a **GitOps** approach to ensure a scalable, secure, and declarative deployment lifecycle.

## 🏗️ Architecture Overview

The pipeline is split into two distinct, decoupled phases:

### 1. Continuous Integration (CI) — Jenkins
* **Triggering:** Automates builds via **GitHub Webhooks** for real-time responsiveness.
* **Build & Test:** Utilizes **Maven** for compiling Java source code and executing unit tests.
* **Code Quality:** Integrates **SonarQube** for Static Application Security Testing (SAST) and quality gate enforcement.
* **Artifact Management:** Containerizes the application using **Docker** and pushes versioned images to a **Container Registry** (ECR/Docker Hub).

### 2. Continuous Delivery (CD) — Argo CD (GitOps)
* **Manifest Management:** Uses a dedicated Git repository for Kubernetes manifests (YAML/Helm).
* **Automated Updates:** Employs **Argo Image Updater** to monitor the registry and automatically update image tags in the manifest repo.
* **State Synchronization:** **Argo CD** (running in **Kubernetes**) pulls the latest configurations, ensuring the cluster state always matches the Git "Source of Truth."

## 🛠️ Technical Stack
* **Orchestration:** Jenkins, Argo CD
* **Build/Quality:** Maven, SonarQube
* **Containerization:** Docker, Docker Agents
* **Platform:** Kubernetes
* **Version Control:** GitHub (Source Code & Manifests)

## 📂 Project Structure
* `/src`: Application source code.
* `/kubernetes-manifests`: K8s Deployment and Service YAML files.
* `Jenkinsfile`: Declarative pipeline script defining the CI stages.

## 🚀 Key Advantages
* **Separation of Concerns:** CI and CD are decoupled for better reliability and security.
* **Declarative Infrastructure:** Entire environment state is defined in Git, allowing for easy auditing and rollbacks.
* **Automation:** Zero-touch deployment from the moment a developer pushes code to the final pod running in production.

## 🔧 Prerequisites
* Jenkins Server with Docker and Maven plugins.
* Kubernetes Cluster (EKS, GKE, or Minikube).
* Argo CD installed within the cluster.
* SonarQube instance for code analysis.

---

### Pro-Tip:
*When you upload this to GitHub, make sure to include the diagram provided earlier in the top section of the README to visually engage visitors!*
