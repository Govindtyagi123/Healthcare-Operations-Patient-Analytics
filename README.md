# Healthcare Operations & Patient Analytics

## Business Problem

Healthcare organizations need to understand how patients move through different stages of care after an appointment.

An appointment may lead to a prescription only, or involve additional services such as laboratory tests, imaging, or pharmacy services. Understanding these care pathways can help identify service utilization patterns, doctor-level prescription activity, and unusual prescription timing or duration patterns.

This project analyzes healthcare operational data using **Python and Power BI** to investigate patient care pathways, service utilization, prescription patterns, and potential data-quality issues.

The goal is not simply to create a dashboard, but to use data to answer operational questions and identify areas that may require further investigation.

---

## Project Objectives

- Analyze appointment-to-prescription care pathways
- Measure Lab, Imaging, and Pharmacy utilization
- Identify common single-service and multi-service pathways
- Analyze prescription activity across doctors
- Examine prescription duration patterns
- Investigate unusual appointment and prescription timestamps
- Build an interactive Power BI dashboard for healthcare operations analysis

---

## Key Business Questions

### Care Pathways

- How are appointments distributed across different care pathways?
- What proportion of appointments are prescription-only?
- How frequently do appointments involve additional services?
- Which multi-service combinations occur most frequently?

### Service Utilization

- How frequently are Lab, Imaging, and Pharmacy services used?
- What proportion of appointments involve multiple services?
- Which combinations of services occur most frequently?

### Doctor Analysis

- How is prescription volume distributed across doctors?
- Which doctors have higher prescription volumes?
- Do doctors show different care or service patterns?
- How does prescription duration vary across doctors?

### Prescription Analysis

- What is the distribution of prescription duration?
- Are there unusually short or long prescription durations?
- Are there records where prescription timing appears inconsistent with appointment timing?

---

## Dataset

The dataset contains healthcare appointment, prescription, doctor, and service-flow information.

### Main Columns

| Column | Description |
|---|---|
| `record_no` | Record identifier |
| `patient_id` | Patient identifier |
| `appointment_id` | Appointment identifier |
| `appointment_start_datetime` | Appointment start date and time |
| `prescription_doctor_id` | Doctor identifier |
| `prescription_doctor_name` | Doctor name |
| `prescription_order_id` | Prescription identifier |
| `prescription_start_datetime` | Prescription start date and time |
| `prescription_end_datetime` | Prescription end date and time |
| `flow_code` | Service-flow code |
| `flow_name` | Healthcare service/care pathway |
| `prescription_duration` | Calculated prescription duration |

### Care Flow Examples

The dataset contains pathways such as:

- Appointment → Prescription
- Appointment → Prescription → Lab
- Appointment → Prescription → Imaging
- Appointment → Prescription → Lab + Imaging
- Appointment → Prescription → Pharmacy
- Appointment → Prescription → Lab + Pharmacy
- Appointment → Prescription → Imaging + Pharmacy

---

# Analytical Approach

## 1. Data Quality & Preparation

The first stage focused on understanding the structure and quality of the healthcare data.

The analysis included:

- Missing-value investigation
- Duplicate-row investigation
- Identifier uniqueness checks
- Datetime conversion
- Appointment and prescription relationship checks
- Prescription duration calculation
- Care-flow categorization
- Investigation of unusual timestamps

A key part of the analysis was checking whether prescription timestamps occurred logically relative to appointment timestamps.

---

## 2. Python Analysis

Python was used for data cleaning, preparation, and exploratory analysis.

### Libraries

- Pandas
- NumPy

The Python analysis included:

- Data cleaning
- Missing-value analysis
- Duplicate detection
- Datetime handling
- Feature creation
- GroupBy analysis
- Care pathway analysis
- Service utilization analysis
- Prescription-duration analysis
- Doctor-level analysis
- Data-quality investigation

Visualization libraries such as Matplotlib, Seaborn, and Plotly were not used for this project.

### Python File

```text
Healthcare Operations & Patient Analytics.ipynb
```

---

# Power BI Dashboard

The cleaned and analyzed data was used to create an interactive Power BI dashboard focused on healthcare operations.

## Page 1 — Healthcare Operations Overview

This page provides a high-level view of healthcare activity.

It focuses on:

