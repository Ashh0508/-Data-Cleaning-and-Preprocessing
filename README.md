# Data Cleaning and Preprocessing – Customer Personality Analysis Dataset

## Objective

Perform data cleaning and preprocessing on the Customer Personality Analysis dataset to improve data quality and prepare it for analysis.

## Dataset

* Dataset Name: marketing_campaign.csv from Kaggle
* Records: 2240 rows
* Features: 29 columns

## Tasks Performed

### 1. Missing Value Handling

* Identified missing values using `isnull().sum()`.
* Filled missing values in the `Income` column using the median value.

### 2. Duplicate Removal

* Checked for duplicate records using `duplicated().sum()`.
* Removed duplicates using `drop_duplicates()`.

### 3. Text Standardization

* Standardized categorical values using `str.strip()` and `str.title()`.
* Ensured consistent formatting in columns such as Education and Marital_Status.

### 4. Date Conversion

* Converted `Dt_Customer` to datetime format using `pd.to_datetime()`.
* Standardized the date format.

### 5. Column Name Cleaning

* Renamed column headers to lowercase.
* Replaced spaces with underscores where necessary.

### 6. Data Type Validation

* Verified data types using `dtypes`.
* Converted date columns to datetime format and ensured numeric columns had appropriate data types.

## Output

* Generated a cleaned dataset named `marketing_campaign_cleaned.csv`.
  
| Metric                | Before Cleaning | After Cleaning |
| --------------------- | --------------- | -------------- |
| Rows                  | 2240            | 2216           |
| Columns               | 29              | 29             |
| Missing Income Values | 24              | 0              |
| Duplicate Rows        | 2               | 0              |

## Challenges Faced

### Dataset Loading Issue
During the preprocessing stage, the dataset was initially loaded incorrectly into Pandas. Instead of creating separate columns, the entire header row was imported as a single column. After investigating the issue, it was found that the dataset was tab-separated rather than comma-separated.

To resolve this, the dataset was loaded using:

```python
df = pd.read_csv("marketing_campaign.csv", sep="\t")
```

## Tools Used

* Python
* Pandas
* Google Colab

## Files Included

* marketing_campaign.csv
* marketing_campaign_cleaned.csv
* data_cleaning.ipynb
* README.md
