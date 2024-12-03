
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
The methodology is illustrated below:
![alien_galaxy_flowchart](https://github.com/user-attachments/assets/7aa1d192-3cf6-468d-85cc-e8d182c1f956)

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
1. **Hierarchical Clustering (4 clusters, average linkage)**:
   - **Silhouette Score**: **0.371533** (highest among all methods).  
   - **Performance**: Best cluster cohesion and separation, making it the most effective for this dataset.  
   - **Implication**: Recommended as the **optimal clustering method** for this dataset.
     
![Hierachical Clustering(2)](https://github.com/user-attachments/assets/1d1e4d17-aae0-46a7-8c27-ca73478dfde8)

2. **KMeans with Random Initialization (4 clusters)**:
   - **Silhouette Score**: **0.368010** (slightly lower than hierarchical clustering).  
   - **Performance**: Competitive results with strong inter-cluster separation.  
   - **Implication**: A solid choice, especially for computational efficiency.
   - 
![K-means with init=random](https://github.com/user-attachments/assets/a9699f2b-cb94-4b27-9e05-78226edc0f00)

3. **KMeans with k-means++ Initialization (4 clusters)**:
   - **Silhouette Score**: **0.339729**.  
   - **Performance**: Underperforms compared to random initialization but still viable.

4. **Hierarchical Clustering (4 clusters, ward linkage)**:
   - **Silhouette Score**: **0.324577**.  
   - **Performance**: Reasonable but outperformed by average linkage.

5. **DBSCAN (default parameters)**:
   - **Silhouette Score**: **-0.14**.  
   - **Performance**: Fails to identify meaningful clusters due to its density-based assumptions.  
   - **Implication**: **Not suitable** for this dataset.

  ![DB scan with default parameters](https://github.com/user-attachments/assets/25caea51-3e65-4d50-98be-b7a2bfc63d77)

### Correlation Heatmap:
To visualize the relationships between variables, a filtered correlation heatmap was created:
![Filtered Coorelation Heatmap](https://github.com/user-attachments/assets/6206ec30-d2be-4c09-b2c8-ad5826db3d75)

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
The project successfully identified that **Hierarchical Clustering (4 clusters, average linkage)** provides the best clustering for the dataset, offering superior cluster cohesion and separation. **KMeans with random initialization (4 clusters)** is a strong alternative, particularly when computational efficiency is prioritized. 

### Future Work:
- Explore advanced clustering algorithms like Gaussian Mixture Models.  
- Investigate time series or dynamic clustering if the dataset evolves.  
- Apply domain knowledge to improve feature engineering and cluster interpretation.

