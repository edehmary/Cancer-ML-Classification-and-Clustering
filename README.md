# Cancer-ML-PREDICTIVE MODELLING & CLUSTERING
## Introduction
This project applies machine learning techniques to classify and cluster cancer patient data from the UAE, with the goal of enhancing diagnostic support and uncovering key patterns in patient demographics, disease progression, and treatment outcomes.

## Cancer Patient Classification & Clustering - UAE Dataset

## Objective 
To analyze cancer patient data from the UAE using machine learning for two main purposes:

* **Classification:** Build predictive models to identify the cancer stage of patients based on available demographic and medical data.

* **Clustering:** Discover hidden patterns and patient subgroups using unsupervised learning to support personalized treatment strategies and healthcare insights

## Research Summary & Key Findings

## I. Exploratory Data Analysis (EDA)

Performed in-depth analysis to identify trends and patterns:

* **Recovery rate over years:**

  - Highest in **2020 (566), 2021 (561)**, and **2022 (559)**
  - Slight dip in **2023 (527)**, possibly due to incomplete records
    
* **Recovery rate by cancer type:**

  - Highest among Leukemia (660), Liver (630), and Breast (614) patients
    
* **Top 5 most common cancer types:**

  - **Leukemia (1314), Liver (1263), Ovarian (1259), Pancreatic (1243), Breast (1241)**

* **Recovery rate for top 5 cancer types:**

   - **Leukemia (660), Liver (630), Breast (614), Ovarian (601), Pancreatic (594)**

* **Feature Engineering:** Created **BMI** from Weight and Height

## II. Statistical Hypothesis Testing 
* Conducted **ANOVA test** on Height across Cancer Stages:

- **F-statistic = 1.8642**, **p-value = 0.1333** → No statistically significant relationship
  
- Similar insignificance observed for **BMI, Age, Weight**, and **Height**
  
## 🤖 Predictive Modeling 
Built models to predict **Cancer Stage (I–IV)** using:

### Features Used

* **Demographics:** Age, Gender, Nationality, Ethnicity
* **Lifestyle:** Smoking Status
* **Medical History:** Comorbidities, Cancer Type, Weight, Height
  
### Models Trained

* Random Forest Classifier
* Logistic Regression
* Support Vector Classifier (OneVsRest and OneVsOne)
* XGBoost Classifier
  
### Results

* **Random Forest (with SMOTE)**: Accuracy = **30%** (highest)
* After tuning: **29%**
  
### Top Features (Feature Importance)

1. Nationality: Expatriate
2. Outcome: Recovered
3. Comorbidities: Unknown
4. Emirate: Fujairah
5. Cancer Type: Ovarian

### Challenges 
* Low accuracy due to:

   - Missing biological features (e.g., tumor markers)
   - Weak correlation in numeric features
   - Sparse high-dimensional encoded features (3138 columns)
   - Possible label noise
     
### Recommendations

* Collect richer clinical/biological data
* Apply deeper dimensionality reduction or feature selection
* Explore non-tabular approaches
  
## Clustering Analysis

Unsupervised learning to uncover patient subgroups:

### Optimal Clusters 
* **Elbow Method** → Best at **k = 2**

### Evaluation Metrics

* **Silhouette Score:** 0.0934 (low cohesion)
* **Davies-Bouldin Index:** 2.8964 (high similarity)
* **Calinski-Harabasz Index:** 1171.59 (moderate dispersion)

### PCA Insights

* **PC1:** BMI (0.709), Weight (0.622), Height (0.331)
* **PC2:** Height (0.649), Weight (0.356)
Age had minimal impact

### Cluster Summary

| Cluster | Age   | BMI   | Weight | Height | Recovery Rate |
|---------|-------|-------|--------|--------|----------------|
| 0       | 53.99 | 29.67 | 80.85  | 1.65   | 50.3%          |
| 1       | 53.15 | 20.11 | 60.03  | 1.73   | 48.4%          |

**Cluster 0:** Higher BMI/weight, slightly better recovery 
**Cluster 1:** Leaner profile, slightly lower recovery

## Tools & Technologies Used

* Python: pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost, imbalanced-learn
* Jupyter Notebook
* SMOTE: Class balancing
* ANOVA: Statistical testing
* PCA: Dimensionality reduction
* KMeans: Clustering

## Dataset Description
1000 patient records with the following fields:

['Patient_ID', 'Age', 'Gender', 'Nationality', 'Emirate',
 'Diagnosis_Date', 'Cancer_Type', 'Cancer_Stage', 'Treatment_Type',
 'Treatment_Start_Date', 'Hospital', 'Primary_Physician', 'Outcome',
 'Death_Date', 'Cause_of_Death', 'Smoking_Status', 'Comorbidities',
 'Ethnicity', 'Weight', 'Height']
 
