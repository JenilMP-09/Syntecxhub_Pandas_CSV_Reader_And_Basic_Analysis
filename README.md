# Pandas CSV Reader and Basic Analysis

## Introduction

This project demonstrates fundamental data analysis operations using the **Pandas** library in Python. The notebook reads a student performance dataset from a CSV file and performs common data exploration, statistical analysis, filtering, slicing, and data export operations.

The project is ideal for beginners learning data analysis with Pandas and understanding how to work with real-world tabular datasets.

---

## Table of Contents

* [Introduction](#introduction)
* [Project Structure](#project-structure)
* [Dataset Information](#dataset-information)
* [Features](#features)
* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)
* [Analysis Performed](#analysis-performed)
* [Examples](#examples)
* [Output](#output)
* [Troubleshooting](#troubleshooting)
* [Future Improvements](#future-improvements)
* [Contributors](#contributors)
* [License](#license)

---

## Project Structure

```text
├── Syntecxhub_Pandas_CSV_Reader_And_Basic_Analysis.ipynb
├── student-mat.csv
└── README.md
```

---

## Dataset Information

The project uses the **Student Performance Dataset**, containing information about student demographics, family background, study habits, and academic performance.

### Dataset Overview

* Rows: 395 students
* Columns: 33 attributes

### Sample Features

| Column    | Description                   |
| --------- | ----------------------------- |
| school    | Student's school              |
| sex       | Gender                        |
| age       | Age                           |
| Medu      | Mother's education level      |
| Fedu      | Father's education level      |
| studytime | Weekly study time             |
| failures  | Number of past class failures |
| absences  | Number of absences            |
| G1        | First period grade            |
| G2        | Second period grade           |
| G3        | Final grade                   |

---

## Features

### 1. Data Loading

* Read CSV files using Pandas
* Create DataFrames for analysis

### 2. Data Inspection

* Display first records using `head()`
* Display last records using `tail()`
* View dataset structure with `info()`
* Check dimensions using `shape`
* Review data types using `dtypes`

### 3. Statistical Analysis

* Generate descriptive statistics
* Calculate means
* Calculate medians
* Count occurrences of values

### 4. Data Selection & Filtering

* Row selection using:

  * `iloc`
  * `loc`
* Conditional filtering
* Column selection

### 5. Export Data

* Save filtered results to CSV files

---

## Requirements

### Python Version

```text
Python 3.8+
```

### Libraries

```text
pandas
```

Install using:

```bash
pip install pandas
```

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/syntecxhub-pandas-analysis.git
cd syntecxhub-pandas-analysis
```

### Install Dependencies

```bash
pip install pandas
```

---

## Usage

### Open the Notebook

```bash
jupyter notebook
```

Open:

```text
Syntecxhub_Pandas_CSV_Reader_And_Basic_Analysis.ipynb
```

### Load Dataset

```python
import pandas as pd

df = pd.read_csv("student-mat.csv", sep=";")
```

---

## Analysis Performed

### Data Inspection

```python
df.head()
df.tail(10)
df.info()
df.shape
df.dtypes
```

### Descriptive Statistics

```python
df.describe()
```

### Mean Calculation

```python
df['Medu'].groupby(df['Medu']).mean()
```

### Median Calculation

```python
df['Medu'].groupby(df['Medu']).median()
```

### Count Final Grades

```python
df['G3'].groupby(df['G3']).count()
```

### Row Selection

```python
df.iloc[:5]
df.loc[:10]
df.iloc[2:10:1]
```

### Filtering Students

Filter female students with a final grade greater than or equal to 10:

```python
df_filtered = df[(df['sex'] == 'F') & (df['G3'] >= 10)]
```

### Grade Distribution

```python
df[(df['sex'] == 'F') & (df['G3'] >= 10)]['G3'].value_counts()
```

### Save Results

```python
df_filtered.to_csv('saved_df.csv', index=False)
```

---

## Examples

### View First Five Records

```python
df.head()
```

### Dataset Shape

```python
print(df.shape)
```

Output:

```text
(395, 33)
```

### Filter High-Performing Female Students

```python
female_students = df[
    (df['sex'] == 'F') &
    (df['G3'] >= 10)
]
```

---

## Output

The project produces:

* Dataset inspection reports
* Statistical summaries
* Filtered student records
* Exported CSV files

Example output file:

```text
saved_df.csv
```

---

## Troubleshooting

### File Not Found Error

Ensure the dataset exists in the project directory:

```text
student-mat.csv
```

### Pandas Not Installed

Install Pandas:

```bash
pip install pandas
```

### Incorrect CSV Delimiter

The dataset uses a semicolon (`;`) separator:

```python
pd.read_csv("student-mat.csv", sep=";")
```

---

## Future Improvements

* Data visualization using Matplotlib
* Statistical correlation analysis
* Missing value handling
* Interactive dashboards
* Export results to Excel
* Automated reporting

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Author

**Jenil M. Panchal**   
(Data Science Enthusiast)
