# Python Lab Data Analysis Engine

## 📌 Project Overview

This project is a Python-based pathology laboratory data analysis engine designed to analyze laboratory operations, patient demographics, diagnostic test utilization, results, revenue, billing, commercial performance, and relationships between key laboratory variables.

The project integrates data from a MySQL database into Python and performs data validation, cleaning, feature engineering, exploratory data analysis (EDA), visualization, and business-oriented analysis using Python.

The primary objective is to transform raw pathology laboratory data into meaningful analytical findings that can support a better understanding of patient patterns, test utilization, laboratory operations, diagnostic outcomes, revenue performance, and commercial activities.

---

## 🎯 Project Objectives

The main objectives of this project are:

* Extract and integrate pathology laboratory data from a MySQL database into Python.
* Verify database schemas and load the required data into Pandas DataFrames.
* Check and correct data types across the datasets.
* Standardize date-related columns and convert them into appropriate datetime formats.
* Identify and handle missing or null values.
* Analyze patient demographics and registration patterns.
* Analyze laboratory test utilization across tests, departments, doctors, and time periods.
* Evaluate laboratory operational performance using result status and turnaround time.
* Analyze diagnostic result patterns across tests, departments, gender, and age groups.
* Analyze revenue, billing, and payment status.
* Evaluate commercial and sales performance across companies, products, and diagnostic tests.
* Analyze time-based patterns in patient registrations and billing.
* Explore relationships between operational, demographic, pricing, discount, and revenue-related variables.
* Generate business-oriented insights from the analytical findings.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* MySQL
* MySQL Connector
* Jupyter Notebook

---

## 🔄 Project Workflow

The overall analytical workflow of the project is:

```text
MySQL Database
↓
Data Extraction & Integration
↓
Schema Verification
↓
Pandas DataFrames
↓
Data Type Validation & Correction
↓
Datetime Standardization
↓
Missing Value Analysis & Handling
↓
Exploratory Data Analysis (EDA)
↓
Data Visualization
↓
Business Analysis & Insights
```

---

## 📂 Project Structure

```text
Python Lab Analysis/
│
├── Dataset/
│   ├── billing.csv
│   ├── company.csv
│   ├── date_dimension.csv
│   ├── department.csv
│   ├── doctor.csv
│   ├── interpretation.csv
│   ├── patients.csv
│   ├── sales.csv
│   ├── test.csv
│   ├── test_discount.csv
│   ├── test_procedure.csv
│   └── test_record.csv
│
├── Lab Schema/
│   └── Lab.sql
│
├── Python Analysis/
│   └── Python_Lab_Analysis.ipynb
│
└── README.md
```

---

# 🔹 3. Exploratory Data Analysis (EDA)

The third stage of the project focuses on exploratory data analysis to understand patterns, distributions, trends, and relationships within the pathology laboratory data.

The EDA is organized into the following analytical areas:

* Patient Demography
* Test Utilization Analysis
* Laboratory Operational Analysis
* Diagnostic Result Analysis
* Revenue & Billing Analysis
* Commercial & Sales Analysis
* Time Analysis
* Advanced Relationship Analysis

---

# 3.1 Patient Demography

This section analyzes the demographic characteristics of patients in the laboratory dataset, including unique patient count, age distribution, gender distribution, and patient distribution across cities.

### Unique Patient

**Business Question:**
What is the number of unique patients in this laboratory dataset?

**Finding:**
The laboratory dataset contains **3,000 unique patients**.

---

### Patient Age Distribution

**Business Question:**
What is the age distribution of patients in the laboratory dataset?

**Finding:**

* Minimum Age: **1 year**
* Maximum Age: **90 years**
* Average Age: **46.19 years**

---

### Gender Distribution

**Business Question:**
How are patients distributed across different genders in the laboratory dataset?

**Finding:**

| Gender | Count |
| ------ | ----: |
| Others | 1,006 |
| Male   | 1,001 |
| Female |   993 |

