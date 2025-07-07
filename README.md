# HR Analytics Project – Employee Segmentation and Attrition Analysis

This repository presents an analytical exploration of an HR dataset to understand employee behavior, satisfaction, performance, and attrition trends using SQL queries.

---

## 📁 Dataset Overview

The dataset `HR_Analytics.xlsx` includes structured employee data with the following attributes:

* **Demographics**: Age, Gender, Marital Status, Age Group
* **Job Information**: Department, Job Role, Job Level
* **Compensation**: Monthly Income, Percent Salary Hike, Salary Slab
* **Satisfaction & Performance**: Job Satisfaction, Environment Satisfaction, Performance Rating, Work-Life Balance
* **Attrition Details**: Attrition, Years at Company, Years in Current Role

---

## 🔹 Project Objectives

The main objectives of the analysis are:

1. **Attrition & Business Travel**: Investigate if frequent business travel is linked to attrition.
2. **Satisfaction vs Attrition**: Determine whether low satisfaction scores contribute to employee churn.
3. **Age-based Analysis**: Analyze attrition, satisfaction, and performance across different age groups.
4. **Gender-based Insights**: Identify patterns based on gender with regard to attrition and performance.
5. **Salary Influence**: Assess whether salary slabs affect job satisfaction and attrition.
6. **Salary Hike & Retention**: Examine the impact of salary hikes on retention.
7. **Promotion & Work Tenure**: Understand if total working years or years at a company affect promotion or attrition.
8. **Current Role Duration**: Explore how long employees remain in a role before leaving.
9. **Work-Life Balance Impact**: Evaluate how balance affects performance and attrition.
10. **Employee Segmentation**: Segment employees based on demographics, performance, satisfaction, and income.

---

## 👨‍💼 Sample SQL Query: Employee Segmentation

```sql
SELECT  
  AgeGroup, Gender, MaritalStatus, Education, Department, 
  JobSatisfaction, EnvironmentSatisfaction, WorkLifeBalance, 
  PerformanceRating,
  CASE  
    WHEN MonthlyIncome < 3000 THEN 'Low Income' 
    WHEN MonthlyIncome BETWEEN 3000 AND 8000 THEN 'Mid Income' 
    ELSE 'High Income' 
  END AS IncomeGroup,
  CASE  
    WHEN PercentSalaryHike < 10 THEN 'Low Hike' 
    WHEN PercentSalaryHike BETWEEN 10 AND 15 THEN 'Moderate Hike' 
    ELSE 'High Hike' 
  END AS HikeGroup,
  COUNT(EmpID) AS NumEmployees
FROM HR_Analytics
GROUP BY  
  AgeGroup, Gender, MaritalStatus, Education, Department, 
  JobSatisfaction, EnvironmentSatisfaction, WorkLifeBalance, 
  PerformanceRating,
  IncomeGroup, HikeGroup
ORDER BY NumEmployees DESC;
```

---

## 💡 Insights & Outcomes

This analysis enables:

* Identification of key factors influencing attrition
* Understanding satisfaction levels across departments and roles
* Strategic workforce segmentation for better HR decision-making
* Data-driven improvements in employee engagement and retention

---

## 📊 Tools Used

* **SQL** for data querying and analysis
* **Spreadsheet tools** for preprocessing and dataset understanding

---

## 🚀 How to Use

1. Clone the repository
2. Import the `HR_Analytics.xlsx` dataset into your SQL database
3. Run the SQL queries provided in the `queries.sql` file (or script them in your interface)
4. Modify or extend the queries to explore more patterns

---

## 🖋️ License

This project is for educational and academic use only.

---

Feel free to fork the project, use it for analysis practice, or enhance it further with data visualizations and dashboards.

---

> Made with ❤️ by Group H | JECRC University
