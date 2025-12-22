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
- Hierarchical clustering (CAH)  
- k-means clustering  

## Tools
- R  
- RStudio  
- R Markdown  
- FactoMineR  
- factoextra  

## Expected Outcomes
This analysis aims to highlight distinct patient profiles and explore their relationship with hospital readmission patterns, providing insights that could support data-driven decision-making in healthcare contexts.

## PCA Results

Principal Component Analysis (PCA) was applied to the numeric variables of the dataset after data cleaning and preprocessing.

Two standard criteria were used to determine the number of components to retain:

- **Kaiser criterion** (eigenvalues > 1), which suggests retaining **5 principal components**.
- **Cumulative explained variance criterion**, according to which approximately **9 components** are required to explain around **80% of the total variance**.

In line with standard academic practice and interpretability considerations, **5 principal components were retained**.

**Interpretation of the first components**
- **First Principal Component** captures the intensity and severity of hospital care, with high contributions from variables such as the number of medications, laboratory procedures, diagnoses, and length of hospital stay. This dimension reflects overall medical complexity and treatment burden.
- **Second Principal Component** represents differences in healthcare utilization patterns, distinguishing patients with frequent emergency or inpatient visits from those with more outpatient-based care.

