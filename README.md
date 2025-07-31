# 🧠 Brain Tumor Detection using CNN on MRI Scans

This project implements a deep learning pipeline for automatic brain tumor detection using MRI images. The model is a custom-built Convolutional Neural Network (CNN) trained from scratch to classify MRI scans into **tumorous** and **non-tumorous** categories.

> 🧪 Accuracy: **89% on test set** | F1-score: **0.88**

---

## 📊 Dataset

- Source: [Kaggle - Brain MRI Images for Brain Tumor Detection](https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection)
- 253 original images:
  - `yes/` folder: 155 tumorous scans
  - `no/` folder: 98 normal scans
- After augmentation:
  - 1085 positive (tumorous)
  - 980 negative (non-tumorous)
  - ➜ Total: 2065 images

---

## ⚙️ Preprocessing Steps

1. Cropping brain region
2. Resizing to (240, 240, 3)
3. Normalizing pixel values to range [0, 1]

---

## 🧠 Model Architecture

A lightweight CNN designed for high accuracy with low computational cost.

- ZeroPadding2D
- Conv2D (32 filters, 7x7 kernel)
- Batch Normalization
- ReLU activation
- MaxPooling (4x4) ×2
- Flatten + Dense → Sigmoid

![Architecture](convnet_architecture.jpg)

---

## 📈 Training Performance

- Optimizer: Adam
- Loss: Binary Crossentropy
- Epochs: 24
- Best Model: Epoch 23

**Accuracy Curve**  
![Accuracy](Accuracy.PNG)

**Loss Curve**  
![Loss](Loss.PNG)

---

## ✅ Final Results

| Metric      | Validation | Test  |
|-------------|------------|-------|
| Accuracy    | 91%        | 89%   |
| F1 Score    | 0.91       | 0.88  |
| AUC-ROC     | 0.94       | -     |
| Sensitivity | 92%        | -     |
| Specificity | 89%        | -     |

---

## 🧠 Why a Custom CNN?

Transfer learning models like ResNet50 and VGG16 were initially tested but overfit the small dataset. A custom CNN was better suited for:
- Limited data
- Faster training on local machine
- Less computational resources

---

## 📁 Project Structure
├── Brain Tumor Detection.ipynb # Main training notebook
├── Data Augmentation.ipynb # Image generator logic
├── yes/ no/ # Raw data folders
├── models/ # Saved trained models
├── convnet_architecture.jpg # Network diagram
├── Accuracy.PNG / Loss.PNG # Training results
└── README.md

---
