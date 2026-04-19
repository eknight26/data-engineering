# ETL Pipeline — Hospital Insurance & Health Data

> **Demonstrate pipeline creation to extract data from hospital insurance and health data, transform and load for downstream analytics.**

---

## Overview

This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline built in a **Databricks workspace** using **SQL**. Hospital insurance and health data is extracted from CSV source files, transformed using SQL to ensure data integrity and business and clinical accuracy, and loaded into analysis-ready tables for downstream analytics.

The pipeline targets **Q1 2025** operations of a synthetic California-based hospital, enabling first-quarter insights across patient profiles, provider performance, financial summaries, claims and denial analysis, and clinical metrics.

---

## Problem Statement

Healthcare organisations generate large volumes of structured data across clinical, operational, and financial domains. Without a reliable pipeline to consolidate and validate this data, analysts are left working with siloed, inconsistent sources. This project solves that by:

- Ingesting raw multi-domain hospital data from CSVs
- Applying data quality checks to ensure integrity
- Structuring data through a **medallion architecture** (Bronze → Silver → Gold)
- Delivering clean, analysis-ready outputs for data and business analysts

---

## Project Details

| Attribute | Details |
|---|---|
| **Project Type** | Data Engineering |
| **Primary Language** | SQL |
| **Platform** | Databricks |
| **Domain** | Healthcare |
| **Data Period** | Q1 2025 |
| **Target Users** | Data & Business Analysts in healthcare organisations |

---

## Dataset

The dataset is fully synthetic and safe for public use. It was generated using custom rules, distributions, and logic reflective of real hospital operations, and simulates the end-to-end operations of a California-based hospital.

- **Source:** [Kaggle — CA Hospital Dataset Q1 2025](https://www.kaggle.com/datasets/rajkumarpadmanabhan/ca-hospital-dataset-q1-2025/data)
- **Total Rows:** 126,000+ across 9 fully integrated tables
- **Use Cases:** Data analytics, machine learning, and healthcare research

### Tables

| Table | Description |
|---|---|
| `patients.csv` | Patient demographics, insurance, date of birth, gender |
| `encounters.csv` | Admission/discharge details, visit types, departments |
| `diagnoses.csv` | ICD-10 diagnosis codes linked to encounters |
| `procedures.csv` | CPT/ICD-10-PCS procedure codes per patient |
| `medications.csv` | Drug names, dosages, prescription data |
| `lab_tests.csv` | Test names, result values, normal ranges |
| `claims_and_billing.csv` | Financial charges, insurance claims, payments |
| `providers.csv` | Doctors, specialisations, provider roles |
| `denials.csv` | Reasons for claim denial, status, appeal information |

---

## Pipeline Architecture

This project follows the **Medallion Architecture** pattern, progressively refining data across three layers:

```
Raw CSVs (Volumes)
      │
      ▼
 ┌─────────┐
 │  BRONZE │  Raw ingestion — no transformations, preserves source data
 └─────────┘
      │
      ▼
 ┌─────────┐
 │  SILVER │  Cleaned & validated — nulls, duplicates, date checks resolved
 └─────────┘
      │
      ▼
 ┌─────────┐
 │   GOLD  │  Analysis-ready — aggregated, joined, and formatted for analytics
 └─────────┘
      │
      ▼
 Downstream Visualisation / Reporting
```

---

## Key Features

- **Extract** — Source CSV files are loaded from Databricks Volumes into the Bronze layer
- **Transform** — SQL transformations applied across Silver layer including:
  - Null and missing value checks
  - Duplicate record detection and resolution
  - Date format validation and range checks
  - Business and clinical rule enforcement
- **Load** — Gold layer tables are loaded as analysis-ready outputs for visualisation tools
- **Medallion Schema** — Bronze, Silver, and Gold schemas maintained within Databricks

---

## Analytics Outputs

The Gold layer supports the following business and clinical analytics domains:

- **Patient Profiles** — Demographics, insurance coverage, and visit history
- **Provider Performance** — Workload, specialisation, and outcomes by provider
- **Financial Summaries** — Charges, payments, and reimbursement rates
- **Claims & Denial Analysis** — Denial reasons, appeal outcomes, and claim statuses
- **Clinical Metrics** — Diagnoses frequency, procedure volumes, lab result trends, and medication patterns

---

## Disclaimer

This dataset is **completely synthetic** and does not contain any real patient or provider information. It is safe for public use and intended solely for analytics, educational, and research purposes.

---

## Data Source

[https://www.kaggle.com/datasets/rajkumarpadmanabhan/ca-hospital-dataset-q1-2025/data](https://www.kaggle.com/datasets/rajkumarpadmanabhan/ca-hospital-dataset-q1-2025/data)
