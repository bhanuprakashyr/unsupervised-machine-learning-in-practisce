# 🔑 Distance Measures Cheat Sheet

| Distance Measure     | Formula                                                                 | Best Use Cases |
|----------------------|-------------------------------------------------------------------------|----------------|
| **Euclidean**        | \(d(x, y) = \sqrt{\sum_{i=1}^n (x_i - y_i)^2}\)                        | K-means, continuous data |
| **Squared Euclidean**| \(d(x, y) = \sum_{i=1}^n (x_i - y_i)^2\)                               | Faster K-means computations |
| **Manhattan (L1)**   | \(d(x, y) = \sum_{i=1}^n \|x_i - y_i\|\)                               | Grid-like paths, sparse data |
| **Minkowski**        | \(d(x, y) = \Big(\sum_{i=1}^n \|x_i - y_i\|^p\Big)^{1/p}\)             | Generalization of Euclidean/Manhattan |
| **Chebyshev**        | \(d(x, y) = \max_i \|x_i - y_i\|\)                                     | Hierarchical clustering (max linkage) |
| **Cosine Distance**  | \(d(x, y) = 1 - \frac{x \cdot y}{\|x\|\|y\|}\)                         | Text mining, high-dimensional vectors |
| **Mahalanobis**      | \(d(x, y) = \sqrt{(x-y)^T S^{-1}(x-y)}\), where \(S\) = covariance matrix | PCA, correlated features |


# 🗺️ Unsupervised Learning Algorithm Map

## 1. Clustering

### K-Means
- **Goal**: Partition data into *k* clusters by minimizing within-cluster variance.  
- **Update Rule**: Assign points → recompute centroids → repeat.  
- **Distance**: Usually Euclidean.  
- **Choosing k**:  
  - **Elbow Method**: Plot SSE vs. k, look for “elbow.”  
  - **Silhouette Score**:  
    \[
    s = \frac{b - a}{\max(a, b)}
    \]
    where *a* = intra-cluster distance, *b* = nearest-cluster distance.  
    Range: \([-1, 1]\). Higher = better.

### Hierarchical Clustering
- **Agglomerative (bottom-up)** or **Divisive (top-down)**.  
- **Linkage**: Single, Complete, Average, Ward.  
- **Visualization**: Dendrogram (tree of merges).  

### DBSCAN
- **Parameters**:  
  - `eps`: neighborhood radius.  
  - `minPts`: minimum neighbors for core point.  
- **Key Feature**: Finds clusters of arbitrary shape, identifies noise.  

---

## 2. Dimensionality Reduction

### PCA (Principal Component Analysis)
- **Step 1**: Standardize data.  
- **Step 2**: Compute covariance matrix.  
- **Step 3**: Eigen-decomposition → eigenvalues (variance explained), eigenvectors (directions).  
- **Step 4**: Select top components → project data.  

Formula:  
\[
Z = XW
\]  
where \(W\) = matrix of eigenvectors.  

### SVD (Singular Value Decomposition)
- Matrix factorization:  
  \[
  A = U \Sigma V^T
  \]  
- Basis for PCA.  
- In recommenders: factorizes user–item matrices (SVD, SVD++).

---

## 3. Association Rule Learning (Market Basket)

### Apriori Algorithm
- **Frequent Itemsets** → Generate association rules.  
- **Metrics**:  
  - **Support**: \( P(A \cup B) \).  
  - **Confidence**: \( P(B|A) = \frac{P(A \cup B)}{P(A)} \).  
  - **Lift**: \( \frac{P(B|A)}{P(B)} \).  

---

## 4. Recommendation Systems

### Types
- **Popularity-based**: Recommend top-N frequent items.  
- **Content-based**: Use item features, cosine similarity.  
- **Collaborative Filtering**:  
  - **User–User** or **Item–Item** similarity.  
  - **Matrix Factorization (SVD, SVD++)** with Surprise library.  

### Evaluation
- **Classification tasks**: Accuracy, Precision, Recall, F1, Classification Report.  
- **Regression/Recommenders**: RMSE, MAE.  

---

## 5. Evaluation & Model Tuning

- **Cross-Validation (k-fold)**: Ensure generalization.  
- **GridSearchCV**: Hyperparameter tuning.  
- **Clustering Metrics**: Silhouette, Davies–Bouldin.  
- **Visualization**: Elbow plots, dendrograms.

---

## 6. Supporting Tools

- **StandardScaler**: Normalize features before PCA/KMeans.  
- **Distance Measures**: Euclidean, Manhattan, Cosine, Mahalanobis.  
- **Improvement Strategy**: Start simple (Logistic Regression / baseline) → apply PCA/KMeans/SVD → evaluate → tune with CV/GridSearch.

