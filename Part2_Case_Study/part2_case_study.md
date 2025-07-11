# Part 2: Case Study Application (40 points)

---

## 1️⃣ Problem Scope (5 points)

### Problem:
Predict whether a patient will be **readmitted within 30 days** after discharge.

### 3 Objectives:
1. Accurately predict patient readmission risk to enable proactive interventions.
2. Identify key risk factors contributing to readmissions.
3. Reduce hospital costs and improve patient outcomes.

### 2 Stakeholders:
- **Hospital Administration:** Optimize resources and reduce penalties.
- **Clinicians:** Use predictions to monitor high-risk patients post-discharge.

---

## 2️⃣ Data Strategy (10 points)

### Proposed Data Sources:
1. **Electronic Health Records (EHRs):** Diagnoses, procedures, medications, vitals.
2. **Patient Demographics:** Age, gender, address (distance from hospital).

---

### 2 Ethical Concerns:
1. **Patient Privacy:** Protect sensitive medical data (HIPAA compliance).
2. **Bias:** Certain demographics may face biased predictions, impacting care quality.

---

### Preprocessing Pipeline:

1. **Data Cleaning:** Remove duplicates, handle missing vitals (impute using median).
2. **Feature Engineering:**
   - Create features like `number_of_prior_admissions`, `average_blood_pressure`.
   - Generate binary features (e.g., `has_chronic_condition`).
3. **Normalization & Encoding:**
   - Normalize numeric features using MinMaxScaler.
   - One-Hot Encode categorical features like discharge type or insurance provider.

---

## 3️⃣ Model Development (10 points)

### Model Chosen:
**Gradient Boosting Classifier (e.g., XGBoost)**

### Why?
✅ Performs well with tabular healthcare data.  
✅ Handles class imbalance effectively.  
✅ Provides feature importance for clinician interpretability.

---

### Hypothetical Confusion Matrix:

|                   | Predicted Readmit | Predicted No Readmit |
|-------------------|-------------------|-----------------------|
| **Actual Readmit**    | 50                | 10                   |
| **Actual No Readmit** | 20                | 120                  |

- **Precision:** 50 / (50 + 20) = 0.714
- **Recall:** 50 / (50 + 10) = 0.833

---

## 4️⃣ Deployment (10 points)

### Integration Steps:
1. **Wrap model in an API (FastAPI/Flask).**
2. **Integrate with the hospital’s EHR system** for automated prediction post-discharge.
3. **Create dashboards** for clinicians to view high-risk patients.
4. **Setup alerts** for high-risk readmission flags.

---

### Compliance:
- Use encryption for data storage and transfer.
- Role-based access controls.
- Anonymize patient data where feasible to align with **HIPAA** guidelines.

---

## 5️⃣ Optimization (5 points)

### Method to Address Overfitting:
**Use Cross-Validation with Early Stopping during training.**

**Why?** It prevents the model from learning noise in the training data and ensures generalization to unseen patient data.

---

