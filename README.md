# 🩺 Deliverable 1 – Data Collection, Cleaning & Exploration

## 📘 Purpose
This lab focuses on preparing a healthcare dataset for data mining and predictive analytics.  
The main objectives were to:
- Select and describe a suitable dataset.
- Load, inspect, and understand its structure using Pandas.
- Clean the data by handling duplicates, inconsistencies, and noisy values.
- Perform exploratory data analysis (EDA) to uncover trends, patterns, and relationships that will guide later modeling.

The dataset (`healthcare_dataset.csv`) contains **55,500 patient admission records** and **15 attributes**, including demographic, medical, and financial information.

---

## 🔍 Key Insights from EDA & Statistical Analysis

### 📊 Summary Findings
- **Age Distribution:** Most patients are between 25 and 65 years old — a primarily adult population.  
- **Billing Amounts:** Emergency admissions show higher average billing compared to elective or urgent cases.  
- **Gender Ratio:** Nearly balanced male–female distribution allows unbiased demographic analysis.  
- **Outliers:** A few high-billing outliers were detected, possibly representing severe or long-term treatments.  
- **Correlations:** Numeric features such as `Billing Amount`, `Room Number`, and `Age` show mild positive correlation, suggesting potential feature interactions for predictive modeling.

### 🧮 Statistical Measures
- Central tendency metrics (mean, median, mode) confirmed normal data distribution for most attributes.  
- Dispersion measures (range, IQR, standard deviation) identified attributes with high variance, guiding normalization and scaling strategies.  
- Outlier detection using IQR revealed 1–2% of records requiring special handling before modeling.

---

## ⚙️ Data Cleaning Highlights
- **Removed 534 duplicates** to eliminate redundancy.  
- **Standardized text fields** (names, hospitals, conditions) using title-case normalization.  
- **Parsed date columns** (`Date of Admission`, `Discharge Date`) into datetime objects.  
- **Validated numerical ranges** — ages > 120 or < 0 were removed; negative billings set to zero.  
- **Saved a cleaned dataset** (`healthcare_dataset_cleaned.csv`) ready for feature engineering and modeling.

---

## 💡 Challenges and Decisions
- **Text inconsistency:** Patient and doctor names contained mixed-case and trailing spaces — resolved with string normalization.  
- **Duplicate records:** Discovered and removed using Pandas `.drop_duplicates()`.  
- **Outlier billing values:** Chose to keep mild outliers for realism but will apply robust scaling in modeling.  
- **Date formatting:** Some date strings were irregular; applied `pd.to_datetime(errors='coerce')` for uniformity.

---

## 🚀 Next Steps
- Apply feature scaling (e.g., StandardScaler or MinMaxScaler).  
- Encode categorical variables with one-hot or target encoding.  
- Split into training/testing sets for predictive models.  
- Explore regression or classification models to predict billing amounts or admission types.

---

**Author:** Sudhanshu Sekhar Dash  
**Course:** MSCS 634 – Advanced Big Data and Data Mining  
**Institution:** University of the Cumberlands
