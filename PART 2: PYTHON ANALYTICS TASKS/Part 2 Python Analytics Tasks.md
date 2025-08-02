# Part 2: Python Analytics Tasks

In this section, we applied Python (using Jupyter Notebook) to clean, analyze, model, and interpret our diabetes dataset.  
The steps followed are outlined below:

---

## 1. Clean the Dataset

### Objectives:
- Handle missing values.
- Correct inconsistent formats.
- Detect and handle outliers.

### Actions Performed:
- **Removed Empty Columns:** The column `ISO` was completely empty and removed from the dataset.  
- **Standardized Text Columns:** 
  - The `Sex` column values were standardized (e.g., "men" → "Men").  
  - The `Age` column values were standardized (only “Crude” values exist).  
- **Corrected Data Types:** The `Year` column was converted to an integer data type.  
- **Checked Outliers:** Verified that `Diabetes_Prevalence` and `Treatment_Proportion` values were within the valid range [0,1]. No extreme outliers were found.

---

## 2. Apply Data Transformations

### Objectives:
- Prepare data for modeling.
- Make numeric and categorical values consistent.

### Actions Performed:
- **Encoded Categorical Variables:** Converted the `Sex` column to numeric values (Men = 1, Women = 0) to use in models.  
- **Scaled Numeric Features:** Scaled numerical columns (`Year`, `Diabetes_Prevalence`, `Treatment_Proportion`) to improve clustering and regression model performance.

---

## 3. Conduct Exploratory Data Analysis (EDA)

### Objectives:
- Understand dataset structure and patterns.
- Explore relationships among variables.

### Actions Performed:
- **Descriptive Statistics:** Generated mean, median, min, max, and standard deviation for key variables.  
- **Trend Analysis:** Created a line chart showing global diabetes prevalence from 1990 to 2022.  
- **Gender Comparison:** Compared diabetes prevalence between men and women using boxplots.  
- **Distribution Analysis:** Visualized treatment coverage distribution and its relationship to diabetes prevalence using scatter plots.  

### Insights from EDA:
- Diabetes prevalence has steadily increased since 1990.  
- Men generally have slightly higher prevalence compared to women.  
- Treatment coverage improved but remains below 50% globally.  
- A positive correlation exists between prevalence and treatment coverage.

---

## 4. Apply a Machine Learning or Clustering Model

### Objectives:
- Use machine learning to classify risk levels and predict prevalence.

### Actions Performed:
- **K-Means Clustering:** Grouped data points into three clusters:
  - **Low Risk**
  - **Medium Risk**
  - **High Risk**  
- **Regression Model:** Used a simple linear regression model to predict diabetes prevalence based on year and gender.

### Outputs:
- Each data record assigned a risk level (Low/Medium/High).  
- Regression model trained to estimate prevalence for future years (e.g., predicted values for 2025).

---

## 5. Evaluate the Model

### Objectives:
- Measure model performance.
- Validate clustering quality and regression accuracy.

### Actions Performed:
- **Clustering Evaluation:** 
  - Calculated the **Silhouette Score** to measure how well data points fit within their clusters. 
  - Result: Score greater than 0.5 → good separation between clusters.
- **Regression Evaluation:** 
  - Calculated **Root Mean Square Error (RMSE)** to assess prediction accuracy.
  - Result: Small RMSE → predictions closely matched observed values.

---

## 6. Structure Code Properly

### Objectives:
- Improve code clarity, readability, and reproducibility.

### Actions Performed:
- **Modular Functions:** Created reusable functions:
  - `clean_data()`
  - `apply_transformations()`
  - `perform_eda()`
  - `train_models()`
- **Markdown Explanations:** Each notebook cell included markdown to explain the purpose and outputs of the code.
- **Inline Comments:** Added comments in the code for clarity, allowing other users to easily understand the workflow.

---

## 7. Incorporate Innovation

### Objectives:
- Enhance the project beyond basic requirements.
- Provide actionable insights for decision-makers.

### Actions Performed:
- **Custom Risk Score:** Developed a custom metric:  
  *Risk Score = (Diabetes Prevalence × 100) − (Treatment Proportion × 50)*  
  - Higher score = higher risk due to high prevalence and/or low treatment coverage.
- **Ensemble Technique:** Implemented a **Random Forest Regressor** to improve predictive accuracy compared to a simple linear regression model.
- **Advanced Visuals:** Integrated Power BI’s **AI-driven Decomposition Tree** to explain the key factors influencing diabetes prevalence.

---

## Summary of Part 2

- The dataset was successfully cleaned and transformed for analysis.
- Exploratory Data Analysis revealed key patterns (increasing prevalence, gender differences, treatment trends).
- Machine learning models provided:
  - Risk classification (Low, Medium, High).
  - Predictive modeling of future prevalence.
- Evaluation metrics confirmed model reliability.
- Innovation (custom risk score, ensemble model, AI visuals) added unique value to the analysis.

