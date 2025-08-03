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

## ℹ About NCD-RisC

**NCD-RisC** stands for **Non-Communicable Disease Risk Factor Collaboration**.

---

### **What does NCD-RisC do?**

* It is a **global network** of health researchers and institutions.
* It collects, harmonizes, and analyzes data on **non-communicable disease (NCD) risk factors** such as:
  * **Diabetes prevalence**
  * **Blood pressure**
  * **Obesity and BMI trends**
  * **Cholesterol levels**
* Its main focus is to track **long-term trends** in these health indicators across **countries and regions**.

---

### **How does NCD-RisC work?**

1. **Data Collection**
   * Collects health data from different sources worldwide (e.g., national health surveys, WHO data, academic research).
2. **Data Standardization**
   * Converts all data into a **standard format** so it can be compared across countries and years.
3. **Statistical Modeling**
   * Uses **advanced statistical models** to estimate trends (like diabetes prevalence from 1980 to the present).
   * Fills gaps where some countries or years have missing data.
4. **Global Reports**
   * Publishes results in **scientific journals** (e.g., The Lancet) and online databases for researchers and policymakers.
   * Provides open-access datasets (like the one you used) for **analysis and decision-making**.

---

### **Why is NCD-RisC important?**

* Helps **governments and health organizations** understand where **disease risks are rising or falling**.
* Supports **global health policies**, like those for diabetes prevention and treatment.
* Enables **researchers** to monitor progress toward health-related Sustainable Development Goals (SDGs).

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

*(Content unchanged from your original markdown)*

---

## **Part 4: Submission & Communication** 📤

*(Content unchanged from your original markdown)*

---

## **Acknowledgment** 🙏

Thanks to **Instructor: Maniraguha Eric** for guidance in the **Introduction to Big Data Analytics** course.

---

## ✅ Conclusion

This project demonstrated how Big Data Analytics can be harnessed to monitor, understand, and forecast diabetes trends across the globe.
By combining statistical analysis, machine learning, and powerful visualization tools, we identified key risk patterns and gaps in treatment coverage.
These insights not only reveal alarming trends but also emphasize the urgency for targeted public health interventions.
Ultimately, this work highlights the potential of data-driven approaches in transforming healthcare monitoring and decision-making.


