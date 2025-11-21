# 🌸 Iris Classification with K-Nearest Neighbors (KNN)

This project explores the **Iris dataset** using the **K-Nearest Neighbors (KNN)** algorithm.  
The goal is to predict the species of an iris flower (*Iris-setosa*, *Iris-versicolor*, *Iris-virginica*) based on its sepal and petal measurements.

---

## 🧭 Project Overview

This notebook follows a **complete machine learning workflow**:

1. **Data Exploration & Visualization**  
   - Load the classic Iris dataset using `scikit-learn`.  
   - Visualize relationships between features using scatter plots and pairplots.  
   - Observe natural clusters and class separations.

2. **Data Preparation**  
   - Split data into **training (80%)** and **testing (20%)** sets.  
   - Standardize features with `StandardScaler` (important for distance-based models like KNN).

3. **Model Training & Evaluation**  
   - Train a KNN classifier with default hyperparameters (`n_neighbors=5`).  
   - Evaluate model performance using:
     - Accuracy  
     - Confusion matrix  
     - Precision, recall, and F1-score  

4. **Confidence Intervals for Accuracy**  
   - Compute a **95% confidence interval** for test accuracy using:
     - **Binomial proportion method**  
     - **Bootstrap resampling**
   - This quantifies the uncertainty in the model’s estimated performance.

5. **Cross-Validation for Robust Estimation**  
   - Apply **5x5 Repeated K-Fold Cross-Validation** to get a more stable estimate of accuracy.  
   - Report the mean and standard deviation across folds.

6. **Final Model and Pessimistic Accuracy Estimate**  
   - Train the final KNN model on the **entire dataset**.  
   - The **pessimistic accuracy** (from cross-validation) is reported as the realistic expected performance on unseen data.  
   - The true accuracy is likely higher, but this approach avoids over-optimism.

---

## 📊 Key Concepts Illustrated

- Feature scaling for distance-based algorithms  
- Model evaluation on held-out data  
- Statistical confidence intervals  
- Cross-validation for unbiased performance estimation  
- Importance of separating model assessment from final training  

---

## 🧠 Technologies Used

- **Python 3**
- **pandas**, **numpy**
- **matplotlib**, **seaborn**
- **scikit-learn**
- **statsmodels**

---

## 🏁 Results Summary

| Metric | Value (Example) |
|--------|-----------------|
| Test Accuracy | ~0.93 |
| 95% CI (Bootstrap) | [0.85, 0.98] |
| Cross-Validated Accuracy | 0.93 ± 0.03 |

---

## 🎨 Visualizations

- Pairplot of all features, colored by species  
- Confusion matrix heatmap  
- Optional: 2D KNN decision boundary illustration  
 
