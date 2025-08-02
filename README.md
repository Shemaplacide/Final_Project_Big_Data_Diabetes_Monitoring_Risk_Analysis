### 🩺 Diabetes Monitoring & Risk Analysis using Big Data Analytics

**👤 Student Name:** Shema Placide  
**🆔 Student ID:** 26497  
**👨‍🏫 Course Instructor:** Maniraguha Eric  
**📚 Course:** Introduction to Big Data Analytics  

---

## 🎯 Welcome & Project Motivation

Diabetes is a global health challenge affecting millions of adults worldwide, leading to serious complications and increased healthcare costs.  
This project uses **Big Data Analytics** to:  
- Monitor diabetes prevalence trends  
- Evaluate treatment coverage  
- Classify risk levels  
- Forecast future patterns  

The goal is to support **data-driven healthcare decision-making** and identify key areas where interventions are most needed.

---

## 📂 Dataset Used

- **Datasets:** `cleaned_diabetes_data` and `NCD_RisC_Lancet_2024_Diabetes_crude_world`  
- **Dataset Access Link:** [View Dataset](https://drive.google.com/drive/folders/1PYxHFTrmxE-gt9Yaw-heFdWxYCK0k8iO?usp=drive_link)

### ℹ️ Key Definitions
- **Diabetes Prevalence:**  
  Percentage of people in a population who have diabetes at a given point in time.  
  *Example:* If 100 out of 1,000 adults have diabetes, prevalence = **10%**.  
  *Why it matters:* Shows how widespread diabetes is and helps measure progress in controlling it.

- **Treatment Proportion:**  
  Percentage of people with diabetes who are receiving proper treatment (like insulin or oral medications).  
  *Example:* If 100 people have diabetes but only 40 are on treatment, treatment proportion = **40%**.  
  *Why it matters:* Low treatment coverage means many diagnosed people are not getting necessary care, leading to serious health complications.

---

## 🏗 Project Structure

This project is divided into four main parts:  
1. **Problem Definition & Planning**  
2. **Python Analytics Tasks**  
3. **Power BI Dashboard**  
4. **Submission & Communication**

---

## **Part 1: Problem Definition & Planning** 📝

### What We Did
- **Sector Selection:** Health sector (Diabetes focus).  
- **Problem Statement:**  
  *“Can we monitor and analyze global diabetes trends, classify risk levels, and forecast future prevalence to support better healthcare planning?”*  
- **Dataset Identification:**  
  - **Title:** NCD RisC Lancet 2024 – Global Diabetes Crude Prevalence  
  - **Structure:** Structured CSV dataset with 66 rows and 11 columns.  
  - **Status:** Required preprocessing.

---

## **Part 2: Python Analytics Tasks** 🐍

### **2.1 Cleaned Dataset** 🧹
- Removed empty columns (e.g., `ISO`)  
- Standardized categorical values (`Sex`, `Age`)  
- Converted year to numeric and handled outliers  

**Image – Cleaned Dataset Preview:**
  
<img width="782" height="290" alt="Cleaned Dataset" src="https://github.com/user-attachments/assets/937f9401-731b-406d-8e94-ae84a83a587e" />

---

### **2.2 Exploratory Data Analysis (EDA)** 📊
- Generated descriptive statistics (mean, min, max, standard deviation)  
- Visualized trends in diabetes prevalence and treatment coverage  
- Compared gender differences and studied variable relationships  

**Image – Correlation Heatmap**

<img width="341" height="272" alt="Part 2 3 Correlation heatmap – numerical strength of relationships (e g , prevalence vs year)" src="https://github.com/user-attachments/assets/b60cd041-6ede-49e1-bb37-6353cd350468" />  

**Image – Pairplot**
 
<img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/cbdef612-2ba4-4642-8457-7388368955f6" />  

---

### **2.3 Machine Learning & Clustering** 🤖
We used:  
- **KMeans Clustering:** to group countries/years into Low, Medium, and High risk levels  
- **Linear Regression:** to predict diabetes prevalence based on Year and Gender  

#### **KMeans Example**
```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

X = df[['Diabetes_Prevalence','Treatment_Proportion']]
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

kmeans = KMeans(n_clusters=3, random_state=42)
df['RiskCluster'] = kmeans.fit_predict(X_scaled)
````

#### **Regression Example**

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

X = df[['Year','Sex_encoded']]
y = df['Diabetes_Prevalence']

model = LinearRegression()
model.fit(X, y)
y_pred = model.predict(X)
rmse = mean_squared_error(y, y_pred, squared=False)
print("RMSE:", rmse)
```

**Image – Clustering Visualization**

<img width="369" height="362" alt="Part 2 3 2 Trained both models (Clustering + Regression)" src="https://github.com/user-attachments/assets/34aeba50-0cee-4eab-be67-6032dfd68fd8" />

**Image – Regression Prediction Plot**

<img width="369" height="362" alt="Part 2 3 2 Trained both models (Clustering + Regression)" src="https://github.com/user-attachments/assets/aca98c5a-50a0-4554-ba3b-a32dc27552eb" />

---

### **2.4 Code Structure & Documentation** 🗂

* Modular functions for cleaning, EDA, modeling, and evaluation
* Markdown explanations and comments for clarity and reproducibility

---

### **2.5 Innovation** 🚀

* **Random Forest Ensemble:** improved prediction performance beyond simple regression
* **Custom Risk Score:** combined prevalence and treatment coverage

#### **Random Forest Example**

```python
from sklearn.ensemble import RandomForestRegressor

rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X, y)
print("Feature Importance:", rf_model.feature_importances_)
```

**Image – Random Forest Feature Importance** 

<img width="447" height="406" alt="Part 2 3 Pairplot – explores multi-variable relationships and gender separation" src="https://github.com/user-attachments/assets/32c91d91-ebd5-4e94-92e6-93db5a247374" />

---

## **Part 3: Power BI Dashboard** 📊

### **3.1 Dashboard Structure**

* Interactive dashboard with slicers for Year, Gender, and Risk Level
* Drill-down options and AI visuals

**Image – Power BI Dashboard Structure**

<img width="571" height="312" alt="Part 3 Power BI Dashboard Structure (3)" src="https://github.com/user-attachments/assets/5f9437e9-89eb-4f43-8e6c-c06d2ff8aea4" />

---

### **3.2 Global Diabetes Monitoring & Risk Analysis (1990–2022)** 🌍

* Showed trends in diabetes prevalence and treatment coverage
* Highlighted gender differences and risk clusters

**Image – Global Trend Chart** 

<img width="500" height="267" alt="Global trend" src="https://github.com/user-attachments/assets/9c9afcef-6f5c-43c8-b152-ab8c03cad373" />

---

### **3.3 Key Findings (EDA + ML)** 📈

* Diabetes prevalence has almost tripled since 1990
* Men show slightly higher prevalence than women
* Treatment coverage improved but is still under 50% globally
* Clustering identified high-risk periods, and forecasts indicate future increases

**Image – Risk Level Distribution** 
<img width="377" height="376" alt="Part 2 3 1 Clustering (Unsupervised) – to group risk levels based on diabetes prevalence   treatment coverage" 
  
  src="https://github.com/user-attachments/assets/60649181-10bf-4e9c-b733-0f1f3a9d3ff9" />

---

### **Power BI Visuals Access**

Due to large file sizes, Power BI visuals are stored in Google Drive:
[View Power BI Visuals](https://drive.google.com/drive/folders/1ooPgSdl84ZJ1eZ1fWkBAWivKnEx0fVcf?usp=drive_link)

---

## **Part 4: Submission & Communication** 📤

* **GitHub Repository:** includes data, notebooks, models, dashboard, and docs
* **PowerPoint Presentation:** summary of introduction, methods, results, and recommendations

  * **Presentation Link:** [View PowerPoint](https://docs.google.com/presentation/d/1tpPkm4ouUMJ5j2fuXFrhY-X9NtyHOXZD/edit?usp=sharing&ouid=101928335647300964929&rtpof=true&sd=true)

---

## **Acknowledgment** 🙏

Thanks to **Instructor: Maniraguha Eric** for guidance in the **Introduction to Big Data Analytics** course.

---

## **How to Run** 🖥

1. Clone this repository
2. Run Jupyter notebooks in `/notebooks`
3. Open `Diabetes_Risk_Analysis.pbix` in Power BI Desktop

---
