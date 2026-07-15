# HR Attrition Analytics Dashboard

An end-to-end HR analytics project that identifies key drivers of employee attrition using SQL for data analysis and Power BI for interactive visualization, based on the IBM HR Analytics Employee Attrition dataset.

---

## 📌 Problem Statement

Employee attrition is one of the most expensive and disruptive challenges an organization can face — the cost of replacing an employee often exceeds 6–9 months of their salary, not counting lost productivity, institutional knowledge, and team morale.

This project analyzes 1,470 employee records to answer a core business question:

> **Which employees are most likely to leave, and what factors are driving that risk?**

The goal is to move HR decision-making from guesswork to data — giving leadership a clear, evidence-based profile of at-risk employees so retention efforts can be targeted where they matter most.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **SQLite (DB Browser)** | Data storage and SQL querying |
| **SQL** | Data aggregation, filtering, and rate calculations |
| **Power BI Desktop** | Interactive dashboard and data visualization |
| **DAX** | Calculated measures and columns |
| **IBM HR Analytics Dataset** | Source data (Kaggle) |

---

## 🔍 Key Findings

- **Overtime is the strongest single risk factor** — employees working overtime attrite at **30.53%**, nearly 3x the rate of those who don't (10.44%).
- **Early tenure is a critical danger zone** — employees with 0–2 years at the company leave at **29.82%**, far above any other tenure group.
- **Sales Representatives are the most at-risk role**, with an attrition rate of **39.76%** — more than double the company average.
- **Compensation matters significantly** — employees earning below ₹5K/month attrite at **21.76%**, compared to just **3.76%** for those earning above ₹15K.
- **Young, single employees are flight risks** — the 18–25 age group (35.77%) and single employees (25.53%) both show elevated attrition compared to their peers.
- **Poor work-life balance nearly doubles attrition risk** — from 14.28% (balanced) to **31.25%** (poor).

**Bottom line:** The highest-risk employee profile is a young, single Sales Representative in their first two years, working overtime, earning below-average pay, with low job satisfaction and poor work-life balance. This is a clear, actionable target for retention strategy.

---

## 📊 Dashboard Overview

The Power BI dashboard is built across 4 pages:

1. **Executive Overview** — headline KPIs, department and job role attrition
2. **Attrition Drivers** — overtime, job satisfaction, work-life balance, income
3. **Demographics** — age, gender, marital status, education field
4. **Tenure & Retention** — attrition by years at company

### Screenshots

**Executive Overview**
![Executive Overview](<Screenshot%20page%201%20Executive%20Overview.png>)

**Attrition Drivers**
![Attrition Drivers](<Screenshot_page%202_Attrition_Drivers.png>)

**Demographics**
![Demographics](<Screenshot_page%203%20Demographics.png>)

**Tenure & Retention**
![Tenure and Retention](<Screenshot%20page%204%20Tenure%20_retention.png>)

---

## 📁 Repository Structure

```
HR_Attrition_Analytics_Dashboard/
│
├── HR_Attrition_Dashboard.pbix                   # Power BI dashboard file
├── HR_Attrition_SQL_Analysis.md                  # Full SQL queries, outputs & insights
├── IBM DATA SET.csv                              # Source dataset
├── Screenshot page 1 Executive Overview.png      # Dashboard page 1
├── Screenshot_page 2_Attrition_Drivers.png       # Dashboard page 2
├── Screenshot_page 3 Demographics.png            # Dashboard page 3
├── Screenshot page 4 Tenure _retention.png       # Dashboard page 4
└── README.md                                     # Project overview (this file)
```

---

## 🧠 Methodology

1. **Data Preparation** — Loaded the IBM HR Analytics dataset into SQLite for structured querying.
2. **SQL Analysis** — Wrote 15+ SQL queries to calculate attrition rates across departments, job roles, demographics, compensation bands, tenure groups, and satisfaction metrics. Full documentation available in [`HR_Attrition_SQL_Analysis.md`](HR_Attrition_SQL_Analysis.md).
3. **Dashboard Design** — Built a 4-page interactive Power BI dashboard using DAX measures to replicate and visualize every SQL finding, enabling stakeholders to explore attrition drivers without writing a single query.
4. **Insight Generation** — Translated statistical patterns into a clear, actionable risk profile for HR decision-makers.

---

## 💡 Skills Demonstrated

- SQL (aggregation, CASE statements, conditional counting, GROUP BY analysis)
- Data cleaning and structuring
- DAX (calculated measures and columns)
- Power BI dashboard design and data storytelling
- Business insight generation from raw data
- End-to-end analytics project execution (data → analysis → visualization → communication)

---

## 👤 About

**Alfiya Taneem**
Electronics & Communication Engineering graduate | Aspiring Data Analyst

📧 alfiyataneem786@gmail.com
🔗 [linkedin.com/in/alfiya-taneem-48916323b](https://linkedin.com/in/alfiya-taneem-48916323b)

---

*This project was completed as part of building a data analytics portfolio targeting Data Analyst roles.*

