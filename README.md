# customer_behavior_analysis
This is a data analytics project showing customer behavior analysis using python, sql and power BI.
## 📌 Project Overview

This project demonstrates an **end-to-end data analytics workflow**, transforming a raw dataset into meaningful business insights through **Python, Exploratory Data Analysis (EDA), data cleaning, PostgreSQL, Power BI, and data storytelling**.

The project follows a structured analytics pipeline:

**Raw Dataset → Python → Data Cleaning & EDA → PostgreSQL → SQL Analysis → Power BI Dashboard → Analytical Report → Gamma Presentation**

The objective is to demonstrate practical skills in **data preparation, exploratory analysis, SQL querying, visualization, dashboard development, reporting, and presentation of analytical findings**.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Load and inspect a dataset using Python.
* Understand the structure and characteristics of the data.
* Perform Exploratory Data Analysis (EDA).
* Identify and handle missing, duplicate, inconsistent, and incorrect data.
* Prepare a clean dataset for further analysis.
* Import the cleaned data into PostgreSQL.
* Perform analytical SQL queries to extract meaningful insights.
* Develop an interactive Power BI dashboard.
* Create a professional analytical report.
* Prepare a presentation using Gamma.
* Communicate data-driven findings clearly to stakeholders.

---

## 🛠️ Tools & Technologies

| Tool / Technology    | Purpose                                        |
| -------------------- | ---------------------------------------------- |
| **Python**           | Data loading, preprocessing, cleaning, and EDA |
| **Pandas**           | Data manipulation and analysis                 |
| **NumPy**            | Numerical analysis                             |
| **Matplotlib**       | Data visualization                             |
| **Seaborn**          | Statistical visualization                      |
| **Jupyter Notebook** | Interactive analysis and documentation         |
| **PostgreSQL**       | Database storage and SQL analysis              |
| **SQL**              | Data querying and analytical analysis          |
| **Power BI**         | Interactive dashboard and visualization        |
| **Gamma**            | Professional presentation creation             |
| **Git / GitHub**     | Version control and project documentation      |

---

## 🔄 Project Workflow

The project follows the following data analytics lifecycle:

```text
                    ┌─────────────────┐
                    │   Raw Dataset   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Python / Pandas │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Data Exploration│
                    │      & EDA      │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │  Data Cleaning  │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   PostgreSQL    │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   SQL Analysis  │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Power BI      │
                    │    Dashboard    │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Analytical      │
                    │     Report      │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Gamma           │
                    │ Presentation    │
                    └─────────────────┘
```

---

# 1. 📥 Data Loading

The project begins by loading the raw dataset into Python using **Pandas**.

### Key activities

* Import the dataset.
* Examine the number of rows and columns.
* Inspect column names and data types.
* Preview sample records.
* Identify categorical and numerical variables.
* Check the overall structure of the dataset.

Example:

```python
import pandas as pd

df = pd.read_csv("data/dataset.csv")

print(df.head())
print(df.shape)
print(df.info())
print(df.describe())
```

---

# 2. 🔍 Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the dataset before making analytical conclusions.

### EDA includes:

* Descriptive statistics
* Distribution analysis
* Frequency analysis
* Correlation analysis
* Outlier identification
* Trend analysis
* Category comparisons
* Relationship analysis between variables

Example:

```python
df.describe()
```

Categorical analysis:

```python
df["category"].value_counts()
```

Correlation analysis:

```python
df.corr(numeric_only=True)
```

Visualizations are created using **Matplotlib** and **Seaborn** to identify patterns and relationships within the data.

---

# 3. 🧹 Data Cleaning

Before performing advanced analysis, the dataset is cleaned and standardized.

### Data cleaning activities include:

* Handling missing values
* Removing duplicate records
* Correcting inconsistent values
* Converting data types
* Standardizing categorical values
* Formatting date columns
* Identifying and handling outliers
* Renaming columns where necessary
* Validating numerical values
* Removing irrelevant records or columns

Example:

