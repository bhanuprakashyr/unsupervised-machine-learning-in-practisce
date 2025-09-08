## Hierarchical (Agglomerative) Clustering

Hierarchical clustering is another clustering technique where:  
- Each data point starts as its own cluster.  
- In each iteration, the closest clusters merge together.  
- This merging process continues until all points are clustered into a hierarchy, which can be visualized with a dendrogram.

**Key Points:**  
- The dendrogram helps decide the number of logical clusters by choosing where to cut the tree.  
- It can reveal sub-clusters within clusters.  
- However, it's computationally expensive for large datasets.


## Linkage Methods in Agglomerative Clustering

| Linkage Type  | Definition                                                                 | When to Use It                                   |
|--------------|-----------------------------------------------------------------------------|----------------------------------------------------|
| Single Linkage | Distance between the two closest points in each cluster (minimum distance).       | Use when you want to find long, chain-like clusters, but beware of “chaining effects.”           |
| Complete Linkage| Distance between the two farthest points in each cluster (maximum distance).        | Use when you want compact, evenly shaped clusters and want to avoid large, spread-out clusters.        |
| Average Linkage | Distance is the average of all pairwise distances between clusters.                | Use when you want a balanced approach that considers the overall average distance between clusters.          |
| Ward’s Linkage   | Minimizes the variance between clusters, resulting in clusters of similar size.              | Use when you want clusters that are similar in size and you want to minimize variance within clusters.  |

