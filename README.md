# 🏥 Diabetic Patient Hospital Readmission Prediction

## 📌 Overview
Diabetes is one of the most prevalent chronic medical conditions worldwide, caused by insufficient insulin production (Type-1) or defective insulin response (Type-2). Hospital readmission for diabetic patients is a major concern in the United States — over $250 million was spent on treating readmitted diabetic inpatients in 2011 alone.

This project leverages Machine Learning to identify key factors influencing patient readmission and predict the probability of readmission within 30 days of discharge.

---

## 🎯 Objective
- Identify key factors that influence hospital readmission for diabetic patients  
- Predict the probability of patient readmission using classification models  
- Help hospitals reduce readmission rates and improve quality of care  

Hospital readmission rates are now considered an indicator of hospital quality. Hospitals face financial penalties if their readmission rate exceeds expected thresholds.

---

## 📊 Dataset
- **Source:** UCI Machine Learning Repository  
- **Coverage:** 10 years of clinical care across 130 US hospitals  
- **Records:** ~101,766 patient encounters  
- **Features:** 50 features including patient demographics, diagnoses, medications, and lab results  

---

## 🔧 Tech Stack

| Category              | Tools/Technologies                          |
|----------------------|--------------------------------------------|
| Language             | Python 3.6+                                |
| Data Manipulation    | Pandas, NumPy                              |
| Visualization        | Matplotlib, Seaborn                        |
| Machine Learning     | Scikit-learn                               |
| Models               | Logistic Regression, Random Forest, AdaBoost, Decision Tree |

---

## 🗂️ Project Structure
```
Diabetic-Patient-Readmission/
│
├── Practicum2.ipynb          # Main Jupyter Notebook
├── IDs_mapping.csv           # Mapping file for categorical IDs
├── README.md                 # Project documentation
└── dataset_diabetes/
    └── diabetic_data.csv     # Raw dataset
```

---

## 📋 Workflow

### 1. 📥 Data Loading & Exploration
- Loaded dataset with 101,766 records and 50 features  
- Explored data types, missing values, and statistical summaries  

### 2. 🧹 Data Wrangling & Preprocessing
- Removed dead patients (discharge disposition IDs: 11, 13, 14, 19, 20, 21)  
- Dropped high-missing columns: `weight`, `payer_code`, `medical_specialty`  
- Encoded target variable: Readmission within 30 days → Binary (0/1)  
- Mapped ICD diagnosis codes to disease categories  
- Filled missing values with appropriate defaults  
- Normalized numerical features using `StandardScaler`  
- One-hot encoded categorical variables  

### 3. 📈 Exploratory Data Analysis (EDA)
- Distribution analysis of readmission rates by gender and age  
- Scatter matrix for detecting multicollinearity  
- Medication count vs. age visualization  
- Histogram distributions of numerical features  
- Correlation analysis between variables  

### 4. 🤖 Model Building

| Model                | Accuracy |
|---------------------|----------|
| Logistic Regression | 88.12%   |
| Decision Tree       | 87.85%   |
| AdaBoost Classifier | 88.46%   |
| Random Forest       | 89.32%   |
| AdaBoost (Tuned)    | 89.87%   |

---

### 5. 🔍 Hyperparameter Tuning
- Applied `GridSearchCV` on AdaBoost with cross-validation  
- Tuned `n_estimators` and `learning_rate`  
- Achieved best accuracy close to **90%**  

---

## 📉 Model Evaluation

### Metrics Used
- Accuracy Score  
- Confusion Matrix  
- Classification Report (Precision, Recall, F1-Score)  
- ROC Curve & AUC  

### ROC Curve Comparison
All models were compared using ROC curves. The Random Forest and Tuned AdaBoost models demonstrated the best overall performance.

### Feature Importance (Random Forest)
Top features influencing readmission:
- `number_inpatient`  
- `number_diagnoses`  
- `number_emergency`  
- `time_in_hospital`  
- `num_medications`  

---

## 📊 Key Findings
- All models achieved strong performance (~88–90%), indicating effective feature engineering and preprocessing  
- Random Forest and Tuned AdaBoost performed best across all evaluation metrics  
- Number of inpatient visits is the strongest predictor of readmission  
- Age group `[70-80)` showed the highest readmission count  
- Proper preprocessing and feature selection significantly improved model performance  

---

## 🙏 Acknowledgements
- Dataset from the UCI Machine Learning Repository  
- Research inspired by the need to reduce healthcare costs and improve patient outcomes  

---

## 👤 Author
**Manchikanti Rajasri**

---

> "Reducing hospital readmissions not only saves costs but saves lives."
