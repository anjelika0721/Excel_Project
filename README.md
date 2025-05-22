# Excel Salary Calculator Dashboard

![Dashboard GIF](images/salary.gif)

## Introduction

As part of my learning journey into data analysis and Excel dashboards, I created this salary dashboard under the mentorship of [mentor's first name]. The dashboard helps job seekers explore salary trends across different job roles, countries, and working styles.

This project helped me understand how to use Excel not only for data entry, but also for visualizing and interpreting real-world job data effectively.

### 📂 Dashboard File

- [Excel Salary Dashboard File](Salary_Calculator.xlsx)

## 🧠 Excel Skills Used

- 📊 Charts (Bar, Map)
- 🧮 Formulas & Array Functions
- 📋 Data Validation
- 🔍 Slicers & Filters

## 📊 Dataset Description

The dataset contains salary information from data-related jobs in 2023, including:
- Job Titles
- Median Salaries
- Countries
- Job Schedule Types (e.g. Full-time, Part-time)
- Technical Skills Required

## 📈 Dashboard Features

### 1. **Median Salary by Job Title**
- Horizontal bar chart showing median salaries by role.
#### Background Table

-[Background Table](images/mediansalarybyjobtitle.png)

### 2. **Country-Level Salary Map**
- Map chart highlights regional salary differences.
- Color-coded for easy understanding of high and low paying countries.

### 3. **Interactive Filters**
- Job title, country, and schedule type slicers added.
- Users can quickly drill down to specific job combinations.

## 🔢 Key Excel Formulas Used

### Median Salary Calculation (Array Formula):

```excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)

