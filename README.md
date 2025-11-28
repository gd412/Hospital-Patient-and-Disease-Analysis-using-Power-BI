# Hospital Patient Analytics Dashboard 

## Abstract

This project presents the design and development of an advanced **Hospital Patient Analytics Dashboard** using Microsoft Power BI. The goal is to transform raw hospital patient data into intelligent, meaningful insights that can support clinical decision-making, hospital administration, and operational planning.

The dashboard integrates a dataset of **10,000 structured patient records**, including demographics, admission details, department mapping, disease information, treatment costs, outcomes, readmissions, and length of stay. Using Power BI's data modeling, DAX calculations, and dynamic visualizations, the system reveals patterns in patient flow, hospital efficiency, treatment expenditures, departmental workload, recovery outcomes, and demographic trends.

The dataset is cleaned, transformed, and enriched with measures such as **Average Length of Stay, Readmission Rate, Total Treatment Cost, Mortality Rate, Recovery Percentage**, and more using DAX. The dashboard provides actionable insights through interactive slicers for gender, department, outcome, readmission, and admission month.

**Keywords—** Power BI, Hospital Analytics, Healthcare Dashboard, DAX, Predictive Analytics

---

## Introduction

Modern healthcare systems rely heavily on data-driven insights to optimize patient care, resource allocation, and hospital operations. With increasing patient volume and complex workflows, visual analytics tools like **Power BI** help hospitals understand critical metrics such as patient demographics, common diseases, length of stay, treatment outcomes, and departmental performance.

This project focuses on building a **professional Power BI dashboard for hospital management**, using a dataset of 10,000 patients. The dashboard provides a clean, interactive front-end that allows hospital administrators to monitor real-time patterns, identify inefficiencies, and improve patient care.

---

## I. Ease of Use

### A. User-Friendly Interface

The dashboard features:

* Intuitive card visuals for key KPIs
* Interactive slicers for filtering data based on demographics and outcomes
* Organized layout separating demographics, disease patterns, cost analysis, and efficiency metrics
* Clean visual hierarchy for quick interpretation

### B. Automated Insights

Once the user interacts with slicers, Power BI automatically recalculates all charts and KPIs using DAX. This allows real-time monitoring of:

* Readmission patterns
* High-cost departments
* Outcomes by age groups
* Disease spread across departments
* Seasonal admission patterns

---

## II. Prepare Your Data

A clean and well-structured dataset is essential for meaningful analytics.

### Dataset Features Included:

* **PatientID** (Unique identifier)
* **Age**
* **Gender**
* **Department** (Cardiology, Neurology, Oncology, Pediatrics, etc.)
* **Disease**
* **AdmissionDate**
* **DischargeDate**
* **LengthOfStay** (calculated)
* **TreatmentCost**
* **Outcome** (Recovered, Deceased, Ongoing)
* **Readmission** (Yes/No)

### Data Sources

The dataset was custom-generated to mimic realistic hospital data patterns. Values were designed based on common healthcare statistics and structured to support meaningful analytics.

---

## III. Abbreviations and Acronyms

* **LOS** – Length of Stay
* **DAX** – Data Analysis Expressions
* **KPI** – Key Performance Indicator
* **CSV** – Comma-Separated Values
* **ETL** – Extract, Transform, Load
* **UI** – User Interface
* **API** – Application Programming Interface

---

## A. Units

* **Age:** Integer (years)
* **Length of Stay:** Days
* **Treatment Cost:** INR (or USD)
* **Outcome:** Categorical
* **Readmission:** Binary categorical

Evaluation Metrics derived:

* **Average LOS** – days
* **Mortality Rate** – percentage
* **Recovery Rate** – percentage
* **Readmission Rate** – percentage

---

## B. Common Mistakes

Common issues in BI healthcare projects include:

* Not validating date columns before calculating LOS
* Incorrect DAX leading to inaccurate KPIs
* Missing relationships between fact and dimension tables
* Overcrowded dashboards
* Poorly designed slicers causing performance issues

