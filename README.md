# 🏥 Hospital Data Analysis | SQL, Python & Power BI

![Project Type](https://img.shields.io/badge/Project-Data%20Analytics-blue)
![Python](https://img.shields.io/badge/Python-Data%20Analysis-yellow)
![SQL](https://img.shields.io/badge/SQL-Data%20Querying-blue)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview

The **Hospital Data Analysis** project focuses on exploring hospital and patient data to understand patient admission patterns, hospital performance, healthcare service utilization, and key operational metrics.

The project demonstrates an end-to-end data analytics workflow, from understanding and cleaning raw data to performing exploratory data analysis, writing SQL queries, and building an interactive Power BI dashboard.

The goal is to transform raw healthcare data into meaningful insights that can help stakeholders understand patient trends, monitor important performance indicators, and make data-driven operational decisions.

**Tools Used:** SQL, Python, and Power BI.

---

## 🎯 Project Objectives

The primary objectives of this project are:

* Analyze hospital and patient data to understand overall healthcare activity.
* Clean and prepare the dataset for accurate analysis.
* Identify missing values, duplicate records, and data quality issues.
* Perform exploratory data analysis using Python.
* Use SQL queries to extract meaningful information from the dataset.
* Create key performance indicators (KPIs) to summarize hospital activity.
* Develop an interactive Power BI dashboard for data visualization.
* Identify patterns and trends in patient-related metrics.
* Present findings in a clear and understandable format.
* Demonstrate practical data analytics skills through a real-world-style project.

---

## 🛠️ Tools & Technologies

| Tool             | Purpose                                                    |
| ---------------- | ---------------------------------------------------------- |
| Python           | Data cleaning, manipulation, and exploratory data analysis |
| Pandas           | Data manipulation and preprocessing                        |
| NumPy            | Numerical operations and data analysis                     |
| SQL              | Data querying, filtering, aggregation, and analysis        |
| Power BI         | Interactive dashboard development                          |
| Power Query      | Data transformation and preparation, if used               |
| DAX              | KPI calculations and analytical measures, if used          |
| Jupyter Notebook | Writing and executing Python analysis, if used             |
| GitHub           | Project documentation and version control                  |

---

## 📂 Project Structure

The repository is organized to make the analysis easy to navigate.

```text
hospital-data-analysis/
│
├── README.md
│
├── dataset/
│   └── hospital_data.csv
│
├── python/
│   └── hospital_analysis.ipynb
│
├── sql/
│   └── hospital_analysis.sql
│
├── powerbi/
│   └── hospital_dashboard.pbix
│
└── screenshots/
    └── hospital_dashboard.png
```

**Note:** This is a suggested folder structure. Replace the example filenames with the actual files included in your repository.

---

## 📊 Dataset Description

The project uses a hospital-related dataset containing patient and healthcare information.

The dataset is examined to understand its structure, identify data quality issues, and prepare the information for further analysis.

### Dataset characteristics

* Contains patient-related records.
* Includes hospital or healthcare-related attributes.
* Supports analysis of patient counts and selected operational metrics.
* Requires data validation and preprocessing before analysis.

### Data quality checks

The following checks can be performed during data preparation:

* Identify missing or null values.
* Check for duplicate records.
* Validate column data types.
* Examine inconsistent or invalid values.
* Review categorical variables.
* Validate numerical fields.
* Confirm that calculated metrics use appropriate denominators.
* Ensure that the data loaded into Power BI matches the source data.

**Dataset privacy:** Do not upload confidential patient information or personally identifiable medical records. Use a publicly available dataset or an appropriately anonymized dataset, and follow its license and sharing restrictions.

---

## 🧹 Data Cleaning & Preprocessing

Data cleaning is an important step because incorrect or incomplete records can affect the reliability of the analysis.

The workflow may include the following steps, depending on the actual dataset.

### 1. Data inspection

* Load the dataset into Python.
* Examine the number of rows and columns.
* Review column names and data types.
* Inspect sample records.
* Generate descriptive statistics.

### 2. Missing-value analysis

* Identify columns containing missing values.
* Calculate the number and percentage of missing values.
* Investigate possible reasons for missing data.
* Decide whether to retain, replace, or exclude missing values based on the analysis requirements.

### 3. Duplicate-record analysis

* Check for duplicate rows.
* Investigate whether duplicate records represent repeated observations or data-entry issues.
* Remove confirmed duplicates when appropriate.

### 4. Data type validation

* Convert columns to suitable data types.
* Validate numeric and categorical fields.
* Ensure that numerical calculations can be performed correctly.

### 5. Data consistency

* Standardize inconsistent category labels where necessary.
* Check for invalid or unexpected values.
* Validate key fields used in calculations.
* Confirm that transformations preserve the intended meaning of the data.

### 6. Final validation

* Compare row counts before and after cleaning.
* Review missing values and duplicates again.
* Validate the cleaned dataset before importing it into Power BI.

**Expected outcome:** A consistent dataset suitable for analysis and visualization.

---

## 🐍 Python Data Analysis

Python is used to inspect, clean, and explore the dataset.

The analysis can be performed with Pandas and NumPy in a Jupyter Notebook.

### Key activities

* Import the dataset.
* Inspect the dataset structure.
* Examine missing values and duplicates.
* Explore numerical and categorical columns.
* Calculate descriptive statistics.
* Identify patterns in the available data.
* Prepare cleaned data for further analysis.

### Example Python workflow

```python
import pandas as pd
import numpy as np

# Load the dataset
df = pd.read_csv("dataset/hospital_data.csv")

# Display the first five records
print(df.head())

# Check dataset dimensions
print("Dataset shape:", df.shape)

# Review column names
print(df.columns.tolist())

# Check data types and non-null counts
df.info()

# Calculate missing values
print(df.isnull().sum())

# Check duplicate rows
print("Duplicate rows:", df.duplicated().sum())

# Generate descriptive statistics
print(df.describe(include="all"))
```

### Example cleaning operations

```python
# Create a working copy
clean_df = df.copy()

# Remove fully duplicated rows when appropriate
clean_df = clean_df.drop_duplicates()

# Review missing values after cleaning
print(clean_df.isnull().sum())

# Confirm the final dimensions
print("Cleaned dataset shape:", clean_df.shape)
```

These snippets are examples. Column-specific cleaning, missing-value treatment, and duplicate handling should be based on the actual dataset rather than applied blindly.

---

## 🗄️ SQL Data Analysis

SQL is used to query and analyze structured data.

The purpose of the SQL analysis is to extract relevant information, calculate summary metrics, and answer questions about the dataset.

### Analytical areas

* Overall record counts.
* Patient-related metrics.
* Hospital-related metrics.
* Average values for selected numerical fields.
* Distribution across available categories.
* Identification of unusual or incomplete records.
* Grouped summaries for reporting.

### Example SQL queries

The following examples assume that a table named `hospital_data` exists and that its columns match the example names. Adjust the table and column names to your actual schema.

#### 1. View sample records

```sql
SELECT *
FROM hospital_data
LIMIT 10;
```

#### 2. Count total records

```sql
SELECT COUNT(*) AS total_records
FROM hospital_data;
```

#### 3. Count distinct hospitals

```sql
SELECT COUNT(DISTINCT Hospital_ID) AS total_hospitals
FROM hospital_data;
```

#### 4. Analyze records by category

```sql
SELECT
    Category,
    COUNT(*) AS total_records
FROM hospital_data
GROUP BY Category
ORDER BY total_records DESC;
```

#### 5. Calculate an average numerical value

```sql
SELECT
    AVG(Deposit) AS average_deposit
FROM hospital_data;
```

#### 6. Find missing values in a selected field

```sql
SELECT
    COUNT(*) AS missing_deposit_records
FROM hospital_data
WHERE Deposit IS NULL;
```

#### 7. Identify repeated identifiers

```sql
SELECT
    Hospital_ID,
    COUNT(*) AS record_count
FROM hospital_data
GROUP BY Hospital_ID
HAVING COUNT(*) > 1
ORDER BY record_count DESC;
```

**Important:** Repeated hospital identifiers do not necessarily indicate duplicate records. A hospital can legitimately appear in many patient records. Use the actual dataset schema and business rules when interpreting these queries.

---

## 📈 Power BI Dashboard

Power BI is used to present important metrics and findings in an interactive dashboard.

The dashboard is intended to help users explore the available data and understand key measures without manually reviewing individual records.

### Key Performance Indicators (KPIs)

The dashboard may include the following metrics, depending on the available columns and implemented calculations.

| KPI                  | Description                                                                                 |
| -------------------- | ------------------------------------------------------------------------------------------- |
| Total Patients       | Number of patients or patient records, based on the dataset's identifier and counting rules |
| Total Hospitals      | Number of distinct hospitals represented in the data                                        |
| Average Deposit      | Average of valid deposit values                                                             |
| Average Visitors     | Average visitor count, if the dataset contains this field                                   |
| Patient Distribution | Distribution across available patient-related categories                                    |
| Category Analysis    | Comparison of records across selected categories                                            |

**KPI validation:** Define each metric precisely. For example, the number of rows is not necessarily the number of unique patients, and the average deposit should exclude or handle missing values appropriately.

### Dashboard features

* KPI cards for important metrics.
* Charts for category-level comparisons.
* Filters and slicers for interactive exploration.
* Clear titles and labels.
* Consistent number formatting.
* Visual comparisons of relevant measures.
* A layout designed to make key findings easy to understand.

### Dashboard screenshots

Add screenshots of your actual dashboard to the `screenshots/` folder.

Once uploaded, you can display a screenshot in this section using:

```markdown
![Hospital Data Analysis Dashboard](screenshots/hospital_dashboard.png)
```

This allows recruiters to preview your work directly from the GitHub README.

---

## 🔍 Business Questions

The project can be used to investigate questions such as:

1. How many patient records are available in the dataset?
2. How many distinct hospitals are represented?
3. What is the average deposit value?
4. How are records distributed across available categories?
5. Which categories contain the largest number of records?
6. Are there missing values that could affect the analysis?
7. Are duplicate records present?
8. How do key metrics change when dashboard filters are applied?
9. Which data quality issues require additional investigation?
10. What useful patterns can be identified from the available fields?

The questions should be answered using the actual dataset and the results of the SQL queries, Python analysis, and Power BI dashboard.

---

## 💡 Key Insights & Findings

This section should contain findings supported by the actual analysis.

Examples of findings you could document after validating your results include:

* The total number of patient records and distinct hospitals.
* Categories with the highest and lowest record counts.
* The average deposit value and its distribution.
* Fields with the greatest number of missing values.
* Duplicate-record patterns and how they were handled.
* Differences in key metrics across selected categories.
* Data quality issues that may influence interpretation.

Avoid adding numerical claims or conclusions that have not been verified against the dataset.

### Recommendations

Based on the findings, potential recommendations may include:

* Improve data completeness for fields with substantial missing values.
* Establish consistent data validation rules.
* Monitor key metrics using a regularly updated dashboard.
* Investigate unusual values before using them in operational decisions.
* Document KPI definitions to ensure consistent reporting.

Recommendations should be refined to match the actual findings.

---

## 🔄 End-to-End Project Workflow

The project follows a structured data analytics workflow.

**Step 1 — Data Collection**

Obtain the dataset from an appropriate source and review its structure.

**Step 2 — Data Understanding**

Identify the available columns, data types, measures, and possible analysis opportunities.

**Step 3 — Data Cleaning**

Inspect missing values, duplicate records, invalid values, and data consistency.

**Step 4 — Python Analysis**

Use Pandas and NumPy to explore the data and prepare it for analysis.

**Step 5 — SQL Analysis**

Write queries to filter, aggregate, group, and summarize the data.

**Step 6 — Power BI Development**

Build a dashboard with clearly defined KPIs, appropriate charts, and useful filters.

**Step 7 — Validation**

Check that the results shown in the dashboard agree with the underlying data and calculations.

**Step 8 — Documentation**

Document the workflow, analytical questions, validated findings, and project files in GitHub.

---

## 🎓 Skills Demonstrated

This project demonstrates practical application of the following skills:

### Technical skills

* Python data manipulation using Pandas.
* Numerical analysis using NumPy.
* SQL querying and aggregation.
* Data cleaning and preprocessing.
* Exploratory data analysis.
* KPI definition and calculation.
* Power BI dashboard development.
* Data visualization.
* Data quality validation.

### Analytical skills

* Breaking business questions into measurable analytical tasks.
* Interpreting summary statistics.
* Identifying data quality issues.
* Comparing metrics across categories.
* Presenting findings in a structured format.
* Communicating analytical results clearly.

---

## 🚀 Future Improvements

Possible future improvements include:

* Add more advanced SQL queries using CTEs and window functions.
* Develop additional measures in DAX.
* Improve dashboard navigation and filtering.
* Add further validation checks.
* Automate data preparation where appropriate.
* Include a data dictionary describing the columns.
* Add more detailed, evidence-based findings.
* Document reproducible steps for running the analysis.

These are potential enhancements rather than features that are necessarily implemented in the current version.

---

## 💻 How to Explore This Project

1. Clone or download the repository.
2. Review the README to understand the project objectives.
3. Open the Python notebook in Jupyter Notebook or a compatible environment.
4. Run the SQL scripts using a compatible database after configuring the correct schema.
5. Open the Power BI report in Power BI Desktop if the `.pbix` file is provided.
6. Review the dashboard screenshots and documented findings.

### Repository

GitHub: https://github.com/azhan-12/hospital-data-analysis

---

## 👨‍💻 About the Author

**Mohammed Azhan**
Aspiring Data Analyst

Interested in transforming raw data into useful insights through data cleaning, SQL analysis, Python, and interactive Power BI dashboards.

### Technical Skills

* Microsoft Excel
* SQL
* Python
* Power BI
* Data Cleaning
* Exploratory Data Analysis
* Data Visualization

### Connect With Me

* GitHub: https://github.com/azhan-12
* LinkedIn: https://www.linkedin.com/in/mohammed-azhan-82078a348/

---

⭐ If you find this project useful, consider giving the repository a star.

**Thank you for visiting my Hospital Data Analysis project!**
