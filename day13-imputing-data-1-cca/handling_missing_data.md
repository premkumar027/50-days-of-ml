# 🧩 Handling Missing Data

In machine learning, dealing with missing data is a crucial step during preprocessing. There are two main approaches:

---

## 🔸 1. Remove Entire Row (Not Preferred)

Also known as **Complete Case Analysis (CCA)** or **List-wise Deletion**.

### 🔹 What is CCA?

Complete-case analysis (CCA) means analyzing **only those rows** where **all variables are present**. Any row with missing data in **any column** is excluded from analysis.

### 🧠 Assumptions for Using CCA:
- Use **only if data is MCAR** (Missing Completely At Random)
- Not suitable if missing data is concentrated (e.g., first 50 rows)

### ✅ Advantages:
1. Simple and easy to implement
2. Preserves variable distribution (if MCAR)

### ❌ Disadvantages:
1. May exclude a large portion of data
2. Could remove informative observations
3. Model will not learn how to handle missing values during deployment

### 🕒 When to Use:
- Data is **MCAR**
- Missing data is **≤ 5%**

---

## 🔸 2. Imputation (Filling Missing Values)

Replacing missing data with estimated or derived values.

---

### 🔹 2.1. Univariate Imputation (Single Variable)

#### 📈 Numerical Features:
| Method             | Description                              |
|--------------------|------------------------------------------|
| Mean/Median        | Fill missing value with central tendency |
| Random Value       | Fill with a random number from feature's distribution |
| End of Distribution| Fill with an extreme value to flag it as outlier |

#### 🧾 Categorical Features:
| Method   | Description                         |
|----------|-------------------------------------|
| Mode     | Most frequent value                 |
| "Missing"| A new category to indicate missing  |

---

### 🔹 2.2. Multivariate Imputation (Multiple Variables)

Uses other features to predict missing values.

| Method            | Description                                          |
|-------------------|------------------------------------------------------|
| KNN Imputer       | Uses nearest neighbors' values to impute             |
| Iterative Imputer | Uses regression models (MICE - Multiple Imputation by Chained Equations) |

---

## 📝 Summary

| Method       | When to Use                              |
|--------------|-------------------------------------------|
| CCA          | If data is MCAR and ≤ 5% missing         |
| Mean/Median  | For numerical columns with light missing |
| Mode/"Missing"| For categorical columns                 |
| KNN/MICE     | For multivariate relationships and better accuracy |
