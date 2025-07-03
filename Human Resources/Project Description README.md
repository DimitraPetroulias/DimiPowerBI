# 📊 Power BI Dashboard for the Human Resources Department

## 🎯 Overall Goal of the Dashboard
To monitor and understand attrition patterns, helping HR and management quickly see:
- How many people are leaving.
- Who is leaving (by age, gender, education, salary, tenure, job role).
- Patterns that could drive intervention.

## 🛠 Operationalising the Business Need
Create a Power BI dashboard to track attrition rate for the whole company and for each department (*HR, Research & Development, Sales*).

Include tracking of high-level Key Performance Indicators (KPIs):
- Number of employees
- Attrition
- Attrition rate
- Average age of employees
- Average monthly salary
- Average length in company

Include the relationship between attrition and the following demographics:
- Gender
- Education
- Job Role
- Salary
- Years at company

## 📂 Data Source

**Files:**
- `HR data.xls` — workbook with multiple sheets of data:
  - `Departments` – DIM table
  - `Education` – DIM table
  - `Jobs` – DIM table
  - `HR_Data` – FACT table

![Data Model](https://github.com/user-attachments/assets/fad86149-9c6c-4d92-a2f9-6bdc2a9b0fd6)


## 🛠 Tools & Technologies
- Power BI Desktop

## ⚙️ Methodology

### A. Data Understanding
- Identified variable definitions, types, and expected ranges.

### B. Data Preparation
- Transformed data before importing within Power Query Editor.
- Checked variable types.
- Checked data consistency and normalised as needed (e.g., replacing invalid values).
- Ensured numerical values were correctly formatted (e.g., converted strings like `None` to `0`).
- Checked and updated relationships between tables within **Model View**:
  - Verified one-to-many relationships.
  - Confirmed primary keys in dimension tables linked to foreign keys in the FACT table.

### C. Preparation of Dashboard
- Created a **slicer** for filtering by department.
- Developed the following visualisations:

  **Cards for tracking:**
  - Number of employees
  - Attrition
  - Attrition rate *(created measure):*  
    ```DAX
    Attrition_Rate = SUM(HR_Data[Attrition_Count]) / SUM(HR_Data[EmployeeCount])
    ```
  - Average age of employees
  - Average monthly salary
  - Average length in company

  **Charts:**
  - Treemap: Gender distribution
  - Donut Chart: Attrition by education
  - Column Charts: Attrition by age and attrition by salary
  - Area Chart: Attrition by years at company
  - Clustered Bar Chart & Matrix: Attrition by job role

### D. Final Dashboard
- Download dashboard: https://github.com/DimitraPetroulias/DimiPowerBI/blob/main/Human%20Resources/Capstone%20Project.pbix
- ![HR PowerBI Dashboard](https://github.com/user-attachments/assets/a6332f05-4477-43b3-b140-a37e60f957a1)


### E. Visualisation Considerations

#### 1 Visual Hierarchy & Layout
- KPIs placed at the top for quick reference.
- Breakdown charts below for deeper insights.
- Consistent gray background to highlight visuals.
- Logical grouping by demographics, tenure, salary, and job role.

#### 2 Color Usage
- Blues for categorical differentiation (e.g., male/female, salary brackets).
- Muted grays to reduce visual clutter.
- Bright blue to highlight key bars.
- Consistent palette for readability.

#### 3 Typography and Labels
- Large, clear fonts for KPIs.
- Simple numeric labels on charts.
- Minimal excess text.

#### 4 Interactivity and Filters
- Department slicer to switch views.
- Dynamic interactions (e.g., clicking job roles to cross-filter other visuals).

#### 5 Contextual Clarity
- Explicit labels (e.g., *Attrition by Salary*, *Attrition by Years at Company*).
- Percentages displayed where relevant.

## 🌱 Future Considerations
- Add trend over time (attrition by month/year).
- Enable tooltip interactivity to display additional metrics.
- Use color-blind safe palettes if necessary.
- Consider predictive indicators (e.g., risk of attrition).
