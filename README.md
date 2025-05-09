# 🦷 CBCT Adaptive Machine Learning Pipeline

This project is a **modular, reusable, and production-ready MLOps pipeline** for CBCT (Cone Beam Computed Tomography) data processing, segmentation, and analysis. The goal is to enable seamless adaptation across multiple datasets and models by altering only configuration files, ensuring efficiency and reproducibility.

---

## 📌 Project Objectives

- ✅ Build a **generalized ML pipeline** adaptable to various CBCT datasets
- ✅ Ensure **reusability** and **scalability** with clean separation of concerns
- ✅ Support **experiment tracking**, **data versioning**, and **CI/CD workflows**
- ✅ Enable **easy deployment and serving** with monitoring and alerting
- ✅ Maintain **modular design** for plug-and-play models, losses, and optimizers

---

## 🧰 Tools Used and Their Purpose

| Area                          | Tool(s)                              | Purpose                                                                 |
|-------------------------------|--------------------------------------|-------------------------------------------------------------------------|
| **Code Versioning**           | Git + GitHub                         | Track code changes, enable collaboration                                |
| **Dataset/Model Versioning**  | DVC                                  | Track changes in datasets and models                                    |
| **Visual Tracking**           | DagsHub                              | Git + DVC UI for lineage and tracking                                   |
| **Environment & CI/CD**       | Docker, GitHub Actions               | Reproducible environments and automated testing/deployment              |
| **Code Quality & Linting**    | Pre-commit Hooks                     | Auto-check code format and syntax before commit                         |
| **Testing**                   | Pytest, Unittest                     | Unit and integration testing                                            |
| **Experiment Tracking**       | MLflow, Weights & Biases (W&B)       | Track experiments, parameters, models, and results                      |
| **Hyperparameter Tuning**     | W&B Sweeps, Optuna                   | Automated search for best hyperparameters                               |
| **Config Management**         | Hydra                                | Dynamically load and override configuration files                       |
| **Data Validation**           | Great Expectations, Pydantic         | Validate data quality and schema                                        |
| **Pipeline Orchestration**    | Apache Airflow                       | Define, schedule, and monitor ML workflows                              |
| **Model Serving**             | FastAPI, TorchServe                  | Deploy models as APIs for real-time inference                           |
| **Monitoring & Drift**        | Prometheus, Grafana, Evidently       | Monitor system health and detect data/model drift                       |
| **Secrets Management**        | HashiCorp Vault, AWS Secrets Manager | Securely store API keys and credentials                                 |
| **Access Control**            | IAM (AWS/GCP)                        | Manage permissions and roles                                            |
| **Cloud Deployment**          | AWS, Azure, GCP, Terraform/AWS CDK   | Deploy and manage infrastructure in cloud                               |
| **Frontend Integration**      | React, Vite, Axios, GraphQL          | Build UI and connect with backend APIs                                  |

---

## 🗂️ Project Structure (Modular)

```bash
project-root/
├── .dvc/                  # DVC metadata for dataset/model versioning
├── .github/               # GitHub Actions for CI/CD
├── checkpoints/           # Saved model checkpoints
├── configs/               # Hydra config files
├── data/
│   ├── raw/               # Original raw CBCT data
│   └── processed/         # Cleaned and preprocessed data
├── deployment/            # Model serving scripts & Docker deploy
├── docker/                # Dockerfiles and compose files
├── logs/                  # Log files for training/evaluation
├── mlruns/                # MLflow experiment logs
├── notebooks/             # Research & exploration notebooks
├── outputs/               # Model predictions, evaluation outputs
├── scripts/               # One-off data manipulation scripts
├── src/
│   ├── data/              # Loading and transformation scripts
│   ├── models/            # Model architectures
│   ├── losses/            # Custom loss functions
│   ├── optimizers/        # Custom optimizers/schedulers
│   ├── train/             # Training loop
│   ├── eval/              # Evaluation pipeline
│   ├── predict/           # Inference code
│   └── utils/             # Utilities (metrics, I/O, transforms)
├── tests/                 # Unit and integration tests
│   └── integration/
├── README.md              # This file
├── requirements.txt       # Python dependencies
└── Makefile               # CLI task automation
