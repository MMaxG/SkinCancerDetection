# Deep Learning for Skin Cancer Detection

**Author:** Max Grönlund  
**Institution:** University of Eastern Finland, Kuopio Campus  
**Supervisor:** Prof. Xiao-Zhi Gao  
**Date:** 2025-05-26

---

## Project overview

This repository contains the code and results for my Master's Thesis comparing deep learning models for **binary classification** of dermatoscopic images: **melanoma vs. benign nevus** (mole). The work is based on experiments using the **HAM10000** dataset and includes Grad-CAM visualizations for explainability.

Four model forks (separate branches in this repo) are included:

- `ResNet50/`  
- `EfficientNet-B4/`  
- `ConvNeXt-Tiny/`  
- `Swin-Transformer/`

Each folder contains training, evaluation, and inference scripts for that architecture.

---

## Quick demo / visuals


Dataset image examples:  
<img width="721" height="369" alt="image" src="https://github.com/user-attachments/assets/58a4de29-d126-4124-90ab-0c7b5410baaa" />

Grad-CAM comparison:  
<img width="1152" height="765" alt="image" src="https://github.com/user-attachments/assets/891a51e9-6eda-4433-b02b-7272c1d24294" />

Training curves (accuracy & loss):  
<img width="1885" height="745" alt="image" src="https://github.com/user-attachments/assets/f49de179-7ac2-45af-953e-0ca9c69a71ab" />

Confusion matrix:  
<img width="1883" height="428" alt="image" src="https://github.com/user-attachments/assets/0af10ad5-e1bc-4e75-9394-cfa9329cd1c5" />


---

## Dataset

**HAM10000** (public): ~10,000 dermatoscopic images.  
- Melanoma: ~1,113 images  
- Nevus (benign): ~6,705 images

Data preparation performed in `data/`:
- Filtering to melanoma vs. nevus (binary)
- Image resizing (224×224 or 380×380 depending on model)
- Normalization and augmentations (flip, rotate, brightness)
- Class balancing where applicable

---

## Results summary

| Model              | AUC-ROC | Notes |
|--------------------|:-------:|:------|
| ResNet50           | **0.922** | Best overall, stable performance |
| EfficientNet-B4    | 0.89    | Variable; lower recall in some runs |
| ConvNeXt-Tiny      | 0.87    | Good precision for melanoma |
| Swin Transformer   | 0.911   | Competitive AUC, higher variance |

Full plots, confusion matrices and Grad-CAM images are available in `results/`.

---

