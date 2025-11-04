# 📊 Data Analysis with Python – Cheat Sheet (Importing Datasets)

| Step | Task | Description (Why it's done) | Code Example |
|------|------|-----------------------------|--------------|
| **1** | Import Libraries | Required to work with data and handle missing values | ```python\n import pandas as pd\nimport numpy as np``` |
| **2** | Load CSV File (Local) | Load dataset from your computer | ```python\n df = pd.read_csv("file_path.csv")``` |
| **3** | Load CSV File (URL) | Load dataset directly from the web (works outside JupyterLite) | ```python\ndf = pd.read_csv("https://example.com/data.csv")``` |
| **4** | Load File Without Header | When the file has no column names | ```python\ndf = pd.read_csv("file.csv", header=None)``` |
| **5** | View Top Rows | Helps inspect structure and values | ```python\ndf.head()``` |
| **6** | View Bottom Rows | Check end of dataset for missing/irregular values | ```python\ndf.tail(10)``` |
| **7** | Check Shape | Returns number of rows and columns | ```python\ndf.shape``` |
| **8** | Display Column Names | Useful when headers are missing or incorrect | ```python\ndf.columns``` |
| **9** | Assign Column Headers | Manually add headers if dataset doesn’t have any | ```python\nheaders = ["col1", "col2", "col3", ...]\ndf.columns = headers``` |
| **10** | Replace "?" with NaN | Converts placeholder missing values to standard NaN | ```python\ndf.replace("?", np.nan, inplace=True)``` |
| **11** | Check Data Types | Identifies int, float, or object (string) types | ```python\ndf.dtypes``` |
| **12** | Check Dataset Summary | Shows non-null counts and types (useful for NaNs) | ```python\ndf.info()``` |
| **13** | Find Missing Values | Count how many NaNs exist in each column | ```python\ndf.isnull().sum()``` |
| **14** | Drop Missing Target Values | Removes rows where key values (e.g., price) are missing | ```python\ndf.dropna(subset=["price"], inplace=True)``` |
| **15** | Reset Index After Drop | Avoids duplicate index numbers | ```python\ndf.reset_index(drop=True, inplace=True)``` |
| **16** | Statistical Summary (Numeric) | Provides mean, median, std, etc. for numerical data | ```python\ndf.describe()``` |
| **17** | Summary for All Columns | Includes object-type columns as well | ```python\ndf.describe(include="all")``` |
| **18** | Save Cleaned File | Export cleaned dataset to a CSV file | ```python\ndf.to_csv("cleaned_dataset.csv", index=False)``` |

---

### ✅ **💡 Notes to Remember**
| Behaviour | Explanation |
|-----------|-------------|
| `header=None` | Use this when the CSV file doesn’t contain column names. |
| `"?" → NaN` | Many real-world datasets use "?" or "-" for missing values; convert them to `NaN` for cleaning. |
| `.info()` vs `.describe()` | `.info()` = structure + missing values; `.describe()` = statistical summary. |
| JupyterLite | Can’t load directly from a URL — download first using pyfetch. |
| `.to_csv()` | Saves your cleaned DataFrame for future reuse so you don’t repeat cleaning steps. |

---

Would you like me to:
✅ Add data cleaning cheat sheet too?  
✅ Convert this to `.md` or `.pdf` file?  
✅ Add visuals or sample dataset output?

I’m ready. Just say the word.
