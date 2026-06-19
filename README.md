<div align="center">

<!-- Animated Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Accenture%20HR%20Analytics&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=38&desc=Power%20BI%20Dashboard%20%7C%20Workforce%20Intelligence&descAlignY=58&descSize=16" width="100%"/>

<!-- Title & Subtitle -->
<h1>📊 Accenture HR Analytics Dashboard</h1>
<p><em>End-to-end Workforce Intelligence built on a Star-Schema data model · Powered by Power BI</em></p>

<!-- Badges Row 1 — Author & Status -->
<a href="https://github.com/RENSEE-GAJIPARA">
  <img src="https://img.shields.io/badge/Author-RENSEE%20GAJIPARA-7c3aed?style=for-the-badge&logo=github&logoColor=white"/>
</a>
<a href="https://linkedin.com/in/rensee-gajipara">
  <img src="https://img.shields.io/badge/LinkedIn-rensee--gajipara-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>
<img src="https://img.shields.io/badge/Status-Completed-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white"/>

<br/><br/>

<!-- Badges Row 2 — Tech Stack -->
<img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
<img src="https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/CSV%20Data-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
<img src="https://img.shields.io/badge/Star%20Schema-purple?style=for-the-badge&logo=databricks&logoColor=white"/>

<br/><br/>

<!-- Badges Row 3 — Stats -->
<img src="https://img.shields.io/badge/Employees%20Tracked-50%2C000-7c3aed?style=flat-square"/>
<img src="https://img.shields.io/badge/Dashboard%20Pages-5-a855f7?style=flat-square"/>
<img src="https://img.shields.io/badge/Tables%20in%20Model-11-8b5cf6?style=flat-square"/>
<img src="https://img.shields.io/badge/Attrition%20Rate-16%25-ef4444?style=flat-square"/>
<img src="https://img.shields.io/badge/Avg%20Tenure-2.5%20yrs-06b6d4?style=flat-square"/>

</div>

---

## 🖼️ Dashboard Preview

<div align="center">

> **Workforce Overview** · the flagship page of a 5-page interactive report

<img src="https://raw.githubusercontent.com/RENSEE-GAJIPARA/RENSEE-GAJIPARA/main/assets/accenture_hr_dashboard_preview.png" alt="Workforce Overview Dashboard" width="90%" style="border-radius:12px; box-shadow: 0 4px 24px rgba(124,58,237,0.25);"/>

*Replace the image path above with the actual hosted screenshot URL after uploading to your repository.*

