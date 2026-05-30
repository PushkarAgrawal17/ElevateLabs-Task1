# ElevateLabs-Task1

# 🚢 Titanic Data Cleaning & Preprocessing for Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-red)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

## 📌 Project Overview

Raw datasets are rarely ready for Machine Learning. They often contain missing values, categorical data, inconsistent feature scales, and outliers that can negatively impact model performance.

This project demonstrates a complete **Data Cleaning & Preprocessing Pipeline** using the **Titanic Dataset**, transforming raw data into a clean and machine-learning-ready format.

---

## 🎯 Objectives

✔ Explore and understand the dataset

✔ Handle missing values effectively

✔ Convert categorical variables into numerical representations

✔ Normalize and standardize numerical features

✔ Detect and remove outliers

✔ Prepare a clean dataset for Machine Learning models

---

## 🛠 Tech Stack

| Tool         | Purpose                   |
| ------------ | ------------------------- |
| Python       | Core Programming          |
| Pandas       | Data Manipulation         |
| NumPy        | Numerical Operations      |
| Matplotlib   | Data Visualization        |
| Seaborn      | Statistical Visualization |
| Scikit-Learn | Data Preprocessing        |

---

## 📂 Dataset

### Titanic Dataset

The dataset contains information about Titanic passengers, including:

* Passenger demographics
* Ticket details
* Passenger fares
* Cabin information
* Embarkation ports
* Survival status

This dataset is widely used for learning Data Science and Machine Learning fundamentals because it contains both numerical and categorical features along with missing values.

---

## 🔍 Data Exploration

Before preprocessing, the dataset was analyzed to understand:

* Dataset dimensions
* Data types
* Missing values
* Statistical summaries
* Feature distributions

### Functions Used

```python
df.head()
df.info()
df.describe()
df.isnull().sum()
```

---

## 🧹 Data Cleaning

### 1️⃣ Handling Missing Values

#### Numerical Features

Missing numerical values were replaced using:

* Mean Imputation
* Median Imputation

```python
df["Age"].fillna(df["Age"].median(), inplace=True)
```

#### Categorical Features

Missing categorical values were filled using the mode:

```python
df["Embarked"].fillna(df["Embarked"].mode()[0], inplace=True)
```

#### Dropping Unnecessary Columns

Columns with excessive missing values were removed.

```python
df.drop("Cabin", axis=1, inplace=True)
```

---

## 🔄 Feature Encoding

Machine Learning algorithms require numerical inputs.

Categorical variables were converted using:

### Label Encoding

```python
from sklearn.preprocessing import LabelEncoder
```

### One-Hot Encoding

```python
pd.get_dummies()
```

Example:

```text
Male   → 1
Female → 0
```

---

## 📏 Feature Scaling

Since features can have different ranges, scaling was applied to ensure fair contribution during model training.

### Standardization

```python
from sklearn.preprocessing import StandardScaler
```

Transforms data to:

```text
Mean = 0
Standard Deviation = 1
```

### Normalization

```python
from sklearn.preprocessing import MinMaxScaler
```

Transforms data to:

```text
Range = [0, 1]
```

---

## 📊 Outlier Detection & Removal

Outliers were visualized using boxplots.

```python
sns.boxplot()
```

### IQR Method

The Interquartile Range (IQR) technique was used to identify extreme values.

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Values outside these bounds were removed from the dataset.

---

## ✅ Results

After preprocessing:

* Missing values were handled successfully
* Categorical features were encoded
* Numerical features were scaled
* Outliers were removed
* Dataset became ML-ready

---

## 📁 Project Structure

```text
ElevateLabs-Task1/
│
├── datasets/
│   ├── Titanic-Dataset.csv
│   └── cleaned_titanic.csv
│
├── notebooks/
│   └── preprocessing.ipynb
│
├── images/
│   └── boxplot.png
│
├── README.md
│
└── requirements.txt
```

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/PushkarAgrawal17/ElevateLabs-Task1.git
```

### Navigate to Project

```bash
cd ElevateLabs-Task1
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Notebook

```bash
jupyter notebook
```

Open:

```text
preprocessing.ipynb
```

---

## 📈 Key Learnings

Through this project, I learned:

* Exploratory Data Analysis (EDA)
* Missing Value Treatment
* Feature Engineering Basics
* Data Encoding Techniques
* Feature Scaling Methods
* Outlier Detection using IQR
* Building an End-to-End Preprocessing Pipeline

---

## 🔮 Future Improvements

* Build reusable preprocessing pipelines
* Automate workflows using Scikit-Learn Pipelines
* Experiment with advanced imputation techniques
* Integrate preprocessing with ML model training

---

## 👨‍💻 Author

**Pushkar Agrawal**

B.Tech CSE Student | Machine Learning Enthusiast | AI Learner

