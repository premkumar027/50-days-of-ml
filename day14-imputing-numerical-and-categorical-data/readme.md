# 🔢 Handling Missing Data: Numerical & Categorical Features



## 📊 Handling Numerical Data

### 1. **Univariate Imputation**
- Imputes missing values using **only the same column**.
- Based on statistical measures (mean, median, etc.)

#### Common Methods:
1. **Mean / Median**
2. **Arbitrary Value**
3. **End of Distribution**
4. **Random Value**



### 📌 Mean / Median Imputation

#### ✅ When to Use:
- Data is **MCAR**
- Missing values are **< 5%**
- Use **mean** if the data is **normally distributed**
- Use **median** if the data is **skewed**

#### ⚠️ Drawbacks:
- Brings in **outliers**
- **Changes the shape** of the distribution
- **Covariance and correlation** may shift
  - Line 149: 4 new columns created after imputation
  - Line 111 vs 155: Covariance changed a lot; correlation changed slightly (as it’s bounded between -1 and 1)
- **Boxplot Observation**:
  - Age: Large outliers after imputation
  - Fare: Distribution looks stable

#### Tools:
- Can be done using **pandas** (simpler)
- Better with **scikit-learn** when working with pipelines


### 📌 Arbitrary Value Imputation

- Replace missing values with a clearly **unrealistic number** (e.g., -1, 999)

#### ✅ Benefits:
- Easy to apply
- Creates a **clear flag** for "missingness"

#### ❌ Disadvantages:
1. **Distorts PDF**
2. Alters **variance**
3. Affects **covariance**

> ⚠️ Rarely used in practice, especially for numeric features.  
> Only use if data is **not missing at random (NMAR)**



### 📌 End of Distribution Imputation

- For **normal distribution**: use `(mean ± 3σ)`
- For **skewed data**: use **IQR range**
  - Lower bound: `Q1 - 1.5 × IQR`
  - Upper bound: `Q3 + 1.5 × IQR`

#### ✅ Benefits:
- Easy to compute
- Simulates rare/extreme values

#### ❌ Disadvantages:
- Alters **distribution shape**
- Changes **variance and covariance**

> Use only if data is **not randomly missing**



## 🧠 Handling Categorical Data

### Two Main Methods:

1. **Most Frequent Category (Mode)**
2. **"Missing" Category Imputation**


### 📌 Most Frequent Category (Mode)

- Replace missing value with the **most common category**

#### ✅ When to Use:
- Data is **MCAR**

#### ✅ Pros:
- Easy and intuitive

#### ❌ Cons:
- Changes the original **category frequency distribution**



### 📌 "Missing" Category Imputation

- Add a new category like `"Missing"` to explicitly label missing data

#### ✅ When to Use:
- If **missing data > 10%**

#### ✅ Benefits:
- Allows model to **treat missingness as a signal**
- No need to guess the true value



## 📝 Summary Table

| Imputation Method        | Best For       | Pros                          | Cons                               |
|--------------------------|----------------|-------------------------------|------------------------------------|
| Mean / Median            | MCAR, <5%       | Simple, fast                  | Alters distribution, adds outliers |
| Arbitrary Value          | NMAR            | Easy, flag for missingness    | Distorts stats                     |
| End of Distribution      | NMAR            | Captures extreme behavior     | Changes PDF, variance              |
| Mode (Categorical)       | MCAR            | Easy                          | Distorts category balance          |
| "Missing" Category       | Missing >10%    | Highlights missing as feature | Adds artificial category           |
