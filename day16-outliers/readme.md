## 🚩 Outliers in Data

**Outliers** are unusual data points that differ significantly from the majority.  
They aren't always "bad," but handling them can be tricky.



### 🤔 What To Do With Outliers

- Decide whether to **keep** or **remove** them.
- Sometimes, adding an extra feature (e.g., `IQ` for students who score high with little study) can **justify or explain** outliers, turning them into valuable insights.



### ⚠️ Bad Effects of Outliers on ML Models

| Model Type             | Effect of Outliers                  |
|------------------------|-------------------------------------|
| Linear Regression      | High sensitivity (can skew results) |
| Logistic Regression    | High sensitivity                    |
| AdaBoost               | High sensitivity                    |
| Deep Learning (NN)     | Can have negative effects           |
| Decision Trees         | No/little effect                    |



### 🕵️ Detecting Outliers

- **Normal Data:**  
  - Points > μ + 3σ (mean + 3 standard deviations) are considered outliers.

- **Boxplot:**  
  - Outliers if < Q1 - 1.5 × IQR or > Q3 + 1.5 × IQR.



### 🧰 Techniques to Treat Outliers

- **Trimming:** Remove outlier rows.
- **Capping (Winsorization):** Cap extreme values at a certain percentile.
- **Z-score Treatment:** Remove rows with |z-score| > threshold.
- **IQR-Based Filtering:** Remove rows outside allowed range.
- **Percentile Cuts:** Exclude top and bottom percentiles.

