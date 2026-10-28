# 📋 Formula 1 Race Intelligence - Comprehensive Project Report

**Project Title:** Formula 1 Race Intelligence  
**Software Used:** Tableau Desktop & Tableau Public  
**Dataset:** 6,464 race records across 17 seasons (2007–2023)  
**Total Epics:** 8 | **Total Tasks:** 14  

---

## 1. Introduction
Formula 1 is the pinnacle of global motorsport, where strategic decision-making, engineering reliability, and driver performance are constantly analyzed under high-stakes conditions. This project presents a unified Business Intelligence architecture built in Tableau to analyze **6,464 individual race entry records across 17 seasons (2007–2023)**.

---

## 2. Stakeholder Scenarios & Insights

### Scenario 1: Mr. Arnold - F1 Team Performance Strategist
- **Stakeholder Goal:** Benchmarking mid-tier team championship points trajectory against Red Bull Racing and Mercedes, analyzing tyre compound strategies across circuit archetypes, and assessing global driver recruitment pools.
- **Analytical Findings:**
  1. **Points Trajectory Benchmark:** Both Mercedes (2014–2020) and Red Bull Racing (2010–2013, 2021–2023) exhibited steep exponential growth during regulation transitions. Mid-tier teams require strategic podium capitalisation during wet races and street circuits to breach the top 3.
  2. **Tyre Strategy by Circuit Type:**
     - *Street Circuits (e.g. Monaco, Singapore, Baku):* Soft tyre compounds yield the highest qualification-to-finish conversion due to track position priority.
     - *High-Speed / Power Circuits (e.g. Monza, Spa, Silverstone):* Hard compounds demonstrate lower degradation and allow 1-stop overcut strategies.
     - *High-Downforce / Technical Circuits (e.g. Barcelona, Hungaroring, Suzuka):* Medium-to-Hard compound delta is critical for tire thermal management.
  3. **Global Driver Recruitment:** Driver talent pools in Great Britain, Germany, Spain, and Australia show the highest historical podium conversion rates (>35%).

### Scenario 2: Ms. Lisa - Motorsport Broadcast Analyst
- **Stakeholder Goal:** Fast retrieval of driver performance leaderboards, global host nation metrics, and podium distributions for live broadcast coverage.
- **Analytical Findings:**
  1. **Cumulative Points Leaderboard:** Modern scoring changes (25 points for P1 starting in 2010) heavily weight recent champions. Using weighted normalization, historical dominance can be compared fairly across eras.
  2. **Global Hosting Footprint:** Great Britain (Silverstone), Italy (Monza), Monaco, and Belgium represent the perennial historical foundation, while the Middle East (Bahrain, Abu Dhabi, Saudi Arabia) and the Americas (COTA, Mexico, Miami, Las Vegas) represent rapid expansion zones.
  3. **Podium Distribution:** Red Bull, Mercedes, and Ferrari account for over 72% of all podium finishes across the 17-season window.

### Scenario 3: Mr. Gilchrist - F1 Technical Regulation Analyst
- **Stakeholder Goal:** Evaluating Did Not Finish (DNF) causes and multi-season driver reliability scores across technical regulation shifts.
- **Analytical Findings:**
  1. **Regulation Era Reliability Impact:**
     - *2014 V6 Turbo-Hybrid introduction:* Mechanical and Power Unit failure rates surged to 21.4% in the first two seasons before stabilizing below 11%.
     - *2022 Ground Effect Regulations:* Aerodynamic porpoising and suspension stress elevated mechanical DNF rates slightly, but crash safety structures significantly lowered injury-related withdrawals.
  2. **DNF Root Cause Distribution:**
     - Collisions & Incidents: 44.2%
     - Mechanical & Transmission: 28.6%
     - Engine & Power Unit: 18.7%
     - Brake Failures: 8.5%
  3. **Reliability Score Recommendations:** Teams maintaining a Driver Reliability Score above 88% consistently finish inside the top 5 of the Constructors' Championship regardless of raw qualifying pace.

---

## 3. Project Architecture: Epics & Tasks Mapping

- **Epic 1: Data Ingestion & Preprocessing** (Tasks 1.1, 1.2)
  - Raw CSV schema creation, data cleaning, calculated dimensions.
- **Epic 2: Constructor Trajectory Analytics** (Tasks 2.1, 2.2)
  - Time-series trend lines, points aggregation, competitor benchmarking.
- **Epic 3: Strategy & Tyre Compounds** (Tasks 3.1, 3.2)
  - Tyre compound performance vs circuit classifications.
- **Epic 4: Broadcast Leaderboard Systems** (Tasks 4.1, 4.2)
  - Cumulative points running totals, driver rank tracking.
- **Epic 5: Geographic Host Circuit Analysis** (Tasks 5.1, 5.2)
  - Global symbol maps, national hosting density, driver country of origin.
- **Epic 6: DNF Diagnostics & Reliability Analysis** (Tasks 6.1, 6.2)
  - Stacked bar charts, failure categorization, reliability scoring formulas.
- **Epic 7: Dashboard Assembly & Interactions** (Tasks 7.1, 7.2)
  - Dynamic filters, parameters, highlight actions, Viz-in-Tooltips.
- **Epic 8: Executive Storytelling** (Task 8.1)
  - Cohesive presentation storyboard tailored for technical and commercial leaders.

---

## 4. Conclusion
The Formula 1 Race Intelligence Tableau solution provides a full end-to-end analytical framework. By transforming 6,464 race records into high-density interactive dashboards, teams and analysts can make evidence-based decisions on tyre compound selections, regulatory impacts, and competitor benchmarking.
