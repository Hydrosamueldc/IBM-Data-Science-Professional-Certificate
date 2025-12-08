# Data Wrangling & Preprocessing 

This summary provides a clear, beginner-friendly explanation of the most important data-wrangling concepts used in data analysis and machine learning.  
It includes **definitions, illustrations, use-cases, and Python code examples**.

---

#  1. Why Data Formatting Matters

Data comes from many different sources (surveys, devices, logs, sensors, websites).  
Each may use **different units, formats, spelling, and data types**.

Before analysis or machine learning, the data must be:

- **Consistent**  
- **Comparable**  
- **Numerically meaningful**  
- **Clean and complete**

If this is not done, models may produce wrong or biased results.

---

#  2. Unit Conversion (Example: MPG → L/100km)

Different countries measure fuel efficiency differently:

- **Miles per gallon (MPG)** → used in the USA  
- **Liters per 100 km (L/100km)** → used in Europe & many countries  

These units measure the *same thing* but in opposite directions:

- Higher MPG = better fuel economy  
- Lower L/100km = better fuel economy  

###  Formula
To convert:

$$
L/100\text{km} = \frac{235}{\text{MPG}}
$$


### Python Code 
```python
df['city_L/100km'] = 235 / df['city-mpg']
```
This makes all fuel efficiency values comparable for global analysis.
---
## 3. Understanding & Fixing Data Types

A dataset may contain:

- Numbers stored as **strings**
- Dates stored as **text**
- Missing values represented as `"?"` or `"NaN"`

Correct data types are crucial because:

- You cannot compute **mean, median, or correlations** on strings.
- **Machine learning models require numeric input**.
- Wrong data types lead to errors and inaccurate analysis.

---

### ✔ Example: Converting a single column to numeric

```python
df['price'] = df['price'].astype(float)
# Converting multiple columns at once
cols = ['price', 'horsepower', 'length']
df[cols] = df[cols].astype(float)
```
---
## 4. Handling Missing Values

Missing values can occur due to:

- Faulty sensors  
- Incomplete forms  
- Scraped web data  
- Human errors  

Handling missing data is essential because most statistical operations and machine-learning models **cannot work with NaN values**.

---

### ### 4.1 Replace Missing Values with Mode (Most Frequent Value)

**Used for:**  
- Categorical data (e.g., `fuel-type`, `body-style`)

** Why this works**  
The most frequently occurring value is usually the safest and most realistic replacement for missing categories.

**Code Example**

```python
MostFrequentEntry = df['attribute_name'].value_counts().idxmax()
df['attribute_name'].replace(np.nan, MostFrequentEntry, inplace=True)
```
---
### 4.2 Replace Missing Values with Mean

Used for:

Numerical data (e.g., price, engine-size)

 Why this works
The mean represents the center of the distribution and provides a balanced replacement without biasing the data too much.

 Code Example

AverageValue = df['attribute_name'].astype(float).mean()
df['attribute_name'].replace(np.nan, AverageValue, inplace=True)
