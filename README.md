
##Alien Galaxy Project
Team Members:
Artem Shelygin - 304291
Keza Kayihura Herta - 296721
Iuliia Glazkova - 305031
Introduction
This project uses machine learning techniques to analyze and cluster data from an alien galaxy dataset. The focus is on cleaning, preprocessing, and applying dimensionality reduction and clustering algorithms to uncover patterns within the data. The final goal is to identify the optimal clustering algorithm and configuration for the dataset.
.
##Methods
We began with data loading from the provided alien galaxy dataset. Missing values are identified and handled through imputation techniques, specifically using the K-Nearest Neighbors (KNN) algorithm to ensure the integrity of the dataset. Outliers are detected and removed using the Z-score method, with a threshold of 6 to balance the retention of valid data points against the exclusion of anomalies. Following this, feature engineering is performed to extract meaningful insights by analyzing feature correlations and filtering redundant or non-informative variables.
Dimensionality reduction is applied through Principal Component Analysis (PCA), allowing the high-dimensional dataset to be visualized and analyzed in reduced dimensions. Subsequently, clustering algorithms including K-Means, Hierarchical Clustering, and DBSCAN are applied to group similar data points. Each algorithm undergoes hyperparameter tuning to optimize clustering performance based on metrics such as silhouette scores, Davies-Bouldin Index, and Calinski-Harabasz Index.



##Experimental Design
Experiments Conducted:
Purpose: To identify the best clustering algorithm and hyperparameters for the dataset.
Baselines: Default configurations of K-Means, Hierarchical, and DBSCAN clustering.
Evaluation Metrics:
Silhouette Score: Measures cluster cohesion and separation.
Davies-Bouldin Index: Evaluates intra-cluster similarity and inter-cluster separation.
Calinski-Harabasz Index: Measures the variance ratio.
Key Experiment Setup:
Hyperparameter optimization for K-Means (clusters, init).
Linkage methods comparison for Hierarchical Clustering.
Epsilon and minimum samples grid search for DBSCAN.

##Results
Main Findings:
K-Means with Random Initialization: Optimal for 4 clusters based on silhouette scores and visual analysis.
Hierarchical Clustering: Produced comparable results but showed challenges in creating distinct clusters.
DBSCAN: Showed suboptimal performance due to low silhouette scores and difficulty handling the dataset's distribution.
Performance Metrics Table:
Clustering Algorithm
Silhouette Score
Davies-Bouldin Index
Calinski-Harabasz Index
K-Means (4 clusters, init=random)
0.72
1.08
2054
K-Means (4 clusters, init=k-means++)
0.70
1.15
2005
Hierarchical (4 clusters, average)
0.75
0.95
2150
Hierarchical (4 clusters, ward)
0.77
0.92
2205
K-Means (5 clusters, init=random)
0.74
1.10
2100

##Conclusions
Summary:
The project successfully identified that K-Means with random initialization provides the best clustering for the dataset with 4 clusters. Dimensionality reduction and preprocessing steps significantly improved clustering results.
Future Work:
Explore advanced clustering algorithms like Gaussian Mixture Models.
Investigate time series or dynamic clustering if the dataset evolves.
Apply domain knowledge to improve feature engineering and cluster interpretation.

