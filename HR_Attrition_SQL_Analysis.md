# HR Attrition Analysis — SQL Documentation

**Dataset:** IBM HR Analytics Employee Attrition Dataset
**Total Records:** 1,470 employees
**Tools:** SQLite (DB Browser), SQL

---

## 1. Total Employees

```sql
SELECT COUNT(*) AS Total_Employees
FROM employee_data;
```

**Result:** 1,470

**Insight:** The organization consists of 1,470 employees, forming the base population for all HR analytics in this study.

---

## 2. Employees Left

```sql
SELECT COUNT(*) AS Employees_Left
FROM employee_data
WHERE Attrition = 'Yes';
```

**Result:** 237

**Insight:** A total of 237 employees have left the company.

---

## 3. Employees Stayed

```sql
SELECT COUNT(*) AS Employees_Stayed
FROM employee_data
WHERE Attrition = 'No';
```

**Result:** 1,233

**Insight:** The majority of employees (1,233) remain with the company.

---

## 4. Overall Attrition Rate

```sql
SELECT
    ROUND(
        (COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0) / COUNT(*),
        2
    ) AS Attrition_Rate
FROM employee_data;
```

**Result:** 16.12%

**Insight:** Overall employee attrition stands at 16.12%, meaning approximately 16 out of every 100 employees have left the organization.

---

## 5. Department-wise Attrition

```sql
SELECT
    Department,
    COUNT(*) AS Total_Employees,
    COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) AS Employees_Left,
    ROUND(
        COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0 / COUNT(*),
        2
    ) AS Attrition_Rate
FROM employee_data
GROUP BY Department
ORDER BY Attrition_Rate DESC;
```

| Department | Total | Left | Attrition Rate |
|---|---|---|---|
| Sales | 446 | 92 | 20.63% |
| Human Resources | 63 | 12 | 19.05% |
| Research & Development | 961 | 133 | 13.84% |

**Insight:** The Sales department has the highest attrition rate (20.63%), indicating a greater retention challenge compared to other departments.

---

## 6. Overtime vs Attrition

```sql
SELECT
    OverTime,
    COUNT(*) AS Total_Employees,
    COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) AS Employees_Left,
    ROUND(
        COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0 / COUNT(*),
        2
    ) AS Attrition_Rate
FROM employee_data
GROUP BY OverTime;
```

| Overtime | Total | Left | Attrition Rate |
|---|---|---|---|
| Yes | 416 | 127 | 30.53% |
| No | 1,054 | 110 | 10.44% |

**Insight:** Employees working overtime have an attrition rate of 30.53% — nearly three times higher than employees who do not work overtime.

---

## 7. Job Role vs Attrition

```sql
SELECT
    JobRole,
    COUNT(*) AS Total_Employees,
    COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) AS Employees_Left,
    ROUND(
        COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0 / COUNT(*),
        2
    ) AS Attrition_Rate
FROM employee_data
GROUP BY JobRole
ORDER BY Attrition_Rate DESC;
```

| Job Role | Total | Left | Attrition Rate |
|---|---|---|---|
| Sales Representative | 83 | 33 | 39.76% |
| Laboratory Technician | 259 | 62 | 23.94% |
| Human Resources | 52 | 12 | 23.08% |
| Sales Executive | 326 | 57 | 17.48% |

**Insight:** Sales Representatives have the highest attrition rate (39.76%), making this the most vulnerable job role in the organization.

---

## 8. Age Group vs Attrition

```sql
SELECT
    CASE
        WHEN Age BETWEEN 18 AND 25 THEN '18-25'
        WHEN Age BETWEEN 26 AND 35 THEN '26-35'
        WHEN Age BETWEEN 36 AND 45 THEN '36-45'
        WHEN Age BETWEEN 46 AND 55 THEN '46-55'
        ELSE '56-60'
    END AS Age_Group,
    COUNT(*) AS Total_Employees,
    COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) AS Employees_Left,
    ROUND(
        COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0 / COUNT(*),
        2
    ) AS Attrition_Rate
FROM employee_data
GROUP BY Age_Group
ORDER BY Attrition_Rate DESC;
```

