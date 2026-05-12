# Predicting Earthquake Severity in Nepal



## 1. Project Description

The 2015 Nepal earthquake killed nearly 9,000 people and displaced over 3 million. The damage was not uniform, some villages were completely destroyed while others nearby survived relatively intact. Understanding what combination of factors; hazard intensity, housing quality, poverty levels, exposure, and vulnerability, drives that difference is critical for disaster preparedness and resource allocation. This project uses the Nepal Earthquake Severity Index dataset, which covers 3,985 Village Development Committees (VDCs) across Nepal's five regions. The goal is to build and compare machine learning classification models that can predict the severity category of a location based on its risk profile and identify which factors matter most.



## 2. Problem Statement

When a disaster strikes, emergency responders and aid organisations must make rapid decisions about where to send resources first. These decisions are often made with incomplete information and under extreme time pressure. A data-driven model that can classify the severity of impact for a given location based on measurable risk factors captured before or during a disaster would significantly improve the speed and accuracy of these decisions. This project asks: can we use the combination of hazard intensity, population exposure, housing fragility, poverty, and vulnerability to reliably predict how severely a community will be affected? If yes, which factors are the strongest predictors, and do they differ across Nepal's regions?



## 3. Research Questions

1. Which risk factors — hazard intensity, exposure, housing, poverty, or vulnerability — are the strongest predictors of earthquake severity?
3. Which classification algorithm performs best on this data — Logistic Regression, KNN, or SVM?
4. Are certain regions of Nepal disproportionately represented in the highest severity categories?
5. What does the distribution of severity categories tell us about inequality in disaster risk across Nepal?



## 4. Tools and Concepts

### Python (pandas, numpy, matplotlib, seaborn)
- Data loading, exploration and cleaning
- Handling missing values and outliers
- Exploratory Data Analysis — distributions, correlations, class imbalance
- Visualisations

### Scikit-learn — Machine Learning
- **Data Preprocessing** — feature scaling using StandardScaler to prepare data for KNN and SVM
- **Train/Test Split** — splitting data to evaluate real-world model performance
- **Classification Models:**
  - *Logistic Regression* — linear baseline model using `class_weight='balanced'`
  - *K-Nearest Neighbors (KNN)* — distance-based model with the Elbow Method to find the optimal k
  - *Support Vector Machine (SVM)* — RBF kernel to handle non-linear boundaries between severity classes
- **Class Imbalance Handling** — SMOTE (Synthetic Minority Oversampling Technique) to address the unequal distribution across severity categories
- **Model Evaluation** — Accuracy, Precision, Recall, F1 Score, ROC-AUC, Confusion Matrix, Classification Report



## 5. Dataset

**Source:** Nepal Earthquake Severity Index (NSET / Humanitarian Data Exchange)

**Size:** 3,985 records, 12 columns

**Coverage:** Village Development Committees (VDCs) across Nepal's 5 regions — Central, Eastern, Western, Mid-Western and Far-Western




## 6. Expected Insights

1. Which combination of risk factors is most predictive of high earthquake severity?
2. How well can a machine learning model classify severity categories on unseen VDCs?
3. Which model generalises best — and is any model overfitting?
4. Are the highest-severity locations concentrated in particular regions or districts?
5. What does the severity distribution reveal about where Nepal is most vulnerable to future earthquakes?