## 📘 Mathematical Transformations – ML Notes

### 🎯 Why Do We Use Mathematical Transformations?

- **Handle Skewed Distributions:** Many real-world datasets are skewed (e.g., income, housing prices). Models often work better with normally distributed data.
- **Reduce Variance and Outliers Impact:** Transforms like log or square root can compress large values and stabilize variance.
- **Improve Model Accuracy:** Especially in linear models and neural networks, better-distributed inputs lead to better learning.
- **Meet Model Assumptions:** Some models (e.g., linear regression) assume linearity or normally distributed residuals.
- **Make Relationships More Linear:** Certain patterns only appear after transformation (e.g., exponential to linear via log).

### 🔷 Types of Mathematical Transformations

We can categorize transformations into two main types:

#### 🔹 1. Function-Based Transformations

| Transformation        | Purpose                                        | When to Use                               |
|------------------------|-----------------------------------------------|--------------------------------------------|
| **Logarithmic (log)** | Compress large values, reduce right skew      | Income, prices, counts with wide range     |
| **Square Root**       | Reduce moderate skew, stabilize spread        | Count-based features like number of visits |
| **Reciprocal (1/x)**  | Invert large values, reduce outlier impact    | Rates, speed, time                         |
| **Exponential (e^x)** | Emphasize small numbers, reverse log          | When boosting small effects is needed      |
| **Absolute Value**    | Remove sign, keep magnitude                   | For symmetric spread without direction     |
| **Sine/Cosine**       | Capture periodic patterns                     | Time of day, seasonality, angles           |

#### 🔹 2. Power-Based Transformations


| Transformation            | Description                                        | Special Notes                                              |
|----------------------------|----------------------------------------------------|------------------------------------------------------------|
| **Power (xⁿ)**            | Raise values to a specific power                   | Manually chosen, good for custom scaling                   |
| **Box-Cox**               | Automatically selects power to normalize data      | Requires **positive** values                               |
| **Yeo-Johnson**           | Like Box-Cox but supports **zero and negative** values | Suitable for most real-world data                          |