---

### Patient Distribution by City

**Business Question:**
Which city contributed the highest number of patients?

**Top 10 Cities by Patient Count:**

| Rank | City      | Patient Count |
| ---: | --------- | ------------: |
|    1 | Patna     |           179 |
|    2 | Chennai   |           171 |
|    3 | Siliguri  |           170 |
|    4 | Bangalore |           165 |
|    5 | Pune      |           161 |
|    6 | Nagpur    |           160 |
|    7 | Hyderabad |           158 |
|    8 | Durgapur  |           156 |
|    9 | Guwahati  |           156 |
|   10 | Delhi     |           153 |

---

# 3.2 Test Utilization Analysis

This section analyzes laboratory test utilization to understand which diagnostic tests are performed most frequently, which departments handle the highest test volumes, which doctors are associated with the highest number of test records, and how test volume changes over time.

### Most Frequently Performed Tests

**Business Question:**
Which diagnostic tests are performed most frequently?

**Finding:**

The analysis shows that **Kidney Function Test (KFT)** was the most frequently performed diagnostic test, with **436 test records**, followed by **Hepatitis B (HBsAg)** with **433 records** and **Vitamin D (25-OH)** with **429 records**.

**Top 10 Most Frequently Performed Tests:**

| Rank | Test Name                            | Test Count |
| ---: | ------------------------------------ | ---------: |
|    1 | Kidney Function Test (KFT)           |        436 |
|    2 | Hepatitis B (HBsAg)                  |        433 |
|    3 | Vitamin D (25-OH)                    |        429 |
|    4 | Total Iron Binding Capacity (TIBC)   |        426 |
|    5 | Iron Studies (Serum Iron)            |        421 |
|    6 | Uric Acid                            |        418 |
|    7 | Calcium (Serum)                      |        415 |
|    8 | Blood Sugar Fasting (FBS)            |        412 |
|    9 | Ferritin                             |        411 |
|   10 | ESR (Erythrocyte Sedimentation Rate) |         40 |

> **Note:** The ESR count should be verified against the notebook output before publishing if this value was not intentionally produced by the analysis. It appears inconsistent with the surrounding test counts and may represent a source-data/filtering issue.

---

### Department-wise Test Volume

**Business Question:**
Which laboratory departments handle the highest number of tests?

**Finding:**

**Biochemistry** handled the highest laboratory test volume with **5,989 test records**, followed by **Hematology** with **2,056** and **Endocrinology** with **1,945** records.

| Rank | Department            | Test Records |
| ---: | --------------------- | -----------: |
|    1 | Biochemistry          |        5,989 |
|    2 | Hematology            |        2,056 |
|    3 | Endocrinology         |        1,945 |
|    4 | Serology & Immunology |        1,240 |
|    5 | Microbiology          |          398 |
|    6 | Clinical Pathology    |          372 |

---

### Doctor-wise Test Activity

**Business Question:**
Which doctors are associated with the highest number of laboratory test records?

**Finding:**

Among the doctors analyzed, **Dr. Debasish Verma (Diabetologist)** was associated with the highest number of laboratory test records, with **280 records**, followed by **Dr. Partha Iyer (Nephrologist)** with **274 records** and **Dr. Manoj Bose (Cardiologist)** with **264 records**.

**Top 10 Doctors by Test Activity:**

| Rank | Doctor             | Specialization    | Test Records |
| ---: | ------------------ | ----------------- | -----------: |
|    1 | Dr. Debasish Verma | Diabetologist     |          280 |
|    2 | Dr. Partha Iyer    | Nephrologist      |          274 |
|    3 | Dr. Manoj Bose     | Cardiologist      |          264 |
|    4 | Dr. Amit Banerjee  | Nephrologist      |          263 |
|    5 | Dr. Subrata Nair   | Hematologist      |          262 |
|    6 | Dr. Sandeep Pal    | Gynecologist      |          261 |
|    7 | Dr. Priya Dutta    | Oncologist        |          258 |
|    8 | Dr. Moumita Iyer   | General Physician |          257 |
|    9 | Dr. Rajesh Sharma  | Hematologist      |          255 |
|   10 | Dr. Tapan Kapoor   | General Physician |          252 |

