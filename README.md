# SOC Incident Classification with LightGBM

## 📑 Project Documentation & Reporting  

### 1. Project Overview
The objective of this project was to build a machine learning model to classify cybersecurity incidents into categories (**BenignPositive, FalsePositive, TruePositive**) based on alert and log data.  
This supports SOC teams in filtering noise, prioritizing alerts, and improving incident response efficiency.  

---

### 2. Methodology

#### a. Data Preprocessing
- **Handling Missing Values**: Dropped rows with missing target labels (`IncidentGrade`), imputed remaining missing features with `-1`.  
- **Encoding**: Object-type features encoded into categorical numeric codes.  
- **Sampling**: Due to dataset size, sampled **5%** of training data for tuning to save memory while preserving class distribution.  

#### b. Baseline Models
- Logistic Regression, Decision Tree, Random Forest were trained first.  
- Random Forest initially struggled (imbalanced dataset).  
- Decision Tree reached **~0.77 F1 (weighted)**.  
- Logistic Regression underperformed (~0.45 F1).  

#### c. Advanced Model (LightGBM)
- Chosen for its scalability and strong performance on tabular data.  
- Hyperparameter tuning with **RandomizedSearchCV** (search over `num_leaves`, `learning_rate`, `max_depth`, `n_estimators`).  
- Best parameters achieved:  
  ```
  num_leaves = 64
  n_estimators = 500
  max_depth = 15
  learning_rate = 0.05
  ```  
- Cross-validation macro-F1 ≈ **0.93**.  

---

### 3. Model Interpretation

#### a. Feature Importance
- Top contributing features identified using LightGBM importance and SHAP values.  
- Example: Network traffic metrics, alert source, severity levels were among the most important predictors.  

#### b. Error Analysis
- Confusion matrix revealed most misclassifications occur between **FalsePositive** and **TruePositive**.  
- Suggests additional feature engineering (e.g., contextual threat intel, temporal features) may improve separation.  

---

### 4. Final Evaluation

- On validation set: **Macro-F1 = 0.94**, **Accuracy = 0.94**.  
- On test set: Similar performance, confirming strong generalization.  
- Outperformed all baseline models significantly.  

---

### 5. Key Findings
- LightGBM is well-suited for this SOC incident grading problem.  
- Model handles imbalance via class weights effectively.  
- Precision and recall balanced across all three classes.  
- Majority of remaining errors linked to borderline FalsePositive/TruePositive cases.  

---

### 6. Recommendations

#### a. SOC Workflow Integration
- Integrate model outputs into SIEM/SOC dashboards.  
- Use predictions to **prioritize alerts**:  
  - **TruePositive → escalate immediately**  
  - **FalsePositive → de-prioritize / auto-close**  
  - **BenignPositive → monitor but no action needed**  
- Automate feedback loop: analysts can confirm/correct labels, feeding back into retraining pipeline.  

#### b. Future Improvements
- Explore **deep learning models** or **ensemble approaches** for even higher accuracy.  
- Add **temporal features** (e.g., frequency of alerts over time).  
- Incorporate **external threat intelligence feeds** to enrich features.  
- Active learning: periodically retrain with **new SOC data** to adapt to evolving threats.  

#### c. Deployment Considerations
- Ensure explainability (via SHAP plots) for analyst trust.  
- Monitor drift (data distribution changes over time).  
- Implement **real-time inference pipeline** (e.g., using FastAPI + model serving).  
- Set up **alert thresholds** to minimize false negatives (missed attacks).  

---

### 7. Conclusion
This project successfully demonstrated that a **LightGBM-based SOC incident classifier** can achieve high accuracy and robustness in identifying cyber alerts.  
The model not only reduces SOC analyst workload but also improves incident response by prioritizing genuine threats.  
