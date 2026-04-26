Overview

This project implements a Single-Block Vision Attention Network (SB-VAN) for automated pneumonia detection from chest X-ray images.
The model is a lightweight transformer-inspired architecture designed for binary classification of chest radiographs into:

Normal
Pneumonia

Unlike conventional deep CNNs or large Vision Transformers, SB-VAN uses a simplified single-block self-attention pipeline to reduce computational complexity while preserving global contextual feature learning.

Objective

The objective of this project is to build an efficient and lightweight deep learning system for automated pneumonia detection from chest X-ray images, suitable for:

low-resource clinical environments
real-time inference
scalable automated screening systems
Dataset

The model is trained and evaluated on the publicly available Chest X-Ray Images (Pneumonia) dataset from Kaggle:

Dataset Link:
https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

Dataset Details
Total images: 5,863
Classes:
Normal
Pneumonia
Image type: Chest X-ray (JPEG)
Final Data Split

The dataset is reorganized into:

Training: 4,172 images
Validation: 1,044 images
Testing: 624 images
Model Architecture

The proposed SB-VAN model follows a simplified encoder-style architecture:

Input Image
Chest X-ray image resized to 224 × 224 × 3
Patch Embedding
The image is divided into 16 × 16 patches and projected into patch embeddings.
Spatial Positional Encoding
Positional information is added to preserve spatial structure.
Single-Head Self Attention
A lightweight self-attention mechanism captures contextual dependencies between image patches.
Feed Forward Network (FFN)
Refines learned contextual representations.
Classification Head
Produces binary prediction:
Normal
Pneumonia
Architecture Flow
Input Image (224×224×3)
        ↓
Patch Embedding
        ↓
Spatial Positional Encoding
        ↓
Single-Head Self Attention
        ↓
Feed Forward Network
        ↓
Classification Head
        ↓
Output (Normal / Pneumonia)
Features
Lightweight attention-based architecture
Single self-attention block
Low computational complexity
Binary chest X-ray classification
Faster inference than deep transformer models
Suitable for real-time clinical screening
Training Configuration

The model is trained using:

Framework: PyTorch
Optimizer: Adam
Loss Function: Cross-Entropy Loss
Batch Size: 32
Learning Rate: 0.001
Epochs: 30
Early Stopping: Enabled
Input Configuration
Image size: 224 × 224
Patch size: 16 × 16
Embedding dimension: 128
Evaluation Metrics

The model is evaluated using:

Accuracy
Precision
Sensitivity (Recall)
Specificity
F1-Score
ROC-AUC
PR-AUC
Performance

The proposed SB-VAN model achieved:

Accuracy: 80.13%
Precision: 77.82%
Sensitivity (Recall): 95.38%
Specificity: 54.70%
F1-Score: 85.71%
ROC-AUC: 0.9086
PR-AUC: 0.9447

These results indicate strong sensitivity and robust discriminative performance for pneumonia detection.

Project Structure
SB-VAN/
│
├── dataset/
│   ├── train/
│   ├── val/
│   └── test/
│
├── outputs/
│   ├── architecture.png
│   ├── training_curves.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   ├── pr_curve.png
│   └── accuracy_curve.png
│
├── sb_van_train.ipynb
├── sb_van_model.py
├── requirements.txt
└── README.md
Output Visualizations

The project generates the following outputs:

architecture.png — System architecture diagram
training_curves.png — Loss curves
confusion_matrix.png — Confusion matrix
roc_curve.png — ROC curve
pr_curve.png — Precision-Recall curve
accuracy_curve.png — Accuracy trend

These plots are used in the research paper for result analysis.

Use Case

This system is designed for:

automated pneumonia screening
chest X-ray triage support
low-resource healthcare deployment
edge-compatible medical AI systems
Future Work

Potential future improvements include:

multi-class thoracic disease classification
explainable attention visualization
Grad-CAM / attention heatmaps
deployment as a web-based clinical screening tool
Citation

If you use this project in academic work, cite the associated research paper:

Single-Block Vision Attention Network (SB-VAN) for Pneumonia Detection from Chest X-ray Images

Author

Aniket Singh Bisht
B.Tech CSE (AIML)
University of Petroleum and Energy Studies (UPES)
