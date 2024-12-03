Alien Galaxy   
Artem Shelygin 304291,
Keza Kayihura Herta 296721,
Iuliia Glazkova, 305031

Introduction
The project focuses on analyzing and addressing missing data in the alien_galaxy.csv dataset. Missing data can significantly impact the quality and reliability of downstream analyses, making it crucial to assess its patterns and randomness.
Our primary goal was to detect and understand the patterns of missing data and determine if they were Missing Completely at Random (MCAR) or exhibited more complex dependencies. This foundational step sets the stage for robust data cleaning and preparation, ultimately enabling better machine learning or statistical modeling.

Methods! 
[3D Clustering Visualization](https://github.com/user-attachments/assets/f77eab16-9b03-4152-a79c-81da54a05dfe)

Our methodology revolves around understanding the "when" and "why" behind missing values in the dataset. Below is a flowchart summarizing the steps we followed:
Key Steps:
Loading the Dataset: We started by importing and inspecting the dataset to understand the structure and identify variables with missing values.
Visualizing Missing Data: Using advanced visualization techniques, we created a missing data matrix and a heatmap. These tools offered insights into how missing values were distributed and whether they correlated across features.
Pattern Analysis: We analyzed whether the missing data pattern was consistent with Missing Completely at Random (MCAR), based on both visualization and statistical checks.
Environment Setup: The tools we relied on include pandas, matplotlib, seaborn, and the missingno library. All details about the environment and dependencies are available in the repository for reproducibility.


Experimental Design
The purpose of our experiments was to validate the hypothesis that the missing data followed the MCAR pattern. This simplifies data cleaning since no complex dependencies need to be accounted for. We relied on:
Visual Baseline: Missing data visualizations.
Evaluation Metric: Percentage of missing data and its uniformity across variables.


Results
Takeaways
The analysis of the Alien Galaxy dataset provided valuable insights into the nature of missing data. Our findings indicate that the missing values are likely Missing Completely at Random (MCAR), as visualized through a uniform distribution of missing entries across features and the lack of strong correlations in the missingness patterns. This conclusion simplifies the process of addressing missing data, as it suggests that simple imputation methods, such as mean or median imputation, are both appropriate and effective for this dataset. Additionally, the systematic evaluation of missing data through tools like heatmaps and missing data matrices ensures that the data cleaning process is rooted in evidence rather than assumptions. This work establishes a foundation for further analyses by ensuring that data preprocessing choices are informed and aligned with the nature of the missing data.

Unanswered Questions and Next Steps
While this analysis confirms the randomness of missing values, it does not explore how different imputation strategies might affect the performance of downstream models. For example, while mean or median imputation appears suitable, it may not fully capture the nuances of more complex datasets or variables with unique distributions. Another unanswered question relates to whether this missing data pattern holds for subsets of the data or if there are latent group-specific variations that were not detected in our aggregate-level analysis. Future work should focus on evaluating the impact of various imputation techniques on predictive model accuracy and other performance metrics. Additionally, advanced methods like multiple imputations or model-based imputations (e.g., k-Nearest Neighbors or regression imputation) should be explored to ensure robustness. Finally, conducting a comparative analysis across related datasets could provide deeper insights into whether the MCAR pattern is consistent in similar contexts or if dataset-specific adjustments are necessary.
