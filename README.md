# Smart Lender Project – Univariate Analysis

## Objective

Univariate analysis is performed to examine the distribution and characteristics of individual features in the loan prediction dataset.

This analysis helps identify feature patterns, data imbalance, outliers, and preprocessing requirements before model development.

---

## Libraries Used

- Python
- Pandas
- Matplotlib
- Seaborn

---

## Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
data = pd.read_csv("loan_prediction.csv")

# Display first five rows
print(data.head())

# Check dataset information
print(data.info())
```

---

## Distribution Analysis

The following plots visualize the distribution of continuous and binary features.

```python
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
sns.histplot(data=data, x="ApplicantIncome", kde=True)
plt.title("Distribution of Applicant Income")

plt.subplot(1, 2, 2)
sns.countplot(data=data, x="Credit_History")
plt.title("Distribution of Credit History")

plt.tight_layout()
plt.show()
```

---

## Categorical Feature Analysis

The following count plots show the frequency of categories in Gender and Education.

```python
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
sns.countplot(data=data, y="Gender")
plt.title("Gender Distribution")

plt.subplot(1, 2, 2)
sns.countplot(data=data, y="Education")
plt.title("Education Distribution")

plt.tight_layout()
plt.show()
```

---

## Observations

- Applicant income is right-skewed (positively skewed), meaning most applicants have lower-to-medium income while a few have very high income.
- Credit history is a binary feature with values 0 and 1.
- Gender and education are categorical features with two main categories.
- Male applicants occur more frequently than female applicants.
- Graduate applicants occur more frequently than non-graduate applicants.
- These plots help identify data distribution and possible preprocessing needs before training machine learning models.

---

## Conclusion

Univariate analysis provides a clear understanding of each feature independently. It supports data cleaning, handling missing values, encoding categorical features, and preparing the dataset for loan approval prediction models.
