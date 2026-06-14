# Data-Cleaning-Preparation-Project-1
# Data Cleaning Project

## Overview

This notebook performs essential data cleaning and preprocessing steps on the dataset **"Dataset for Data Analytics.xlsx"**. The goal is to improve data quality, remove inconsistencies, and prepare the dataset for further analysis and modeling.

## Objectives

* Load and inspect the dataset.
* Identify missing values.
* Detect and remove duplicate records.
* Handle missing values in categorical features.
* Generate descriptive statistics for understanding the dataset.

## Dataset

**File:** `Dataset for Data Analytics.xlsx`

The dataset contains transactional data used for analytics and business intelligence purposes.

## Data Cleaning Steps

### 1. Import Required Libraries

The notebook begins by importing the Pandas library, which is used for data manipulation and analysis.

```python
import pandas as pd
```

### 2. Load the Dataset

The Excel dataset is loaded into a Pandas DataFrame.

```python
df = pd.read_excel('Dataset for Data Analytics.xlsx')
```

### 3. Initial Data Inspection

Basic inspection is performed to understand the dataset structure and preview the records.

```python
df.head()
df.shape
```

### 4. Missing Value Analysis

The notebook checks each column for missing values.

```python
df.isnull().sum()
```

This helps identify columns that require data imputation or correction.

### 5. Duplicate Record Detection

Duplicate entries are identified to prevent biased analysis.

```python
df.duplicated().sum()
```

### 6. Remove Duplicate Records

All duplicate rows are removed from the dataset.

```python
df.drop_duplicates(inplace=True)
```

### 7. Analyze CouponCode Column

The data type and unique values of the `CouponCode` column are examined.

```python
df['CouponCode'].dtype
df['CouponCode'].unique()
```

### 8. Handle Missing Coupon Codes

Missing values in the `CouponCode` column are replaced with a meaningful placeholder value.

```python
df['CouponCode'] = df['CouponCode'].fillna('NO_COUPON')
```

This ensures that missing coupon information is explicitly represented rather than left as null.

### 9. Generate Descriptive Statistics

Summary statistics are generated to understand the distribution of numerical features.

```python
df.describe()
```

## Results

After cleaning:

* Duplicate records are removed.
* Missing values in the `CouponCode` column are handled.
* The dataset becomes more consistent and suitable for exploratory data analysis (EDA), visualization, and machine learning tasks.

## Tools Used

* Python
* Pandas
* Jupyter Notebook

## Conclusion

The data cleaning process improves the overall quality and reliability of the dataset. Proper handling of duplicates and missing values ensures more accurate analytical insights and better performance in downstream data science tasks.
