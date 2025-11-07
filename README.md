# -Exploratory-Data-Analysis-EDA---Task-5
Extract insights using visual and statistical exploration.

1. Import Libraries

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Display settings
pd.set_option('display.max_columns', None)
sns.set(style='whitegrid')


---

2. Load Dataset

# Load your dataset
df = pd.read_csv("data.csv")

# Show first few rows
df.head()


---

3. Basic Info and Summary

# Dataset overview
df.info()

# Statistical summary
df.describe()

# Checking missing values
df.isnull().sum()

# Unique values per column
df.nunique()


---

4. Univariate Analysis

Focus on understanding each column separately.

# Example for numerical columns
num_cols = df.select_dtypes(include=np.number).columns

for col in num_cols:
    plt.figure(figsize=(6,4))
    sns.histplot(df[col], kde=True)
    plt.title(f"Distribution of {col}")
    plt.show()

# Example for categorical columns
cat_cols = df.select_dtypes(include='object').columns

for col in cat_cols:
    plt.figure(figsize=(6,4))
    sns.countplot(x=col, data=df)
    plt.title(f"Count Plot of {col}")
    plt.xticks(rotation=45)
    plt.show()


---

5. Bivariate Analysis

Check relationships between variables.

# Correlation heatmap
plt.figure(figsize=(10,6))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title("Correlation Heatmap")
plt.show()

# Pairplot for relationships
sns.pairplot(df)
plt.show()

# Scatterplot example
sns.scatterplot(x='Feature1', y='Feature2', data=df)
plt.title('Feature1 vs Feature2')
plt.show()


---

6. Outlier Detection

for col in num_cols:
    plt.figure(figsize=(6,4))
    sns.boxplot(x=df[col])
    plt.title(f"Boxplot of {col}")
    plt.show()


---

7. Observations and Insights

(Example — replace with your own dataset findings)

Visualization	Observation

Histogram of Age	Most customers are between 25–40 years old.
Countplot of Gender	Slightly more males than females in dataset.
Heatmap	Income and Spending Score show moderate positive correlation.
Boxplot of Price	A few high-value outliers present.
Pairplot	Age negatively correlates with Spending Score.



---

8. Summary of Findings

Key Takeaways:

Dataset has no major missing values (if any, handled appropriately).

Numerical variables are normally distributed except Income, which is right-skewed.

Strong correlation found between Annual Income and Spending Score.

A few outliers exist in numerical columns (e.g., Price).

No major data imbalance, but slight skew toward male customers.



---

9. Outcome

✅ Skill Gained:

Ability to identify patterns, trends, and anomalies

Understand relationships between features

Produce clear visual summaries for data-driven decisions



---

PDF Report (Structure Example)

When exporting to PDF, include:

Title: Exploratory Data Analysis on [Dataset Name]
Sections:

1. Dataset Overview


2. Summary Statistics


3. Visual Analysis (with plots)


4. Observations


5. Key Insights and Recommendations