---

### Monthly Test Volume

**Business Question:**
How does the volume of laboratory tests change over time?

**Finding:**

The monthly analysis shows that laboratory test volume **fluctuated over the period from January 2022 to September 2026**, with no continuous upward or downward trend.

The highest monthly test volume was recorded in **January 2025 with 250 test records**, while the lowest was **September 2026 with 100 records**. The September 2026 value should be interpreted carefully because the dataset may represent only a partial month.

The monthly trend was visualized using a **line chart** to observe changes in laboratory test volume over time.

---

# 3.3 Laboratory Operational Analysis

This section analyzes laboratory operational performance by examining result status, turnaround time (TAT), department-wise TAT, and the distribution of completed and incomplete laboratory workflows.

### Result Status Distribution

**Business Question:**
What is the distribution of laboratory test records by result status?

**Finding:**

The majority of laboratory test records were **Completed**, with **9,320 records**. This was followed by **Pending (1,171)**, **In Progress (895)**, and **Cancelled (614)** records.

| Result Status | Test Records |
| ------------- | -----------: |
| Completed     |        9,320 |
| Pending       |        1,171 |
| In Progress   |          895 |
| Cancelled     |          614 |

---

### Turnaround Time (TAT) Distribution

**Business Question:**
How long does it take for the laboratory to generate test reports?

**Why does this matter?**

Turnaround time is an important operational metric for laboratory performance. Understanding its distribution helps identify typical reporting times and potential delays.

**Finding:**

The analysis calculates turnaround time in hours between the **test date** and the **report date** for laboratory test records.

TAT values are available only when a valid report date is present. Therefore, records without a report date do not contribute to TAT statistics.

The available TAT data shows that completed records generally had short reporting times, with an average turnaround time of approximately **1.50 hours**.

---

### Turnaround Time by Department

**Business Question:**
How does laboratory turnaround time vary across departments?

**Why does this matter?**

Comparing turnaround time across departments can help identify differences in operational workload and reporting-time variability.

**Finding:**

Turnaround time was compared across laboratory departments using a **box plot**. The visualization helps identify differences in the distribution and variability of reporting times across departments and can highlight departments with relatively higher or more variable turnaround times.

---

### Operational Status Analysis

**Business Question:**
How many laboratory test records are completed, pending, in progress, or cancelled?

**Why does this matter?**

Understanding operational status volumes helps identify the current distribution of completed and incomplete laboratory workflows.

**Finding:**

The laboratory dataset contains **9,320 completed records**, **1,171 pending records**, **895 in-progress records**, and **614 cancelled records**.

| Result Status | Test Records |
| ------------- | -----------: |
| Completed     |        9,320 |
| Pending       |        1,171 |
| In Progress   |          895 |
| Cancelled     |          614 |

---

# 3.4 Diagnostic Result Analysis

This section analyzes laboratory result patterns across diagnostic tests, departments, gender groups, and patient age groups to understand differences in laboratory workflow outcomes.

### Test-wise Result Status

**Business Question:**
How are result statuses distributed across different diagnostic tests?

**Why does this matter?**

Test-wise result analysis helps identify differences in result patterns across commonly performed diagnostic tests and provides a deeper understanding of laboratory testing activity.

**Finding:**

The analysis shows that result statuses vary across diagnostic tests, with **Completed** records generally representing the largest share of records for the tests shown.

For example, **Calcium (Serum)** had **317 completed records**, while **Blood Sugar Fasting (FBS)** had **315 completed records** among the displayed test results.

---

### Department-wise Result Pattern

**Business Question:**
How does result status vary across laboratory departments?

**Why does this matter?**

