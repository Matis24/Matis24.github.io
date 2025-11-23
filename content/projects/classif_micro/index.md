---
title: Microscopic Image Classification
date: 2025-08-20
links:
  - type: site
    url: https://www.kaggle.com/competitions/challenge-miashs-2025
tags:
  - DeepLearning
  - Computer Vision
  - Ensemble Learning
  - Image Classification
  - Kaggle
image:
  filename: "micro.jpg"
summary: "Developed a deep learning ensemble (CNN, ViT, ConvNeXt) for automatic Collembola species identification from microscope images, achieving a 0.71 macro F1-score on Kaggle, which earned the **first place** in the competition."
---

## Project Overview

Developed a deep learning pipeline to automatically identify *Collembola* (microscopic soil arthropods) from microscope images — a challenging task due to their very small size and subtle morphological differences.

---

## Objective

- Classify *Collembola* species from a test dataset, evaluated by **macro F1-score** on Kaggle.  
- Resolve conflicting labels from multiple experts and refine the training dataset accordingly.

---

## Dataset

- **1,117 YOLO-annotated images**, covering **9 species**  
- Bounding boxes in **YOLO+** format  
- Selected only images with consistent labels to reduce annotation noise

---

## Methodology

- **Baseline:** Pretrained **ResNet-50**  
- Explored architectures:  
  - CNN  
  - CNN + XGBoost  
  - Vision Transformer (ViT)  
  - ConvNeXt-Base  
- Applied image augmentations (horizontal/vertical flips)  
- Small batch sizes (4–8) to improve generalization

---

## Results

| Model | Macro F1-score |
|-------|----------------|
| ResNet-50 | 0.54 |
| CNN + XGBoost | 0.57 |
| ViT | 0.49 |
| ConvNeXt-Base | 0.62 |

---

## Ensemble Approach

Combined model predictions weighted by **per-class F1-scores** from the validation set.  
This ensemble leveraged the strengths of each model to improve accuracy and robustness.

| Dataset | Macro F1-score |
|---------|----------------|
| Public | 0.66 |
| Private | **0.71** |

---

## Team

Matis Breillad, Ivan Arisoy, Mehdi Belkhiter, Axel Carot

---

## 🚀 Key Takeaways

- Complete DL workflow: **data cleaning → model training → ensemble evaluation**  
- Addressed **label conflicts** and used robust ensembling  
- Achieved **0.71 macro F1-score** on a real-world imbalanced dataset
