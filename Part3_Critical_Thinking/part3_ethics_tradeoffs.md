# Part 3: Critical Thinking (20 points)

---

## 1️⃣ Ethics & Bias (10 points)

### How might biased training data affect patient outcomes in the case study?

Biased training data can:
- Lead to **inaccurate predictions** for underrepresented groups (e.g., minority populations).
- Cause **higher false positives or false negatives** in readmission risk, leading to unequal care.
- **Erode trust** between patients and healthcare providers if AI recommendations feel unfair.

**Example:** If most training data is from urban patients, rural patient patterns may be misclassified.

---

### Strategy to mitigate bias:

✅ **Use diverse, representative datasets** during training.  
✅ **Monitor model performance across demographic subgroups.**  
✅ Apply **re-weighting or re-sampling techniques** to balance the dataset during training.

---

## 2️⃣ Trade-offs (10 points)

### Discuss the trade-off between model interpretability and accuracy in healthcare.

✅ **Interpretability:**
- Easier to explain to clinicians and patients.
- Helps in understanding why predictions are made.
- Essential for high-stakes decisions in healthcare.

✅ **Accuracy:**
- High predictive performance may use complex models (e.g., deep learning).
- Such models may act as black boxes, reducing interpretability.

**Trade-off:**  
A highly accurate model with low interpretability may be less usable in healthcare settings where **explainability is legally and ethically important**.

**Balanced Approach:**  
Using interpretable models (like Decision Trees, SHAP with XGBoost) while maintaining acceptable accuracy is often preferred.

---

### If the hospital has limited computational resources, how might this impact model choice?

- Complex models (deep learning) may require **GPUs and high RAM** to train/infer, which may be infeasible.
- Simpler models like **Logistic Regression, Random Forests, or XGBoost with limited depth** can be used for efficiency.
- Cloud deployment with scalable compute can be considered, but if on-premise is required, **efficient models should be prioritized**.

---