A department-level result status comparison can help identify differences in completed, pending, in-progress, and cancelled laboratory records across diagnostic departments.

**Finding:**

Among the completed laboratory records, **Biochemistry** had the highest number with **4,654 completed records**, followed by **Hematology (1,592)** and **Endocrinology (1,500)**.

| Department            | Completed Records |
| --------------------- | ----------------: |
| Biochemistry          |             4,654 |
| Hematology            |             1,592 |
| Endocrinology         |             1,500 |
| Serology & Immunology |               982 |
| Microbiology          |               307 |
| Clinical Pathology    |               285 |

---

### Result Status by Gender

**Business Question:**
How does the distribution of laboratory result status vary by gender?

**Why does this matter?**

Comparing result status proportions across gender groups provides a demographic view of laboratory workflow outcomes within the dataset.

**Finding:**

The result status distribution is broadly similar across the three gender groups. **Completed records accounted for approximately 78%** of records for Female, Male, and Other groups.

| Gender | Cancelled (%) | Completed (%) | In Progress (%) | Pending (%) |
| ------ | ------------: | ------------: | --------------: | ----------: |
| Female |         4.72% |        77.76% |           7.19% |      10.33% |
| Male   |         5.30% |        77.61% |           8.07% |       9.02% |
| Other  |         5.34% |        77.62% |           7.12% |       9.92% |

---

### Age vs Result Status

**Business Question:**
How does patient age distribution vary across laboratory result statuses?

**Why does this matter?**

Comparing age distributions across result statuses can reveal differences in the demographic composition of laboratory records associated with different workflow outcomes.

**Finding:**

The average patient age was relatively similar across most result statuses, ranging from **46.20 years for Cancelled records** to **48.94 years for In Progress records**.

The age range for all result statuses was **1 to 90 years**.

| Result Status | Average Age | Minimum Age | Median Age | Maximum Age |
| ------------- | ----------: | ----------: | ---------: | ----------: |
| Cancelled     |       46.20 |           1 |         46 |          90 |
| Completed     |       46.55 |           1 |         48 |          90 |
| In Progress   |       48.94 |           1 |         51 |          90 |
| Pending       |       46.29 |           1 |         48 |          90 |

---

# 3.5 Revenue & Billing Analysis

This section analyzes laboratory revenue and billing performance to understand total sales revenue, revenue contribution by diagnostic tests and departments, and the distribution of payment statuses.

### Total Revenue Overview

**Business Question:**
What is the total revenue generated from laboratory sales?

**Finding:**

The laboratory generated total sales revenue of approximately **90.79 million**.

---

### Revenue by Diagnostic Test

**Business Question:**
Which diagnostic tests generate the highest revenue?

**Finding:**

**Blood Sugar Fasting (FBS)** generated the highest revenue among the diagnostic tests, with approximately **11.34 million** in revenue. It was followed by **Total Iron Binding Capacity (TIBC)** with approximately **6.33 million** and **Iron Studies (Serum Iron)** with approximately **6.19 million**.

**Top 10 Revenue-Generating Diagnostic Tests:**

| Rank | Test Name                          | Revenue |
| ---: | ---------------------------------- | ------: |
|    1 | Blood Sugar Fasting (FBS)          |  11.34M |
|    2 | Total Iron Binding Capacity (TIBC) |   6.33M |
|    3 | Iron Studies (Serum Iron)          |   6.19M |
|    4 | Kidney Function Test (KFT)         |   5.66M |
|    5 | CBC (Complete Blood Count)         |   5.48M |
|    6 | Cholesterol Total                  |   5.20M |
|    7 | Vitamin B12                        |   5.08M |
|    8 | Triglycerides                      |   4.79M |
|    9 | Hepatitis B (HBsAg)                |   4.41M |
|   10 | Thyroid Profile - T3               |   4.35M |

---

### Department-wise Revenue

**Business Question:**
Which laboratory departments contribute the most to overall revenue?

**Finding:**

