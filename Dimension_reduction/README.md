# 📉 Dimensionality Reduction Techniques

Dimensionality reduction helps simplify data, reduce noise, and avoid the curse of dimensionality.  
Here are three commonly used techniques:

---

## 1. Principal Component Analysis (PCA)
- **Type**: Linear technique.  
- **Idea**: Transform features into new axes (principal components) that capture the maximum variance.  
- **Steps**:
  1. Standardize data.  
  2. Compute covariance matrix.  
  3. Perform eigen decomposition → eigenvalues (variance explained), eigenvectors (directions).  
  4. Select top components → project data.  
- **Formula**:  
  \[
  Z = XW
  \]  
  where \(W\) = eigenvectors of covariance matrix.  
- **Limitations**: Only captures **linear relationships**.  

---

## 2. Kernel PCA
- **Type**: Nonlinear extension of PCA.  
- **Idea**: Use the **kernel trick** to map data into a higher-dimensional space where linear PCA can capture nonlinear patterns.  
- **Common kernels**: Polynomial, RBF (Gaussian), Sigmoid.  
- **When to use**:  
  - Data not linearly separable.  
  - You want to capture curved or nonlinear structures.  

---

## 3. Multiple Correspondence Analysis (MCA)
- **Type**: Extension of PCA for categorical data.  
- **Idea**: Finds principal components from categorical variables by analyzing relationships between categories.  
- **Use case**: Survey data, categorical datasets (e.g., gender, occupation, preferences).  
- **Benefit**: Provides a low-dimensional representation of categorical data similar to PCA for numeric data.  

---

## ✅ Summary
- **PCA**: Best for numeric, linear data.  
- **Kernel PCA**: Best for nonlinear numeric data.  
- **MCA**: Best for categorical data.  
