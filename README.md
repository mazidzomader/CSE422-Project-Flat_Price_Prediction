# 🏠 Flat Price Category Prediction using Machine Learning
📌 *Developed as part of a CSE422: Artificial Intelligence.*

This repository contains an end-to-end **Artificial Intelligence / Machine Learning lab project** focused on predicting **flat price categories** using multiple supervised and unsupervised learning algorithms.

The project follows a **methodologically correct ML pipeline**, emphasizing proper preprocessing, model comparison, and evaluation rather than artificially inflating accuracy.

---

## 📌 Problem Statement

Given housing-related features such as location, size, number of bedrooms, security level, and distance from the city center, the objective is to:

- **Predict the price category** of a flat (`Low`, `Medium`, `High`) using supervised learning.
- **Explore natural groupings** in the data using unsupervised learning (K-Means clustering).

---

## 📂 Dataset Description

The dataset includes the following features:

| Feature | Description |
|------|-----------|
| Location | City Center / Suburbs / Countryside |
| Size_sqft | Flat size in square feet |
| Num_Bedrooms | Number of bedrooms |
| Num_Bathrooms | Number of bathrooms |
| Has_Balcony | Whether the flat has a balcony |
| Floor_Number | Floor on which the flat is located |
| Building_Age_Years | Age of the building |
| Parking_Available | Parking availability |
| Nearby_Schools | Availability of schools nearby |
| Distance_to_CityCenter_km | Distance from city center |
| Security_Level | Low / Medium / High |
| **Price_Category** | Target variable (Low / Medium / High) |

---

## 🧪 Machine Learning Algorithms Used

### 🔹 Supervised Learning
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Naive Bayes
- Neural Network (MLP)

### 🔹 Unsupervised Learning
- K-Means Clustering

---

## 🔄 Project Workflow

### 1️⃣ Data Inspection
- Checked data types, shape, missing values, and basic statistics.

### 2️⃣ Data Cleaning
- Removed irrelevant columns.
- Handled missing values using:
  - Mean (continuous)
  - Median (discrete numeric)
  - Mode (categorical)
- Removed duplicate rows.

### 3️⃣ Encoding
- **Ordinal Encoding**:
  - `Location` (Countryside < Suburbs < City Center)
  - `Security_Level` (Low < Medium < High)
  - `Price_Category` (Low < Medium < High)
- **One-Hot Encoding**:
  - `Has_Balcony`
  - `Parking_Available`
  - `Nearby_Schools`

### 4️⃣ Correlation Analysis
- Generated correlation heatmap.
- No strong multicollinearity detected.
- All features retained.

### 5️⃣ Train–Validation–Test Split
- 70% Training
- 10% Validation
- 20% Testing  
(Split performed **before scaling** to avoid data leakage.)

### 6️⃣ Feature Scaling
- **RobustScaler** applied to numerical features:
  - Size, bedrooms, bathrooms, floor number, building age, distance
- Scaler fitted **only on training data**, then applied to validation and test sets.

### 7️⃣ Model Training & Evaluation
- Models trained on training set.
- Hyperparameters evaluated using validation set.
- Final performance reported on test set.
- Accuracy, confusion matrix, and classification reports used for evaluation.

---

## 📊 Results Summary

| Model | Test Accuracy (Approx.) |
|----|----------------|
| Logistic Regression | ~34% |
| KNN | ~32–35% |
| Decision Tree | ~34–40% |
| Naive Bayes | ~35–45% |
| Neural Network | Evaluated |
| K-Means | Clusters compared post-hoc |

> ⚠️ Accuracy close to random baseline (~33%) indicates that **Price_Category is weakly separable** based on available features. This outcome is discussed and justified rather than hidden.

---

## 🧠 Key Observations

- Logistic Regression served as a **baseline model**.
- Non-linear models did not significantly outperform baseline, indicating:
  - Overlapping class distributions
  - Weak signal in categorical price labels
- Decision Tree successfully overfit training data (100%), confirming:
  - Correct preprocessing
  - No data leakage
  - Proper feature–label alignment
- Dummy classifier achieved similar accuracy, reinforcing conclusions.

---

## ✅ Validation & Sanity Checks

Extensive preprocessing validation was performed:
- X–y alignment checks
- Class distribution checks across splits
- Scaling sanity checks
- Dummy classifier baseline
- Overfit-on-purpose Decision Tree test

This ensures the pipeline is **correct and trustworthy**.

---

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib / Seaborn

---
## 👥 Team Members


- **1.** [Abdullah Al Mazid Zomader](https://github.com/mazidzomader)
- **2.** [Avisheek Pal Joy](https://github.com/gTOY77)

---

## 🎯 Conclusion

This project demonstrates a **realistic and academically sound machine learning workflow**.  
Rather than forcing high accuracy, the focus is on:

- Correct preprocessing
- Honest evaluation
- Model comparison
- Proper interpretation of results

Such an approach reflects **good ML practice** and aligns with real-world data science principles.

---
  