**Biochemistry** was the highest revenue-generating department, generating approximately **44.44 million** in revenue. It was followed by **Hematology (18.39 million)** and **Endocrinology (14.83 million)**.

| Rank | Department            | Revenue |
| ---: | --------------------- | ------: |
|    1 | Biochemistry          |  44.44M |
|    2 | Hematology            |  18.39M |
|    3 | Endocrinology         |  14.83M |
|    4 | Serology & Immunology |  11.07M |
|    5 | Microbiology          |   1.76M |
|    6 | Clinical Pathology    |   0.30M |

---

### Payment Status Distribution

**Business Question:**
What is the distribution of laboratory bills across different payment statuses?

**Finding:**

**Paid** bills were the most common payment status, with **9,044 bills**, followed by **Unpaid (1,407)**, **Partially Paid (1,196)**, and **Refunded (353)** bills.

| Payment Status | Bill Count |
| -------------- | ---------: |
| Paid           |      9,044 |
| Unpaid         |      1,407 |
| Partially Paid |      1,196 |
| Refunded       |        353 |

---

### 3.5 Business Insights

* The laboratory generated total sales revenue of approximately **90.79 million**.
* **Blood Sugar Fasting (FBS)** generated the highest revenue among the diagnostic tests, contributing approximately **11.34 million**.
* **Total Iron Binding Capacity (TIBC)** and **Iron Studies (Serum Iron)** were also among the major revenue-generating diagnostic tests.
* **Biochemistry** was the highest revenue-generating department, generating approximately **44.44 million**.
* **Hematology** and **Endocrinology** generated approximately **18.39 million** and **14.83 million**, respectively.
* **Clinical Pathology** generated approximately **0.30 million**, the lowest department-level revenue in the dataset.
* **Paid** bills were the most common payment status, with **9,044 bills**.

---

# 3.6 Commercial & Sales Analysis

This section analyzes commercial and sales performance across laboratory suppliers, products, and diagnostic tests to understand major revenue contributors and the relationship between test pricing and revenue.

### Company-wise Revenue

**Business Question:**
Which companies contribute the most to laboratory sales revenue?

**Finding:**

**Transasia Bio-Medicals** generated the highest sales revenue among the companies, with approximately **6.82 million** in revenue. It was followed by **Beckman Coulter (6.76 million)** and **Tulip Diagnostics (6.63 million)**.

**Company-wise Revenue:**

| Rank | Company                  | Revenue |
| ---: | ------------------------ | ------: |
|    1 | Transasia Bio-Medicals   |   6.82M |
|    2 | Beckman Coulter          |   6.76M |
|    3 | Tulip Diagnostics        |   6.63M |
|    4 | Erba Mannheim            |   6.57M |
|    5 | Thermo Fisher Scientific |   6.38M |
|    6 | Randox Laboratories      |   6.13M |
|    7 | Agappe Diagnostics       |   6.10M |
|    8 | Mindray Medical          |   6.10M |
|    9 | Abbott Diagnostics       |   6.02M |
|   10 | Diasys Diagnostics       |   5.99M |
|   11 | Siemens Healthineers     |   5.91M |
|   12 | Accurex Biomedical       |   5.44M |
|   13 | Bio-Rad Laboratories     |   5.41M |
|   14 | Roche Diagnostics        |   5.28M |
|   15 | Span Diagnostics         |   5.25M |

---

### Product-wise Revenue

**Business Question:**
Which products generate the highest sales revenue for the laboratory?

**Finding:**

**TIBC Reagent Kit** generated the highest product-wise revenue, with approximately **6.33 million** in sales. It was followed by **Iron (Fe) Reagent Kit (6.19 million)** and **KFT Panel Reagent Kit (5.66 million)**.

**Top 10 Revenue-Generating Products:**

