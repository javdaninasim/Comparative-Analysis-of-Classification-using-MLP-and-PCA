# Comparative Analysis of Classification Using MLP and PCA

> An empirical comparison of **MLP classifiers** with and without **PCA**-based dimensionality reduction.  
> **Author:** Nasim Javdani · [GitHub](https://github.com/javdaninasim) · [LinkedIn](https://linkedin.com/in/nasim-javdani-810a9932a)

---

## Overview

This project systematically investigates how **Principal Component Analysis (PCA)** affects the performance of **Multi-Layer Perceptron (MLP)** classifiers. By varying the number of retained principal components and comparing raw vs. compressed feature spaces, the project quantifies the trade-offs in accuracy, training time, and generalization.

---

## Repository Structure

```
Comparative-Analysis-of-Classification-using-MLP-and-PCA/
│
├── code.ipynb                 # Complete implementation of preprocessing, PCA, MLP, and evaluation
├── MLP and PCA.pdf            # Project report
├── README.md                  # Project documentation
```

---

## Experiments

### 1. Exploratory Data Analysis
- Dataset statistics, class distributions, feature correlations
- Standardization / normalization of input features

### 2. PCA Analysis
- Scree plot and cumulative explained variance curve
- Selection of optimal number of components (e.g., 95% variance retained)
- 2D and 3D PCA projections colored by class label

### 3. Baseline MLP (Raw Features)
- Fully connected neural network on the original feature space
- Hyperparameter search: hidden layers, units, activation, learning rate, dropout
- Evaluation: accuracy, F1-score, confusion matrix

### 4. PCA + MLP Pipeline
- PCA applied upstream; MLP trained on reduced representation
- Sweep over number of PCA components: k = {2, 5, 10, 20, 50, ...}
- Comparison of accuracy and training wall-clock time at each k

### 5. Results & Comparison
- Accuracy vs. number of PCA components curve
- Training time speedup
- Overfitting analysis (train vs. validation curves)
- Qualitative discussion of when PCA helps and when it hurts

---

## Background

PCA projects data onto the directions of maximum variance, discarding low-variance dimensions that often carry noise. This can reduce overfitting and speed up training, but at the cost of removing potentially discriminative information. Whether PCA improves an MLP depends heavily on the dataset structure, class separability in the PCA subspace, and network capacity.

---

## Technologies

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Jupyter Notebook | Interactive experiments and reporting |
| scikit-learn | PCA, MLP classifier, evaluation metrics |
| PyTorch | Alternative deep MLP implementation |
| NumPy / Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualization |

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/javdaninasim/Comparative-Analysis-of-Classification-using-MLP-and-PCA.git
   cd Comparative-Analysis-of-Classification-using-MLP-and-PCA
   ```
2. Install dependencies:
   ```bash
   pip install numpy pandas scikit-learn torch matplotlib seaborn jupyter
   ```
3. Run notebooks in order (1 → 5).

---

## Course Info

- **Topic:** Computer Vision / Pattern Recognition
- **Institution:** Sharif University of Technology, Department of Computer Engineering
