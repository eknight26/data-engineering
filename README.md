
This project demonstrates an ETL pipeline where hospital insurance and health data is extracted from CSVs, transformed using SQL to ensure data integrity and business and clinical accuracy, and loaded for downstream analytics.

The dataset was obtained from https://www.kaggle.com/datasets/rajkumarpadmanabhan/ca-hospital-dataset-q1-2025/data

The dataset contains 9 tables: patients, encounters, diagnoses, procedures, medications, lab_tests, claims_and_billing, providers, and denials.

This synthetic dataset simulates the end-to-end operations of a California-based hospital for Q1 2025. It includes over 126,000 rows across 9 fully integrated tables that capture patient visits, clinical procedures, diagnoses, lab tests, medication prescriptions, provider details, billing, claims, and denials — designed for data analytics, machine learning, and healthcare research.

Tables Included: patients.csv – Patient demographics, insurance, DOB, gender

encounters.csv – Admission/discharge details, visit types, departments

diagnoses.csv – ICD-10 diagnosis codes linked to encounters

procedures.csv – CPT/ICD-10-PCS procedure codes per patient

medications.csv – Drug names, dosages, prescription data

lab_tests.csv – Test names, result values, normal ranges

claims_and_billing.csv – Financial charges, insurance claims, payments

providers.csv – Doctors, specializations, provider roles

denials.csv – Reasons for claim denial, status, appeal info

This dataset is completely synthetic and safe for public use. It was generated using custom rules, distributions, and logic reflective of real hospital operations.
