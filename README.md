# 🌍 Country Clustering into Continents using Machine Learning

## 📌 Introduction
This project applies **unsupervised machine learning** techniques to cluster countries based on their geographical coordinates (latitude and longitude).  
Two clustering methods were implemented: **K-Means Clustering** and **Hierarchical Clustering (Agglomerative)**.  
The goal is to evaluate which method best identifies clusters that align with the seven continents.

---

## 🎯 Objectives
- Apply **K-Means Clustering** and determine the optimal number of clusters.
- Apply **Agglomerative Hierarchical Clustering** with different parameters and linkage methods.
- Compare both algorithms and identify the most meaningful continent mapping.
- Produce a final mapping of countries → clusters → continents.

---

## 📂 Dataset
- **countries_clusters.csv**  
  Columns:  
  - `latitude` → country’s latitude  
  - `longitude` → country’s longitude  
  - `country_name` → country name  
  - `cluster` → final cluster assignment  

---

## ⚙️ Part 1: K-Means Clustering
### Optimal k Value
- Elbow method suggested **k = 7** (aligning with 7 continents).  
- Final choice: **k = 10**, because SSE reduction flattened after 10 and intra-cluster variance minimized.

### Final Parameters
| Parameter              | Value     |
|-------------------------|-----------|
| Number of Clusters      | 10        |
| Algorithm               | `lloyd`   |
| Initialization          | `k-means++` |
| Max Iterations          | 100       |
| Number of Initializations | 15     |
| Tolerance               | 0.01      |
| Random State            | 42        |
| SSE                     | 46.24     |
| Iterations Run          | 4         |

### Best Clustering Justification
Distances between centroids are large while intra-cluster distances are small, ensuring well-separated and distinct groups.

### Example Centroids
Cluster 0: [-0.032, -0.230]
Cluster 1: [ 0.585, 0.668]
Cluster 2: [-1.123, 0.018]
Cluster 3: [-0.046, 1.229]
Cluster 4: [ 0.768, -2.836]
Cluster 5: [-0.966, -1.746]
Cluster 6: [ 1.847, -1.189]
Cluster 7: [ 0.292, -1.194]
Cluster 8: [-2.366, -1.194]
Cluster 9: [ 1.395, -0.013]


### Cluster → Continent Mapping
| Cluster | Continent     |
|---------|---------------|
| 0       | Europe        |
| 1       | Asia          |
| 2       | North America |
| 3       | Europe        |
| 4       | Antarctica    |
| 5       | South America |
| 6       | Oceania       |
| 7       | Africa        |
| 8       | Oceania       |
| 9       | Asia          |

---

## ⚙️ Part 2: Hierarchical Clustering
### Parameters
| Parameter         | Value      |
|-------------------|------------|
| Number of Clusters | 9         |
| Distance Metric    | Manhattan |
| Linkage            | Complete  |

### Justification
Balanced dendrogram and scatterplot showed **well-separated clusters**, meaning meaningful continent groupings.

### Cluster → Continent Mapping
| Cluster | Continent     |
|---------|---------------|
| 0       | Asia          |
| 1       | Europe        |
| 2       | North America |
| 3       | Africa        |
| 4       | Oceania       |
| 5       | Oceania       |
| 6       | South America |
| 7       | Africa        |
| 8       | Antarctica    |

---

## 📊 Part 3: Best Clustering
Final chosen algorithm: **Agglomerative Clustering**

| Cluster | Continent     |
|---------|---------------|
| 0       | Asia          |
| 1       | Europe        |
| 2       | North America |
| 3       | Africa        |
| 4       | Oceania       |
| 5       | Oceania       |
| 6       | South America |
| 7       | Africa        |
| 8       | Antarctica    |

---