| Age Group | Attrition Rate |
|---|---|
| 18–25 | 35.77% |
| 26–35 | 19.14% |
| 56–60 | 17.02% |
| 46–55 | 11.50% |
| 36–45 | 9.19% |

**Insight:** Employees aged 18–25 have the highest attrition rate, suggesting younger employees are significantly more likely to leave.

---

## 9. Gender vs Attrition

| Gender | Attrition Rate |
|---|---|
| Male | 17.01% |
| Female | 14.80% |

**Insight:** Male employees show a slightly higher attrition rate than female employees, though the gap is relatively small.

---

## 10. Marital Status vs Attrition

| Marital Status | Attrition Rate |
|---|---|
| Single | 25.53% |
| Married | 12.48% |
| Divorced | 10.09% |

**Insight:** Single employees are considerably more likely to leave than married or divorced employees.

---

## 11. Education Field vs Attrition

| Education Field | Attrition Rate |
|---|---|
| Human Resources | 25.93% |
| Technical Degree | 24.24% |
| Marketing | 22.01% |
| Life Sciences | 14.62% |
| Medical | 13.58% |
| Other | 13.41% |

**Insight:** Employees from Human Resources and Technical Degree backgrounds show the highest attrition rates.

---

## 12. Job Satisfaction vs Attrition

| Job Satisfaction | Attrition Rate |
|---|---|
| 1 | 22.84% |
| 2 | 16.43% |
| 3 | 16.52% |
| 4 | 11.33% |

**Insight:** Lower job satisfaction is associated with higher employee attrition.

---

## 13. Work-Life Balance vs Attrition

| Work-Life Balance | Attrition Rate |
|---|---|
| 1 | 31.25% |
| 2 | 16.86% |
| 3 | 14.28% |
| 4 | 17.65% |

**Insight:** Employees reporting poor work-life balance (level 1) are far more likely to leave the organization.

---

## 14. Monthly Income Group vs Attrition

| Income Group | Attrition Rate |
|---|---|
| Below 5K | 21.76% |
| 10K–15K | 13.51% |
| 5K–10K | 11.14% |
| 15K+ | 3.76% |

**Insight:** Higher income is strongly associated with lower attrition. Employees earning above 15K have the lowest attrition rate by a wide margin.

---

## 15. Years at Company vs Attrition

| Experience | Attrition Rate |
|---|---|
| 0–2 Years | 29.82% |
| 3–5 Years | 13.82% |
| 6–10 Years | 12.28% |
| 10+ Years | 8.13% |

**Insight:** Employees with 0–2 years of tenure have the highest attrition rate, pointing to retention challenges during the early stages of employment.

---

## Executive Summary

| Metric | Value |
|---|---|
| Total Employees | 1,470 |
| Overall Attrition Rate | 16.12% |
| Highest Department Attrition | Sales (20.63%) |
| Highest Job Role Attrition | Sales Representative (39.76%) |
| Highest Age Group Attrition | 18–25 years (35.77%) |
| Overtime Employee Attrition | 30.53% |
| Highest Marital Status Attrition | Single (25.53%) |
| Highest Education Field Attrition | Human Resources (25.93%) |
| Lowest Job Satisfaction Attrition | Level 4 (11.33%) |
| Highest Work-Life Balance Attrition | Level 1 (31.25%) |
| Highest Income Group Attrition | Below 5K (21.76%) |
| Highest Experience Group Attrition | 0–2 Years (29.82%) |

**Key takeaway:** Attrition risk is highest among young, single, early-tenure employees working overtime in low-paying Sales roles with poor work-life balance and low job satisfaction — a clear, actionable retention profile for HR intervention.
