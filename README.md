# PROBLEM 1: CKD Progression Analysis – Synthea Dataset

## Overview

This problem analyzes the progression of Chronic Kidney Disease (CKD) stages in synthetic patient data from the Synthea dataset. The goal is to track how patients transition through CKD stages over time and to quantify the average duration spent at each stage.

## Data Sources

- **conditions.csv**: Used to identify CKD diagnosis codes and provider-assigned staging.
- **observations.csv**: Used to extract laboratory eGFR values for objective, guideline-based CKD staging and progression tracking.

Other Synthea CSVs were not used to maintain focus on disease stage transitions based on diagnosis and laboratory data.

## CKD Staging (by eGFR)

| Stage | eGFR (mL/min/1.73 m²) | Description                           |
|-------|-----------------------|---------------------------------------|
| G1    | ≥ 90                  | Normal or high (with kidney damage)   |
| G2    | 60–89                 | Mild decrease (with kidney damage)    |
| G3a   | 45–59                 | Mild to moderate decrease             |
| G3b   | 30–44                 | Moderate to severe decrease           |
| G4    | 15–29                 | Severe decrease                       |
| G5    | < 15                  | Kidney failure (ESRD)                 |

## Key Results

Mean and median time (in days) for each CKD stage transition across patients:

| From | To   | Mean (days) | Median (days) | Count |
|------|------|-------------|---------------|-------|
| G1   | G2   |   951.3     |   724.5       |  10   |
| G2   | G3a  |  1556.8     |  1764.0       |   5   |
| G3a  | G3b  |    85.4     |    98.0       |   5   |
| G3b  | G4   |   795.7     |   868.0       |   3   |
| G4   | G5   |   238.0     |   238.0       |   1   |

- **Early stages (G1→G2, G2→G3a):** Patients typically spend several years before progressing.
- **G3a→G3b:** Progression is much faster, with a median of just 98 days.
- **Later stages:** Fewer patients are represented, but transitions tend to accelerate.

## Visualization

An interactive Gantt chart was generated to visualize individual patient CKD stage timelines.

**References:**
- [KDIGO 2024 CKD Guideline (PDF)](https://kdigo.org/wp-content/uploads/2024/03/KDIGO-2024-CKD-Guideline.pdf)
- [UK Kidney Association: CKD Staging](https://www.ukkidney.org/health-professionals/information-resources/uk-eckd-guide/ckd-staging)