| Rank | Product                       | Revenue |
| ---: | ----------------------------- | ------: |
|    1 | TIBC Reagent Kit              |   6.33M |
|    2 | Iron (Fe) Reagent Kit         |   6.19M |
|    3 | KFT Panel Reagent Kit         |   5.66M |
|    4 | PCV (Hematocrit) Reagent Kit  |   5.44M |
|    5 | Total Cholesterol Reagent Kit |   5.20M |
|    6 | Vitamin B12 CLIA Kit          |   5.08M |
|    7 | Triglycerides Reagent Kit     |   4.79M |
|    8 | ESR Reagent Kit               |   4.64M |
|    9 | HBsAg Rapid Test Kit          |   4.41M |
|   10 | T3 ELISA Kit                  |   4.35M |

---

### Test Price vs Revenue

**Business Question:**
Is there a relationship between diagnostic test price and the revenue generated by the test?

**Finding:**

The test-level revenue figures show that revenue is influenced by factors beyond test price, including **the volume of tests performed**.

For example, **Blood Sugar Fasting (FBS)** generated approximately **11.34 million** in revenue with **412 test records**, while **CBC** generated approximately **5.48 million** at a price of **350**, and **Cholesterol Total** generated approximately **5.20 million** at a price of **300**.

This indicates that a lower-priced diagnostic test can generate higher overall revenue when its testing volume is substantially higher.

---

### 3.6 Business Insights

* **Transasia Bio-Medicals** generated approximately **6.82 million** in sales revenue.
* **Beckman Coulter** and **Tulip Diagnostics** generated approximately **6.76 million** and **6.63 million**, respectively.
* **TIBC Reagent Kit** generated approximately **6.33 million** in product-wise revenue.
* **Iron (Fe) Reagent Kit** and **KFT Panel Reagent Kit** generated approximately **6.19 million** and **5.66 million**, respectively.
* **Blood Sugar Fasting (FBS)** generated approximately **11.34 million** in revenue despite its test price of **120**.
* **CBC** generated approximately **5.48 million** in revenue at a test price of **350**.
* **Cholesterol Total** generated approximately **5.20 million** in revenue at a test price of **300**.
* The analysis indicates that revenue is influenced by both **test volume and revenue per test**, rather than test price alone.

---

# 3.7 Time Analysis

This section analyzes time-based patterns in patient registrations and laboratory billing to understand monthly patient registration trends and yearly changes in billing amounts.

### Monthly Patient Registrations

**Business Question:**
How does the number of newly registered patients change from month to month?

**Finding:**

Monthly patient registrations fluctuated throughout the analysis period.

The highest monthly patient registration was **67**, recorded in **December 2024** and **November 2025**. The lowest monthly registration was **34**, recorded in **September 2026**.

Because 2026 contains data only through September, the September 2026 value should be interpreted as a partial-period observation.

---

### Year-wise Billing Amount Comparison

**Business Question:**
How does the laboratory's total billing amount vary across different years?

**Finding:**

The annual billing amount remained relatively stable from **2022 to 2025**, ranging from approximately **1.02 million to 1.05 million**.

The highest annual billing amount among the complete years was recorded in **2025**, at approximately **1.05 million**.

The billing amount for **2026** was approximately **0.67 million**; however, the 2026 data covers only **January to September** and therefore should not be directly compared with the complete years.

|  Year | Billing Amount |
| ----: | -------------: |
|  2022 |          1.02M |
|  2023 |          1.05M |
|  2024 |          1.02M |
|  2025 |          1.05M |
| 2026* |          0.67M |

*2026 includes data from January to September only.

---

### 3.7 Business Insights

* The highest monthly patient registration was **67**, recorded in **December 2024** and **November 2025**.
* The lowest monthly registration was **34**, recorded in **September 2026**.
* Annual billing remained relatively stable from **2022 to 2025**, ranging from approximately **1.02 million to 1.05 million**.
* **2025** recorded the highest annual billing amount among the complete years, at approximately **1.05 million**.
* The **2026** billing amount was approximately **0.67 million**, but the period covers only January to September and should therefore be interpreted separately from complete years.

