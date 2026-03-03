# 🗑️ Garbage Dataset Experiments

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.18841812-blue)](https://doi.org/10.5281/zenodo.18841812)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the complete set of experiments, code, and results for the research article:

**"The Garbage Dataset (GD): A Multi-Class Image Benchmark for Automated Waste Segregation"**

🔗 **Repository**: https://github.com/sumn2u/garbage-dataset-experiments  
📄 **Article**: https://doi.org/10.5281/zenodo.18841812  
📊 **Dataset (Kaggle)**: https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2/

---

## 📌 Overview

This project provides a benchmarking framework used to evaluate state-of-the-art deep learning models on the newly introduced Garbage Dataset (GD). The dataset was constructed through multiple collection methods including the DWaste mobile app and curated web sources, with rigorous validation through checksums and outlier detection.

The dataset consists of **12,259 labeled images** across 10 common household waste categories:

| Category | Category | Category |
|----------|----------|----------|
| Metal | Glass | Biological |
| Paper | Battery | Trash |
| Cardboard | Shoes | Clothes |
| Plastic | | |

The primary goal of this repository is to support reproducible research in automated waste segregation and computer vision applications for environmental sustainability.

---

## 📂 Repository Structure

The repository is organized into Jupyter notebooks for each experimental setup, including variations in image input size (256px and 384px).

### 📊 Exploratory Data Analysis (EDA)

- eda-garbage-dataset.ipynb
- eda-garbage-dataset-256.ipynb
- eda-garbage-dataset-384.ipynb

These notebooks analyze:
- Class imbalance and distribution characteristics
- Visual separability (PCA and t-SNE)
- Background complexity using entropy and saliency measures
- Brightness variations and outlier detection

---

### 🤖 Model Training

The following notebooks implement transfer learning using different backbone architectures. Each model was trained with three input resolutions: default, 256×256, and 384×384.

| Architecture | Notebook Pattern |
|--------------|------------------|
| EfficientNetV2M | garbage-classification-efficientnetv2m-tl-v2*.ipynb |
| EfficientNetV2S | garbage-classification-efficientnetv2s-tl-v2*.ipynb |
| MobileNet | garbage-classification-mobilenet-tl-v2*.ipynb |
| ResNet50 | garbage-classification-resnet50-tl-v2*.ipynb |
| ResNet101 | garbage-classification-resnet101-tl-v2*.ipynb |

Each notebook includes:
- Data loading and preprocessing
- Transfer learning setup
- Model training and validation
- Performance evaluation with metrics (accuracy, F1-score)
- Carbon emission tracking

---

### 📈 Results Visualization

The repository includes training curve visualizations from the experiments:

- Training_accuracy.png
- Training_loss.png
- Validation_accuracy.png
- Validation_loss.png

These figures show the training and validation performance of the top-performing models, demonstrating convergence and generalization characteristics.

---

## 🏆 Key Findings

Based on the benchmarking experiments described in the accompanying research article:

- **Best Performing Model:** **EfficientNetV2S** achieved the highest classification accuracy (**95.13%**) with an **F1-score of 0.95**, while maintaining a moderate computational (carbon) cost.

- **Dataset Characteristics:** Analysis revealed inherent dataset characteristics including class imbalance, a skew toward high-outlier classes (plastic, cardboard, paper), and varying brightness conditions — all critical considerations for real-world deployment.

- **Environmental Trade-offs:** Models were evaluated not only on predictive performance but also on estimated operational carbon emissions, highlighting important trade-offs in model selection for practical deployment.

---

## 🚀 How to Use This Repository

### 1️⃣ Download the Dataset

The Garbage Dataset (GD) is available on Zenodo:

👉 https://doi.org/10.5281/zenodo.18841812

Download and organize it according to the folder structure expected in the notebooks. The dataset includes 12,259 labeled images across all 10 categories.

---

### 2️⃣ Set Up the Environment

The experiments are implemented in **Python** using **Jupyter Notebooks**.

Install the required libraries:
```sh
pip install tensorflow torch scikit-learn numpy matplotlib pandas
```
(Optional) Create a virtual environment before installing dependencies:

Create virtual environment:
```sh
python -m venv garbage-env
```
Activate it (Linux/Mac):
```sh
source garbage-env/bin/activate
```
Activate it (Windows):
```sh
garbage-env\Scripts\activate
```
---

### 3️⃣ Run Experiments

1. Open a notebook (e.g., garbage-classification-efficientnetv2s-tl-v2.ipynb)
2. Update dataset paths if necessary to point to your local GD copy
3. Execute cells sequentially

Each notebook guides you through:
- Data loading and preprocessing
- Model training with transfer learning
- Performance evaluation
- Results visualization

---

## 📚 Citation

If you use this repository or the Garbage Dataset (GD) in your research, please cite the original article:
```sh
@dataset{garbage_dataset_2026,
  author = {Kunwar, Suman},
  title = {The Garbage Dataset (GD): A Multi-Class Image Benchmark for Automated Waste Segregation},
  year = {2026},
  publisher = {Zenodo},
  doi = {10.5281/zenodo.18841812}
}
```

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🌱 Supporting Sustainable AI Research

This repository contributes to research in environmentally responsible AI and intelligent waste management systems. By providing benchmark results that include carbon emission estimates alongside traditional performance metrics, we hope to encourage more holistic evaluation criteria in machine learning research.

---

**If you find this work useful, consider ⭐ starring the repository!**  
Your support helps promote research in sustainable AI applications.
