# Predicting Earthquake Severity in Nepal



## 1. Project Description

The 2015 Nepal earthquake killed nearly 9,000 people and displaced over 3 million. The damage was not uniform, some villages were completely destroyed while others nearby survived relatively intact. Understanding what combination of factors; hazard intensity, housing quality, poverty levels, exposure, and vulnerability, drives that difference is critical for disaster preparedness and resource allocation. This project uses the Nepal Earthquake Severity Index dataset, which covers 3,985 Village Development Committees (VDCs) across Nepal's five regions. The goal is to build and compare machine learning classification models that can predict the severity category of a location based on its risk profile and identify which factors matter most.



## 2. Problem Statement

When a disaster strikes, emergency responders and aid organisations must make rapid decisions about where to send resources first. These decisions are often made with incomplete information and under extreme time pressure. A data-driven model that can classify the severity of impact for a given location based on measurable risk factors captured before or during a disaster would significantly improve the speed and accuracy of these decisions. This project asks: can we use the combination of hazard intensity, population exposure, housing fragility, poverty, and vulnerability to reliably predict how severely a community will be affected? If yes, which factors are the strongest predictors, and do they differ across Nepal's regions?



## 3. Research Questions

3. ML Workflow

i) Data Cleaning — Handle the single missing row, check for outliers in the scoring columns, and standardise column names for easier use throughout the project.
ii) Exploratory Data Analysis — Understand the distribution of each feature, identify class imbalance across severity categories, and explore regional patterns using visualisations such as histograms, box plots, count plots and a correlation heatmap.
iii) Class Imbalance Treatment — Apply SMOTE (Synthetic Minority Oversampling Technique) to balance the severity categories before training. The dataset is heavily skewed — Highest severity locations make up less than 0.5% of all records — so without this step the model would simply predict the majority class every time.
iv) Train / Test Split — Split the balanced data into 80% for training and 20% for testing, using stratification to ensure all severity classes appear proportionally in both sets.
v) Feature Scaling — Apply StandardScaler to bring all features onto the same scale, which is required for KNN and SVM since both rely on distance calculations.
vi) Model Training — Train three classification models on the balanced, scaled data:

- Logistic Regression — linear baseline model
- K-Nearest Neighbors (KNN) — distance-based model with the Elbow Method used to find the optimal k
- Support Vector Machine (SVM) — RBF kernel to handle non-linear boundaries between severity classes


vii) Model Evaluation — Evaluate each model using Accuracy, Precision, Recall, F1 Score, ROC-AUC, Confusion Matrix and Classification Report. Recall is the priority metric — misclassifying a high-severity location as low-risk means aid may never reach it.
viii) Model Comparison — Compare all three models side by side in a summary table and ROC curve plot to identify the best performing model.



## 4. Tools


### Python
- pandas — data loading, cleaning and manipulation
- numpy — numerical operations
- matplotlib & seaborn — visualisations including heatmaps, histograms, box plots and ROC curves

### Scikit-learn
- train_test_split — splitting data into training and testing sets
- StandardScaler — feature scaling
- LogisticRegression — baseline classification model
- KNeighborsClassifier — distance-based classification
- SVC — Support Vector Machine classifier
- classification_report, confusion_matrix, roc_auc_score, roc_curve — model evaluation

### Imbalanced-learn
- SMOTE — oversampling minority severity classes to address class imbalance



## 5. Dataset

**Source:** Nepal Earthquake Severity Index (NSET / Humanitarian Data Exchange)

**Size:** 3,985 records, 12 columns

**Coverage:** Village Development Committees (VDCs) across Nepal's 5 regions — Central, Eastern, Western, Mid-Western and Far-Western




## 6. Columns
i) P_CODE - Unique location identifier

ii) VDC_NAME - Village Development Committee name

iii) DISTRICT - District the VDC belongs to

iv) REGION - One of Nepal's five geographic regions

v) Hazard (Intensity) - Earthquake ground shaking intensity score

vi) Exposure - Population and asset exposure score

vii) Housing - Housing fragility score

viii) Poverty - Poverty index score

ix) Vulnerability - Combined vulnerability score

x) Severity - Raw composite severity score

xi) Severity Normalized - Severity scaled to 0–10

xii) Severity category - Target variable > Lowest, Low, Medium-Low, Medium-High, High, Highest