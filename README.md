

---

```
# 🧠 MLOps Capstone Project – End-to-End ML System on AWS EKS

This project demonstrates a full **MLOps pipeline** for building, tracking, deploying, and monitoring an ML model using **modern DevOps practices and cloud-native tools**. It covers the entire lifecycle — from data versioning to real-time prediction APIs deployed on **Amazon EKS**, with **monitoring via Prometheus and Grafana**.

---

## 🚀 Tech Stack

- 🐍 Python 3.10 (Conda Virtual Env)
- 📦 DVC for Data & Model Versioning
- 📊 MLflow via DagsHub for Experiment Tracking
- 🧪 Scikit-learn, XGBoost for modeling
- 🐳 Docker for Containerization
- 🔄 GitHub Actions CI/CD
- ☁️ AWS (S3, IAM, ECR, EKS, EC2)
- 🔧 eksctl, kubectl for EKS management
- 🌐 Flask for serving model APIs
- 📈 Prometheus & Grafana for Monitoring

---

## 📁 Project Structure

```
.
├── data/                       # DVC-managed datasets
├── flask_app/                 # Flask REST API app for model inference
├── notebooks/                 # Experimentation notebooks
├── src/                       # Modularized ML pipeline code
│   ├── data_ingestion.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   └── ...
├── dvc.yaml                   # DVC pipeline definition
├── params.yaml                # All configurable hyperparams
├── Dockerfile                 # App container config
├── .github/workflows/ci.yaml # GitHub Actions CI/CD pipeline
└── requirements.txt
```

---

## 🔁 Workflow Overview

### 1. 📦 Initial Setup
- Created project with `cookiecutter` template
- Modularized ML code under `src/`
- Initialized DVC for data version control
- Integrated MLflow with [DagsHub](https://dagshub.com)

### 2. 📊 Experiment Tracking
- Logged experiments via MLflow
- Visualized metrics (accuracy, F1, precision)
- Stored artifacts remotely

### 3. 🔁 DVC Pipeline
- Tracked stages: ingestion → preprocessing → modeling → evaluation
- Versioned dataset + model artifacts
- Switched DVC remote to **S3**

### 4. 🧪 Flask App
- Built a `/predict` endpoint using Flask
- Containerized with Docker
- Exposed on port `5000`

### 5. ✅ CI/CD via GitHub Actions
- Tested and built image
- Auto-pushed to **ECR**
- Deploys app to **Amazon EKS**

### 6. ☸️ Kubernetes (EKS) Deployment
- Used `eksctl` to create a managed EKS cluster
- Deployed app as a LoadBalancer service
- Monitored pod status, logs, and node metrics via `kubectl`

### 7. 📈 Observability
- Hosted **Prometheus** on EC2 (port 9090)
- Hosted **Grafana** on EC2 (port 3000)
- Scraped metrics from Flask app (`/metrics`)
- Built dashboards for:
  - API latency
  - Prediction class distribution
  - Live request throughput

---

## 🌐 Live Monitoring Metrics

| Metric | Description |
|--------|-------------|
| `app_request_latency_seconds_bucket` | Prometheus histogram of API latency |
| `model_prediction_count_total` | Total predictions made per class |
| `app_request_latency_seconds_created` | Timestamp of last prediction |
| `kubectl get pods/svc/nodes` | Kubernetes resource status |

---

## 🧪 Test the API Locally

```bash
docker run -p 5000:5000 -e CAPSTONE_TEST=<your_token> capstone-app:latest
curl http://localhost:5000/predict -X POST -H "Content-Type: application/json" -d '{"input": "test"}'
```

---

## 🛠 CI/CD Steps

```yaml
# .github/workflows/ci.yaml
- Test src scripts
- Build Docker image
- Push to ECR
- Trigger EKS deployment
```

---

## ☁️ Cloud Monitoring (Prometheus + Grafana)

- 📍 Prometheus Target: `http://<external-ip>:9090`
- 📊 Grafana UI: `http://<external-ip>:3000` (user/pass: admin/admin)
- 📌 Dashboards:
  - Endpoint latency
  - Request volume
  - Class prediction histogram

---

## 🔒 Secrets & Security

Environment variables & tokens managed via:
- AWS Secrets Manager
- GitHub Repository Secrets
- IAM Roles & S3 bucket policies

---

## 🧹 AWS Resource Cleanup

```bash
eksctl delete cluster --name flask-app-cluster --region us-east-1
dvc remote remove myremote
aws ecr delete-repository ...
aws s3 rm s3://your-bucket-name --recursive
```

---

## 🧾 Key Concepts Explained

- **CloudFormation**: Infrastructure defined as code; eksctl uses this behind the scenes.
- **PVCs (PersistentVolumeClaims)**: Used by pods in Kubernetes for dynamic EBS volume provisioning.
- **Fleet Requests**: AWS EC2 request quotas impacting EKS auto-scaling.

---

## 🙌 Acknowledgements

- [DrivenData cookiecutter template](https://github.com/drivendata/cookiecutter-data-science)
- [DagsHub](https://dagshub.com) for seamless MLflow integration
- AWS community docs and Prometheus/Grafana OSS

---

## 📬 Contact

👤 **Azahar Mahaboob**  
📧 [Reach me on LinkedIn](https://www.linkedin.com/in/azahar-s-22a427182/)  
📦 [DockerHub](https://hub.docker.com/u/azahar002) | 🧪 [DagsHub Repo](https://dagshub.com/Azahar002/MLOps-Capstone-Project)

---
```

---
