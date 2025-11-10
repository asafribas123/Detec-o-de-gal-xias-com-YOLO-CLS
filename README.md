# 🌌 Galaxy Morphology Classification with YOLO-CLS

This repository contains all scripts and data pipelines used in the work  
**“Deep Learning-Based Morphological Analysis of Galaxies from SDSS and DECaLS Using YOLO-CLS”**  
by **Asaf Ribas (FURG, 2025)**.

It provides the full implementation for downloading, preprocessing, and classifying galaxies with the **YOLOv8-CLS** deep learning architecture, applied to real astronomical survey data.

---

## 🪐 Overview

Galaxy morphology is a cornerstone of extragalactic astronomy, offering insights into galaxy formation, evolution, and environmental effects.  
However, visual classification of millions of galaxies has become infeasible due to scale and human bias.  
This repository presents a **deep learning framework** for automated morphological classification, bridging computer vision and astrophysics.

Our model — **YOLOv8-CLS** — was trained on a curated, cross-matched dataset combining **SDSS DR8**, **DECaLS**, **Galaxy Zoo**, and **redMaPPer** catalogs.

---

## 📂 Repository Structure

├── downloads_dataset.ipynb # Download and preprocessing scripts
├── Yolo_dados.ipynb # YOLO-CLS training and evaluation
├── dataset_cls/ # Structured dataset (train/val)
├── results/ # Plots, confusion matrices, accuracy curves
└── README.md # Project documentation

---

## 📦 Dataset

- **Sources:** SDSS DR8, DECaLS, Galaxy Zoo, redMaPPer cluster catalog  
- **Coverage:** ~19,865 deg² across northern and equatorial hemispheres  
- **Sample size:** ≈18,000 galaxies  
- **Classes:** `smooth`, `spiral`, `irregular`  
- **Preprocessing:** 128×128 px resizing, normalization [0,1], rotation/flip/brightness augmentations  

Each image is prepared for YOLO-CLS ingestion in the standard Ultralytics format.

---

## ⚙️ Installation

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/asafribas123/galaxy_classification_with_YOLO-CLS.git
cd galaxy_classification_with_YOLO-CLS
pip install -r requirements.txt
Or manually:
pip install ultralytics numpy pandas matplotlib seaborn tqdm h5py

## 🚀 Usage

Run the preprocessing notebook: python downloads_dataset.ipynb
Then train and evaluate the YOLO-CLS model: python Yolo_dados.ipynb

## 📊 Results
Metric	Value
Top-1 Accuracy	0.90
Top-5 Accuracy	1.00
Macro F1-Score	0.91

Performance by class:

Smooth: 0.87 F1

Spiral: 0.91 F1

Irregular: 0.94 F1

Example:


## 🧠 Methodology Summary

Architecture: YOLOv8-CLS (classification head adaptation)

Training: 30 epochs, batch size 16, image size 128×128

Optimizer: SGD (momentum = 0.937), cosine LR schedule

Hardware: AMD Ryzen 5 4600G (CPU-based training)

The model achieved high stability, generalization, and interpretability — comparable to or exceeding CNNs such as ResNet-50 and EfficientNet.

## 🔗 Related Files

File: downloads_dataset.ipynb
Repository: https://github.com/asafribas123/Galaxy_classification_with_YOLO-CLS
If you use this repository, please cite: @article{ribas2025yolocls,
  title={Deep Learning-Based Morphological Analysis of Galaxies from SDSS and DECaLS Using YOLO-CLS},
  author={Ribas, Asaf},
  journal={IEEE Journal of Computational Modeling},
  year={2025}
}
## Asaf Ribas
Physicist and M.Sc. Student in Computational Modeling – FURG
Research in galaxy morphology, machine learning, and spectroscopy
📧 asaf.ribas@furg.br

