

Project By: Amantle Michelle Makati

Date Completed: 14 March 2026

This Dataset was from Kaggle the link is below:
https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data

---

# Heart Disease Diagnostic Analysis and Prediction

### **Predictive Modeling for Early Cardiovascular Risk Detection**

## 📌 Project Overview

Cardiovascular diseases (CVDs) remain the leading cause of global mortality, claiming an estimated **17.9 million lives annually**. Heart failure represents a critical clinical milestone—a chronic condition where the heart's pumping capacity can no longer meet systemic demands.

This project utilizes a clinical dataset of **918 observations** to model the relationship between patient demographics and physiological health. The primary objective is to enable early detection of heart disease, acting as a predictive screen to allow healthcare providers to prioritize patients and initiate preventative care protocols.

---

## 📊 Dataset Features

The analysis evaluates 11 key clinical features to classify patients as **Normal (0)** or **Heart Disease (1)**:

| Feature | Meaning |
| --- | --- |
| **Age** | Age of the patient [years] |
| **Sex** | Gender [M: Male, F: Female] |
| **Chest Pain Type** | [TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal, ASY: Asymptomatic] |
| **Resting BP** | Resting blood pressure [mm Hg] |
| **Cholesterol** | Serum cholesterol [mm/dl] |
| **Fasting BS** | Fasting blood sugar [1: > 120 mg/dl, 0: otherwise] |
| **Resting ECG** | [Normal, ST: Wave Abnormality, LVH: Left Ventricular Hypertrophy] |
| **Max HR** | Maximum heart rate achieved [60 - 202] |
| **Exercise Angina** | Exercise-induced angina [Y: Yes, N: No] |
| **Oldpeak** | ST depression measured in depression |
| **ST_Slope** | Slope of peak exercise ST segment [Up, Flat, Down] |

---

## ⚙️ Machine Learning Pipeline

### **Phase 1: Data Acquisition & Cleaning**

* **Auditing:** Identified "Zero" values in `Cholesterol` and `RestingBP` (medically impossible).
* **Imputation:** Applied **Median Imputation** to handle missing/zero values, ensuring robustness against outliers.

### **Phase 2: Preparation & Encoding**

* **Train-Test Split:** Data was split into **Training (80% / 734 rows)** and **Testing (20% / 184 rows)** sets to avoid data leakage.
* **Feature Encoding:** * **Binary Mapping:** Converted simple categories to 1s and 0s.
* **One-Hot Encoding:** Expanded complex categories (e.g., `Chest Pain Type`) into multiple binary columns.
* **Binned Age:** Segmented age into Young, Middle, Senior, and Elderly brackets.


* **Feature Scaling:** Standardized numerical values (Mean=0, Std=1) to ensure variables with large ranges (like Cholesterol) do not overpower smaller ranges.

### **Phase 3: Model Development & Evaluation**

* **Algorithm:** Logistic Regression was selected for its effectiveness in binary classification.
* **Stability:** The model achieved a remarkably low **1.19% performance gap** between training and test sets, indicating high generalization.

---

## 📈 Performance Metrics

The final evaluation on unseen test data yielded the following results:

* **Overall Accuracy:** 86%
* **Heart Disease (Class 1):**
* **Precision:** 90% (Low False Positives)
* **Recall:** 85% (High Sensitivity)
* **F1-Score:** 88%


* **Normal (Class 0):**
* **F1-Score:** 84%



**Interpretation:** The model is highly precise (90%) when identifying heart disease, making it a reliable diagnostic aid. The high macro and weighted averages (86%) confirm consistent performance across all patient groups.

---

## 🛠️ Technical Stack

* **Language:** Python
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** `Pandas`, `NumPy`, `Matplotlib`, `Seaborn`, `Scikit-Learn`

---

## 🚀 How to Run

1. **Clone/Download** the repository and ensure the dataset (`heart.csv`) is in the same folder.
2. **Install Dependencies:**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn

```


3. **Run the Notebook:** Execute the cells in sequence. Ensure the **Train-Test Split** is performed before **Feature Scaling** to maintain a valid medical evaluation.