</div>

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Key Metrics at a Glance](#-key-metrics-at-a-glance)
- [Dashboard Pages](#-dashboard-pages)
- [Data Model — Star Schema](#-data-model--star-schema)
- [Dataset Details](#-dataset-details)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [How to Use](#-how-to-use)
- [Key Insights](#-key-insights)
- [Author](#-author)

---

## 🌟 Project Overview

This project delivers a **comprehensive HR Analytics solution** modelled on an Accenture-style enterprise workforce dataset. It transforms raw HR data across 11 CSV tables into an interactive **5-page Power BI report** with cross-filtered slicers, KPI cards, custom DAX measures, and a Bing Maps employee-distribution layer.

The dashboard enables HR leaders and business partners to answer questions like:

- **Who is leaving, and why?** — Attrition breakdown by department, location, job level, and reason
- **Are we paying fairly?** — Compensation analysis across salary bands, bonus tiers, and job levels
- **Who is ready to grow?** — Performance ratings, promotion flags, and high-performer identification
- **Where is hiring effort going?** — Recruitment funnel stages and sourcing channels
- **What does training ROI look like?** — Course completion rates by category and department

---

## 📈 Key Metrics at a Glance

| Metric | Value |
|--------|-------|
| 👥 Total Employees | **50,000** |
| ✅ Active Employees | **48,006** |
| ⏱️ Avg. Tenure | **2.50 years** |
| 📉 Attrition Rate | **16.00%** |
| ♀️ Gender Ratio (Female) | **39.22%** |
| 🗓️ Data Period | **2022 – 2025** |

---

## 🖥️ Dashboard Pages

| # | Page | Description |
|---|------|-------------|
| 1 | **Workforce Overview** | KPI cards, gender composition donut, hiring trend line, employee distribution map |
| 2 | **Attrition & Retention** | Attrition drivers, department heatmaps, exit-reason breakdown |
| 3 | **Compensation Analysis** | Salary bands, bonus distribution, pay equity by gender & level |
| 4 | **Performance & Promotion** | Rating distributions, high-performer %, promotion flags by department |
| 5 | **Recruitment & Training** | Funnel stage analysis, source effectiveness, training completion by category |

All pages share a **unified slicer panel**: Year · Department · City · Gender · Job Level, with a one-click *Clear All Slicers* button.

---

## 🗂️ Data Model — Star Schema

```
                     ┌──────────────┐
                     │   DimDate    │
                     └──────┬───────┘
                            │ DateKey
         ┌──────────────────┼──────────────────┐
         │                  │                  │
  ┌──────┴──────┐    ┌──────┴──────┐   ┌──────┴──────┐
  │ DimEmployee │    │DimDepartment│   │ DimLocation │
  └──────┬──────┘    └──────┬──────┘   └──────┬──────┘
         │                  │                  │
         └──────────────────┼──────────────────┘
                            │ EmployeeID / DeptID / LocationID
            ┌───────────────┼───────────────────┐
            │               │                   │
   ┌────────┴─────┐  ┌──────┴──────┐  ┌─────────┴──────┐
   │FactAttrition │  │FactWorkforce│  │FactPerformance │
   └──────────────┘  └─────────────┘  └────────────────┘
            │               │                   │
   ┌────────┴─────┐  ┌──────┴──────┐  ┌─────────┴──────┐
   │FactCompensation│ │FactTraining │  │FactRecruitment │
   └──────────────┘  └─────────────┘  └────────────────┘
                            │
                     ┌──────┴──────┐
                     │ DimJobLevel │
                     └─────────────┘
```

**4 Dimension Tables · 6 Fact Tables · 1 Date Table**

---

## 📁 Dataset Details

### Dimension Tables

| Table | Key Columns | Description |
|-------|-------------|-------------|
| `DimEmployee` | EmployeeID, EmployeeName, Gender, DepartmentID, LocationID, JobLevelID | Master employee registry |
| `DimDepartment` | DepartmentID, DepartmentName | Department lookup |
| `DimJobLevel` | JobLevelID, JobLevel | Seniority tier lookup |
| `DimLocation` | LocationID, City | Office location lookup |
| `DimDate` | DateKey, Date, Year, Month, Quarter | Standard date dimension |

### Fact Tables

| Table | Key Columns | Description |
|-------|-------------|-------------|
| `FactAttrition` | EmployeeID, AttritionReason, DepartmentID | Employee exits with exit-reason codes |
| `FactWorkforce` | EmployeeID, CurrentSalary, TenureYears, YearsExperience, IsActive | Snapshot of active/inactive workforce |
| `FactCompensation` | EmployeeID, BaseSalary, Bonus, VariablePay | Detailed compensation breakdown |
| `FactPerformance` | EmployeeID, PerformanceRating, PromotedFlag, HighPerformerFlag | Annual review outcomes |
| `FactTraining` | EmployeeID, CourseCategory, CompletedFlag | Training completion records |
| `FactRecruitment` | CandidateID, EmployeeID, DateKey, Source, Stage | Hiring funnel data |

---

## 🛠️ Tech Stack

<div align="center">

| Tool | Purpose |
|------|---------|
| ![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black&style=flat-square) | Report authoring, DAX measures, data modelling |
| ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white&style=flat-square) | Data generation & preprocessing |
| ![CSV](https://img.shields.io/badge/CSV-217346?logo=microsoftexcel&logoColor=white&style=flat-square) | Raw dataset format |
| **DAX** | KPI calculations, dynamic measures, time intelligence |
| **Bing Maps** | Employee geospatial distribution visual |
| **Power Query (M)** | ETL, column transforms, relationship scaffolding |

</div>

---

## 📂 Project Structure

```
Accenture-HR-Analytics/
│
├── 📁 Dataset/
│   ├── DimDate.csv
│   ├── DimDepartment.csv
│   ├── DimEmployee.csv
│   ├── DimJobLevel.csv
│   ├── DimLocation.csv
│   ├── FactAttrition.csv
│   ├── FactCompensation.csv
│   ├── FactPerformance.csv
│   ├── FactRecruitment.csv
│   ├── FactTraining.csv
│   └── FactWorkforce.csv
│
├── 📁 Assets/
│   └── dashboard_preview.png
│
├── Accenture_HR_Analytics_Dashboard.pbix   ← Power BI report
├── Accenture_HR_Analytics_Report.pdf       ← Exported PDF report
└── README.md
```

---

## 🚀 How to Use

### Prerequisites
- Power BI Desktop (latest version) — [Download here](https://powerbi.microsoft.com/desktop/)

### Steps

1. **Clone or download this repository**
   ```bash
   git clone https://github.com/RENSEE-GAJIPARA/Accenture-HR-Analytics.git
   cd Accenture-HR-Analytics
   ```

2. **Open the report**
   - Launch Power BI Desktop
   - Open `Accenture_HR_Analytics_Dashboard.pbix`

3. **Refresh data (if needed)**
   - Go to **Home → Transform Data → Data Source Settings**
   - Update the CSV folder path to your local `Dataset/` directory
   - Click **Refresh** to reload all 11 tables

4. **Explore the dashboard**
   - Use the left-side navigation panel to switch between the 5 dashboard pages
   - Use the top slicer bar to filter by Year, Department, City, Gender, or Job Level
   - Click **Clear All Slicers** at the bottom-left to reset all filters

---

## 💡 Key Insights

> Derived from the Workforce Overview page (all filters cleared)

- **Equal department distribution** — All departments have the same headcount, suggesting a deliberately balanced organizational structure
- **Low average tenure (2.5 yrs)** — The company is continuously onboarding new talent; high hiring velocity is accompanied by relatively short average tenures
- **High employee retention (96%)** — Only ~2,000 of 50,000 employees are inactive, indicating strong overall engagement
- **16% attrition rate** — While retention is high in volume, the attrition rate signals meaningful turnover worth investigating by department and role level
- **39% female workforce** — Gender diversity is present but the 61/39 split indicates room for growth toward parity

---

## 👤 Author

<div align="center">

<a href="https://github.com/RENSEE-GAJIPARA">
  <img src="https://img.shields.io/badge/GitHub-RENSEE%20GAJIPARA-181717?style=for-the-badge&logo=github&logoColor=white"/>
</a>
&nbsp;
<a href="https://linkedin.com/in/rensee-gajipara">
  <img src="https://img.shields.io/badge/LinkedIn-rensee--gajipara-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

<br/><br/>

**B.Tech in AI & Data Science** · SCET Surat (2023 – 2027)

*Aspiring Data Analyst & ML Engineer · Open to AI/ML and Data Science internships*

</div>

---

<div align="center">

<!-- Animated Footer -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer&animation=twinkling" width="100%"/>

<sub>⭐ If this project helped you, give it a star on GitHub!</sub>

</div>
