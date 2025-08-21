# 🛠️ Feature Engineering

Feature Engineering is the process of preparing raw data into features that improve model performance.



## 1. Feature Transformation

Transform existing data to make it more suitable for machine learning algorithms.

- **Feature Scaling**  
- Why? Some ML algorithms (e.g., k-NN, SVM, Gradient Descent-based models) are sensitive to feature scale. Scaling ensures all features contribute equally. For eg. In age and salary, salary is big number andd age is small so model might think that salary is more important than age.
  - Standardization (Z-score normalization)  
  - Normalization (Min-Max scaling)  
  - Robust or MaxAbs scaling for special cases

- **Encoding Categorical Features** 
- Why? Most ML algorithms only work with numbers. Categorical variables must be encoded into numerical form. 
  - Ordinal Encoding (for ordered categories)  
  - One-Hot Encoding (for unordered categories)  
  - Label Encoding (only for target variables)

- **Missing Value Imputation**  
- Why? Many ML models can't handle missing data directly, so we need to fill or remove them to ensure the model works properly.

  - Drop missing values (if very few or MCAR)  
  - Replace with statistical values: mean, median (for numerical)  
  - Replace with mode (for categorical)
  - Custom values like "Missing" category (for categorical)
    

- **Outlier Detection and Handling** 
- Why? Outliers can skew model predictions and lead to poor performance. 
  - Use IQR method, Z-score, or visual tools (boxplot) to detect  
  - Remove or transform outliers based on model sensitivity



## 2. Feature Construction

Create new meaningful features from raw data.  
Example: From a `Date`, extract `year`, `month`, `day`, `weekday`, `is_weekend`, `quarter`, etc.



## 3. Feature Selection

Select the most relevant features using:

- **Filter Methods** – Correlation, Chi-Square  
- **Wrapper Methods** – Recursive Feature Elimination (RFE)  
- **Embedded Methods** – Feature importance from models like Lasso, Random Forests



## 4. Feature Extraction

Transform high-dimensional data into fewer dimensions:

- **PCA (Principal Component Analysis)**  
- **t-SNE (for visualization)**  
- **Autoencoders (deep learning)**

---

## 🔁 Standardization vs Normalization

| Aspect                 | Standardization                          | Normalization                          |
|------------------------|-------------------------------------------|-----------------------------------------|
| Also called            | Z-score scaling                           | Min-Max scaling                         |
| Formula                | \( x' = \frac{x - \mu}{\sigma} \)         | \( x' = \frac{x - x_{min}}{x_{max} - x_{min}} \) |
| Output Range           | Mean = 0, Std = 1 (can go below 0 or above 1) | [0, 1] typically                       |
| Sensitive to outliers? | Less                                      | More                                    |
| Keeps outliers?        | ✅ Yes                                     | ❌ Compresses them                      |
| Assumes distribution?  | Best for normally distributed data         | No distribution assumption              |
| Use Cases              | PCA, SVM, Logistic/Linear Regression       | KNN, K-Means, Neural Networks           |
| Scikit-learn method    | `StandardScaler()`                        | `MinMaxScaler()`                        |

---

### ✅ When to Use **Standardization**
- Data is **normally distributed** or roughly symmetric
- Algorithms that assume **Gaussian distribution**:
  - Linear/Logistic Regression
  - Principal Component Analysis (PCA)
  - Support Vector Machines (SVM)
- Outliers should be retained

### ✅ When to Use **Normalization**
- You want **feature values between 0 and 1**
- Using **distance-based models** like:
  - K-Nearest Neighbors (KNN)
  - K-Means Clustering
- Data has **different units** or **wide value ranges**
- When working with **Neural Networks**



### ✨ Rule of Thumb:
> Use **Standardization** by default.  
> Use **Normalization** when your model or data demands strict scaling to a fixed range or is sensitive to distances.