- Overall appointment activity
- Patient and prescription volume
- Doctor activity
- Care pathway distribution
- Changes in appointment activity over time
- The overall relationship between appointments and prescriptions

The purpose is to provide a starting point for understanding the overall operational picture.

---

## Page 2 — Care Pathway & Service Utilization

This page focuses on how patients move through different healthcare services after their appointments.

It investigates:

- Lab utilization
- Imaging utilization
- Pharmacy utilization
- Prescription-only pathways
- Single-service pathways
- Multi-service pathways
- Common combinations of healthcare services
- Prescription duration patterns

The purpose is to understand **how healthcare services are being utilized and how different services are combined within patient care pathways**.

---

## Page 3 — Doctor & Prescription Performance

This page focuses on doctor-level prescription activity and care patterns.

It investigates:

- Prescription workload across doctors
- Doctor-level prescription activity
- Differences in prescription duration
- Doctor-level care patterns
- Service patterns associated with different doctors

The purpose is to understand **how prescription activity and care patterns vary across doctors**.

---

# Data Quality Investigation

During the analysis, some records showed prescription timestamps that appeared to occur before the corresponding appointment timestamp.

Instead of automatically removing these records, they were treated as a **data-quality investigation**.

This raises an important operational question:

> Are these genuine workflow events, data-entry issues, or timestamp inconsistencies?

This matters because timestamp inconsistencies can affect:

- Prescription duration
- Appointment-to-prescription analysis
- Operational timing metrics
- Doctor-level workflow analysis

---

# Key Analytical Areas

The project focuses on four major areas:

### 1. Care Pathway Analysis

Understanding how appointments progress into prescriptions and additional healthcare services.

### 2. Service Utilization

Measuring the usage of Lab, Imaging, Pharmacy, and multi-service pathways.

### 3. Doctor-Level Analysis

Understanding differences in prescription activity and care patterns across doctors.

### 4. Prescription Workflow

Examining prescription duration and identifying potentially unusual timing patterns.

---

# Business Insight Framework

The project follows a business-problem-first analytical approach:

**Business Problem → Business Questions → Metrics → Analysis → Findings → Recommendations**

Rather than creating insights simply from charts, each finding should answer a specific operational question.

Examples include:

- Which care pathways account for the largest share of appointments?
- Which healthcare services are most frequently used?
- Which service combinations are common?
- How is prescription workload distributed across doctors?
- Are prescription durations consistent?
- Are there timestamp records that require further investigation?

---

# Recommendations Framework

Depending on the validated findings, the analysis can support recommendations around:

- Monitoring high-volume care pathways
- Reviewing unusual prescription-duration records
- Investigating timestamp inconsistencies
- Monitoring service combinations for operational planning
- Reviewing doctor-level prescription workload
- Improving validation of appointment and prescription timestamps

Recommendations are based on the observed data rather than assumptions.

---

# Project Structure

```text
Healthcare Operations & Patient Analytics/
│
├── Healthcare Operations & Patient Analytics.ipynb
│
├── Healthcare Operations & Patient Analytics.pbix
│
└── README.md
```

---

# Tools & Technologies

- **Python**
  - Pandas
  - NumPy
- **Power BI**
  - Data Modeling
  - DAX
  - Interactive Dashboard
- **Jupyter Notebook**
- **GitHub**

---

# Skills Demonstrated

- Business Problem Solving
- Data Cleaning
- Exploratory Data Analysis
- Healthcare Operations Analytics
- Care Pathway Analysis
- Service Utilization Analysis
- Doctor-Level Analysis
- Prescription Analysis
- Date & Time Analysis
- Data Quality Investigation
- KPI Development
- Power BI Dashboard Development
- Business Insight Generation

---

# Project Outcome

This project demonstrates an end-to-end healthcare analytics workflow:

**Business Problem**  
↓  
**Business Questions**  
↓  
**Data Cleaning & Validation**  
↓  
**Python Analysis**  
↓  
**Metric Development**  
↓  
**Power BI Dashboard**  
↓  
**Findings & Recommendations**

The project demonstrates how healthcare operational data can be used to investigate business questions, understand patient care pathways, analyze service utilization, examine prescription patterns, and identify potential data-quality issues.

---

## Repository Description

**Healthcare operations analytics project using Python and Power BI to analyze patient care pathways, service utilization, prescription patterns, and operational data quality.**
