---

## 🔍 **Detailed Theoretical Analysis of ML Models**

---

### 📘 **1. Linear Regression**

#### ✅ Purpose:

To **predict the Satisfaction Rating** (a continuous value between 1 and 5) based on session behaviour.

#### 🧠 Concept:

Linear regression attempts to model the relationship between independent variables (features) and a continuous dependent variable (target) using a **straight line (hyperplane)**.

#### ✅ Why Suitable:

* The target (`SatisfactionRating`) is **numeric and continuous**.
* Session-level attributes like time, task type, and prompts are **numeric predictors**.

#### 📊 Interpretation:

* R² Score: **0.61** → \~61% of the variation in satisfaction is explained by the model.
* Mean Squared Error (MSE): **0.51**

#### 🧪 Limitation:

* Assumes a **linear** relationship.
* Sensitive to **outliers** and **non-normality**.

---

### 📘 **2. Logistic Regression**

#### ✅ Purpose:

To **predict whether a student will reuse the AI assistant** (`UsedAgain` = Yes/No).

#### 🧠 Concept:

Logistic regression is used for **binary classification**. It maps input features to a **probability** using the logistic (sigmoid) function:

* Output is between 0 and 1 and is interpreted as the probability of class 1.
* A threshold (usually 0.5) is used to classify the outcome.

#### ✅ Why Suitable:

* Target is binary (True/False).
* Interpretable coefficients for understanding feature influence.

#### 📊 Performance:

* Accuracy: **69.2%**
* Recall (Reused): **100%**
* Recall (Not Reused): **0%**

#### ❌ Problem:

* **Severe class imbalance** in the dataset.
* Logistic regression **fails to classify the minority class** ("Not Reused").

#### 🧪 Limitations:

* Works poorly if features are not linearly separable.
* Biased toward majority class if **data is imbalanced**.

---

### 📘 **3. KMeans Clustering**

#### ✅ Purpose:

To identify **hidden behavioral groups** among students **without labels**.

#### 🧠 Concept:

KMeans is an **unsupervised algorithm** that partitions the dataset into **K clusters**. It does so by minimizing the **within-cluster variance** (inertia).

#### ✅ Why Suitable:

* To **group users** based on session characteristics like prompt count, session time, and task type.
* No target variable required.

#### 📊 Outcome:

* **2 clusters** identified: likely represent **light** and **heavy** AI users.
* Visualized via **PCA** to reduce dimensions.

#### 🧪 Limitations:

* Needs to **predefine K** (number of clusters).
* Sensitive to **outliers and initialization**.
* Assumes **spherical clusters**.

---

### 📘 **4. K-Nearest Neighbors (KNN)**

#### ✅ Purpose:

To classify whether the student will **reuse the AI assistant** based on session features.

#### 🧠 Concept:

KNN is a **lazy learning algorithm**. It **stores the training data** and classifies a new data point based on the **majority vote** of its **K nearest neighbors** (usually using Euclidean distance).

#### 🧮 Steps:

1. Compute distance from test point to all training points.
2. Select the **K nearest points**.
3. Perform **majority voting**.

#### ✅ Why Suitable:

* Non-parametric, flexible.
* Works well when **decision boundary is non-linear**.

#### 📊 Performance:

* Accuracy: **66.6%**
* Recall (Reused): **87%**
* Recall (Not Reused): **21%**

✅ Performs **better than logistic regression**, but still **suffers from class imbalance**.

#### 🧪 Limitations:

* Computationally expensive for large datasets.
* Performance is **highly dependent on K** and **feature scaling**.
* Imbalanced datasets can **bias nearest neighbors**.

---

## 📌 Summary Table

| Model               | Type               | Task                    | Strengths                              | Limitations                         |
| ------------------- | ------------------ | ----------------------- | -------------------------------------- | ----------------------------------- |
| Linear Regression   | Supervised (Reg)   | Satisfaction Prediction | Interpretable, fast                    | Linear assumptions                  |
| Logistic Regression | Supervised (Class) | Reuse Prediction        | Simple, interpretable                  | Poor with class imbalance           |
| KMeans Clustering   | Unsupervised       | Behavior Clustering     | Reveals hidden patterns                | Needs K, assumes spherical clusters |
| KNN Classifier      | Supervised (Class) | Reuse Prediction        | Non-linear modeling, no training phase | Slow for large data, sensitive to K |

