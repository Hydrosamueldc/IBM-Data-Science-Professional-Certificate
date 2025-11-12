# DATA WRANGLING — SUMMARY

## Introduction

**Data Wrangling** is the process of transforming raw data into a clean and usable format suitable for analysis.  
It involves formatting, cleaning, transforming, and organizing data so that it can be efficiently analyzed or used to build machine learning models.

By mastering data wrangling, you can ensure data consistency, reliability, and better insights.

---

## 1. DATA FORMATTING

### Definition
Data formatting is the process of making data from various sources consistent and comparable by converting it into a uniform structure or unit.

### Importance
- Ensures consistency across datasets.  
- Simplifies data analysis and comparison.  
- Prevents errors during calculations and visualization.

### Example
Convert "city miles per gallon" (mpg) to "city liters per 100 kilometers" for easier comparison.

### Python Example
```python
# Convert miles per gallon (mpg) to liters per 100 km
df["city-L/100km"] = 235 / df["city-mpg"]
```
---

## CORRECTING DATA TYPES

### Definition
Data type correction ensures that each variable has the proper data type (e.g., **integer**, **float**, **string**) required for analysis.


### Importance
- Prevents computational errors.  
- Ensures compatibility with statistical and machine learning methods.  
- Helps in accurate data manipulation.  

### Example
Convert numeric data stored as strings into floats or integers.


### Python Example
```python
# Check and convert data types
df["price"] = df["price"].astype(float)
print(df.dtypes)
```
---

## 3. DATA NORMALIZATION

### Definition
Data normalization is the process of scaling data into a standard range or distribution.  
It ensures that no variable dominates due to its scale, making models more accurate and fair.



###  Techniques
- **Feature Scaling:** Adjusts values to a common scale.  
- **Min-Max Normalization:** Scales data between 0 and 1.  
- **Z-Score Standardization:** Centers data around the mean with unit variance.  


###  Python Example
```python
# Min-Max normalization
df["normalized_column"] = (df["column"] - df["column"].min()) / (df["column"].max() - df["column"].min())

# Z-Score normalization
df["standardized_column"] = (df["column"] - df["column"].mean()) / df["column"].std()
```
---
## 4. BINNING

### Definition
Binning is a data pre-processing method that groups continuous data into intervals or categories (bins).  
It is useful for simplifying complex numerical data and improving visualization or model performance.



###  Importance
- Reduces the impact of small observation errors.  
- Converts continuous data into categorical form for easier interpretation.  
- Enhances visualization.  



###  Example
Classify prices into “Low,” “Medium,” and “High” ranges.


###  Python Example
```python
import numpy as np
import pandas as pd

# Create bins and group names
bins = np.linspace(min(df["price"]), max(df["price"]), 4)
group_names = ["Low", "Medium", "High"]

# Apply binning
df["price-binned"] = pd.cut(df["price"], bins, labels=group_names, include_lowest=True)

# Visualize the distribution
df["price-binned"].value_counts().plot(kind="bar")
```
---
##  5. ENCODING CATEGORICAL VARIABLES

### Definition
Encoding is the process of converting categorical variables (text-based) into numerical form so they can be used in machine learning models.



###  Importance
- Machine learning models require numerical inputs.  
- Helps the model interpret qualitative information quantitatively.  



###  Technique: One-Hot Encoding
Each category becomes a new column with binary values (**0** or **1**) indicating presence or absence.


### 🔹 Python Example
```python
# One-Hot Encoding using pandas
df = pd.get_dummies(df, columns=["fuel-type"])
```
# Example result:
# fuel-type_diesel | fuel-type_gas
#         1        |        0
#         0        |        1

---
##  KEY TAKEAWAYS

- **Data Formatting** → Makes data consistent and comparable.  
- **Correcting Data Types** → Ensures accurate representation of information.  
- **Data Normalization** → Standardizes data for fair comparison.  
- **Binning** → Groups continuous data into meaningful categories.  
- **Encoding** → Converts categorical values into numerical format.  

