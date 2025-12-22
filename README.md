# Hospital Readmission Analysis

This project explores patient profiles associated with hospital readmission using multivariate statistical methods.

## Context
Hospital readmissions are a major concern for healthcare systems, as they may indicate issues related to patient management, treatment effectiveness, or post-discharge care. Identifying patient profiles associated with higher readmission risk can help improve healthcare planning and resource allocation.

## Objective
The objective of this project is to identify and characterize patient profiles associated with hospital readmission using interpretable statistical techniques.

## Data
The analysis is based on a public healthcare dataset containing anonymized patient-level information related to hospital admissions and readmissions.

## Methodology
- Data cleaning and preprocessing  
- Exploratory data analysis  
- Principal Component Analysis (PCA)   
- k-means clustering  

## Tools
- R  
- RStudio  
- R Markdown  
- FactoMineR  

## Expected Outcomes
This analysis aims to highlight distinct patient profiles and explore their relationship with hospital readmission patterns, providing insights that could support data-driven decision-making in healthcare contexts.

## PCA Results

A PCA was applied to the numeric variables of the dataset (13 variables, 101,766 observations) after data cleaning and standardization.

Two standard criteria were used to determine the number of components to retain:

- **Kaiser criterion** (eigenvalues > 1), which suggests retaining **5 principal components**.
- **Cumulative explained variance criterion**, according to which approximately **9 components** are required to explain around **80% of the total variance**.

In line with standard academic practice and interpretability considerations, **5 principal components were retained**.

**Interpretation of the first components**
- **First Principal Component** captures the intensity and severity of hospital care, with high contributions from variables such as the number of medications, time in hospital, lab procedures, and number of diagnoses. These variables show high contributions and strong coordinates on the first axis, indicating that PC1 captures the overall intensity of medical care.
- **Second Principal Component** is associated with patient administrative and admission characteristics, including
encounter ID, patient number, and discharge disposition.
These variables are well represented on the second axis, as confirmed by their cos² values.

_The retained principal components are used as input for hierarchical clustering (CAH) and k-means clustering to identify patient profiles associated with hospital readmission patterns._

## Clustering (k-means)

After reducing the dimensionality of the dataset using PCA (5 retained components),
k-means clustering was applied on the individuals coordinates in the PCA space.

A partition into **4 clusters** was selected, based on interpretability and stability
considerations.

The resulting clusters are well balanced and reveal distinct patient profiles.

The k-means clustering applied to the retained PCA components (k = 4) reveals four distinct patient profiles:

- **Cluster 1** corresponds to patients with moderate hospital stays and medication use, suggesting stable chronic conditions with regular follow-up.
- **Cluster 2** groups low-severity patients characterized by short hospital stays, few procedures, and minimal use of healthcare resources.
- **Cluster 3** represents intermediate cases with moderate levels of hospitalization, procedures, and diagnoses.
- **Cluster 4** includes high-complexity patients with long hospital stays, high medication intake, frequent procedures, and multiple diagnoses, indicating a higher risk of hospital readmission.

These clusters highlight meaningful heterogeneity in patient profiles and support the identification of high-risk groups for targeted healthcare interventions.

## Clustering Results 

## Clustering and interpretation

Based on the retained PCA components, a k-means clustering (k = 4) was performed to identify patient profiles.

The clusters were interpreted using the mean values of the original numerical variables for each group.

- **Cluster 1 – Standard hospitalization patients**: patients with moderate length of stay and average medical resource usage.
- **Cluster 2 – Acute care patients**: patients frequently admitted through emergency services, with short but intensive hospital stays.
- **Cluster 3 – Low-severity patients**: patients with low medical complexity, few procedures, and short hospitalizations.
- **Cluster 4 – Complex patients**: patients characterized by long hospital stays, high medication use, and multiple procedures.

These profiles highlight heterogeneity in patient trajectories and may be relevant for understanding hospital readmission patterns.

## Conclusion

This project applied multivariate statistical methods to explore hospital readmission data.

Principal Component Analysis (PCA) was first used to reduce dimensionality while preserving most of the information contained in the original variables. The retained components captured key aspects of hospital utilization and patient severity.

Subsequently, k-means clustering on the PCA coordinates allowed the identification of distinct patient profiles, ranging from low-severity cases to complex patients requiring intensive care.

This analysis highlights the existence of distinct patient profiles with different levels of healthcare utilization. The results suggest that patients with higher medical complexity and longer hospital stays are more likely to be associated with readmission risk.


