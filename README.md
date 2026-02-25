# 🧠 Data Preprocessing for Machine Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0%2B-orange)
![pandas](https://img.shields.io/badge/pandas-1.3%2B-yellow)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-green)

## 📋 Overview

This repository contains comprehensive templates and tools for **data preprocessing** in machine learning projects. Data preprocessing is one of the most critical steps in the ML pipeline, as the quality of data directly impacts model performance.

### ✨ What's Inside

- ✅ **Template files** for quick start
- ✅ **Complete preprocessing tools** with all essential steps
- ✅ **Sample dataset** for practice
- ✅ **Well-documented code** in both Python and Jupyter Notebook formats

## 📂 Repository Structure

data-preprocessing/
│
├── 📓 data_preprocessing_template.ipynb     # Template notebook
├── 📜 data_preprocessing_template.py         # Template Python script
├── 📓 data_preprocessing_tools.ipynb         # Complete tools notebook
├── 📜 data_preprocessing_tools.py             # Complete tools Python script
├── 📊 Data.csv                                # Sample dataset
└── 📖 README.md                                # Project documentation

## 🚀 Getting Started

### Prerequisites

Make sure you have the following libraries installed:

```bash
pip install numpy pandas matplotlib scikit-learn
```

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/data-preprocessing.git
   cd data-preprocessing
   ```

2. **Choose your preferred format**
   - For a quick start: Use `data_preprocessing_template.py` or `.ipynb`
   - For complete preprocessing: Use `data_preprocessing_tools.py` or `.ipynb`

3. **Run the code**
   ```bash
   python data_preprocessing_template.py
   ```
   Or open the Jupyter notebooks in your preferred environment.

## 📊 Sample Dataset (Data.csv)

The included dataset contains 10 samples with 4 columns:

| Column    | Description                  | Type      |
|-----------|------------------------------|-----------|
| Country   | Country of residence         | Categorical |
| Age       | Age in years                 | Numerical |
| Salary    | Annual salary in USD         | Numerical |
| Purchased | Purchase decision (Yes/No)   | Target variable |

## 🔧 Preprocessing Steps Covered

### 1️⃣ Importing Libraries
```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
```

### 2️⃣ Importing Dataset
- Separate features (X) and target variable (y)
- Handle different data types

### 3️⃣ Handling Missing Data
- Using `SimpleImputer` from scikit-learn
- Strategy: Mean imputation for numerical data

### 4️⃣ Encoding Categorical Data
- **Independent variables**: OneHotEncoder
- **Dependent variable**: LabelEncoder

### 5️⃣ Splitting Dataset
- Training set (80%) and Test set (20%)
- Random state for reproducibility

### 6️⃣ Feature Scaling
- Standardization using `StandardScaler`
- Applied to numerical features only

## 💻 Code Examples

### Template Version (Basic)
```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

dataset = pd.read_csv('Data.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, -1].values
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
```

### Complete Version (With All Tools)
```python
# Importing libraries
import numpy as np
import pandas as pd

# Import dataset
dataset = pd.read_csv('Data.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, -1].values

# Handle missing data
from sklearn.impute import SimpleImputer
imputer = SimpleImputer(missing_values=np.nan, strategy='mean')
imputer.fit(X[:, 1:3])
X[:, 1:3] = imputer.transform(X[:, 1:3])

# Encode categorical data
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder, LabelEncoder
ct = ColumnTransformer(transformers=[('encoder', OneHotEncoder(), [0])], remainder='passthrough')
X = np.array(ct.fit_transform(X))
le = LabelEncoder()
y = le.fit_transform(y)

# Split dataset
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=1)

# Feature scaling
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
X_train[:, 3:] = sc.fit_transform(X_train[:, 3:])
X_test[:, 3:] = sc.transform(X_test[:, 3:])
```

## 📈 Why Data Preprocessing Matters?

| Without Preprocessing | With Preprocessing |
|----------------------|-------------------|
| ❌ Missing values cause errors | ✅ Missing values handled |
| ❌ Categorical data can't be used | ✅ Categories encoded properly |
| ❌ Features with different scales bias the model | ✅ All features on same scale |
| ❌ Model performance suffers | ✅ Optimal model performance |

## 🤝 Connect With Me

**Saleh Tarkshvand**  
Data Science Enthusiast | Machine Learning Learner

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/saleh-tarkshvand-67049026a)

Feel free to connect with me on LinkedIn for discussions about data science, machine learning, or collaboration opportunities!

## 📝 License

This project is open source and available for learning purposes.

## ⭐ Show Your Support

If you find this repository helpful, please consider giving it a star! It helps others discover this resource too.

---

**Happy Learning! 🚀 | Made with ❤️ by Saleh Tarkshvand**
