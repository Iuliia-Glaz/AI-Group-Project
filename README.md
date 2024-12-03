![Hierachical Clustering(2)](https://github.com/user-attachments/assets/ef473893-d171-4099-acaa-63d26906a445)
# Alien Galaxy Project

## Team Members:
- **Artem Shelygin** - 304291  
- **Keza Kayihura Herta** - 296721  
- **Iuliia Glazkova** - 305031  

---

## Introduction
This project uses machine learning techniques to analyze and cluster data from an alien galaxy dataset. The focus is on cleaning, preprocessing, and applying dimensionality reduction and clustering algorithms to uncover patterns within the data. The final goal is to identify the optimal clustering algorithm and configuration for the dataset.

---

## Methods

We began with data loading from the provided alien galaxy dataset. Missing values were identified and handled through imputation techniques, specifically using the K-Nearest Neighbors (KNN) algorithm to ensure the integrity of the dataset. Outliers were detected and removed using the Z-score method, with a threshold of 6 to balance the retention of valid data points against the exclusion of anomalies. Following this, feature engineering was performed to extract meaningful insights by analyzing feature co...

Dimensionality reduction was applied through Principal Component Analysis (PCA), allowing the high-dimensional dataset to be visualized and analyzed in reduced dimensions. Subsequently, clustering algorithms, including K-Means, Hierarchical Clustering, and DBSCAN, were applied to group similar data points. Each algorithm underwent hyperparameter tuning to optimize clustering performance based on metrics such as silhouette scores, Davies-Bouldin Index, and Calinski-Harabasz Index.

### Flowchart

![alien_galaxy_flowchart](https://github.com/user-attachments/assets/b51187ab-7633-4a3b-863c-2e4a7601a539)

---

## Experimental Design

### Experiments Conducted:
1. **Purpose**: To identify the best clustering algorithm and hyperparameters for the dataset.  
2. **Baselines**: Default configurations of K-Means, Hierarchical, and DBSCAN clustering.  
3. **Evaluation Metrics**:  
   - **Silhouette Score**: Measures cluster cohesion and separation.  
   - **Davies-Bouldin Index**: Evaluates intra-cluster similarity and inter-cluster separation.  
   - **Calinski-Harabasz Index**: Measures the variance ratio.  

### Key Experiment Setup:
- Hyperparameter optimization for K-Means (`clusters`, `init`).  
- Linkage methods comparison for Hierarchical Clustering.  
- Epsilon and minimum samples grid search for DBSCAN.

---

## Results

### Main Findings:
- **K-Means with Random Initialization**: Optimal for 4 clusters based on silhouette scores and visual analysis.  
![K-means with init=random](https://github.com/user-attachments/assets/0eb8da02-fdef-41ce-87fc-16fad1f1f150)

- **Hierarchical Clustering**: Produced comparable results but showed challenges in creating distinct clusters.  
 ![Hierachical Clustering(2)](https://github.com/user-attachments/assets/994beedf-45db-4b9e-b260-f5f86d287d18)

- **DBSCAN**: Showed suboptimal performance due to low silhouette scores and difficulty handling the dataset's distribution.  
![DB scan with default parameters](https://github.com/user-attachments/assets/06a1b419-6056-4c8f-be31-fe7e70505131)

### Correlation Heatmap:
To visualize the relationships between variables, a filtered correlation heatmap was created:
![Filtered Coorelation Heatmap](https://github.com/user-attachments/assets/c06c77b7-b1d4-428a-b30e-a0d8ebfb1c75)

### Performance Metrics Table:
| Clustering Algorithm                    | Silhouette Score | Davies-Bouldin Index | Calinski-Harabasz Index |
|-----------------------------------------|------------------|-----------------------|--------------------------|
| KMeans (4 clusters, init=random)        | 0.368010         | 1.063667             | 2060.024907              |
| KMeans (4 clusters, init=k-means++)     | 0.339729         | 0.978934             | 1944.760596              |
| Hierarchical (4 clusters, average)      | 0.371533         | 0.701945             | 833.760778               |
| Hierarchical (4 clusters, ward)         | 0.324577         | 0.944441             | 1758.477732              |
| KMeans (5 clusters, init=random)        | 0.333002         | 1.026948             | 1955.665989              |
| KMeans (5 clusters, init=k-means++)     | 0.332238         | 1.032815             | 1955.571110              |
| Hierarchical (5 clusters, average)      | 0.228646         | 0.807510             | 663.209367               |
| Hierarchical (5 clusters, ward)         | 0.324577         | 0.944441             | 1758.477732              |

---

## Conclusions

### Summary:
The project successfully identified that K-Means with random initialization provides the best clustering for the dataset with 4 clusters. Dimensionality reduction and preprocessing steps significantly improved clustering results.

### Future Work:
- Explore advanced clustering algorithms like Gaussian Mixture Models.  
- Investigate time series or dynamic clustering if the dataset evolves.  
- Apply domain knowledge to improve feature engineering and cluster interpretation.

