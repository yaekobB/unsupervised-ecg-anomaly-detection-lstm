# Unsupervised ECG Anomaly Detection Using an LSTM Autoencoder

An end-to-end **PyTorch** implementation of a reconstruction-based anomaly detection pipeline for **12-lead ECG recordings** using an **LSTM Autoencoder**.

This project investigates whether reconstruction error can be used as an anomaly score to identify **Atrial Fibrillation (AF)** in ECG recordings without using diagnostic labels during model optimization.
> **Domain:** AI for Healthcare · Medical Time Series · Deep Learning · Unsupervised Learning  
> **Keywords:** ECG Analysis · Anomaly Detection · LSTM Autoencoder · Biomedical Signal Processing · PyTorch  
> **Project:** M.Sc. in Artificial Intelligence and Computer Science  
> **Institution:** University of Calabria

---

# Overview

Unlike supervised ECG classification, this project approaches AF detection as an **unsupervised anomaly detection** problem.

The model learns to reconstruct ECG signals from normal temporal patterns. During inference, recordings that are reconstructed poorly receive higher anomaly scores and are evaluated against the available AF labels.

The implementation adapts a reconstruction-based anomaly detection workflow to the **Georgia ECG dataset** and implements a complete preprocessing, training, evaluation, and visualization pipeline.

---

# Key Features

- End-to-end ECG anomaly detection pipeline
- Recording-level preprocessing and data validation
- Leakage-free train/validation/test partitioning
- Sliding-window ECG representation
- LSTM encoder-decoder autoencoder implemented in PyTorch
- Reconstruction-based anomaly scoring
- Recording-level score aggregation
- Validation-based threshold selection
- Quantitative and qualitative evaluation
- Single-recording inference and visualization

---

# Dataset

This project is based on the **Georgia** subset of the **PhysioNet/Computing in Cardiology Challenge 2020** dataset.

Only a subset of **3,000 ECG recordings** from the publicly available dataset was used in this project after preprocessing and validation.

The original dataset is available from:

**https://physionet.org/content/challenge-2020/1.0.2/**

The dataset is **not included** in this repository.

---

# Project Pipeline

```text
ECG Recordings
        │
        ▼
Data Validation
        │
        ▼
Recording-Level Split
        │
        ▼
Training-Only Normalization
        │
        ▼
Sliding Window Generation
        │
        ▼
LSTM Autoencoder
        │
        ▼
Window Reconstruction Error
        │
        ▼
Recording-Level Anomaly Score
        │
        ▼
Threshold Selection
        │
        ▼
Performance Evaluation
```

---

# Repository Structure

```text
unsupervised-ecg-anomaly-detection-lstm/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── unsupervised_ecg_anomaly_detection_lstm.ipynb
│
├── figures/
│
└── docs/
    └── Project_Report.pdf
```

---

# Installation

```bash
git clone https://github.com/<your-username>/unsupervised-ecg-anomaly-detection-lstm.git
cd unsupervised-ecg-anomaly-detection-lstm

python -m venv .venv
pip install -r requirements.txt
```

---

# Usage

1. Download the Georgia ECG dataset.
2. Configure the dataset path in the notebook.
3. Open `notebooks/unsupervised_ecg_anomaly_detection_lstm.ipynb`.
4. Run the notebook sequentially.

---

# Results

The implementation demonstrates a complete reconstruction-based anomaly detection workflow for 12-lead ECG recordings, including preprocessing, model training, recording-level anomaly scoring, threshold selection, and qualitative evaluation.

Detailed methodology and experimental results are available in the accompanying project report.

---

# Documentation

See:

```text
docs/Project_Report.pdf
```

---

# Future Work

- Transformer Autoencoders
- Variational Autoencoders
- CNN-LSTM architectures
- Self-supervised ECG representation learning
- Explainable AI for anomaly localization
- Evaluation on additional ECG datasets

---

# Disclaimer

This repository is intended for educational and research purposes only.

It is **not** intended for clinical diagnosis or medical decision-making.

---

# License

See the **LICENSE** file for licensing information.
