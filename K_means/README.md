# K-means Clustering

K-means is an **unsupervised learning algorithm** used to partition data into **K clusters**.  

---

## How It Works
1. **Initialization**  
   - Select K initial centroids.  
   - In plain K-means, these are chosen randomly.  
   - In **K-means++**, centroids are initialized in a smarter, spread-out way for better results.  

2. **Assignment**  
   - Each data point is assigned to the nearest centroid using a distance metric (commonly **Euclidean distance**).  

3. **Update**  
   - Recalculate each centroid as the mean of all points in its cluster.  

4. **Repeat**  
   - Steps 2 & 3 continue until centroids stop changing significantly (convergence) or the maximum number of iterations is reached.  

---

## Choosing the Number of Clusters (K)
- **Elbow Method**  
  Plot the within-cluster sum of squares (WCSS/inertia) against different values of K.  
  The "elbow" point suggests a good choice of K.  

- **Silhouette Score**  
  A higher silhouette score indicates better-defined clusters (points are close to their cluster and far from others).  

---

## Pros and Cons

**Pros** ✅  
- Simple and easy to understand.  
- Efficient on small to medium datasets.  

**Cons** ❌  
- Sensitive to initial centroid placement.  
- Requires specifying K beforehand.  
- Struggles with clusters of varying shapes and densities.  
- Can be computationally expensive on very large datasets.  

---