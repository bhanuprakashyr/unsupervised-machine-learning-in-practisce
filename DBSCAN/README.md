# 🌌 DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

## Overview
DBSCAN is a density-based clustering algorithm. Unlike KMeans or Hierarchical clustering, it does **not require the number of clusters in advance** and can find clusters of **arbitrary shape**. It is also robust to outliers by marking them as noise.

## Key Concepts
- **Epsilon (ε)**: The neighborhood radius. Points within this distance are considered neighbors.
- **minPts**: The minimum number of neighbors required (including the point itself) for a point to be a **core point**.

### Point Types
- **Core Point**: Has at least `minPts` neighbors within radius ε.
- **Border Point**: Has fewer than `minPts` neighbors, but is within ε of a core point.
- **Noise Point**: Neither core nor border (an outlier).

## Algorithm Steps
1. Pick an unvisited point.
2. If it is a **core point**, start a new cluster and expand it by visiting all neighbors within ε.
3. Repeat recursively for each neighbor that is also a core point.
4. Continue until all points are visited.

## Parameters to Tune
- **ε (eps)**: Too small → many noise points; Too large → fewer, overly merged clusters.
- **minPts**: Rule of thumb = `2 * number_of_dimensions`.

## Pros
- Does not require number of clusters in advance.
- Can find arbitrarily shaped clusters.
- Naturally identifies outliers (noise).

## Cons
- Sensitive to choice of ε and minPts.
- Struggles in datasets with varying density.

## When to Use
- Spatial/geographic data (irregular cluster shapes).
- Datasets with noise/outliers.
- When the number of clusters is unknown.
