# Principal Component Analysis (PCA) on World Happiness Data

This repository contains two Jupyter notebooks that explore **Principal Component Analysis (PCA)** applied to the **World Happiness Index** dataset.  
The goal is to understand how PCA works both **from first principles** and **using a production-ready library**, and to compare the results.

---

## 📊 Dataset

The analysis is based on the World Happiness data, using the following numerical features:

- GDP per capita  
- Social support  
- Healthy life expectancy  
- Freedom to make life choices  
- Generosity  
- Perceptions of corruption  

Each row corresponds to a country, and PCA is used to reduce the dimensionality of this multivariate dataset while preserving as much variance as possible.

---

## 📁 Notebooks Overview

### 1. `homemade_PCA.ipynb` — PCA from scratch

This notebook implements **PCA manually**, following the mathematical definition step by step:

- Centering (and optionally standardizing) the data  
- Computing the covariance matrix  
- Eigenvalue and eigenvector decomposition  
- Sorting components by explained variance  
- Projecting the data onto principal components  

**Purpose of this notebook:**
- Build an intuitive and mathematical understanding of PCA
- Verify what PCA is actually doing under the hood
- Gain confidence in interpreting eigenvectors, eigenvalues, and variance ratios

This notebook is mainly **educational** and useful for learning and validation.

---

### 2. `sklearn_PCA.ipynb` — PCA using scikit-learn

This notebook performs PCA using the `sklearn.decomposition.PCA` class:

- Fast and reliable PCA computation
- Explained variance ratios and cumulative variance
- Clean transformation into PCA space
- Easy integration with pandas DataFrames

**Purpose of this notebook:**
- Perform PCA efficiently and cleanly
- Focus on analysis and interpretation rather than implementation details
- Use a method suitable for real-world pipelines and larger datasets

---

## 🔍 Comparison of Results

Both approaches were compared carefully:

- The **principal components** are equivalent (up to sign)
- The **explained variance ratios** are nearly identical
- The **projected data** in PCA space matches across methods

➡️ **Conclusion:**  
There is **no significant difference** in the results between the manual PCA and the scikit-learn PCA.

---

## ⚡ Recommendation

- ✅ Use **`homemade_PCA.ipynb`** to **learn and understand PCA**
- 🚀 Use **`sklearn_PCA.ipynb`** for **speed, clarity, and practical applications**

For any real analysis or modeling workflow, the **scikit-learn implementation is recommended** due to its efficiency, numerical stability, and simplicity.

---

## 🧠 Key Takeaways

- PCA reveals that a small number of latent dimensions explain most of the variance in global happiness data
- The first principal component alone captures a very large fraction of the total variance
- Manual implementations are valuable for learning, but libraries should be used in practice

---

## 📌 Requirements

- Python 3.x  
- numpy  
- pandas  
- scikit-learn  
- matplotlib / seaborn (for visualization)

---

## 📈 Possible Extensions

- PCA visualization (2D / biplots)
- Clustering countries in PCA space
- Interpreting principal components semantically
- Comparing PCA across multiple years of happiness data

---

## 📝 Notes

The sign of principal components may differ between implementations — this is expected and does not affect interpretation.

---

*This project was created as an exploratory and educational exercise in dimensionality reduction and data analysis.*
