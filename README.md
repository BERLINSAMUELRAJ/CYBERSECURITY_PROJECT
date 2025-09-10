# Microsoft: Classifying Cybersecurity Incidents with Machine Learning 

![](https://github.com/BERLINSAMUELRAJ/CYBERSECURITY_PROJECT/blob/main/Top-5-Applications-of-Machine-Learning-in-Cyber-Security1.jpg)

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

![](https://github.com/BERLINSAMUELRAJ/CYBERSECURITY_PROJECT/blob/main/175948891_m_normal_none%20(1).jpg)
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

---

## 📊 Results & Model Analysis

### 1️⃣ Overall Performance
- **Accuracy:** 94% → 94% of all predictions were correct.  
- **Macro-F1 Score:** 0.933 → Balanced performance across all classes.  
- **Weighted Metrics:** Also 94%, which aligns with overall accuracy.  

✅ This is very strong performance for a **3-class classification problem**.

---

### 2️⃣ Per-Class Analysis

| Class          | Precision | Recall | F1-score | Support  | Interpretation                                                                         |
| -------------- | --------- | ------ | -------- | -------- | -------------------------------------------------------------------------------------- |
| BenignPositive | 0.93      | 0.96   | 0.94     | 832,432  | Model predicts this class very reliably, slightly under-predicting others.             |
| FalsePositive  | 0.94      | 0.89   | 0.91     | 406,393  | Slightly lower recall → some FalsePositive instances are missed. Could tune threshold. |
| TruePositive   | 0.95      | 0.94   | 0.94     | 664,543  | Very balanced precision and recall → excellent.                                        |

**Observations:**
- Model performs slightly worse in **recall for FalsePositive**.  
- This is common in imbalanced scenarios where **FalsePositive is less represented** than TruePositive or BenignPositive.  
- Otherwise, all classes have **high precision and recall**.

---

### 🔍 Insights
- **LightGBM** is the **top choice** for both accuracy and stability.  
- **Random Forest** is a solid alternative if you prefer a simpler model with less tuning.  
- **Logistic Regression** is **not suitable** for this dataset without heavy feature engineering or balancing.  
- **XGBoost** is competitive, but in the current setup, **LightGBM slightly outperforms it**.

---

### 📈 Model Comparison
- **Logistic Regression (0.45 F1):** Very low. Likely due to high non-linearity and/or imbalance.  
- **Decision Tree (0.78 F1):** Much better, but risk of overfitting remains.  
- **Random Forest (0.93 F1):** Solid performance; ensemble reduces overfitting.  
- **LightGBM (0.95 F1):** Best performer. Gradient boosting handles class imbalance and complex interactions well.  
- **XGBoost (0.93 F1):** Slightly worse than LightGBM, but still very strong.  

---

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

