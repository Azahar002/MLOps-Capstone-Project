# 🧠 MLOps Capstone Project: End-to-End ML Pipeline with CI/CD & Kubernetes

This project demonstrates the **complete MLOps lifecycle** — from data ingestion to deploying a Flask-based ML application on AWS EKS, with MLflow tracking, DVC for data versioning, CI/CD automation using GitHub Actions, and observability through Prometheus & Grafana.

---

## 🚀 Key Highlights

- 📦 Cookiecutter project scaffolding
- 🧪 MLflow + DagsHub for experiment tracking
- 📁 DVC for data and model versioning
- 🧬 Modular ML pipeline (ingestion, preprocessing, training, evaluation)
- 🧪 Unit Testing with GitHub Actions
- 🐳 Dockerized Flask App
- ☁️ Deployment on AWS EKS (via `eksctl`)
- 📈 Monitoring via Prometheus & Grafana
- 🔐 Secrets managed with GitHub & AWS IAM

---

## 🛠️ Tech Stack

- **Language**: Python 3.10
- **ML Tracking**: MLflow, DagsHub
- **Data Versioning**: DVC (local + S3 backend)
- **Orchestration**: GitHub Actions CI/CD, DVC Pipelines
- **Deployment**: Docker, AWS ECR, AWS EKS, eksctl, kubectl
- **Monitoring**: Prometheus, Grafana (on EC2)
- **Web Framework**: Flask
- **Cloud**: AWS (IAM, S3, ECR, EKS, EC2)

---

## 📁 Project Structure

```
.
├── .github/workflows       # CI/CD Pipeline definition
├── data/                   # Version-controlled data via DVC
├── flask_app/              # Dockerized Flask inference app
├── src/
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   ├── model_evaluation.py
│   ├── register_model.py
│   └── logger/
├── tests/                  # Unit tests
├── dvc.yaml                # DVC pipeline definition
├── params.yaml             # Model parameters
├── Dockerfile
└── requirements.txt
```

---

## 🧪 Experiment Tracking (MLflow via DagsHub)

- Setup MLflow remote tracking using DagsHub
- Authenticate using token and configure secrets in GitHub
- Track parameters, metrics, and model artifacts

---

## 🔁 Reproducible Pipelines with DVC

- Modular stages: ingestion → processing → training → evaluation
- Remote storage setup: local + AWS S3
- Trigger with `dvc repro`
- Push to S3 with `dvc push`

---

## 🐳 Docker & Flask App

- Dockerize the Flask app
- Environment variable setup for secure deployment
- Image pushed to DockerHub & ECR

---

## 🚢 Kubernetes (AWS EKS)

- `eksctl` to provision cluster and nodegroups
- Docker image pulled from ECR and deployed via CI/CD
- External access via LoadBalancer service

---

## 📊 Monitoring with Prometheus & Grafana

- Prometheus scrapes metrics from Flask app
- Grafana visualizes live metrics
- EC2 setup with open ports (9090, 3000)

---

## 🔁 CI/CD Automation

- GitHub Actions: Test, Build Docker image, Push to ECR, Deploy to EKS
- Secrets managed using GitHub environment variables

---

## 📦 Cleanup

- Kubernetes cleanup: pods, services, secrets, EKS cluster
- AWS cleanup: ECR images, S3 buckets, EC2 instances
- Validate deletion via AWS CLI

---

## 🧠 Concepts Covered

- Infrastructure-as-Code (IaC) via `eksctl`
- Data and model versioning (DVC)
- Experiment tracking and model registry (MLflow)
- CI/CD automation (GitHub Actions)
- Production-grade deployment on Kubernetes
- Monitoring and observability for ML services

---

## 📍 Recruiter Note

> This project showcases **real-world MLOps best practices** and highlights my ability to **design, deploy, and monitor** full ML systems on cloud-native infrastructure. It reflects hands-on expertise with AWS, Kubernetes, CI/CD, and scalable ML pipelines.

---

## 📎 Bonus Topics (Explained in Docs)

- What is PVC in Kubernetes?
- How CloudFormation is involved in EKS
- AWS Fleet Requests and quota limits

---

## 👨‍💻 Author

**Shaik Azahar Mahaboob**  
Cloud | DevOps | MLOps Engineer  
[LinkedIn](https://linkedin.com) • [GitHub](https://github.com/azahar002)

