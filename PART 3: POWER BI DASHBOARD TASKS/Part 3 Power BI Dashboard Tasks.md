# Part 3: Power BI Dashboard Tasks

In this section, we designed an interactive Power BI dashboard to communicate insights from our diabetes dataset.  
The dashboard focuses on problem clarity, interactivity, appropriate visuals, design clarity, and innovation.

**Power BI Dashboard Link:**  
[View the Power BI Visuals](https://drive.google.com/drive/folders/1ooPgSdl84ZJ1eZ1fWkBAWivKnEx0fVcf?usp=drive_link)

---

## 1. Communicate the Problem & Insights Clearly

### Objective:
Provide users with immediate context about the health challenge being analyzed and the purpose of the dashboard.

### Actions Performed:
- Added a **title**: *“Global Diabetes Monitoring & Risk Analysis”*.
- Included a **summary text box** highlighting:
  - Rising diabetes prevalence trends (1990–2022).
  - Gender differences in prevalence rates.
  - Treatment coverage performance.
  - Risk level classification and future forecast.
- Displayed **Key Metrics (Cards)**:
  - Average Global Diabetes Prevalence.
  - Average Treatment Coverage.
  - Predicted Prevalence for 2025.

### Outcome:
Users can quickly understand what the dashboard represents and why it matters.

---

## 2. Incorporate Interactivity

### Objective:
Allow users to filter and explore data dynamically.

### Actions Performed:
- **Slicers**:
  - **Year Slicer**: Filter by specific year or a range of years.
  - **Gender Slicer**: Filter by Men or Women.
  - **Risk Level Slicer**: Filter records by Low, Medium, or High risk.
- **Filters**:
  - Page-level filter applied to focus only on the "Crude" age group.
- **Drill-Down**:
  - Enabled drill-down in line charts so users can click a year to see gender-specific data.
- **Hover Tooltips**:
  - Added tooltips showing detailed values (Risk Score, Treatment Coverage) when hovering over charts.

### Outcome:
The dashboard is not static; it is an interactive tool for dynamic analysis.

---

## 3. Use Appropriate Visuals

### Objective:
Select chart types that best communicate the data insights.

### Actions Performed:
- **Cards**: Display key KPIs (Average Prevalence, Average Treatment, Predicted 2025 Prevalence).
- **Line Charts**: 
  - Show diabetes prevalence trend over time, broken down by gender.
  - Show treatment coverage trend globally.
- **Scatter Plot**:
  - Plot Diabetes Prevalence vs. Treatment Coverage, colored by risk clusters (Low, Medium, High).
- **Clustered Column Chart**:
  - Show count of records in each custom risk level category.
- **Bar Chart**:
  - Show year-over-year (YoY) percentage change in prevalence.
- **Decomposition Tree (AI Visual)**:
  - Explain factors contributing to changes in diabetes prevalence.
- **Forecast Line Chart**:
  - Display predicted future prevalence using forecasting tools.

### Outcome:
Visuals clearly align with the analysis goals and make complex relationships easy to understand.

---

## 4. Ensure Design Clarity

### Objective:
Make the dashboard professional, clean, and easy to read.

### Actions Performed:
- Applied a **consistent color scheme**:
  - Blue for diabetes prevalence.
  - Green for treatment coverage.
  - Gradient (green → orange → red) for risk levels.
- **Clean Layout**:
  - Slicers aligned on the left side.
  - Charts and visuals arranged logically on the right side.
- **Clear Labels & Titles**:
  - Added axis titles, legends, and descriptive chart titles.
- Used **grid alignment** and avoided clutter by using tooltips for details instead of overcrowded text.

### Outcome:
The dashboard is visually appealing and user-friendly for decision-makers.

---

## 5. Add Innovative Features

### Objective:
Enhance the dashboard beyond standard visuals.

### Actions Performed:
- **Custom Risk Score (DAX)**:
  - Created a new measure combining diabetes prevalence and treatment coverage.
- **AI Visual (Decomposition Tree)**:
  - Automatically explains the key drivers of changes in diabetes prevalence.
- **Key Influencers Visual**:
  - Identifies which factors (Year, Gender, Treatment Coverage) most affect prevalence.
- **Forecasting Feature**:
  - Predicts future prevalence trends for proactive health planning.
- **Custom Tooltips and Bookmarks**:
  - Allows smooth navigation between Overview and Risk Analysis pages.
  - Provides additional insights on hover without cluttering the visuals.

### Outcome:
The dashboard is not only analytical but also predictive and explanatory, providing added value for decision-making.

---

## Summary of Part 3

The Power BI dashboard delivers:
- Clear communication of the problem and key insights.
- Full interactivity through slicers, filters, and drill-downs.
- A variety of visuals matched to data goals.
- Professional design with consistent themes and clear layouts.
- Innovative features (custom risk score, AI-driven visuals, forecasting, and interactive navigation).

These features make the dashboard a powerful tool for monitoring diabetes risk and planning health interventions.