```python
# Check missing values
df.isnull().sum()

# Remove duplicates
df = df.drop_duplicates()

# Convert date column
df["date"] = pd.to_datetime(df["date"])

# Check data types
df.dtypes
```

The final cleaned dataset is then prepared for database analysis and visualization.

---

# 4. 🗄️ PostgreSQL Database

After cleaning, the dataset is loaded into **PostgreSQL** for structured storage and SQL-based analysis.

### Database activities include:

* Creating the database
* Creating tables
* Defining appropriate data types
* Importing the cleaned dataset
* Validating the imported records
* Performing SQL analysis

Example table structure:

```sql
CREATE TABLE analytics_data (
    id SERIAL PRIMARY KEY,
    date DATE,
    category VARCHAR(100),
    region VARCHAR(100),
    quantity INTEGER,
    revenue NUMERIC(12,2)
);
```

---

# 5. 🧮 SQL Analysis

PostgreSQL is used to answer analytical questions and generate insights from the cleaned dataset.

### SQL analysis may include:

* Filtering records
* Aggregation
* Grouping
* Sorting
* Calculating totals and averages
* Ranking
* Time-based analysis
* Category analysis
* Regional analysis
* Percentage calculations
* Subqueries
* Common Table Expressions (CTEs)
* Window functions
* Business KPI calculations

Example:

```sql
SELECT
    category,
    SUM(revenue) AS total_revenue
FROM analytics_data
GROUP BY category
ORDER BY total_revenue DESC;
```

Example of a monthly analysis:

```sql
SELECT
    DATE_TRUNC('month', date) AS month,
    SUM(revenue) AS monthly_revenue
FROM analytics_data
GROUP BY month
ORDER BY month;
```

The SQL analysis provides the foundation for the business insights presented in the dashboard and final report.

---

# 6. 📊 Power BI Dashboard

The cleaned and analyzed data is used to create an interactive **Power BI dashboard**.

### Dashboard components may include:

* KPI cards
* Revenue / sales metrics
* Category performance
* Regional performance
* Time-series trends
* Interactive filters
* Slicers
* Bar charts
* Line charts
* Pie / donut charts
* Tables and matrices
* Drill-down analysis

### Example KPIs

Depending on the dataset, the dashboard can present metrics such as:

* **Total Revenue**
* **Total Sales**
* **Total Customers**
* **Total Orders**
* **Average Order Value**
* **Growth Rate**
* **Top Performing Category**
* **Top Performing Region**

The dashboard is designed to allow users to interactively explore the data and identify important trends and patterns.

---

# 7. 📈 Analytical Report

A professional analytical report is created to document the complete analysis process and findings.

### Report structure

#### 1. Executive Summary

A concise overview of the project and its key findings.

#### 2. Introduction

Background, purpose, and objectives of the analysis.

#### 3. Dataset Description

Description of the dataset, variables, size, and data sources.

#### 4. Data Preparation

Explanation of data loading, cleaning, preprocessing, and validation.

#### 5. Exploratory Data Analysis

Key patterns, distributions, trends, and relationships identified during EDA.

#### 6. SQL Analysis

Description of the analytical questions and SQL queries used to answer them.

#### 7. Power BI Dashboard

Explanation of dashboard components, KPIs, filters, and visualizations.

#### 8. Key Findings

Important insights discovered through the analysis.

#### 9. Recommendations

Data-driven recommendations based on the findings.

#### 10. Conclusion

Summary of the overall analysis and its implications.

---

# 8. 🎤 Gamma Presentation

A professional presentation is created using **Gamma** to communicate the project results to a non-technical or business audience.

The presentation summarizes:

* Project background
* Business questions
* Dataset overview
* Data preparation
* EDA findings
* SQL analysis
* Power BI dashboard
* Key insights
* Recommendations
* Conclusion

The presentation focuses on **data storytelling**, ensuring that technical analysis is translated into clear and understandable business insights.

---

# 📁 Project Structure

