# Mobile Money Fraud Detection



## 1. Project Description

Mobile money has transformed financial access across Africa. In Kenya alone, M-Pesa processes billions of shillings in transactions every day, giving millions of people access to financial services who would otherwise have none. But as mobile money has grown, so has financial fraud, fraudulent agents exploit the system by taking control of customer accounts and attempting to drain funds through transfers and cash-outs.
Detecting fraud in real time is a critical challenge. Transactions happen in seconds, the volume is enormous, and fraudulent transactions make up a tiny fraction of all activity, making them extremely difficult to spot without a data-driven approach.
This project uses the PaySim synthetic dataset, which simulates one month of mobile money transactions modelled on real transaction logs from a mobile financial service operating across 14 African countries. The goal is to build and compare machine learning classification models that can reliably identify fraudulent transactions, and determine which algorithm performs best under the extreme class imbalance that defines this problem.



## 2. Problem Statement

Fraud in mobile money systems causes direct financial harm to individuals and erodes trust in the platforms that millions of people depend on. The core challenge is that fraudulent transactions are rare, less than 0.2% of all transactions in this dataset are fraudulent. A model that simply predicts every transaction as legitimate would achieve over 99% accuracy while catching zero fraud cases. This is why standard accuracy is meaningless here, and why handling class imbalance is the central technical challenge.


## 3. Dataset
- Source: PaySim Synthetic Financial Dataset — Kaggle

- Size: ~6.3 million transactions, 11 columns (30-day simulation — 1 step = 1 hour)


Columns
 
 - step > Hour of the simulation (1–744, representing 30 days)

 - type > Transaction type — CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER

 - amount > Transaction amount in local currency

 - nameOrig > Sender account ID

 - oldbalanceOrg > Sender balance before the transaction

 - newbalanceOrig > Sender balance after the transaction

 - nameDest > Receiver account ID

 - oldbalanceDest > Receiver balance before the transaction

 - newbalanceDest > Receiver balance after the transaction

 - isFraud > Target — 1 = fraudulent, 0 = legitimate

 - isFlagged > FraudSystem flag for large illegal transfers, for reference only



## 4. ML WorkFow
i) Data Cleaning

ii) Exploratory Data Analysis

iii) Feature Engineering

iv) Encoding

v) Class Imbalance Treatment

vi) Train / Test Split

vii) Feature Scaling

viii) Model Training

ix) Model Evaluation

x) Model Comparison



## 5. Tools


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