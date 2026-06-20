<div align="center">

<h1 align="center">🔬 Comparative Analysis of Classification Using MLP and PCA</h1>
<h3 align="center">Empirical Study on Dimensionality Reduction Impact | Sharif University of Technology</h3>

[**GitHub**](https://github.com/javdaninasim/Comparative-Analysis-of-Classification-using-MLP-and-PCA) &nbsp; ⬩ &nbsp; [**University**](https://sharif.edu/)

</div>

---

### 📚 Project Overview

```python
class ComparativeAnalysis:
    def __init__(self):
        self.institution = "Sharif University of Technology"
        self.department = "Computer Engineering"
        self.focus = "Pattern Recognition & Computer Vision"
        
    def research_question(self):
        return """
        How does Principal Component Analysis (PCA) dimensionality reduction
        affect the classification performance and training efficiency of 
        Multi-Layer Perceptron (MLP) classifiers?
        """
    
    def methodology(self):
        return {
            "Baseline": "MLP on raw feature space",
            "Treatment": "MLP with upstream PCA transformation",
            "Metrics": ["Accuracy", "F1-Score", "Training Time", "Overfitting Analysis"],
            "Variations": "Sweep over k = {2, 5, 10, 20, 50, ...} PCA components"
        }
```

---

### 📂 Repository Structure

```
Comparative-Analysis-of-Classification-using-MLP-and-PCA/
│
├── code.ipynb                    # Complete implementation & experiments
├── MLP and PCA.pdf               # Full research report with findings
└── README.md                     # Project documentation
```

---

### 🎯 Research Framework

#### **Phase 1: Exploratory Data Analysis (EDA)**
- Dataset statistics and class distributions
- Feature correlation analysis
- Data standardization/normalization
- Visualization of feature space

#### **Phase 2: PCA Analysis**
- **Scree Plot Generation:** Visualize explained variance by component
- **Cumulative Variance Curve:** Identify elbow point for optimal k
- **Variance Retention:** Determine components needed for 95%+ variance
- **2D & 3D Projections:** Visualize class separation in reduced space
- **Component Interpretation:** Analyze loadings and feature importance

#### **Phase 3: Baseline MLP Classifier**
- **Architecture:** Fully connected neural network on original features
- **Hyperparameter Tuning:**
  - Hidden layer sizes
  - Number of hidden layers
  - Activation functions (ReLU, Tanh, Sigmoid)
  - Learning rate
  - Dropout rates
  - Batch size
- **Performance Metrics:**
  - Classification accuracy
  - F1-score (macro/weighted)
  - Confusion matrix analysis
  - ROC-AUC curves

#### **Phase 4: PCA + MLP Pipeline**
- **Preprocessing Chain:** Raw Features → PCA → MLP
- **Component Sweep:** Train MLP for k = {2, 5, 10, 20, 50, ...}
- **Performance Comparison:** 
  - Accuracy vs. number of components
  - Training time at each k
  - Convergence speed
  - Memory usage

#### **Phase 5: Comparative Analysis & Results**
- **Accuracy Curves:** Baseline vs PCA+MLP across different k
- **Time-Accuracy Trade-off:** Training speedup vs. performance loss
- **Overfitting Analysis:** Train/validation performance gap
- **Statistical Significance:** t-tests or significance tests
- **Practical Recommendations:** When to use PCA

---

### 🧪 Key Research Questions

1. **Dimensionality Sweet Spot:** What number of PCA components maintains classifier performance?
2. **Computational Efficiency:** How much training time speedup does PCA provide?
3. **Variance-Accuracy Relationship:** Is there a correlation between retained variance and accuracy?
4. **Dataset Sensitivity:** How do results vary across different datasets?
5. **Overfitting Mitigation:** Does PCA reduce model overfitting?

---

### 📊 Expected Outcomes

| Aspect | Expected Finding |
| :--- | :--- |
| **Accuracy Trade-off** | Small accuracy drop (1-5%) with significant dimensionality reduction |
| **Training Time** | 2-10x speedup depending on feature and component reduction |
| **Optimal Components** | Typically 80-95% of components needed for 95%+ variance retention |
| **Overfitting Impact** | PCA may reduce overfitting by acting as regularization |
| **Dataset Dependency** | Results vary based on dataset structure and noise levels |

---

### ⚡ Tech Stack

<div align="left">
  <img src="https://img.shields.io/badge/Python-1A1A1A?style=for-the-badge&logo=python&logoColor=3776AB" alt="Python" />
  <img src="https://img.shields.io/badge/Jupyter-1A1A1A?style=for-the-badge&logo=jupyter&logoColor=F37726" alt="Jupyter" />
  <img src="https://img.shields.io/badge/scikit--learn-1A1A1A?style=for-the-badge&logo=scikit-learn&logoColor=F7931E" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/PyTorch-1A1A1A?style=for-the-badge&logo=pytorch&logoColor=EE4C2C" alt="PyTorch" />
  <img src="https://img.shields.io/badge/NumPy-1A1A1A?style=for-the-badge&logo=numpy&logoColor=013243" alt="NumPy" />
  <img src="https://img.shields.io/badge/Pandas-1A1A1A?style=for-the-badge&logo=pandas&logoColor=150458" alt="Pandas" />
  <img src="https://img.shields.io/badge/Matplotlib-1A1A1A?style=for-the-badge&logo=python&logoColor=11557C" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Seaborn-1A1A1A?style=for-the-badge&logo=python&logoColor=0055D4" alt="Seaborn" />
</div>

<br>

> **Core Libraries:** `scikit-learn` (PCA, MLPClassifier) ⬩ `PyTorch` (MLP implementation) ⬩ `NumPy` ⬩ `Pandas` ⬩ `Matplotlib/Seaborn`

---

### 📖 Notebook Structure

**`code.ipynb`** contains:

1. **Imports & Setup** – Libraries and configuration
2. **Data Loading & EDA** – Dataset exploration
3. **PCA Implementation** – Scree plot, variance analysis, visualization
4. **Baseline MLP** – Full-dimensional classifier
5. **Hyperparameter Tuning** – Optimize baseline performance
6. **PCA+MLP Pipeline** – Systematic comparison across k
7. **Results & Visualization** – Accuracy curves, trade-offs
8. **Analysis & Conclusions** – Key findings and recommendations

---

### 💡 Key Insights

| Finding | Implication |
| :--- | :--- |
| **PCA is Regularization** | Dimensionality reduction acts as implicit regularization, reducing model variance |
| **Curse of Dimensionality** | High-dimensional raw features can lead to overfitting; PCA mitigates this |
| **Information Preservation** | First few PCs often capture 80-90% of variance with minimal accuracy loss |
| **Computational Gains** | Training time often scales with feature dimension; PCA provides linear algebra benefits |
| **Noise Filtering** | Lower-variance components (noise) are discarded, improving generalization |
| **Dataset-Dependent** | Optimal k varies; manifold properties determine ideal dimensionality |

---

### 📚 Theoretical Background

**Principal Component Analysis (PCA):**
- Linear transformation to orthogonal basis maximizing variance
- Eigenvalue decomposition of covariance matrix
- Identifies principal directions in feature space
- Information loss vs. dimensionality trade-off

**Multi-Layer Perceptron (MLP):**
- Universal function approximator with hidden layers
- Backpropagation for weight optimization
- Prone to overfitting in high-dimensional spaces
- Computational cost scales with feature dimension

**Combined Approach:**
- PCA as preprocessing reduces curse of dimensionality
- Lower input dimension → faster training
- Potential information loss must be balanced against gains
- Empirical comparison essential for decision-making

---

### 📄 Report & Findings

See **`MLP and PCA.pdf`** for:
- Detailed methodology
- Full experimental results
- Statistical analysis
- Visualizations and plots
- Conclusions and recommendations

---

### 🎓 Learning Outcomes

- ✨ Understand **PCA algorithm** and its geometric interpretation
- 🧠 Master **MLP architecture** and training dynamics
- 📊 Conduct **empirical comparative studies** in ML
- 🔬 Analyze **trade-offs** between accuracy and efficiency
- 💪 Build **end-to-end ML pipelines** with proper evaluation

---

### ℹ️ Project Information

| Detail | Information |
| :--- | :--- |
| **Institution** | Sharif University of Technology, Dept. of Computer Engineering |
| **Topic** | Computer Vision / Pattern Recognition / ML |
| **Project Type** | Comparative Analysis / Empirical Study |
| **Focus** | Dimensionality Reduction & Classification |
| **Datasets** | Multiple benchmark datasets |
| **Report** | Included as PDF |
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=808080&height=100&section=footer" width="100%"/>
</div>