---

# 3.8 Advanced Relationship Analysis

This section analyzes relationships between test volume, revenue, turnaround time, patient age, test frequency, test price, and discount percentage to identify factors associated with laboratory utilization, operational performance, and commercial outcomes.

### Test Volume vs Revenue

**Business Question:**
Is higher test volume associated with higher sales revenue?

**Why does this matter?**

Understanding the relationship between test volume and revenue helps identify whether frequently performed diagnostic tests also generate higher commercial value for the laboratory.

**Finding:**

The analysis compares the number of tests performed with the revenue generated by each diagnostic test.

The results show that higher test volume does not always correspond directly to higher revenue. For example, **Blood Sugar Fasting (FBS)** generated approximately **11.34 million** in revenue with **412 test records**, while **Cholesterol Total** generated approximately **5.20 million** with **119 test records**.

This indicates that revenue is influenced by both **test volume and revenue per test**, rather than test volume alone.

---

### Turnaround Time (TAT) vs Result Status

**Business Question:**
How does turnaround time vary across different laboratory result statuses?

**Why does this matter?**

Comparing turnaround time across result statuses helps identify operational differences between completed, pending, in-progress, and cancelled laboratory records.

**Finding:**

The available TAT data contains turnaround time values for **Completed** records only.

Completed records had an average turnaround time of approximately **1.50 hours**, with a median of **1 hour** and a maximum of **3 hours**.

TAT values were not available for **Cancelled, In Progress, and Pending** records because these records did not have valid report dates in the analyzed dataset.

Therefore, the TAT statistics for those statuses are shown as not available rather than zero.

| Result Status | Total Records | Records with TAT | Average TAT (Hours) | Median TAT (Hours) | Maximum TAT (Hours) |
| ------------- | ------------: | ---------------: | ------------------: | -----------------: | ------------------: |
| Cancelled     |           614 |                0 |                   — |                  — |                   — |
| Completed     |         9,320 |            9,320 |                1.50 |               1.00 |                3.00 |
| In Progress   |           895 |                0 |                   — |                  — |                   — |
| Pending       |         1,171 |                0 |                   — |                  — |                   — |

> **Important:** The `Total Records` column represents all records by result status, while `Records with TAT` represents records for which both test date and report date were available.

---

### Age vs Test Frequency

**Business Question:**
Is patient age associated with the frequency of laboratory tests performed?

**Why does this matter?**

Age-wise test frequency analysis helps identify whether laboratory utilization varies across different patient age groups.

**Finding:**

The analysis compares patient age with the number of laboratory tests performed for each patient.

The sample shows variation in test frequency across different age groups. For example, patients aged **30 and 9 years** had **6 and 7 tests**, respectively, while patients aged **86 and 85 years** had **3 and 2 tests**.

The analysis helps explore whether patient age is associated with differences in laboratory test utilization.

---

### Revenue, Price & Discount Correlation

**Business Question:**
How are test price, discount, and revenue related to each other?

**Finding:**

The correlation analysis shows that **test price and revenue had almost no linear correlation**, with a correlation coefficient of approximately **-0.03**.

**Discount percentage and revenue** showed a **weak positive correlation** of approximately **0.29**, while **test price and discount percentage** showed a **moderate positive correlation** of approximately **0.41**.

| Variable   | Price | Discount % | Revenue |
| ---------- | ----: | ---------: | ------: |
| Price      |  1.00 |       0.41 |   -0.03 |
| Discount % |  0.41 |       1.00 |    0.29 |
| Revenue    | -0.03 |       0.29 |    1.00 |

---

### 3.8 Business Insights

* Test price and revenue showed **almost no linear correlation**, with a correlation coefficient of approximately **-0.03**.
* Discount percentage and revenue showed a **weak positive correlation** of approximately **0.29**.
* Test price and discount percentage showed a **moderate positive correlation** of approximately **0.41**.
* The correlation results indicate that **test price alone does not explain revenue variation**, and test volume may also contribute to overall revenue generation.
* These correlation values represent **associations within the analyzed dataset and do not establish causal relationships**.

