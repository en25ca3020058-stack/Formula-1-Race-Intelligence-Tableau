# 🏎️ Formula 1 Race Intelligence - Tableau BI Project

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![F1](https://img.shields.io/badge/Formula_1-FF1801?style=for-the-badge&logo=formula1&logoColor=white)
![Data](https://img.shields.io/badge/Records-6%2C464_Entries-blue?style=for-the-badge)
![Seasons](https://img.shields.io/badge/Seasons-17_Championships-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

A comprehensive Business Intelligence and Race Analytics platform built on **6,464 Formula 1 race records spanning 17 seasons (2007–2023)**. This project delivers interactive dashboards, statistical benchmarking, and diagnostic insights across three key motorsport operational scenarios.

---

## 📑 Table of Contents
1. [Executive Summary](#-executive-summary)
2. [Project Scenarios](#-project-scenarios)
3. [Project Architecture (8 Epics & 14 Tasks)](#-project-architecture-8-epics--14-tasks)
4. [Dataset Specifications](#-dataset-specifications)
5. [Tableau Dashboards Overview](#-tableau-dashboards-overview)
6. [Core Calculated Fields](#-core-calculated-fields)
7. [Repository Structure](#-repository-structure)
8. [How to Open and Run](#-how-to-open-and-run)
9. [Tableau Public Live Demo](#-tableau-public-live-demo)

---

## 🏁 Executive Summary
Formula 1 is a sport where fractions of a second and data-driven decisions decide world championships. This project unifies 17 seasons of telemetry and race classification data into an actionable visual intelligence suite using **Tableau Desktop / Tableau Public**. 

The system empowers team strategists, broadcast journalists, and FIA compliance analysts to transition from raw telemetry data into intuitive visual diagnostics.

---

## 🎯 Project Scenarios

### 🏎️ Scenario 1: Mr. Arnold - F1 Team Performance Strategist
- **Persona**: Rajan, Senior Performance Strategist at a mid-tier constructor.
- **Objective**: 
  - Benchmark championship points trajectory against dominant powerhouses (**Red Bull Racing** and **Mercedes**).
  - Evaluate tyre compound longevity and efficiency (**Soft, Medium, Hard, Intermediate**) across circuit archetypes (*Street, High-Speed Power, High-Downforce Technical*).
  - Identify emerging global driver talent pools and recruitment pipelines.

### 🎙️ Scenario 2: Ms. Lisa - Motorsport Broadcast Analyst
- **Persona**: Divya, Motorsport Data Journalist & Broadcast Analyst.
- **Objective**: 
  - Rapidly retrieve historical driver performance leaderboards with running total career points.
  - Visualize global Grand Prix hosting frequency via geographic distribution maps.
  - Produce podium achievement distributions by constructor and driver for live pre/post-race coverage.

### 🛡️ Scenario 3: Mr. Gilchrist - F1 Technical Regulation Analyst
- **Persona**: Arvind, FIA Technical Regulation Compliance Analyst.
- **Objective**: 
  - Diagnose Did Not Finish (**DNF**) patterns across teams and circuit conditions.
  - Categorize failures into *Engine Failures, Brake Failures, Collisions / Incidents, and Mechanical Failures*.
  - Evaluate multi-season driver reliability scores across regulatory rule changes (V8 era, 1.6L Turbo-Hybrid era, and Ground Effect era).

---

## 🏗️ Project Architecture (8 Epics & 14 Tasks)

| Epic | Epic Title | Task ID | Deliverable |
| :--- | :--- | :--- | :--- |
| **Epic 1** | **Data Ingestion & Schema Modeling** | `TASK-1.1` | Clean, format, and parse 6,464 race records into normalized relational CSV structure. |
| | | `TASK-1.2` | Define calculated dimensions (DNF classification, circuit archetypes, completion metrics). |
| **Epic 2** | **Constructor Trajectory Analytics** | `TASK-2.1` | Build multi-line season points progression benchmarked vs Mercedes & Red Bull. |
| | | `TASK-2.2` | Implement moving averages and constructors standings variance indicators. |
| **Epic 3** | **Tyre Compound Strategy Dynamics** | `TASK-3.1` | Create tyre compound points efficiency matrix across Soft, Medium, Hard, and Intermediate. |
| | | `TASK-3.2` | Segment tyre wear and performance against circuit archetypes (Street vs Technical). |
| **Epic 4** | **Broadcast & Driver Leaderboards** | `TASK-4.1` | Build dynamic running total cumulative points leaderboard across all 17 seasons. |
| | | `TASK-4.2` | Design KPI stat cards for wins, podium finishes, pole positions, and career longevity. |
| **Epic 5** | **Geographic Circuit Intelligence** | `TASK-5.1` | Construct global symbol and density map for Grand Prix hosting nations. |
| | | `TASK-5.2` | Map driver talent pool distribution by nationality and podium conversion rates. |
| **Epic 6** | **Reliability & DNF Diagnostics** | `TASK-6.1` | Group granular mechanical issues into standard failure types (Engine, Brake, Mechanical). |
| | | `TASK-6.2` | Develop Driver Reliability stacked bar chart measuring completion percentage. |
| **Epic 7** | **Interactive Dashboard Systems** | `TASK-7.1` | Build 3 customized, high-density Tableau dashboards tailored to each stakeholder. |
| | | `TASK-7.2` | Configure bidirectional cross-filtering, highlight actions, and custom Viz-in-Tooltips. |
| **Epic 8** | **Storytelling & Executive Report** | `TASK-8.1` | Publish an interactive 5-point Tableau Storyboard synthesizing strategic recommendations. |

---

## 📊 Dataset Specifications
- **Total Records**: 6,464 Rows
- **Championship Seasons**: 17 Seasons (2007 through 2023)
- **Primary Key**: `Race_ID` (1 to 323) + `Driver_Name`
- **Fields (19 Columns)**:
  - `Race_ID`, `Season`, `Round`, `Grand_Prix`, `Circuit_Name`, `Circuit_Type`, `Country`
  - `Driver_Name`, `Driver_Nationality`, `Constructor_Name`, `Grid_Position`, `Finishing_Position`
  - `Points`, `Status`, `DNF_Category`, `Tyre_Compound`, `Laps_Completed`, `Podium_Finish`, `Race_Completion_Flag`

---

## 🧮 Core Calculated Fields (Tableau)

### 1. DNF Category Grouping
```tableau
IF CONTAINS(LOWER([Status]), "engine") OR CONTAINS(LOWER([Status]), "power unit") THEN "Engine Failure"
ELSEIF CONTAINS(LOWER([Status]), "brake") THEN "Brake Failure"
ELSEIF CONTAINS(LOWER([Status]), "collision") OR CONTAINS(LOWER([Status]), "accident") THEN "Collision / Incident"
ELSEIF CONTAINS(LOWER([Status]), "gearbox") OR CONTAINS(LOWER([Status]), "suspension") 
    OR CONTAINS(LOWER([Status]), "hydraulics") OR CONTAINS(LOWER([Status]), "mechanical") THEN "Mechanical Failure"
ELSEIF [Status] = "Finished" OR CONTAINS([Status], "Lap") THEN "Classified Finish"
ELSE "Other DNF"
END
```

### 2. Driver Reliability Score (%)
```tableau
SUM([Race_Completion_Flag]) / COUNT([Race_ID])
```

### 3. Cumulative Championship Points
```tableau
RUNNING_SUM(SUM([Points]))
```

### 4. Podium Conversion Rate
```tableau
SUM([Podium_Finish]) / COUNT([Race_ID])
```

---

## 📂 Repository Structure
```
Formula-1-Race-Intelligence/
│
├── Dataset/
│   └── f1_race_intelligence_data.csv       # 6,464 clean records across 17 seasons
│
├── Workbook/
│   └── Formula_1_Race_Intelligence.twb     # Interactive Tableau Workbook (Worksheets & Dashboards)
│
├── Screenshots/
│   ├── dashboard_1_team_strategist.png     # Dashboard 1 preview
│   ├── dashboard_2_broadcast_hub.png       # Dashboard 2 preview
│   └── dashboard_3_fia_regulations.png     # Dashboard 3 preview
│
├── Documentation/
│   ├── Data_Dictionary.md                  # Column definitions and metadata
│   └── Project_Report.md                   # Full scenario analysis and regulatory recommendations
│
└── README.md                               # Project documentation
```

---

## 💻 How to Open and Run
1. **Clone or Download** this repository to your local computer.
2. Ensure you have **Tableau Desktop** (or **Tableau Public** free edition) installed.
3. Open `Workbook/Formula_1_Race_Intelligence.twb`.
4. If prompted to locate the data source, browse to `Dataset/f1_race_intelligence_data.csv`.
5. Interact with the dashboards, filter by season, constructor, or driver.

---

## 🌐 Tableau Public Live Demo
- **Live Interactive Dashboard**: `[Insert your Tableau Public link here]`
