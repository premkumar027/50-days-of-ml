# 📦 Binning and Binarization

We use **binning** and **binarization** to convert **numerical data into categorical data** to simplify models, handle outliers, and improve interpretability.



## 📊 From Numerical to Categorical

**Numerical:**  
`Age = [15, 22, 37, 45, 63]`

**Categorical (after binning):**  
`AgeGroup = ['Teen', 'Young Adult', 'Adult', 'Adult', 'Senior']`



## 🔹 Discretization / Binning

**Discretization** (or **binning**) is the process of converting **continuous numerical data** into **discrete intervals** or **bins**.

### ✅ Benefits:
- Helps handle **outliers**
- Improves **value spread**
- Useful for models that handle categorical data better



## 📂 Types of Binning

### 1. **Unsupervised Binning**

#### 📌 a. Equal Width (Uniform) Binning
- Divides range into **equal-sized bins**
- Outliers are **handled well**
- Data **spread remains unchanged**
- **Bin size** = (max - min) / number of bins

#### 📌 b. Equal Frequency (Quantile) Binning
- More commonly used
- You select the number of intervals 
- Each bin has **equal number of data points**
- Handles **outliers well**
- Provides **well-balanced spread**

#### 📌 c. K-Means Binning
- Useful when data has **clusters**
- Uses **centroids** as bins
- Assigns data to the nearest centroid
- Repeats:
  - Assign points to closest centroid
  - Shift centroid to the mean of assigned group
  - Stop when centroids no longer change



### 2. **Supervised Binning**

#### 📌 a. Decision Tree Binning
- Bins are chosen based on **target variable**
- Binning process **learns from labeled data**
- Will be covered after decision tree algorithms



### 3. **Custom Binning**

- Manually create bins using **domain knowledge**
- Example: Age bins — `0–18: Teen`, `19–35: Young Adult`, etc.
- Can be created using **manual cutoffs** based on logic or domain insights



## 🔸 Binarization

**Binarization** converts **numeric values into binary categories** based on a **threshold**.

### Example:
For a salary column with values like:
`[5L, 3L, 14L, 23L]`

If threshold = 6L:
- Values ≥ 6L → `1`
- Values < 6L → `0`

Used when you want to:
- Mark values as **high/low**
- Convert numeric data into **binary flags**



## 📝 Summary

| Technique       | Purpose                                     | When to Use                          |
|------------------|---------------------------------------------|---------------------------------------|
| Equal Width      | Fixed-size bins                            | Simple, range-based grouping          |
| Equal Frequency  | Equal-sized bins by data count             | Better value distribution             |
| K-Means Binning  | Cluster-aware binning                      | Data with natural groupings           |
| Custom Binning   | Manual, domain-specific                    | You know what bins make sense         |
| Decision Tree    | Supervised learning-based binning          | When using labeled data               |
| Binarization     | Threshold-based binary conversion          | Need binary features from numeric     |
