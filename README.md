# Healthcare Operations & Patient Analytics

## Business Problem

Healthcare organizations need to understand how patients move through different stages of care after an appointment.

An appointment may lead to a prescription only, or involve additional services such as laboratory tests, imaging, or pharmacy services. Understanding these care pathways can help identify service utilization patterns, doctor-level prescription activity, and unusual prescription timing or duration patterns.

This project uses healthcare operational data to investigate these questions through **Python-based analysis and an interactive Power BI dashboard**.

The goal is not simply to create charts, but to understand:

- How patients move through different care pathways
- How frequently additional services are used
- How prescription activity is distributed across doctors
- How prescription duration varies
- Whether appointment and prescription timestamps contain unusual patterns

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

# Key Business Questions

### Care Pathways

- How are appointments distributed across different care pathways?
- What proportion of appointments are prescription-only?
- How frequently do appointments involve additional services?
- Which multi-service combinations occur most frequently?

### Service Utilization

- How frequently is Lab service used?
- How frequently is Imaging service used?
- How frequently is Pharmacy service used?
- What percentage of appointments involve multiple services?

### Doctor Analysis

- How is prescription volume distributed across doctors?
- Which doctors have higher prescription volumes?
- Do doctors show different care/service patterns?
- How does prescription duration vary across doctors?

### Prescription Analysis

- What is the distribution of prescription duration?
- Are there unusually short or long prescription durations?
- Are there records where prescription timing appears inconsistent with the appointment timing?

---

# Dataset

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

### Purpose

Provide a high-level view of healthcare activity.

### Visuals

- Total Appointments — KPI Card
- Total Patients — KPI Card
- Total Prescriptions — KPI Card
- Total Doctors — KPI Card
- Appointment Trend Over Time — Line Chart
- Care Mix — 100% Stacked Bar Chart
- Appointment → Prescription Overview
- Appointments by Doctor — Bar Chart

### Main Questions

- What is the overall healthcare activity?
- How are appointments distributed across care pathways?
- How does appointment activity change over time?
- How is appointment activity distributed across doctors?

---

## Page 2 — Care Pathway & Service Utilization

### Purpose

Understand how patients move through healthcare services after their appointments.

### Visuals

- Lab Appointments — KPI Card
- Imaging Appointments — KPI Card
- Multi-Service Appointments — KPI Card
- Service-Level Appointment Distribution — 100% Stacked Bar Chart
- Multi-Service Combinations — Bar Chart
- Key Service Metrics — KPI Cards
- Prescription Duration Distribution — Bar/Column Chart

### Main Questions

- How common are additional services?
- Which service combinations occur most frequently?
- What proportion of appointments involve multiple services?
- How is prescription duration distributed?

---

## Page 3 — Doctor & Prescription Performance

### Purpose

Analyze doctor-level prescription activity and care patterns.

### Visuals

- Total Doctors — KPI Card
- Total Prescriptions — KPI Card
- Average Prescription Duration — KPI Card
- Prescription Volume by Doctor — Horizontal Bar Chart
- Prescription Duration by Doctor — Bar Chart
- Doctor Care Mix — Bar Chart
- Doctor Prescription Summary — Table/Matrix

### Main Questions

- How is prescription workload distributed across doctors?
- How does prescription duration vary across doctors?
- Do doctors show different care/service patterns?
- Which doctors have higher prescription volumes?

A **Date slicer** can be used to analyze doctor activity for a selected period. A separate Doctor slicer is not necessary because the page itself is focused on doctor-level analysis.

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

Understanding how appointments progress into prescriptions and additional services.

### 2. Service Utilization

Measuring the usage of Lab, Imaging, Pharmacy, and multi-service pathways.

### 3. Doctor-Level Analysis

Understanding differences in prescription volume and care patterns across doctors.

### 4. Prescription Workflow

Examining prescription duration and identifying potentially unusual timing patterns.

---

# Business Insight Framework

The final analysis is structured around:

**Business Problem → Questions → Metrics → Analysis → Findings → Recommendations**

Rather than creating insights simply from charts, each finding should answer a specific operational question.

Examples include:

- Which care pathways account for the largest share of appointments?
- Which services are most frequently used?
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
**KPI & Metric Development**  
↓  
**Power BI Dashboard**  
↓  
**Findings & Recommendations**

The project focuses on demonstrating how a Data Analyst can use operational data to answer business questions and investigate potential workflow and data-quality issues, rather than simply building a collection of charts.
