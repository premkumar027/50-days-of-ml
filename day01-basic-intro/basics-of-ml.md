# 📘 Basics of Machine Learning

Machine Learning is a field of computer science where systems learn from data to make predictions or decisions without being explicitly programmed.

---

## 🔰 Types of Machine Learning

1. **Supervised Learning**
   - **Regression** – Target/output is numerical  
   - **Classification** – Target/output is categorical  

2. **Unsupervised Learning**
   - Clustering  
   - Dimensionality Reduction  
   - Anomaly Detection  
   - Association Rule Learning  

3. **Semi-supervised Learning**

4. **Reinforcement Learning**

---

## 🔄 Learning Approaches

### 🔹 Batch / Offline Learning
- Model is trained on the **entire dataset at once**
- Requires retraining from scratch if new data is added  

### 🔹 Online Learning
- Model learns **incrementally**
- Ideal for real-time or continuously incoming data  
- 🔧 Libraries: `River`, `Vowpal Wabbit`

---

## 🧠 Learning Strategies

### 🔸 Instance-Based Learning
- Memorizes training examples  
- Uses **similarity** to make predictions  
> **Example**: k-Nearest Neighbors (k-NN)

### 🔸 Model-Based Learning
- Builds a **generalized model** from training data  
- Learns parameters and applies to unseen data  
> **Example**: Linear Regression, Decision Trees, Neural Networks

---

## ⚠️ Common ML Problems

1. Data Collection  
2. Insufficient or Unlabeled Data  
3. Non-representative Data  
4. Poor Quality Data  
5. Irrelevant Features  
6. Overfitting  
7. Underfitting  
8. Software Integration Challenges  
9. Deployment Issues (Offline Learning)  
10. High Costs  

---

## 🔁 Machine Learning Development Lifecycle

1. Frame the Problem  
2. Gather Data (CSV, APIs, Web Scraping, etc.)  
3. Preprocess Data  
4. Perform EDA (Exploratory Data Analysis)  
5. Feature Engineering & Selection  
6. Train, Evaluate, and Select Model  
7. Model Deployment  
8. Testing  
9. Optimization  

---

## 🧑‍💻 Data-Centric Job Roles

| Role           | Skills |
|----------------|--------|
| **Data Analyst** | Programming, Statistics, Data Viz, SQL, Excel, Storytelling, Communication |
| **Data Engineer** | Programming, DSA, DBMS, Cloud, Pipelines, Distributed Systems |
| **Data Scientist** | Statistics + Software Development |
| **ML Engineer** | Programming, Math, ML Models, Software Dev |

---

## 🧮 Tensors in ML

Tensors are data containers used for numerical operations.

### 📏 Tensor Dimensions (Axes / Rank)

- **0D Tensor** – Scalar  
  `1`  
- **1D Tensor** – Vector  
  `[2, 3, 7, 1, 9]`  
- **2D Tensor** – Matrix  
  `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`  
- **ND Tensor** – Tensor  
  `[[[1, 2]], [[3, 4]]]`

### 📦 Examples

- **4D Tensor** – Group of 50 images  
- **5D Tensor** – Video (Frames over time)

---