This project mitigates all these by:

* Standardizing dates
* Creating meaningful relationships
* Using optimized DAX expressions
* Placing slicers only on the right panel
* Using a structured, minimalistic design approach

---

## Methodology

### Steps Followed:

1. **Data Creation:** 10,000-patient dataset generated programmatically.
2. **Data Import:** CSV loaded into Power BI Desktop.
3. **Data Cleaning:**

   * Ensured correct date formats
   * Calculated LengthOfStay field
   * Validated categorical fields
4. **Data Modeling:**

   * Built star schema
   * Created necessary relationships
5. **DAX Measures:**

   * Total Patients
   * Average Age
   * Total Treatment Cost
   * Average Length of Stay
   * Recovery Rate
   * Mortality Rate
   * Readmission Percentage
6. **Dashboard Layout:**

   * KPI cards
   * Demographics charts
   * Disease distribution
   * Cost analytics
   * Efficiency analysis
7. **Performance Optimization:**

   * Disabled unnecessary interactions
   * Reduced heavy visuals

---

## VII. Power BI Metrics and Models

### A. DAX Measures Used

**Total Patients**

```
Total Patients = COUNT('PatientData'[PatientID])
```

**Average Length of Stay**

```
Avg LOS = AVERAGE('PatientData'[LengthOfStay])
```

**Total Treatment Cost**

```
Total Cost = SUM('PatientData'[TreatmentCost])
```

**Readmission Rate**

```
Readmission % =
DIVIDE(
    CALCULATE(COUNT('PatientData'[PatientID]), 'PatientData'[Readmission] = "Yes"),
    [Total Patients]
)
```

**Recovery Rate**

```
Recovery Rate =
DIVIDE(
    CALCULATE(COUNT('PatientData'[PatientID]), 'PatientData'[Outcome] = "Recovered"),
    [Total Patients]
)
```

---

## Accuracy and Insights

The dashboard reveals:

* Departments with the highest treatment cost
* Age groups with longer recovery times
* Seasonal admission spikes
* Diseases with higher mortality or readmission risk
* Gender-based health trends

These insights help hospitals improve patient care and operational planning.

---

## Literature Survey

Relevant studies in healthcare BI analytics include:

1. **Hospital Analytics with Business Intelligence Platforms** – Discusses the impact of BI tools on healthcare efficiency.
2. **Data-Driven Decision Making in Healthcare** – Highlights the role of dashboards in patient management.
3. **Predictive Analytics in Hospitals** – Shows how modeling enhances resource planning.
4. **Visualization Techniques for Healthcare Data** – Emphasizes interface simplicity and clarity.
5. **Improving Patient Outcomes Using Analytics** – Demonstrates using data to reduce readmissions.

These studies reinforce the importance of structured dashboards for real-time hospital analysis.

---

## Figures and Tables

### Table: Sample Model Comparison (Example)

| Model                   | Accuracy | F1-Score |
| ----------------------- | -------- | -------- |
| Power BI + DAX Insights | High     | High     |
| Excel Dashboard         | Medium   | Medium   |
| Manual Tracking         | Low      | Low      |

---

## Acknowledgement

We express gratitude to:

* Power BI community for documentation and best practices
* Open-source contributors for visualization ideas
* Healthcare professionals who inspired the dataset design
* Mentors and peers providing feedback and suggestions

---

## Result

The Hospital Patient Analysis Dashboard effectively transforms raw patient data into insightful visualizations. It:

* Identifies high-risk areas
* Helps optimize hospital processes
* Improves understanding of patient demographics
* Provides real-time trends for readmissions, outcomes, and costs

This empowers administrators with accurate and actionable intelligence.

---

## References

[1] Microsoft Power BI Documentation
[2] DAX Guide – SQLBI
[3] Kaggle Healthcare Datasets
[4] WHO Health Statistics Reports
[5] Healthline – Medical Conditions and Treatment Patterns