---

# 🔄 Project Workflow

```text
┌──────────────────────┐
│     MySQL Database   │
│   Laboratory Data    │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│   Data Extraction    │
│   MySQL Connector    │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│  Data Validation &   │
│      Cleaning        │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│    Pandas DataFrames │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Exploratory Data     │
│ Analysis (EDA)       │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Visualization &      │
│ Relationship Analysis│
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Business Insights    │
└──────────────────────┘
```

---

# 🗄️ Database Schema & Relationships

```text
                         ┌─────────────────┐
                         │    patients     │
                         │-----------------│
                         │ patient_id      │
                         │ name            │
                         │ age             │
                         │ gender          │
                         │ city            │
                         └────────┬────────┘
                                  │
                                  │
                         ┌────────▼────────┐
                         │  test_record    │
                         │-----------------│
                         │ record_id       │
                         │ patient_id      │
                         │ test_id         │
                         │ doctor_id       │
                         │ test_date       │
                         │ report_date     │
                         │ result_status   │
                         └───────┬─────────┘
                                 │
               ┌─────────────────┼─────────────────┐
               ↓                 ↓                 ↓
        ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
        │    test     │   │   doctor    │   │ department  │
        └─────────────┘   └─────────────┘   └─────────────┘
               │
               ↓
        ┌────────────────┐
        │ test_procedure │
        └────────────────┘
               │
               ↓
        ┌────────────────┐
        │ test_discount  │
        └────────────────┘

        ┌─────────────┐
        │    sales    │
        └──────┬──────┘
               │
        ┌──────▼──────┐
        │   company   │
        └─────────────┘

        ┌─────────────┐
        │   billing   │
        └─────────────┘

        ┌────────────────┐
        │ interpretation │
        └────────────────┘

        ┌────────────────┐
        │ date_dimension │
        └────────────────┘
```

---

# 📌 Project Highlights

| Metric                  |     Value |
| ----------------------- | --------: |
| Unique Patients         |     3,000 |
| Laboratory Test Records |    12,000 |
| Completed Test Records  |     9,320 |
| Total Sales Revenue     |    90.79M |
| Data Analysis Period    | 2022–2026 |
| Analytical Sections     |         8 |

---

# 💡 Business Insights & Recommendations

### Key Insights

* **Biochemistry** handled the highest laboratory test volume and generated the highest department-wise revenue.
* **Blood Sugar Fasting (FBS)** generated the highest diagnostic-test revenue at approximately **11.34M**.
* Total laboratory sales revenue was approximately **90.79M**.
* **Test volume and revenue per test** both contribute to revenue variation.
* Test price alone showed almost no linear correlation with revenue.
* Laboratory test volume fluctuated over time, with **January 2025** recording the highest monthly test volume.
* Annual billing remained relatively stable from **2022 to 2025**.
* Completed records represented the majority of laboratory result statuses.
* The available completed-record TAT data showed an average reporting time of approximately **1.50 hours**.

### Recommendations

* Monitor high-volume diagnostic tests to support laboratory resource planning.
* Track department-wise turnaround time to identify operational variations.
* Monitor pending and in-progress test records as part of workflow management.
* Evaluate discount patterns across diagnostic tests and pricing levels.
* Analyze test volume together with revenue per test for commercial planning.
* Monitor monthly and yearly trends while accounting for partial-year or partial-month data.

---

# 📁 Project Files

| File / Folder                               | Description                           |
| ------------------------------------------- | ------------------------------------- |
| `Dataset/`                                  | Laboratory datasets in CSV format     |
| `Lab Schema/Lab.sql`                        | MySQL database schema and SQL queries |
| `Python Analysis/Python_Lab_Analysis.ipynb` | Complete Python analysis              |
| `README.md`                                 | Project documentation                 |

