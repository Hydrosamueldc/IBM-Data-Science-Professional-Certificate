# 🧹 DATA WRANGLING — SUMMARY

## Introduction

**Data Wrangling** is the process of transforming raw data into a clean and usable format suitable for analysis.  
It involves formatting, cleaning, transforming, and organizing data so that it can be efficiently analyzed or used to build machine learning models.

By mastering data wrangling, you can ensure data consistency, reliability, and better insights.

---

## 🔧 1. DATA FORMATTING

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

## 🧮 CORRECTING DATA TYPES

### 🔹 Definition
Data type correction ensures that each variable has the proper data type (e.g., **integer**, **float**, **string**) required for analysis.


### 🔹 Importance
- Prevents computational errors.  
- Ensures compatibility with statistical and machine learning methods.  
- Helps in accurate data manipulation.  



### 🔹 Example
Convert numeric data stored as strings into floats or integers.


### 🔹 Python Example
```python
# Check and convert data types
df["price"] = df["price"].astype(float)
print(df.dtypes)
```
---
