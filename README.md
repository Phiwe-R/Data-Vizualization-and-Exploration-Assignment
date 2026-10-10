# COMS4060A / COMS7056A: Data Exploration & Analysis Assignment 1

**University of the Witwatersrand**  
**Course:** Data Visualization and Exploration (COMS4060A/COMS7056A)  
**Instructor:** Muhammad Nasir  
**Submission Deadline:** September 7, 2026  
**Link to OverLeaf Folder:** [**OverLeaf Folder**](https://www.overleaf.com/9586117564gbvjkmmznxjf#c68e3e)
---

## 📌 Project Overview
This repository contains our group's implementation for **Assignment 1**, focusing on cleaning, feature engineering, and extracting insights from a messy, user-submitted global fuel logs dataset (`logbook_assignment1.csv`). 

The project delivers:
1. **`notebook.ipynb`**: A single, clean Jupyter notebook containing sequential code execution and explicit question numbering.
2. **`report.pdf`**: A formal research document presenting all figures, analyses, and domain interpretations formatted in the **NeurIPS LaTeX** template.

---

## 👥 Team Roles & Task Distribution

Total Assessment Marks: **105 Marks**

---

### 🟢 Person 1: Data Preprocessing & Cleaning (28 Marks)
**Focus:** Data pipeline ingestion, string parsing, datatype conversions, missing value handling, and baseline summary statistics.

* **Section 1.1 — Date Fields [7 Marks]**
  * Identify percentage of invalid `date_fueled` entries.
  * Apply `date_captured` as a proxy where `date_fueled` is invalid.
  * Convert column to datetime (`NaT` for invalid records).
  * Filter date range (remove dates prior to 2005 or in the future).
  * Plot and comment on the distribution of fueling dates.
* **Section 1.2 — Numeric Fields [21 Marks]**
  * Calculate missing percentages for `gallons`, `miles`, and `odometer`.
  * Impute missing values using interdependent relationships ($miles = gallons \times mpg$).
  * Clean thousands delimiters (commas) and cast object strings to floats.
  * Plot numeric distributions and evaluate sanity.
  * Compute full descriptive statistics (mean, std, max, min, mode, quartiles) and interpret results.

---

### 🔵 Person 2: Feature Engineering & Global Fleet Exploration (22 Marks)
**Focus:** Regex extraction, unit standardization, and macroeconomic/global-scale fleet visualization.

* **Section 2 — Feature Engineering [12 Marks]**
  * Parse currency symbols and codes (accounting for Swiss Franc period notation).
  * Extract numerical floats for `total_spent` and `cost_per_gallon`.
  * Extract `car_make`, `car_model`, `car_year`, and `User ID` from the vehicle URL string.
  * Convert imperial measurements to metric (`litres filled` choosing US/UK gallon standards, `km driven`, and `litres per 100km`).
* **Section 3 — Vehicle Exploration [10 Marks]**
  * Plot unique active users per country (using currency proxy).
  * Plot daily active usage over time to evaluate app adoption.
  * Analyze vehicle age distribution per country relative to fueling date.
  * Identify most popular vehicle makes and models globally.

---

### 🟣 Person 3: Outlier Removal & Advanced Modeling (28 Marks)
**Focus:** Multi-currency anomaly detection, missed fill-up logic, feature interactions, and ML feature importance.

* **Section 4.1 — Outlier Removal [13 Marks]**
  * Identify top 5 currencies by transaction volume.
  * Define and justify domain rules/thresholds for multi-currency outlier removal (e.g., cross-currency unit mismatches).
  * Report total count of removed anomalous records.
* **Section 4.2 — Fuel Efficiency (Part 1) [15 Marks]**
  * **Q1:** Compare Jan 2022 cost per litre across top countries converted to ZAR using average exchange rates.
  * **Q2:** Develop heuristic rule using odometer deltas to detect missed fill-up logging events.
  * **Q3:** Plot and explain average distance (km) per tank across countries.
  * **Q4:** Plot and analyze the relationship between vehicle age and distance driven between fill-ups.
  * **Q8:** Construct correlation matrix between fuel efficiency, distance, age, and vehicle model.
  * **Q9:** Train a Random Forest model to compute feature importance rankings and contrast with correlation findings.

---

### 🟡 Person 4: Localized Case Studies & Report Compilation (27 Marks)
**Focus:** Vehicle sanity benchmarks, South African economic/behavioral analysis, and NeurIPS LaTeX integration.

* **Section 4.2 — Fuel Efficiency (Part 2) [11 Marks]**
  * **Q5:** Sanity check fuel efficiency values for top 5 South African vehicles.
  * **Q6:** Determine most fuel-efficient vehicles per country and evaluate realistic thresholds.
  * **Q7:** Compare fuel efficiency variations across seasons for top 5 Canadian vehicles.
* **Section 4.3 — Fuel Usage in South Africa [16 Marks]**
  * Filter dataset exclusively to South African drivers (ZAR currency).
  * Plot SA fuel prices over time.
  * Evaluate refueling volume spikes on Tuesdays relative to other days.
  * Isolate dataset to 1st Tuesday and 1st Wednesday of each month.
  * Engineer price movement indicator (Price UP vs. Price DOWN).
  * Test consumer behavior hypotheses regarding price-change days (1st Wednesday drop vs. 1st Tuesday hike).
* **Integrator & Group Lead Responsibilities:**
  * Assemble team code sections into the master Jupyter Notebook.
  * Merge team write-ups and compiled figures into the NeurIPS LaTeX document.

---

