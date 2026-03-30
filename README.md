# ☁️ Azure Demand Forecasting & Capacity Optimization System 

<div align="center">

![Azure](https://img.shields.io/badge/Microsoft_Azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![ML](https://img.shields.io/badge/Machine_Learning-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

**End-to-End Azure Demand Forecasting System with ML, Power BI & Streamlit**

</div>

---

## 🚀 Live Demo

👉 **Streamlit Dashboard:**  
https://azure-forecasting.streamlit.app/

---

## 📋 Project Overview

This project focuses on building a **complete end-to-end predictive system** to forecast Azure Compute and Storage demand and optimize infrastructure capacity.

It covers:
- Data preprocessing  
- Feature engineering  
- Machine learning modeling  
- Forecast generation  
- Business insights via dashboards  

---

## 🎯 Problem Statement

Cloud providers must plan infrastructure in advance.

| Issue | Impact |
|------|--------|
| Over-Provisioning | Wasted cost |
| Under-Provisioning | Service downtime |
| Poor Forecasting | Bad planning decisions |

👉 Solution:  
A **data-driven forecasting system** that predicts demand and suggests capacity actions.

---

## 📊 Dataset

- 2 Years of Daily Data  
- 4 Regions: US-East, US-West, Europe-North, India-South  
- 2 Services: Compute, Storage  

Columns include:
- usage_units  
- provisioned_capacity  
- cost_usd  
- availability_pct  
- is_holiday  

---

## 🧠 Project Pipeline
Raw Data → Cleaning → Feature Engineering → ML Model → Forecast → Dashboards


---

## ⚙️ Technical Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib  
- Power BI  
- Streamlit  

---

## 🗺️ Milestones

### ✅ Milestone 1 – Data Preparation
- Cleaned dataset  
- Handled missing values  
- Created base features  

---

### ✅ Milestone 2 – Feature Engineering
- Lag features (t-1, t-7, t-30)  
- Rolling averages  
- Capacity metrics  

---

### ✅ Milestone 3 – Model Development

**Best Model:** Gradient Boosting  

| Metric | Value |
|------|------|
| MAE | 40 |
| RMSE | 89 |
| MAPE | 0.43% |
| R² | 0.9987 |

👉 Huge improvement from baseline (21% → 0.43%)

---

### ✅ Milestone 4 – Forecast & Deployment

- Generated 30-day forecasts  
- Built capacity recommendation logic  
- Created Power BI dashboard  
- Deployed Streamlit app  

---

## 📊 Power BI Dashboard

![Power BI Dashboard](powerbi_dashboard.png)

---

## 🌐 Streamlit Dashboard

Features:
- Interactive filtering  
- Forecast visualization  
- Region & service analysis  
- Capacity recommendations  
- Download forecast data  

Run locally:

```bash
pip install -r requirements.txt
streamlit run app.py