```text
data-analytics-project/
│
├── data/
│   ├── raw/
│   │   └── dataset.csv
│   │
│   └── cleaned/
│       └── cleaned_dataset.csv
│
├── notebooks/
│   └── data_analysis.ipynb
│
├── sql/
│   ├── database_schema.sql
│   ├── data_loading.sql
│   └── analysis_queries.sql
│
├── powerbi/
│   └── analytics_dashboard.pbix
│
├── reports/
│   └── analytical_report.pdf
│
├── presentation/
│   └── project_presentation.pdf
│
├── images/
│   ├── eda/
│   └── dashboard/
│
├── requirements.txt
│
└── README.md
```

---

# 🧪 Python Environment

The Python analysis requires the following packages:

```text
pandas
numpy
matplotlib
seaborn
jupyter
```

Install the required packages using:

```bash
pip install -r requirements.txt
```

---

# 🔑 Key Analytical Questions

The project is designed around business questions that can be answered using the available data.

Examples include:

1. What are the overall performance metrics?
2. Which categories generate the highest results?
3. Which regions or locations perform best?
4. How does performance change over time?
5. What are the major trends in the dataset?
6. Which products or categories contribute most to overall performance?
7. Are there significant differences between groups?
8. What factors are associated with higher performance?
9. What anomalies or unusual patterns exist?
10. What insights can support better business decisions?

The specific questions are adapted according to the characteristics of the selected dataset.

---

# 💡 Key Insights

The project converts raw data into actionable insights through multiple analytical stages.

The final insights are derived from:

**Python EDA + Data Cleaning + PostgreSQL SQL Analysis + Power BI Visualization**

Examples of potential insights include:

* Identification of high-performing categories.
* Identification of underperforming segments.
* Detection of significant trends over time.
* Identification of regional differences.
* Discovery of unusual or anomalous records.
* Identification of important performance indicators.
* Understanding relationships between key variables.

---

# 📌 Deliverables

The project produces the following major deliverables:

| Deliverable             | Description                                    |
| ----------------------- | ---------------------------------------------- |
| **Python Notebook**     | Data loading, cleaning, EDA, and visualization |
| **Clean Dataset**       | Prepared dataset for analysis                  |
| **PostgreSQL Database** | Structured analytical database                 |
| **SQL Queries**         | Analytical queries and KPI calculations        |
| **Power BI Dashboard**  | Interactive data visualization                 |
| **Analytical Report**   | Detailed documentation of findings             |
| **Gamma Presentation**  | Executive presentation of project results      |

---

# 🚀 Skills Demonstrated

This project demonstrates practical skills in:

### Data Analytics

* Data exploration
* Data cleaning
* Data preprocessing
* Statistical analysis
* Exploratory Data Analysis

### Python

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

### SQL & Databases

* PostgreSQL
* Database design
* SQL querying
* Aggregations
* CTEs
* Subqueries
* Window functions
* KPI calculations

### Business Intelligence

* Power BI
* Dashboard development
* Data visualization
* Interactive reporting
* KPI design

### Data Communication

* Analytical reporting
* Data storytelling
* Business insights
* Presentation development
* Executive communication

---

# 🔄 End-to-End Analytics Pipeline

The complete project demonstrates how a data analyst can transform raw data into actionable information:

```text
Raw Data
   ↓
Data Loading
   ↓
Data Exploration
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
PostgreSQL Database
   ↓
SQL Analysis
   ↓
Power BI Dashboard
   ↓
Business Insights
   ↓
Analytical Report
   ↓
Gamma Presentation
```

---

# 📚 Conclusion

This project demonstrates a complete **end-to-end data analytics process**, combining programming, database technologies, SQL, business intelligence, visualization, reporting, and presentation.

Rather than focusing on a single analytical tool, the project demonstrates how different technologies can work together to transform a raw dataset into **clean data, meaningful analysis, interactive visualizations, and clearly communicated business insights**.

---

## 👤 Author

**Michael Aweke**

Data Analytics Project

---

## ⭐ Project Purpose

This project was developed as a practical demonstration of an end-to-end **Data Analytics workflow and portfolio project**, showcasing the ability to work with data from the initial loading and cleaning stages through SQL analysis, dashboard development, reporting, and professional presentation.

