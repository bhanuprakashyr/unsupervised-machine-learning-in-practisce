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
