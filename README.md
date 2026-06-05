# ⚡ Steel Industry Energy Consumption Analysis & Forecasting

## 👥 Authors (Group 8 - Business Intelligence)
* **Trần Thúy Hồng** (Data Analyst / Developer)
* **Huỳnh Hoàng Hải Yến**, **Nguyễn Thị Thanh Thảo**, **Trương Kim Đăng**, **Nguyễn Hương Thủy**

---

## 📌 1. Project Overview & Business Problem
The steel manufacturing industry is highly energy-intensive, representing a massive portion of industrial operational costs and carbon emissions. This project applies **Business Intelligence (BI)** and **Predictive Modeling** to analyze electricity consumption patterns and forecast future energy usage ($Usage\_kWh$). 

By accurately predicting energy needs, data-driven decisions can be made to optimize production scheduling, reduce peak load demand, control operational costs, and actively mitigate environmental impact ($CO_2$ emissions).

## 🎯 2. Project Objectives
* **Analyze:** Identify core factors and operational behaviors that heavily impact energy consumption.
* **Classify:** Categorize production load types (`Light`, `Medium`, `Maximum`) using supervised Machine Learning algorithms.
* **Forecast:** Develop a robust statistical forecasting model to predict electricity usage ($Usage\_kWh$).
* **Decision Support:** Build interactive BI dashboards to help management monitor energy trends in real-time[cite: 2].

## 🛠️ 3. Tools & Technologies Used
* **Data Preprocessing:** Python (Pandas, NumPy)[cite: 2]
* **Business Intelligence & Dashboard:** Power BI[cite: 2]
* **Machine Learning (Classification):** Orange Data Mining[cite: 2]
* **Statistical Analysis & Forecasting:** R Programming (VScode environment)[cite: 2]

---

## 🔄 4. Methodology & Implementation

### 📥 Data Preparation & ETL
* **Source:** Kaggle (Steel Industry Energy Consumption Dataset)[cite: 2].
* **Volume:** Initial dataset contained **28,032 rows and 20 columns**[cite: 2].
* **Preprocessing (Python):** Checked for duplicates and handled missing values (confirmed clean/complete dataset)[cite: 2].
* **Outlier Removal (R):** Applied the **IQR (Interquartile Range) method** to clean heavily skewed numerical distributions[cite: 2]. The dataset was filtered down to **20,384 rows** for stable modeling[cite: 2].
* **Feature Engineering:** One-Hot encoding applied to categorical features (`WeekStatus`, `Day_of_week`, `Load_Type`)[cite: 2], and Z-score standardization applied to numerical features[cite: 2].

### 🤖 Machine Learning Load-Type Classification (Orange)
We trained and evaluated four models to classify production loads (`Light`, `Medium`, `Maximum`)[cite: 2]:
1. **Decision Tree**[cite: 2]
2. **Support Vector Machine (SVM)**[cite: 2]
3. **Logistic Regression**[cite: 2]
4. **Random Forest**[cite: 2]

### 📈 Statistical Forecasting Model (R)
A **Multiple Linear Regression (MLR)** model was developed to forecast the exact $Usage\_kWh$ based on power factors, $CO_2$ emissions, normalized solar minutes (NSM), and load type categories[cite: 2]:

Usage_kWh = β0 + β1*(CO2) + β2*(Lagging_Reactive_Power) + β3*(Leading_Reactive_Power) + β4*(NSM) + ε


## 📊 5. Key Findings & Model Performance

### 💡 Business Intelligence Insights (Power BI)
* **The Energy-Carbon Link:** Electricity consumption shares a near-perfect positive correlation with carbon emissions (**$r = 0.99$**)[cite: 2]. Reducing energy use by 1% directly saves $3.21\text{ tCO}_2$[cite: 2].
* **Temporal Patterns:** **87% of total electricity** is consumed during weekdays (Monday to Friday), leaving weekends (13%) as prime opportunities for system maintenance and energy-saving tests[cite: 2].
* **Reactive Power Impact:** Lagging Current Reactive Power heavily affects efficiency (**$r = 0.90$**)[cite: 2]. Implementing proper power factor correction can optimize $5\% - 8\%$ of energy loss[cite: 2].

### 🤖 Machine Learning Evaluation Metrics
Across 10-fold stratified cross-validation, **Random Forest** comprehensively outperformed the other models[cite: 2]:

| Model | AUC | Classification Accuracy (CA) | F1-Score | Precision | Recall |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest** | **0.985** | **0.918** | **0.918** | **0.918** | **0.918** |
| Decision Tree | 0.932 | 0.901 | 0.901 | 0.901 | 0.901 |
| Logistic Regression | 0.917 | 0.787 | 0.786 | 0.791 | 0.787 |
| SVM | 0.782 | 0.689 | 0.669 | 0.662 | 0.689 |

> **Conclusion:** Random Forest provides highly robust, accurate, and stable classification for factory load management[cite: 2].

### 📉 Forecasting Accuracy
* The statistical forecasting model achieved an outstanding **R-squared value of 0.9746 (97.49% accuracy)**[cite: 2].
* The model's residuals tightly centered around 0 with a near-normal distribution, confirming predictive reliability[cite: 2].
* Forecasted outputs were successfully converted back from Z-scores to original **kWh scales** to be fully ready for management reporting[cite: 2].

---

## 🖼️ 6. Dashboard Preview

<img width="810" height="860" alt="image" src="https://github.com/user-attachments/assets/64f58114-c8d5-4ac4-9071-2eaf981a7e83" />
