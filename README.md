# Diabetes Monitoring & Risk Analysis using Big Data Analytics

**Student Name:** Shema Placide  
**Student ID:** 26497  
**Course Instructor:** Maniraguha Eric  
**Course:** Introduction to Big Data Analytics  

---

## Welcome & Project Motivation

Diabetes is a global health challenge affecting millions of adults worldwide, leading to serious complications and increased healthcare costs.  
This project leverages **Big Data Analytics** to monitor diabetes prevalence trends, evaluate treatment coverage, classify risk levels, and forecast future patterns.  
The goal is to support **data-driven healthcare decision-making** and help identify key areas where interventions can have the greatest impact.

---

## Dataset Used

- **cleaned_diabetes_data** and **NCD_RisC_Lancet_2024_Diabetes_crude_world**  
- **Dataset Access Link:** [View Dataset](https://drive.google.com/drive/folders/1PYxHFTrmxE-gt9Yaw-heFdWxYCK0k8iO?usp=drive_link)

---

## Project Structure

This project is divided into four parts:

---

## **Part 1: Problem Definition & Planning**

### What We Did
- **Sector Selection:** Focused on the **Health Sector** (Non-Communicable Diseases – Diabetes).  
- **Problem Statement:**  
  *“Can we monitor and analyze global diabetes trends, classify risk levels, and forecast future prevalence to support better healthcare planning?”*
- **Dataset Identification:**  
  - **Title:** NCD RisC Lancet 2024 – Global Diabetes Crude Prevalence  
  - **Structure:** Structured CSV dataset with 66 rows and 11 columns.  
  - **Status:** Required preprocessing (cleaning and transformations).

---

## **Part 2: Python Analytics Tasks**

### **2.1 Cleaned Dataset**
- Removed empty columns (e.g., `ISO`).  
- Standardized categorical values (`Sex`, `Age`) and corrected data types.  
- Verified and handled outliers.  

**Image – Cleaned Dataset Preview:**  
*(Insert image of cleaned dataset sample here)*

---

### **2.2 Exploratory Data Analysis (EDA)**
- Generated **descriptive statistics** for prevalence and treatment coverage.  
- Visualized global trends and gender comparisons.  
- Explored multi-variable relationships.

**Image – Correlation Heatmap**  
- Shows numerical strength of relationships (e.g., prevalence vs year).  
*(Insert correlation heatmap image here)*  

**Image – Pairplot**  
- Explores multi-variable relationships and gender separation.  
*(Insert pairplot image here)*  

---

### **2.3 Machine Learning & Clustering**
- **Trained both models (Clustering + Regression):**  
  - K-Means Clustering: Segmented risk into Low, Medium, and High.  
  - Linear Regression: Predicted diabetes prevalence based on year and gender.  

**Image – Clustering Visualization**  
- Shows three distinct risk groups based on prevalence and treatment coverage.  
*(Insert clustering visualization image here)*  

**Image – Regression Prediction Plot**  
- Shows model fit and prediction accuracy.  
*(Insert regression prediction plot here)*  

---

### **2.4 Code Structure & Documentation**
- **Structured Code Properly using Modular Functions (2):**  
  - Created functions for cleaning, EDA, model training, and evaluation.  
- **Met Academic Requirements for Clarity & Reproducibility (1):**  
  - Added markdown explanations, comments, and a logical workflow.

---

### **2.5 Innovation**
- **Incorporated Ensemble Technique for Prediction (2):**  
  - Used **Random Forest Regressor** to improve predictive accuracy.  
- Created a **Custom Risk Score** combining diabetes prevalence and treatment coverage.  

**Image – Random Forest Feature Importance**  
- Shows which features (Year, Gender) impact predictions most.  
*(Insert feature importance image here)*  

---

## **Part 3: Power BI Dashboard**

### **3.1 Dashboard Structure (3)**
- Built an interactive Power BI dashboard with:
  - Year, Gender, and Risk Level slicers.  
  - Drill-down and filtering capabilities.  
  - AI visuals and forecasting.  

**Image – Power BI Dashboard Structure**  
- Layout of slicers, KPIs, charts, and AI visuals.  
*(Insert Power BI structure screenshot here)*  

---

### **3.2 Global Diabetes Monitoring & Risk Analysis (1990–2022)**
- Showed trends in diabetes prevalence and treatment coverage over time.
- Compared prevalence by gender and highlighted risk clusters.

**Image – Global Trend Chart**  
- Shows how diabetes prevalence increased from 1990 to 2022.  
*(Insert global trend image here)*  

---

### **3.3 Key Findings (from EDA + ML) (2)**
- Diabetes prevalence has almost tripled since 1990.  
- Men consistently show slightly higher prevalence than women.  
- Treatment coverage improved but remains below 50% globally.  
- Clustering identified periods of **High Risk** in recent years, and forecasting predicts further increases.  

**Image – Risk Level Distribution**  
- Shows count of records per risk level (Low, Medium, High).  
*(Insert risk level distribution image here)*  

---

### **Power BI Visuals Access**
Due to large file sizes, all Power BI visuals and related reports are stored in Google Drive:  
[View Power BI Visuals](https://drive.google.com/drive/folders/1ooPgSdl84ZJ1eZ1fWkBAWivKnEx0fVcf?usp=drive_link)

---

## **Part 4: Submission & Communication**

- **GitHub Repository:**  
  - Well-structured folders (data, notebooks, models, dashboard, docs).  
  - README file with overview, instructions, and screenshots.  
  - All Python notebooks and Power BI `.pbix` file included.
- **PowerPoint Presentation:**  
  - Covers introduction, methodology, results, recommendations, and future work.  
  - **Presentation Link:** [View PowerPoint](https://docs.google.com/presentation/d/1tpPkm4ouUMJ5j2fuXFrhY-X9NtyHOXZD/edit?usp=sharing&ouid=101928335647300964929&rtpof=true&sd=true)

---

## **Why This Project Matters**

This project:
- Supports healthcare policy by providing actionable insights.  
- Uses **Big Data Analytics** to identify trends and forecast future diabetes risks.  
- Introduces innovation through a **custom risk score** and **ensemble modeling**.  
- Delivers an interactive dashboard for decision-makers.

---

## **Acknowledgment**

Special thanks to **Instructor: Maniraguha Eric** for guidance during the **Introduction to Big Data Analytics** course.

---

## **How to Run**
1. Clone this repository.  
2. Open Python notebooks under `/notebooks` to view cleaning, analysis, and modeling.  
3. Open `Diabetes_Risk_Analysis.pbix` in Power BI Desktop to explore the interactive dashboard.  

---

## **Images (Replace placeholders with actual images)**
- `images/cleaned_dataset.png`
- `images/correlation_heatmap.png`
- `images/pairplot.png`
- `images/clustering.png`
- `images/regression_prediction.png`
- `images/randomforest_feature_importance.png`
- `images/powerbi_structure.png`
- `images/global_trend.png`
- `images/risk_level_distribution.png`

