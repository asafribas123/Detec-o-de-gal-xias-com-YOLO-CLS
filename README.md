# 🌌 Galaxy Morphology Classification with YOLO-CLS

This repository contains all scripts and data pipelines used in the work:  
**“Deep Learning-Based Morphological Analysis of Galaxies from SDSS and DECaLS Using YOLO-CLS”**  
by *Asaf Ribas* (FURG, 2025).

It provides the complete implementation for **downloading**, **preprocessing**, and **classifying galaxies** using the **YOLOv8-CLS** deep learning architecture, applied to real astronomical survey data.

---

## 🪐 Overview

Galaxy morphology is a cornerstone of extragalactic astronomy, providing insight into galaxy formation, evolution, and environmental interactions.  
However, visual classification of millions of galaxies is no longer feasible due to data scale and human bias.

This repository presents a **deep learning framework for automated morphological classification**, bridging **computer vision** and **astrophysics**.  
Our model — **YOLOv8-CLS** — was trained on a curated, cross-matched dataset combining **SDSS DR8**, **DECaLS**, **Galaxy Zoo**, and **redMaPPer** catalogs.

---
├── downloads_dataset.ipynb # Dataset download and preprocessing
├── Yolo_dados.ipynb # YOLO-CLS training and evaluation
├── dataset_cls/ # Structured dataset (train / val)
├── results/ # Plots, confusion matrices, learning curves
└── README.md # Project documentation

---

## 📦 Dataset

- **Sources:** SDSS DR8, DECaLS, Galaxy Zoo, redMaPPer cluster catalog  
- **Coverage:** ~19,865 deg² (northern + equatorial hemispheres)  
- **Sample size:** ≈18,000 galaxies  
- **Classes:** *smooth*, *spiral*, *irregular*  
- **Preprocessing:**  
  - Image resizing: 128 × 128 px  
  - Normalization: [0, 1]  
  - Augmentations: rotation, flip, brightness  

Each image is formatted for **YOLO-CLS** ingestion in the standard **Ultralytics** structure.

---

## ⚙️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/asafribas123/Galaxy-classification-with-YOLO-CLS.git
cd Galaxy-classification-with-YOLO-CLS
pip install -r requirements.txt
```
## 📂 Repository Structure
├── downloads_dataset.ipynb # Dataset download and preprocessing
├── Yolo_dados.ipynb # YOLO-CLS training and evaluation
├── dataset_cls/ # Structured dataset (train / val)
├── results/ # Plots, confusion matrices, learning curves
└── README.md # Project documentation

---

## 📦 Dataset

- **Sources:** SDSS DR8, DECaLS, Galaxy Zoo, redMaPPer cluster catalog  
- **Coverage:** ~19,865 deg² (northern + equatorial hemispheres)  
- **Sample size:** ≈18,000 galaxies  
- **Classes:** *smooth*, *spiral*, *irregular*  
- **Preprocessing:**  
  - Image resizing: 128 × 128 px  
  - Normalization: [0, 1]  
  - Augmentations: rotation, flip, brightness  

Each image is formatted for **YOLO-CLS** ingestion in the standard **Ultralytics** structure.

---

## ⚙️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/asafribas123/Galaxy-classification-with-YOLO-CLS.git
cd Galaxy-classification-with-YOLO-CLS
pip install -r requirements.txt
```
Or install manually:
```bash
pip install ultralytics numpy pandas matplotlib seaborn tqdm h5py
```
🚀 Usage
```bash
python downloads_dataset.ipynb
```
Train and evaluate the YOLO-CLS model:
```bash
python Yolo_dados.ipynb
```
All intermediate data and model outputs are automatically saved under the dataset_cls/ and results/ directories.

📊 Results
Metric	Value
Top-1 Accuracy	0.90
Top-5 Accuracy	1.00
Macro F1-Score	0.91

Per-class performance:

Smooth → F1 = 0.87

Spiral → F1 = 0.91

Irregular → F1 = 0.94

(See confusion matrix and learning curves under /results.)

🧠 Methodology Summary

Architecture: YOLOv8-CLS (classification head adaptation)

Training: 30 epochs | batch size 16 | image size 128 × 128

Optimizer: SGD (momentum = 0.937) + cosine LR schedule

Hardware: AMD Ryzen 5 4600G (CPU-based training)

The model achieved high stability, generalization, and interpretability, comparable to or exceeding CNNs such as ResNet-50 and EfficientNet.

🔗 Reference Files

File: downloads_dataset.ipynb

Repository: github.com/asafribas123/Galaxy-classification-with-YOLO-CLS

🧾 Citation

If you use this repository, please cite:
```bash
@article{ribas2025yolocls,
  title   = {Deep Learning-Based Morphological Analysis of Galaxies from SDSS and DECaLS Using YOLO-CLS},
  author  = {Ribas, Asaf},
  journal = {IEEE Journal of Computational Modeling},
  year    = {2025}
}
```
👤 Author

Asaf Ribas
Physicist & M.Sc. Student in Computational Modeling – FURG
Research in galaxy morphology, machine learning, and spectroscopy
📧 asaf.ribas@furg.br
📧 asafibas@hotmail.com

