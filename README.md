# 🏥 NewLife Hospital Hub  
### 🌐 Clinical Data Analysis (2024–2030): Synthetic Hospital Admissions  
*Power BI • SQL • BI Analysis*

![alt text](./pics/image.png) <!-- Replace with final banner path -->

---

## 📌 Table of Contents
- [🏥 NewLife Hospital Hub](#-newlife-hospital-hub)
    - [🌐 Clinical Data Analysis (2024–2030): Synthetic Hospital Admissions](#-clinical-data-analysis-20242030-synthetic-hospital-admissions)
  - [📌 Table of Contents](#-table-of-contents)
  - [📊 Project Background](#-project-background)
  - [📃 Workflow](#-workflow)
  - [🧱 Data Structure \& ERD](#-data-structure--erd)
  - [📈 Executive Summary](#-executive-summary)
    - [Top 3 insights for leadership:](#top-3-insights-for-leadership)
  - [🔍 Insights Deep Dive](#-insights-deep-dive)
    - [🏥 Category 1 — Network-Wide Admission Performance](#-category-1--network-wide-admission-performance)
    - [🦠 Category 2 — Infection Control \& Patient Safety](#-category-2--infection-control--patient-safety)
    - [☠️ Category 3 — Mortality Risk \& Severity Management](#️-category-3--mortality-risk--severity-management)
    - [🚀 Category 4 — Strategies Outcome \& Future Impact](#-category-4--strategies-outcome--future-impact)
  - [🎯 Recommendations](#-recommendations)
  - [⚠️ Assumptions \& Caveats](#️-assumptions--caveats)
  - [📚 Learnings \& Practice](#-learnings--practice)
  - [Next Steps](#next-steps)
  - [📎 Resources \& Files](#-resources--files)
  - [About me](#about-me)

---

## 📊 Project Background
This **learning & portfolio project** project **simulates a hospital network BI scenario** to practice SQL-driven data generation, data profiling, KPI calculation, and Power BI dashboard development. Practical BI delivery skills are showcased in a healthcare context.

It uses a simple **synthetic dataset** representing 6 daily hospital metrics across 10 fictitious facilities over multiple years. The goal was to:

- Explore trends in admissions, readmissions, infections & mortality
- Practice transparency around data quality and assumptions while demonstrating business thinking and insights capabilities
- Present insights visually for decision-makers
- Present a data analysis project professionally in a GitHub repo such as this present one

Core KPIs analyzed:
- 🏥 Admissions  
- 🔁 Readmissions / Admissions Rate  
- 🦠 Infections / Admissions Rate  
- ☠️ Deaths / Infections Rate  

This analysis was performed with:  
**SQL** → Built a fully synthetic, HIPAA-safe clinical dataset of 20M records using SQL-based data generation loops (**MS SQL Server**).  
**Power BI** → interactive report with branding and key visualizations - link to the report itself [here](https://app.powerbi.com/view?r=eyJrIjoiMzE0YjU5YTMtMGRiZC00ZjJjLWI3YzctMjQ2NWNjYjEyZmIxIiwidCI6ImM5YTM3Nzk4LTFjNGQtNDY2Ni04YTczLTMzY2M2MzE0ZmVmZSJ9&pageName=46815e9473cb662ad64a) and to the report project folder [here](./Power%20BI%20Project). 

---

## 📃 Workflow
1️⃣ **SQL — Data creation**  
Simulated 20M rows of hospital data using loops in MS SQL Server  - find the SQL code [here](./SQL/SQL_Code_For_SyntheticData.sql).  

2️⃣ **SQL — Data profiling & Update**  
Secondly, more SQL code was used to do data profiling over the dataset as it is more time-efficient do so at the source  - find the SQL code [here](./SQL/SQL_for_Profiling_Data.sql).
In that same SQL code, an update of the dataset was simulated, meaning more data was added on top of the first initial data (more years of data). That SQL code prevented years mismatch, ensuring data integrity. 

3️⃣ **Power BI — Import & Modeling Basics**  
Then only relevant columns were imported into Power BI via a SQL query and processed and analysed for report building.  
Following best practices, a date table was created using DAX, ensuring proper date hierarchy.  
The simplicity of the dataset did not call for data modeling.  
Usually the report is then safely and selectively distributed to members and stakeholders of the organization. Here it was instead publicly made available without any secured access needed. 

---

## 🧱 Data Structure & ERD

The data model consists of **6 clinical columns** with data spanning over 6 years - 2024 to 2030 (this is not a forecast):

| Table | Description | Total |
|---|---|---:|
| `Admissions` | All patient intake per hospital & year | 1.33B |
| `Readmissions` | Repeat visits within a defined post-care window | 61M |
| `Infections` | Clinical infection incidents | 27M |
| `Deaths` | In-hospital mortality | 16M |

HospitalID ranges from 1 to 10 and represents each facility.  
AdmissionDate was linked to a new date table for full, granular time hierarchy. 

📌 ERD:

![Simple ERD](./pics/image-1.png)  

The column 'AverageLengthOfStay' was excluded during import within Power BI as it was not needed.

→ Simple data structure but sufficient for demonstrating BI mechanics

---

## 📈 Executive Summary
*Reminder: This is a fictitious summary, based on the analysis of the synthetic data.*  

> **The NewLife Hospitals Hub delivers exceptionally consistent and safe care across the network — with major clinical improvements in 2030 explaining a sharp drop in the same year.**

### Top 3 insights for leadership:
1️⃣ **Performance is balanced across all 10 hospitals**  
Variance across all hospitals for each column total is **<0.03%**, showing a unified system.

2️⃣ **Clinical care is high-value and safe**  
| Metric | Result |
|---|---:|
| Readmissions / Admissions | **5%** |
| Infections / Admissions | **2%** |
| Deaths / Admissions | **1%** |

3️⃣ **A transformative improvement occurs post-2029**  
→ Sharp drop in admissions, infections & deaths: ~11% drop in each category between 2029 and 2030  
→ Effectively lowering network burden: ~17M less admissions (from ~192M to ~175M)

📊 Dashboard Screenshot:  
Re-admissions / Admissions
![Re-admissions / Admissions](./pics/image-2.png)

Infections / Admissions
![Infections / Admissions](./pics/image-3.png)

Deaths / Admissions
![Deaths / Admissions](./pics/image-4.png)

---

## 🔍 Insights Deep Dive

---

### 🏥 Category 1 — Network-Wide Admission Performance
- Total: **1.33bn**
- Year-over-year stable until **2029**
- **Major decline in 2030** → strategic prevention outcome starting to show
- Admission Variance between hospitals: **0.019%**

📌 Interpretation:  
> Hub is distributing patient load efficiently → no overload risk

![admissions performance](./pics/image-5.png)

---

### 🦠 Category 2 — Infection Control & Patient Safety
- Total infections: **27M** → **2%** of admissions
- Infection Variance across hospitals: **0.021%**
- Significant drop starting **2030**

📌 Interpretation:
> Infection prevention protocols are strong, standardized & improving

![Infection Control & Patient Safety](./pics/image-6.png)

---

### ☠️ Category 3 — Mortality Risk & Severity Management
- Total deaths: **16M** → **1%** of admissions
- **~60% of infections result in death**  
→ Indicates that infections represent *high-severity cases*

📌 Interpretation:
> Network treats **highly critical** patients while maintaining stable survival rates

![Mortality Risk & Severity](./pics/image-7.png)

---

### 🚀 Category 4 — Strategies Outcome & Future Impact
| Phase | Trend | Impact |
|---|---|---|
| 2024–2029 | Stable patterns | Predictable resource planning |
| 2030 | Sharp Metrics decline | Reduced admissions burden & cost |

📌 Interpretation:
> Prevention & digital health strategies significantly reduce patients' hospital dependency

![Strategies Outcome](./pics/image-8.png)

---

## 🎯 Recommendations

| Area | Action |
|---|---|
| Prevention & Digital Health strategies | Scale preventive care initiatives sooner to accelerate benefits |
| Severe infection case mortality | Deploy AI-based risk detection & rapid AI clinical alert systems. Investigate demographic and social data of the state for more explanations on the infection rate |
| Readmissions at 5% | Strengthen post-discharge digital care & telehealth monitoring |
| Uniform performance | Maintain standardized training & protocols across the network |
| Decline in hospital load | Gradual workforce shifts to outpatient & tele-care. Adjust staffing models gradually to avoid over-capacity |

---

## ⚠️ Assumptions & Caveats
- High mortality/infection ratio is due to **case severity**, not poor care  
- Drop in hospital dependency assumes **prevention and digital-care adoption** were initiated and are still active - present time is assumed to be sometime after year 2030 (it is not a forecast)
- No hospital identifiers columns for privacy and **HIPAA compliance** concerns 

**Data Limitations:**
- Fully synthetic dataset — not based on real patients
- Simplified metrics — no demographics, no diagnosis groups
- Limited feature depth restricts causal insights


---
## 📚 Learnings & Practice
**SQL:**  
- Practiced loops, random value generation using MS SQL Syntax
- Reinforced data profiling importance early in pipeline  

**Power BI**
- Slicers, metrics, SQL import
- DAX Date dimension for proper filtering
- Applied Storytelling and Design best practices
- Complex bookmarks for an efficient interactive UI

**Healthcare Domain Knowledge:**  
- Gained initial experience analyzing core hospital performance metrics (admissions, readmissions, infections, mortality)
- Recognized the importance of **additional clinical context** for deeper insights
- Identified key missing variables:
  - Age groups, gender, ZIP code  
  - Diagnosis / severity indicators  
  - Admission department or case type  
- Understood how richer data would enable:
  - Improved patient segmentation  
  - More realistic risk and outcome comparisons  
  - Increased decision-making relevance for healthcare stakeholders  

---
## Next Steps
This work could evolve with the following additions: 

**Benchmarking :**

- Compare each hospital against:
- Hub average
- National benchmark standards
- Best-in-class hospital inside network

➡ Introduces competitive context.

**Cost & Finance Layer for Avoidable Cost Savings :**  
Add financial performance tables:

- Cost per Admission
- Cost per Readmission (roughly ×2)
- ICU daily cost multipliers
- Bed turnover revenue effects

With those we can calculate **Avoidable Cost Savings** from admissions, readmissions, infections, ICU days, etc., by extracting a baseline volume and/or rate, and then capturing data on new volume (after improvement). 

**Demographics, Case & Clinical Severity Data:**  
Data on the followings will further deepen analysis on Mortality/Infection, patient segmentation, and make sharper KPIs: 

- age groups, gender, zip, insurance type
- comorbidity index, admission type, ICD-10 group, ICU/Regular Ward

---

## 📎 Resources & Files
- Power BI: following best practices, the report source files are available as a packaged project file [here](/Power%20BI%20Project/).
- The Power BI report is available online [here](https://app.powerbi.com/view?r=eyJrIjoiMzE0YjU5YTMtMGRiZC00ZjJjLWI3YzctMjQ2NWNjYjEyZmIxIiwidCI6ImM5YTM3Nzk4LTFjNGQtNDY2Ni04YTczLTMzY2M2MzE0ZmVmZSJ9&pageName=46815e9473cb662ad64a).
- SQL: all the sql queries that were used in the project are within 2 sql files that are saved in this [folder](./SQL/).

---

## About me
Jean-Yves Tran | [LinkedIn](https://www.linkedin.com/in/jytran-datascience/) | [Professional Website](https://datascience-jy.com/data-analyst-portfolio)  

I am a Junior Data Analyst transitioning from 9+ years as a senior freelance motion designer. I use Power BI, SQL & Python to turn raw data into clear, actionable reports for stakeholders. 

I love working with data because I enjoy finding root causes and explanations behind problems. Understanding how numbers reflect business processes feels like one of the most concrete ways to grasp how a company truly operates. I also appreciate that my work can influence future decisions and create real impact. I’m also driven by continuous learning, and data analytics gives me that every day.