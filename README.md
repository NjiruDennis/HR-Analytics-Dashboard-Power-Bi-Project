# HR-Analytics-Dashboard-Power-Bi-Project


## Table of Contents

* [Project Overview](#project-overview)
* [Data Source](#data-source)
* [Tools Used](#tools-used)
* [Data Cleaning/Preparation](#data-cleaningpreparation)
* [Exploratory Data Analysis](#exploratory-data-analysis)
* [Data Analysis](#data-analysis)
* [Results/Findings](#resultsfindings)
* [Recommendations](#recommendations)
* [Limitations](#limitations)

## Project Overview

This project aims to provide insights into employee attrition, demographics, and workforce composition within a human resources department. The analysis focuses on identifying the key drivers of employee attrition across departments, salary levels, job roles, gender, age groups, and experience, to help HR departments make data-driven decisions on retention and workforce planning.

## Data Source

The primary dataset used for this analysis is an **HR Analytics** dataset containing **1,417** employee records, including fields such as department, job role, salary slab, age, gender, years of experience, and attrition status.

## Tools Used

* **Power BI** - Data Cleaning and Transformation & Data Visualization and Dashboard Development

## Data Cleaning/Preparation

The data preparation phase was carried out in Power Query and included the following steps:

1. **Data Loading and Inspection**: Loaded the dataset into Power BI and inspected it for quality issues.
2. **Removing Null Values**: Identified and removed records with missing or null values to ensure analysis accuracy.
3. **Removing Duplicate Records**: Checked for and eliminated duplicate entries to avoid inflated metrics.
4. **Fixing Inconsistent Text Values**: Standardized inconsistent categorical values across columns such as department, job role, and gender to ensure clean grouping and filtering.

## Exploratory Data Analysis

Key questions explored in this analysis include:

1. What is the overall attrition rate across the organisation?
2. Which departments have the highest attrition?
3. How does attrition vary across salary slabs?
4. Which job roles have the highest attrition counts?
5. How does job satisfaction level relate to attrition by role?
6. What is the age group distribution of employees?
7. How does attrition differ between male and female employees?
8. At what experience levels does attrition spike?
9. What is the employee count distribution across departments?

## Data Analysis

Key DAX measures and features used in the analysis:

```dax
-- Attrition Rate
Attrition Rate % = DIVIDE([Attrition Count], [Total Employees], 0) * 100

-- Active Employees
Active Employees = CALCULATE(COUNT(HR_Analytics[EmployeeNumber]), HR_Analytics[Attrition] = "No")

-- Average Age
Average Age = AVERAGE(HR_Analytics[Age])

-- Average Experience
Avg Experience = AVERAGE(HR_Analytics[YearsAtCompany])
```

### Power BI Dashboard Visual

#### HR Analytics Dashboard
An interactive single-page dashboard covering attrition by department, salary slab, job role, satisfaction, gender, age group, and experience trend, with an age group slicer and department slicer for dynamic filtering.

> 📸 *Add your dashboard screenshot here after uploading to GitHub:*
> `<img width="900" alt="HR Analytics Dashboard" src="https://github.com/NjiruDennis/HR-Analytics-Dashboard-Power-Bi-Project/blob/main/Dashboard%20Screenshot.png" />`

## Results/Findings

From the analysis, the following key insights were discovered:

* **Overall Attrition:** Out of 1,417 total employees, 231 have left, giving an attrition rate of **16.3%**, with 1,186 currently active.
* **Attrition by Department:** Sales accounts for the highest attrition (84 employees, 36%), followed by Operations (52, 23%) and Human Resources (43, 19%).
* **Attrition by Salary Slab:** Employees earning in the **6-10 LPA** range have the highest attrition count (399 total records), while those earning **10+ LPA** have the lowest attrition (48), suggesting higher pay is linked to better retention.
* **Attrition by Job Role:** Laboratory Technicians (59) and Sales Executives (56) record the highest attrition counts, with lower satisfaction scores (1 and 2) contributing significantly.
* **Age Group Distribution:** The largest employee group is **26-35 years** (588), followed by **36-45 years** (446), indicating a relatively young to mid-career workforce.
* **Attrition by Gender:** Male employees account for 63% of attrition (146), compared to 37% for female employees (85).
* **Attrition Trend by Experience:** Attrition spikes sharply in the early years of employment, peaking around 5 years of experience, then declining significantly, suggesting early-tenure employees are the highest flight risk.
* **Department Size:** Operations is the largest department (512 employees), followed by Administration (406) and Sales (207).
* **Average Profile:** The average employee is **36.94 years old** with **7.04 years** of experience.

## Recommendations

Based on these findings, the following actions are recommended:

* **Focus Retention Efforts on Sales:** With 36% of all attrition coming from Sales, targeted interventions such as career development programmes, incentive structures, and manager support are needed urgently.
* **Review Lower Salary Bands:** The high attrition in lower salary slabs suggests compensation may be a driver. A salary benchmarking exercise for entry and mid-level roles is recommended.
* **Early Tenure Support:** Since attrition peaks around the 5-year mark, structured onboarding, mentorship, and career pathing programmes for employees in their first 1-5 years could significantly reduce early exits.
* **Address Laboratory Technician and Sales Executive Turnover:** These roles show both high attrition counts and low satisfaction scores. Role-specific engagement surveys and workload reviews are recommended.
* **Gender-Inclusive Retention Strategies:** While male attrition is higher in absolute terms, both genders need targeted retention initiatives, particularly in high-turnover departments.
* **Leverage High Earner Retention Patterns:** Employees earning 10+ LPA show the lowest attrition. Understanding what keeps this group engaged can inform broader retention strategy.

## Limitations

* The dataset does not include exit interview data or reasons for leaving, which limits the ability to confirm the root causes behind attrition trends.
* Salary is represented in slabs rather than exact figures, which reduces the precision of compensation-related analysis.
* The dataset is a snapshot in time and does not capture longitudinal trends in attrition over multiple years.
