# 🩺 Diabetes Monitoring & Risk Analysis using Big Data Analytics

**👤 Student Name:** Shema Placide  
**🆔 Student ID:** 26497  
**👥 Group:** B  
**👨‍🏫 Course Instructor:** Maniraguha Eric  
**📂 GitHub Link:** [Project Repository](https://github.com/Shemaplacide/Final_Project_Big_Data_Diabetes_Monitoring_Risk_Analysis/tree/main)  
**📘 Course:** Introduction to Big Data Analytics  

---

## 🎯 Welcome & Project Motivation

Diabetes is a global health challenge affecting millions of adults worldwide, leading to serious complications and increased healthcare costs.  
This project leverages **Big Data Analytics** to:  
- 📊 Monitor diabetes prevalence trends  
- 🏥 Evaluate treatment coverage  
- 🧮 Classify risk levels  
- 🔮 Forecast future patterns  

The goal is to support **data-driven healthcare decision-making** and help identify key areas where interventions can have the greatest impact.

---

## 📊 Dataset Used

- **cleaned_diabetes_data** and **NCD_RisC_Lancet_2024_Diabetes_crude_world**  
- **🔗 Dataset Access Link:** [View Dataset](https://drive.google.com/drive/folders/1PYxHFTrmxE-gt9Yaw-heFdWxYCK0k8iO?usp=drive_link)

---

## 📖 Key Definitions

- **📈 Diabetes Prevalence:** Percentage of people in a population who have diabetes at a given point in time.  
  *Why it matters:* Helps assess how widespread diabetes is and monitor progress in controlling it.

- **💊 Treatment Proportion:** Percentage of people with diabetes who are receiving proper treatment.  
  *Why it matters:* Low treatment coverage signals gaps in access to essential care.

- **📅 Year:** The calendar year for which the data was recorded.

- **🔻 Diabetes Prevalence Lower CI & 🔺 Upper CI:** Confidence intervals showing the possible range of true prevalence.

- **🔻 Treatment Proportion Lower CI & 🔺 Upper CI:** Confidence intervals showing uncertainty in treatment coverage estimates.

- **🏷 Risk Label:** A tag indicating Low, Medium, or High risk.

- **🗂 Risk Cluster:** Groups produced by K-Means clustering based on prevalence and treatment coverage.

- **👥 Age:** Population age category. This dataset uses “Crude” (all ages combined).

---

## 🏗 Project Structure

This project is divided into four parts:  
1. **📝 Problem Definition & Planning**  
2. **🐍 Python Analytics Tasks**  
3. **📊 Power BI Dashboard**  
4. **📤 Submission & Communication**

---

## **Part 1: Problem Definition & Planning** 📝

### What We Did
- **Sector Selection:** Focused on the **Health Sector** (Non-Communicable Diseases – Diabetes).  
- **Problem Statement:**  
  *“Can we monitor and analyze global diabetes trends, classify risk levels, and forecast future prevalence to support better healthcare planning?”*  
- **Dataset Identification:**  
  - **Title:** NCD RisC Lancet 2024 – Global Diabetes Crude Prevalence  
  - **Structure:** Structured CSV dataset with 66 rows and 11 columns.  
  - **Status:** Required preprocessing (cleaning and transformations).

---

## **Part 2: Python Analytics Tasks** 🐍

### **2.1 Cleaned Dataset** 🧹
- Removed empty columns (e.g., `ISO`).  
- Standardized categorical values (`Sex`, `Age`) and corrected data types.  
- Verified and handled outliers.  

**🖼 Image – Cleaned Dataset Preview:** 

<img width="782" height="290" alt="Cleaned Dataset" src="https://github.com/user-attachments/assets/937f9401-731b-406d-8e94-ae84a83a587e" />

---

### **2.2 Exploratory Data Analysis (EDA)** 📊
- Generated descriptive statistics for prevalence and treatment coverage.  
- Visualized global trends and gender comparisons.  
- Explored multi-variable relationships.

**🖼 Image – Correlation Heatmap**  

<img width="341" height="272" alt="Part 2 3 Correlation heatmap – numerical strength of relationships (e g , prevalence vs year)" src="https://github.com/user-attachments/assets/b60cd041-6ede-49e1-bb37-6353cd350468" />  

**🖼 Image – Pairplot**  

<img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/cbdef612-2ba4-4642-8457-7388368955f6" />  

---

### **2.3 Machine Learning & Clustering** 🤖
- **Trained Models (Clustering + Regression):**  
  - **K-Means Clustering:** Segmented risk into Low, Medium, and High.  
  - **Linear Regression:** Predicted diabetes prevalence based on year and gender.  

#### Example Python Code (K-Means)
```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

X = df[['Diabetes_Prevalence','Treatment_Proportion']]
X_scaled = StandardScaler().fit_transform(X)

kmeans = KMeans(n_clusters=3, random_state=42)
df['RiskCluster'] = kmeans.fit_predict(X_scaled)
````

#### Example Python Code (Regression)

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

X = df[['Year','Sex_encoded']]
y = df['Diabetes_Prevalence']

model = LinearRegression()
model.fit(X, y)
y_pred = model.predict(X)
rmse = mean_squared_error(y, y_pred, squared=False)
```

**🖼 Image – Clustering Visualization**

<img width="369" height="362" alt="Part 2 3 2 Trained both models (Clustering + Regression)" src="https://github.com/user-attachments/assets/34aeba50-0cee-4eab-be67-6032dfd68fd8" />

**🖼 Image – Regression Prediction Plot**

<img width="431" height="273" alt="Part 2 6 1 Incorporate Innovation Ensemble Technique for Prediction (2)" src="https://github.com/user-attachments/assets/ac0a4939-df5c-40e3-a83b-76acf376bc2e" />

---

### **2.4 Code Structure & Documentation** 📑

* **Modular Functions** used for cleaning, transformation, and modeling.
* Markdown explanations and inline comments for clarity and reproducibility.

---

### **2.5 Innovation** 🚀

* **Random Forest Regressor:** Improved predictive accuracy beyond linear regression.
* **Custom Risk Score:** Combined prevalence and treatment coverage to create a single risk metric.

#### Example Python Code (Random Forest)

```python
from sklearn.ensemble import RandomForestRegressor

rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X, y)
importances = rf_model.feature_importances_
```

**🖼 Image – Random Forest Feature Importance**

<img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/32c91d91-ebd5-4e94-92e6-93db5a247374" />

---

## **Part 3: Power BI Dashboard** 📊

### **3.1 Dashboard Structure**

* Interactive dashboard with Year, Gender, and Risk Level slicers.
* Drill-down and AI visuals included.

**🖼 Image – Power BI Dashboard Structure**

<img width="571" height="312" alt="Part 3 Power BI Dashboard Structure (3)" src="https://github.com/user-attachments/assets/5f9437e9-89eb-4f43-8e6c-c06d2ff8aea4" />

---

### **3.2 Global Diabetes Monitoring & Risk Analysis (1990–2022)** 🌍

* Trends in diabetes prevalence and treatment coverage.
* Gender-based comparisons and risk clusters.

**🖼 Image – Global Trend Chart**

<img width="500" height="267" alt="Global trend" src="https://github.com/user-attachments/assets/9c9afcef-6f5c-43c8-b152-ab8c03cad373" />

**🖼 Image – Part 3 Global Diabetes Monitoring & Risk Analysis (1990–2022)**

<img width="585" height="329" alt="Part 3 Global Diabetes Monitoring   Risk Analysis (1990-2022)" src="https://github.com/user-attachments/assets/8696e669-23b1-4d05-b732-686ba48b928e" />

---

### 🚀 Innovation in Power BI Dashboard

As part of adding **advanced features** to the Power BI dashboard, I integrated interactive and intelligent tools that go beyond traditional charts. This helps make the data exploration more dynamic and user-friendly for decision-makers.

#### ✅ Feature Used: Smart Narrative (AI Visual)

I implemented the **Smart Narrative** AI visual in Power BI to automatically generate **data-driven summaries** based on underlying charts and calculations. This feature uses **artificial intelligence** to detect insights and patterns (e.g., average prevalence, top risk years, gender differences) and present them in clear, human-readable language.

**🔍 Why It Matters:**

* It reduces manual explanation.
* Helps non-technical users understand trends quickly.
* Automatically updates when slicers or filters are changed.

**📌 How It Was Used:**

* Placed the Smart Narrative visual on the **Insights Summary page**.
* It provides real-time interpretation of trends in diabetes prevalence, treatment coverage, and risk level.
* Works with slicers (Year, Gender, Risk Level) to deliver **context-aware summaries**.

**🧠 Example Smart Narrative Output:**

> "From 1990 to 2022, diabetes prevalence increased significantly. The year 2022 had the highest recorded prevalence. Males consistently showed higher rates than females. Risk levels shifted from low to high, especially after 2005."

---

### **3.3 Key Findings (from EDA + ML)** 📈

* Diabetes prevalence tripled since 1990.
* Men show slightly higher prevalence than women.
* Treatment coverage improved but remains under 50%.
* Risk clustering shows high-risk years increasing.

**🖼 Image – Risk Level Distribution**

<img width="377" height="376" alt="Part 2 3 1 Clustering (Unsupervised) – to group risk levels based on diabetes prevalence   treatment coverage" src="https://github.com/user-attachments/assets/60649181-10bf-4e9c-b733-0f1f3a9d3ff9" />

---

### **Power BI Visuals Access** 📁

Due to large file sizes, visuals are stored in Google Drive:
[View Power BI Visuals](https://drive.google.com/drive/folders/1ooPgSdl84ZJ1eZ1fWkBAWivKnEx0fVcf?usp=drive_link)

---
