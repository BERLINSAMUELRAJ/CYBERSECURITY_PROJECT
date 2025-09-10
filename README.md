# Microsoft: Classifying Cybersecurity Incidents with Machine Learning  

## 📌 Project Overview  
This project focuses on building a machine learning model to **predict the triage grade of cybersecurity incidents** using Microsoft’s GUIDE dataset. The triage grades include:  
- **True Positive (TP)**  
- **Benign Positive (BP)**  
- **False Positive (FP)**  

The goal is to enhance the efficiency of **Security Operation Centers (SOCs)** by automating incident classification and supporting guided response systems.  

---

## 🎯 Skills Takeaway  
- Data Preprocessing and Feature Engineering  
- Machine Learning Classification Techniques  
- Model Evaluation Metrics (Macro-F1 Score, Precision, Recall)  
- Cybersecurity Concepts and Frameworks (MITRE ATT&CK)  
- Handling Imbalanced Datasets  
- Model Benchmarking and Optimization  

---

## 🌐 Domain  
**Cybersecurity and Machine Learning**  

---

## 📝 Problem Statement  
You are working as a **Data Scientist at Microsoft**, tasked with building a model to predict the triage grade of incidents (TP, BP, FP) using the GUIDE dataset.  

The solution should:  
- Train the model on **train.csv**  
- Evaluate performance on **test.csv**  
- Report **Macro-F1, Precision, and Recall**  
- Ensure generalization for real-world SOC applications  

---

## 💼 Business Use Cases  
- **Security Operation Centers (SOCs):** Automate triage to prioritize real threats.  
- **Incident Response Automation:** Suggest guided responses to reduce resolution time.  
- **Threat Intelligence:** Improve detection by using historical data.  
- **Enterprise Security Management:** Reduce false positives and improve overall security posture.  

---

## 🔍 Approach  

### 1. Data Exploration & Understanding  
- Load dataset and inspect structure.  
- Perform **EDA (Exploratory Data Analysis)** with visualizations and correlations.  
- Identify **class imbalance** and potential anomalies.  

### 2. Data Preprocessing  
- Handle **missing values** (imputation/removal).  
- **Feature engineering** (derived fields like timestamp features, feature combinations).  
- Encode categorical features (One-hot, Label Encoding).  
- Normalize/scale numerical variables.  

### 3. Data Splitting  
- Split dataset into **train-validation** and test sets.  
- Apply **stratification** for imbalanced target distribution.  

### 4. Model Selection & Training  
- **Baseline Models:** Logistic Regression, Decision Tree.  
- **Advanced Models:** Random Forest, XGBoost, LightGBM, Neural Networks.  
- Apply **RandomizedSearchCV / GridSearchCV** for hyperparameter tuning.  
- Use **Cross-Validation (k-fold)** for robust evaluation.  

### 5. Model Evaluation & Tuning  
- Metrics: **Macro-F1, Precision, Recall**.  
- Tune hyperparameters (learning rate, tree depth, estimators).  
- Handle **class imbalance** (SMOTE, class weights, ensemble techniques).  

### 6. Model Interpretation  
- **Feature Importance:** SHAP values, Permutation importance, Model-specific importance.  
- **Error Analysis:** Identify common misclassifications → refine features or model complexity.  

### 7. Final Evaluation on Test Set  
- Evaluate on **test.csv**.  
- Report **Final Macro-F1, Precision, Recall**.  
- Compare results with baseline and validation performance.  

### 8. Documentation & Reporting  
- Document entire process (data prep → training → evaluation).  
- Summarize key findings and insights.  
- Provide deployment and SOC integration recommendations.  

---

## 📊 Results  
By project completion, the deliverables include:  
- A **robust ML model** capable of accurate triage prediction.  
- Insights into **feature importance** and error distribution.  
- A documented workflow covering preprocessing, training, tuning, and evaluation.  

---

## 📈 Evaluation Metrics  
The project will be assessed using:  
- **Macro-F1 Score** → balances all classes equally.  
- **Precision** → ensures minimal false positives.  
- **Recall** → ensures no critical threats are missed.  

---

## 📂 Dataset Overview  
The **GUIDE Dataset** has 3 hierarchies:  
1. **Evidence** → granular details (IP, email, user info).  
2. **Alert** → multiple evidences combined into a potential threat.  
3. **Incident** → multiple alerts forming a complete incident.  

- 1M triage-annotated incidents  
- 45 features + labels + unique identifiers  
- Stratified **70%-30% split (train/test)**  

---

## ⚙️ Dataset Preprocessing Highlights  
- Missing value handling  
- Feature engineering (derived fields, categorical encodings)  
- Normalization of numeric features  

---

## 📦 Project Deliverables  
- **Source Code** (with preprocessing → training → evaluation pipeline).  
- **Trained Model File** ready for deployment.  
- **Documentation** of methodology and insights.  
- **Presentation** summarizing outcomes and business impact.  

---

## 📌 Project Guidelines  
- Follow **PEP 8** standards.  
- Use **Git** for version control.  
- Modular, reusable, and well-commented code.  
- Document all assumptions and iterations.  

---

## 📚 References  
- [EDA Guide](#)  
- [Project Live Evaluation](#)  
- [Capstone Explanation Guideline](#)  
- [Orientation (Tamil)](#)  
- [Orientation (English)](#)  

---

## ⏳ Timeline  
**Duration:** 1 Week  

- **Project Doubt Clarification Session**  
  - Tue, Thu, Sat (5:00 PM – 7:00 PM)  
  - [Booking Link](https://forms.gle/XC553oSbMJ2Gcfug9)  

- **Live Evaluation Session**  
  - Mon–Sat (11:30 PM – 12:30 PM)  
  - [Booking Link](https://forms.gle/1m2Gsro41fLtZurRA)  
