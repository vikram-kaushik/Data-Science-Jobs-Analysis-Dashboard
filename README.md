# Data Science Jobs Analysis Dashboard 📊

A comprehensive data analytics portfolio featuring two distinct Excel projects from **Luke Barousse's Excel for Data Analytics Course**. Showcases end-to-end data processing, interactive dashboard design, and market analysis using advanced Excel features.

---

### Project 1: Excel Salary Dashboard

### Introduction

This interactive dashboard was built to help job seekers investigate salaries for their desired roles and ensure they are being fairly compensated. It allows users to filter by job title, country, and schedule type to get tailored salary insights.

### Salary Dashboard  
<img width="800" height="273" alt="ScreenRecording2026-06-22102013-ezgif com-optimize" src="https://github.com/user-attachments/assets/20944e3a-a359-476c-8831-1b838d166247" />




### Excel Skills Used

- **📉 Charts** — Bar chart and map chart for visual salary comparisons
- **🧮 Formulas and Functions** — Multi-criteria MEDIAN/IF array formulas and FILTER function
- **❎ Data Validation** — Dropdown lists to restrict and guide user input

### Dashboard Highlights

#### 📊 Data Science Job Salaries — Bar Chart
- Horizontal bar chart sorted by descending median salary
- Quickly shows that Senior roles and Engineers earn more than Analyst roles

#### 🗺️ Country Median Salaries — Map Chart
- Color-coded global map to visualize salary levels by region
- Highlights geographic salary disparities at a glance

#### 🧮 Key Formula — Median Salary by Job Title
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
```
Filters by job title, country, and schedule type simultaneously to return a precise median salary.

#### ⏰ Job Schedule Type Filter Formula
```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```
Generates a clean unique list of schedule types, excluding combined entries and blanks.

### Conclusion

This dashboard provides a practical tool for exploring salary trends across data job titles, locations, and work types — helping professionals make informed career decisions.

---

## Project 2: Data Science Job Market Analysis

### Introduction

This project digs into the data science job market to answer four key questions around skills and compensation — helping job seekers understand what to learn and what to expect to earn.

### Analytical Charts From Project 2  
<img width="1859" height="469" alt="Screenshot 2026-06-22 103737" src="https://github.com/user-attachments/assets/28e9748a-d36b-4b34-8d2a-08d0d270a83c" />
<img width="1440" height="484" alt="Screenshot 2026-06-22 103709" src="https://github.com/user-attachments/assets/ae828a04-1197-4876-a1f8-94f027a72572" />
<img width="920" height="497" alt="Screenshot 2026-06-22 103648" src="https://github.com/user-attachments/assets/da559fb7-788b-4521-8070-4b8ae3aa8d4f" />


### Questions Analyzed

1. **Do more skills get you better pay?**
2. **What's the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What's the pay for the top 10 skills?**

### Excel Skills Used

- **📊 Pivot Tables** — Summarizing salary and skill data across dimensions
- **📈 Pivot Charts** — Combo charts for visualizing salary vs. skill likelihood
- **🧮 DAX** — Custom measures for median salary calculations
- **🔍 Power Query** — ETL pipeline to extract, clean, and load data
- **💪 Power Pivot** — Data model with relationships across tables

### Analysis Highlights

#### 1️⃣ Do More Skills Get You Better Pay?
Used Power Query to extract and clean two datasets — job info and skills per job ID — then merged them for analysis.

**Key Insight:** There is a positive correlation between number of skills requested and median salary. Roles like Senior Data Engineer and Data Scientist (high skill count) command significantly higher pay than roles like Business Analyst.

#### 2️⃣ Salary for Data Jobs by Region
Built a PivotTable on a Power Pivot data model with a DAX measure for US vs. Non-US median salary comparison.

```
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])

=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")
```

**Key Insight:** Senior Data Engineers and Data Scientists command top salaries globally. The US salary premium is most pronounced in high-tech roles.

#### 3️⃣ Top Skills of Data Professionals
Created a relational data model in Power Pivot linking job data and skills data via `job_id`.

**Key Insight:** SQL and Python dominate across all data roles. AWS and Azure are rising fast, reflecting the industry's shift toward cloud.

#### 4️⃣ Pay for the Top 10 Skills
Built a combo PivotChart with median salary (clustered column) on the primary axis and skill likelihood % (line with markers) on the secondary axis.

**Key Insight:** Python, Oracle, and SQL are tied to the highest salaries. PowerPoint and Word rank lowest in both salary and demand.

### Conclusion

Using Power Query, Power Pivot, DAX, and advanced charting, this project uncovered that specialized skills — particularly Python, SQL, and cloud technologies — are directly linked to higher compensation in the data science market.

---

## 🛠️ Tools & Technologies

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

- Microsoft Excel (Power Query, Power Pivot, DAX, Pivot Tables, Charts, Data Validation)

## 📂 Dataset

Real-world data science job postings from 2023, sourced via Luke Barousse's Excel for Data Analytics Course. Includes job titles, salaries, locations, and required skills.

## 🙏 Acknowledgements

Projects built by following [Luke Barousse's Excel for Data Analytics Course](https://www.youtube.com/@LukeBarousse) on YouTube.
