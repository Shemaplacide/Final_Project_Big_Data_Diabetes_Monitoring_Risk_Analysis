
### 🩺 Diabetes Monitoring & Risk Analysis using Big Data Analytics

**👤 Student Name:** Shema Placide  
**🆔 Student ID:** 26497  
**👨‍🏫 Course Instructor:** Maniraguha Eric  
**📚 Course:** Introduction to Big Data Analytics  

---

## 🎯 Welcome & Project Motivation

Diabetes is a global health challenge affecting millions of adults worldwide, leading to serious complications and increased healthcare costs.  
This project leverages **Big Data Analytics** to monitor diabetes prevalence trends, evaluate treatment coverage, classify risk levels, and forecast future patterns.  
The goal is to support **data-driven healthcare decision-making** and help identify key areas where interventions can have the greatest impact.

---

## 📂 Dataset Used

- **cleaned_diabetes_data** and **NCD_RisC_Lancet_2024_Diabetes_crude_world**  
- **Dataset Access Link:** [View Dataset](https://drive.google.com/drive/folders/1PYxHFTrmxE-gt9Yaw-heFdWxYCK0k8iO?usp=drive_link)

---

## 🏗 Project Structure

This project is divided into four main parts:

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

**Image – Cleaned Dataset Preview:**  
<img width="782" height="290" alt="Cleaned Dataset" src="https://github.com/user-attachments/assets/937f9401-731b-406d-8e94-ae84a83a587e" />

---

### **2.2 Exploratory Data Analysis (EDA)** 📊
- Generated **descriptive statistics** for prevalence and treatment coverage.  
- Visualized global trends and gender comparisons.  
- Explored multi-variable relationships.

**Image – Correlation Heatmap**  
<img width="341" height="272" alt="Part 2 3 Correlation heatmap – numerical strength of relationships (e g , prevalence vs year)" src="https://github.com/user-attachments/assets/b60cd041-6ede-49e1-bb37-6353cd350468" />  

**Image – Pairplot**  
<img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/cbdef612-2ba4-4642-8457-7388368955f6" />  

---

### **2.3 Machine Learning & Clustering** 🤖
We applied **KMeans Clustering** for risk segmentation and **Linear Regression** for predicting diabetes prevalence.  
This combination allowed us to identify high-risk groups and also forecast future prevalence values.

#### **KMeans Clustering Code Example**
```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# Select features
X = df[['Diabetes_Prevalence','Treatment_Proportion']]

# Scale values
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Train KMeans
kmeans = KMeans(n_clusters=3, random_state=42)
df['RiskCluster'] = kmeans.fit_predict(X_scaled)
````

#### **Linear Regression Code Example**

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

# Prepare data
X = df[['Year','Sex_encoded']]
y = df['Diabetes_Prevalence']

# Train model
model = LinearRegression()
model.fit(X, y)
y_pred = model.predict(X)

# Model evaluation
rmse = mean_squared_error(y, y_pred, squared=False)
print("RMSE:", rmse)
```

**Image – Clustering Visualization** <img width="369" height="362" alt="Part 2 3 2 Trained both models (Clustering + Regression)" src="https://github.com/user-attachments/assets/34aeba50-0cee-4eab-be67-6032dfd68fd8" />

**Image – Regression Prediction Plot** <img width="369" height="362" alt="Part 2 3 2 Trained both models (Clustering + Regression)" src="https://github.com/user-attachments/assets/aca98c5a-50a0-4554-ba3b-a32dc27552eb" />

---

### **2.4 Code Structure & Documentation** 🗂

* **Modular Functions** used for data cleaning, transformation, and model training.
* Clear markdown documentation ensured **academic clarity and reproducibility**.

---

### **2.5 Innovation** 🚀

* Used a **Random Forest Ensemble** to improve prediction accuracy beyond linear regression.
* Designed a **Custom Risk Score** combining prevalence and treatment coverage.

#### **Random Forest Code Example**

```python
from sklearn.ensemble import RandomForestRegressor

rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X, y)
importance = rf_model.feature_importances_
print("Feature Importance:", importance)
```

**Image – Random Forest Feature Importance** <img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/32c91d91-ebd5-4e94-92e6-93db5a247374" />

---

## **Part 3: Power BI Dashboard** 📊

### **3.1 Dashboard Structure (3)**

* Interactive dashboard with Year, Gender, and Risk Level slicers.
* Drill-down features and AI visuals.

**Image – Power BI Dashboard Structure** <img width="571" height="312" alt="Part 3 Power BI Dashboard Structure (3)" src="https://github.com/user-attachments/assets/5f9437e9-89eb-4f43-8e6c-c06d2ff8aea4" />

---

### **3.2 Global Diabetes Monitoring & Risk Analysis (1990–2022)** 🌍

* Trends in diabetes prevalence and treatment coverage.
* Gender-based comparisons and risk clusters.

**Image – Global Trend Chart** <img width="500" height="267" alt="Global trend" src="https://github.com/user-attachments/assets/9c9afcef-6f5c-43c8-b152-ab8c03cad373" />

---

### **3.3 Key Findings (from EDA + ML) (2)** 📈

* Diabetes prevalence nearly tripled since 1990.
* Men show slightly higher prevalence than women.
* Treatment coverage improved but is still <50%.
* Clustering identified high-risk years; forecast shows further increases.

**Image – Risk Level Distribution** <img width="377" height="376" alt="Part 2 3 1 Clustering (Unsupervised) – to group risk levels based on diabetes prevalence   treatment coverage" src="https://github.com/user-attachments/assets/60649181-10bf-4e9c-b733-0f1f3a9d3ff9" />

---

### **Power BI Visuals Access** 📁

Due to large file sizes, all Power BI visuals are stored in Google Drive:
[View Power BI Visuals](https://drive.google.com/drive/folders/1ooPgSdl84ZJ1eZ1fWkBAWivKnEx0fVcf?usp=drive_link)

---

## **Part 4: Submission & Communication** 📤

* **GitHub Repository:** Well-structured folders (data, notebooks, models, dashboard, docs).
* **PowerPoint Presentation:** Covers introduction, methodology, results, recommendations, and future work.

  * **Presentation Link:** [View PowerPoint](https://docs.google.com/presentation/d/1tpPkm4ouUMJ5j2fuXFrhY-X9NtyHOXZD/edit?usp=sharing&ouid=101928335647300964929&rtpof=true&sd=true)

---

## **Acknowledgment** 🙏

Thanks to **Instructor: Maniraguha Eric** for guidance in the **Introduction to Big Data Analytics** course.

---

## **How to Run** 🖥

1. Clone this repository.
2. Run Jupyter notebooks in `/notebooks`.
3. Open `Diabetes_Risk_Analysis.pbix` in Power BI Desktop.

---

```

