# Part 1: Short Answer Questions (30 points)

---

## 1️⃣ Problem Definition (6 points)

### Hypothetical AI Problem:
**Predicting Student Dropout Rates in Kenyan Universities using AI.**

### 3 Objectives:
1. Predict the likelihood of a student dropping out before graduation.
2. Identify key risk factors contributing to dropout rates.
3. Enable proactive interventions by universities to reduce dropout rates.

### 2 Stakeholders:
- **University Administration:** For designing student support programs.
- **Ministry of Education:** For national education policy planning.

### 1 KPI:
**Model ROC-AUC Score on Validation Data** to measure how well the model distinguishes between likely dropouts and continuing students.

---

## 2️⃣ Data Collection & Preprocessing (8 points)

### 2 Data Sources:
1. Student Academic Records (grades, attendance, progression).
2. Socioeconomic Data (household income, funding, parental education).

### 1 Potential Bias:
**Socioeconomic bias**: Students from low-income backgrounds may be overrepresented in dropout predictions, leading to unfair interventions.

### 3 Preprocessing Steps:
1. **Handle Missing Data:** Impute missing values using mean or domain-informed imputation.
2. **Normalization:** Scale numeric features (grades, income) using MinMaxScaler.
3. **Encoding Categorical Variables:** Apply One-Hot Encoding to categorical features (e.g., funding source).

---

## 3️⃣ Model Development (8 points)

### Model:
**Random Forest Classifier**

**Why?**  
- Handles mixed data types.
- Robust to outliers and missing data.
- Provides feature importance, aiding interpretability.

### Data Split:
- 70% Training
- 15% Validation
- 15% Test

### 2 Hyperparameters to Tune:
1. **n_estimators:** Number of trees (impacts accuracy and compute cost).
2. **max_depth:** Controls tree depth to prevent overfitting.

---

## 4️⃣ Evaluation & Deployment (8 points)

### 2 Evaluation Metrics:
1. **Accuracy:** Overall correct predictions.
2. **ROC-AUC Score:** Measures ability to distinguish between dropout vs. continue, especially useful with imbalanced data.

### What is Concept Drift?
When the statistical properties of input data change over time, reducing model accuracy post-deployment (e.g., new policies or economic shifts affecting dropout drivers).

**Monitoring Concept Drift:**
- Monitor prediction vs. actual dropout quarterly.
- Use tools like MLFlow or EvidentlyAI.
- Retrain the model periodically with fresh data.

### 1 Technical Deployment Challenge:
**Scalability:** Handling high-volume prediction requests during peak university enrollment and evaluation periods.

---

