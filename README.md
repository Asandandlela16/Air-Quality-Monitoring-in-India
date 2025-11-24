# 🌫️ Air Quality Monitoring in India  
### *Data Cleaning • Exploratory Data Analysis • AQI Calculation • Multiple Linear Regression Modeling*

This project performs a complete end-to-end analysis of India’s air quality dataset, including pollutant index calculations, exploratory data analysis, and prediction of AQI (Air Quality Index) using **Multiple Linear Regression**.

---

## 📌 Project Overview

Air pollution is a major environmental challenge in India. In this project, we analyze historical air quality data from multiple states to:

- Clean and preprocess the large dataset (435k+ rows)
- Handle missing values and detect/remove outliers  
- Create pollutant-specific indices (SI, NI, RPI, SPI)
- Compute AQI based on Indian Government standards  
- Visualize pollutant distribution across states  
- Build multiple linear regression models to predict AQI  

---

## 🧰 Technologies Used

- **Python**
- **Pandas, NumPy**
- **Matplotlib, Seaborn**
- **Scikit-Learn**
- **Statsmodels**
- **Google Colab**

---

## 📥 Dataset Summary

- Rows: **435,742**
- Columns: **12**
- Pollutants studied:
  - **SO₂** (Sulphur Dioxide)  
  - **NO₂** (Nitrogen Dioxide)  
  - **RSPM** (Respirable Suspended Particulate Matter)  
  - **SPM** (Suspended Particulate Matter)

Initial inspection showed:
- Many missing values  
- Incorrect data types  
- Outliers in pollutant columns  

---

## 🧹 Data Cleaning Steps

### ✔️ Removed irrelevant columns
- `stn_code`, `agency`, `sampling_date`, `location_monitoring_station`

### ✔️ Handled missing values
Missing pollutant values were filled using **state-level mean imputation**.

### ✔️ Outlier Removal
Outliers were removed using **IQR (Interquartile Range)** for:
- SO₂  
- NO₂  
- RSPM  
- SPM  

### ✔️ Label Encoding
- Encoded `state` and `type` into numerical categories.

---

## 📊 Exploratory Data Analysis (EDA)

### 🔹 Pollutant Distribution by State  
Generated **bar plots** showing average SO₂, NO₂, RSPM, and SPM levels across Indian states.

### 🔹 Correlation Heatmap  
A heatmap was created to identify relationships among pollutant levels and AQI.

---

## 🧮 AQI & Pollutant Index Calculations

Following Indian CPCB standards, individual pollutant indices were computed:

- **SI** — SO₂ Index  
- **NI** — NO₂ Index  
- **RPI** — RSPM Index  
- **SPI** — SPM Index  

The overall AQI was calculated as:

AQI = max(SI, NI, RPI, SPI)


A new `AQI` column was added to the dataset.

---

## 🤖 Machine Learning Approach

### 🎯 Goal  
Predict **AQI** using pollutant concentrations and pollutant indices.

### 🧪 Three Multiple Linear Regression Models Built

#### **Model 1**  
Input variables:  
`si`, `ni`, `rpi`, `spi`

#### **Model 2**  
Input variables:  
`so2`, `no2`, `spm`

#### **Model 3**  
Input variables:  
`rspm`, `spm`, `spi`, `rpi`

Each model included:
- Dummy encoding  
- Train-test split  
- Prediction scatter plots  
- OLS summary  
- Cross-validation  

---

## 📈 Backward Elimination

A backward elimination function was implemented to automatically remove statistically insignificant features based on **p-values > 0.05**, improving model interpretability.

---

## 🧪 Model Evaluation

Models were evaluated using:

- **R² Score**  
- **Mean Squared Error (MSE)**  
- **10-Fold Cross-Validation**  ( training on 9 and evaluating on the rest) 
- **Scatter Plots for Predicted vs Actual AQI**  

---


---

## 🚀 Results & Insights

- AQI is most strongly influenced by particulate matter (**RSPM and SPM**).  
- Strong correlation observed between particulate pollutants and AQI.  
- Linear regression works but suffers from **multicollinearity**.  
- Feature engineering significantly boosted performance.

---


## 🙌 Acknowledgements

This project forms part of my Data Science portfolio.  
Datasets are sourced from publicly accessible government environmental records. You can find the orgn csv on my drive folder





