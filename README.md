# Distinguish-AI-Faces

> **Computer Vision Project — Akdeniz University**  
> **Authors:** Yusuf Samed Çelik & Zehra Selin Karabıcak  
> **Department of Computer Engineering**  
>  
> **Title:** Distinguishing AI-Generated Faces from Real Humans

---

## 📌 Project Overview

Recent advancements in Generative Adversarial Networks (GANs) have made it increasingly difficult to distinguish AI-generated faces from real human photos. This project aims to develop a computer vision system that can accurately classify whether a face is real or synthesized.

This project is divided into two primary components:
- **Data Pipeline:** Collecting and preprocessing a balanced dataset of real and AI-generated faces.
- **Training Pipeline:** Designing and training a deep convolutional neural network (CNN) to perform binary classification.

---

## 🎯 Objectives

- 🔹 Build a **custom dataset** combining real faces and GAN-generated faces (e.g., from [thispersondoesnotexist.com](https://thispersondoesnotexist.com)).
- 🔹 Develop a **CNN-based deep learning model** from scratch (no pre-trained weights).
- 🔹 Evaluate the model using **cross-validation**, measuring **accuracy**, **precision**, **recall**, and **F1-score**.
- 🔹 Deploy the model training process on **Google Cloud Vertex AI** using a containerized workflow.

---

## 🧠 Theoretical Motivation

### Why This Problem Matters

- GANs can create images that are **visually indistinguishable** from real ones.
- These fake faces pose serious **security, ethical, and societal risks**, including misinformation, identity fraud, and loss of trust in digital media.
- Identifying subtle **artifacts or inconsistencies** in generated images is essential for **content moderation**, **cybersecurity**, and **media integrity**.

---

## 🏗️ Repository Structure

```bash
distinguish-ai-faces/
│
├── .github/
│   └── workflows/
│       └── build-and-push.yml        # Docker image build + push to GCR
│
├── data_pipeline/                    # Data collection and preprocessing
│   ├── scrape_faces.py               # Web scraping from sources
│   ├── preprocess.py                 # Image resizing, normalization, etc.
│   ├── upload_to_gcs.py              # Upload to Google Cloud Storage
│   ├── requirements.txt
│   └── README.md
│
├── training_pipeline/               # Model development and training
│   ├── train.py                      # Training loop and validation
│   ├── model.py                      # CNN model architecture
│   ├── config.py                     # Parameters (batch size, epochs, etc.)
│   ├── Dockerfile                    # Containerized training definition
│   ├── requirements.txt
│   └── README.md
│
├── deploy_model.md                  # Instructions for Vertex AI training jobs
├── setup_env.md                     # GCP setup, IAM roles, buckets, etc.
├── .gitignore
└── README.md                        # This file
```

---

## ⚙️ Tools & Technologies

- 🧠 **Python** (PyTorch or TensorFlow)
- 🐳 **Docker** for containerizing the training environment
- ☁️ **Google Cloud Platform**:
  - Cloud Storage (dataset storage)
  - Artifact Registry (store container images)
  - Vertex AI (training on GPU-enabled VMs)
- 🛠️ **GitHub Actions** for CI/CD automation

---

## 🧪 Model & Evaluation

- Architecture: Custom-built **CNN**
- Training: From scratch using randomly initialized weights
- Dataset:
  - Real faces: Web scraped from open datasets
  - Fake faces: GAN-generated from online sources
- Metrics:
  - ✅ Accuracy
  - 🎯 Precision
  - 🔁 Recall
  - 🧮 F1-Score
- Evaluation Strategy: **Cross-validation**

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Docker installed and running
- GCP Project with:
  - Vertex AI, Artifact Registry, and GCS enabled
  - Service Account with required IAM roles

### Clone the repository

```bash
git clone https://github.com/your-username/distinguish-ai-faces.git
cd distinguish-ai-faces
```

---

## 🔄 CI/CD Workflow

- When new code is pushed to the `main` branch, a GitHub Actions workflow:
  - Builds the training image via `Dockerfile`
  - Pushes it to GCP's **Artifact Registry**
  - Optionally triggers a **Vertex AI custom job**

---

## 📤 Dataset Pipeline

The `data_pipeline/` module handles:
- 🔍 Scraping real and AI-generated faces
- 🦼️ Preprocessing (resizing, normalization)
- ☁️ Uploading structured data to GCS for training

---

## 🎓 Training Pipeline

The `training_pipeline/` module performs:
- Model construction with custom CNN
- GPU-based training using Vertex AI
- Saves model artifacts to GCS after training

---

## ✅ Expected Outcome

- A robust CNN that can reliably detect AI-generated faces
- Insights into detectable artifacts present in GAN-based imagery
- Potential integration into systems requiring **image authenticity verification**

---

## 📘 Academic References

- Karras et al. *StyleGAN2: Analyzing and Improving the Image Quality of GANs* (CVPR 2020)
- Wang et al. *CNN-based Detection of GAN-generated Faces*
- [ThisPersonDoesNotExist.com](https://thispersondoesnotexist.com)

---

## 📄 License

This project is intended for academic use under Akdeniz University. License TBD depending on submission guidelines.

---

## 🤍 Acknowledgements

Special thanks to our advisors and reviewers at Akdeniz University’s Department of Computer Engineering.

