## 🔤 Encoding Categorical Data

Categorical features contain labels that must be converted into numerical form so machine learning algorithms can process them.



### 1. Ordinal Encoding

- Converts ordered categories into numerical values based on rank.
- Common for features like Education Level, Ratings, Size (Small, Medium, Large).
- The encoded values reflect the **ranking**, but **not the magnitude** of difference.
- Often used with algorithms that can leverage the order (like linear models or tree-based models).

> ❗ Misuse on nominal data may mislead models by implying order where none exists.



### 2. Label Encoding

- Encodes target variable (labels) into numeric format.
- Used **only** for output/target column, not features.
- Each category gets a unique integer, but **no notion of order** is assumed.
- Common in classification problems where the target is categorical.



### 3. One-Hot Encoding

- Converts each category into a **binary column** (0 or 1).
- Suitable for **nominal data** where categories have **no order**.
- Prevents introducing false ordering or relationships.
- One category is typically **dropped** (n-1 encoding) to avoid **dummy variable trap**.
- Works well with linear models, distance-based algorithms, etc.

> ⚠️ Be cautious with high-cardinality data, too many new columns can lead to memory issues or overfitting.



### 4. Dummy Variable Trap

- Occurs when one category can be predicted using the rest (multicollinearity).
- To avoid it, drop one column after one-hot encoding (e.g., use only n-1 columns).

---

### ✅ Summary Table

| Encoding Type   | Use Case                             | Ordered? | Output Columns |
|------------------|----------------------------------------|----------|----------------|
| Ordinal Encoding | Ordered features                       | ✅ Yes   | 1              |
| Label Encoding   | Target/Output variable only            | ❌ No    | 1              |
| One-Hot Encoding | Nominal (unordered) features           | ❌ No    | n or n-1       |

---

### 🧠 Good Practices

- Understand the nature of your categories (ordered or not).
- Avoid label encoding for nominal features.
- Always apply same encoding logic on both train and test sets.
- Use category reduction or embeddings for very high-cardinality data.


