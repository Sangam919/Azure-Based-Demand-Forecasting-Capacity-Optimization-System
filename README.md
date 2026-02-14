# ☁️ Azure Demand Forecasting & Capacity Optimization System

<div align="center">

![Azure](https://img.shields.io/badge/Microsoft_Azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![ML](https://img.shields.io/badge/Machine_Learning-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Status](https://img.shields.io/badge/Status-Milestone_1_Complete-success?style=for-the-badge)

**Predictive system for Azure Compute and Storage demand forecasting**

Supporting the Azure Supply Chain team in optimized capacity provisioning decisions

[Overview](#-project-overview) • [Problem](#-problem-statement) • [Dataset](#-dataset-description) • [Milestones](#-project-milestones) • [Installation](#-installation) • [Usage](#-usage)

</div>

---

## 📋 Project Overview

This project focuses on building a **production-ready predictive system** to accurately forecast Azure Compute and Storage demand. The solution applies advanced data science, feature engineering, and machine learning techniques to drive forecasting accuracy and efficiency for the Azure Supply Chain team.

### 🎯 Project Objectives

- **Accurate Forecasting**: Predict Azure service demand with high precision across regions
- **Optimized Planning**: Support informed capacity provisioning decisions
- **Cost Reduction**: Minimize both over-investment and under-investment in infrastructure
- **Actionable Intelligence**: Deliver integrated insights for strategic decision-making

### 💰 Expected Business Impact

- Improved accuracy in forecasting Azure service demand
- Optimized capacity planning and provisioning across regions
- **Reduction in CAPEX waste**: ~$120M annual savings potential per 1% gain in accuracy
- Actionable intelligence for the Azure Supply Chain team via integrated insights

> **Impact**: For enterprise-scale cloud operations, even a 1% improvement in forecast accuracy translates to millions in infrastructure cost savings annually.

---

## 🚨 Problem Statement

### The Challenge

Cloud infrastructure providers face a critical challenge in capacity planning:

| Scenario | Problem | Business Impact |
|----------|---------|----------------|
| **Over-Provisioning** | Excessive capacity allocation | Wasted CAPEX, reduced ROI, idle resources |
| **Under-Provisioning** | Insufficient capacity for demand | Service degradation, customer churn, SLA violations |
| **Reactive Planning** | Manual, gut-feel decisions | Suboptimal resource allocation, missed opportunities |
| **Poor Visibility** | Limited demand forecasting | Strategic misalignment, emergency procurement |

### Our Solution

A **data-driven, ML-powered forecasting pipeline** that:
- Analyzes historical Azure Compute and Storage usage patterns (2+ years)
- Incorporates regional variations, seasonal trends, and external factors
- Provides accurate demand predictions for proactive capacity planning
- Enables strategic infrastructure investment decisions

---

## 📊 Dataset Description

### Overview

The dataset represents **enterprise-level historical Azure demand** aggregated across multiple dimensions for forecasting-ready analysis.

### Data Structure

| Column | Type | Description | Example Values |
|--------|------|-------------|----------------|
| `timestamp` | DateTime | Daily usage date | 2023-04-01 to 2025-03-31 |
| `region` | Categorical | Azure deployment region | US-East, US-West, Europe-North, India-South |
| `service_type` | Categorical | Service category | Compute, Storage |
| `usage_units` | Numerical | Actual demand consumed | 4,148 - 16,839 units |
| `provisioned_capacity` | Numerical | Allocated infrastructure capacity | 4,791 - 21,904 units |
| `cost_usd` | Numerical | Daily operational cost | $84.23 - $957.44 |
| `availability_pct` | Numerical | Service uptime percentage | 99.70% - 99.99% |
| `is_holiday` | Boolean | Holiday/special event indicator | 0 (No) / 1 (Yes) |

### Dataset Characteristics

```
📊 DATASET STATISTICS
────────────────────────────────────────────────────
Time Period         : April 1, 2023 → March 31, 2025
Total Duration      : 730 days (~2 years)
Total Records       : 5,200 observations
Geographic Regions  : 4 (US-East, US-West, Europe-North, India-South)
Service Categories  : 2 (Compute, Storage)
Data Frequency      : Daily aggregated usage
Missing Values      : 5.9% (usage), 5.9% (cost), 7.0% (availability)
Data Quality        : Realistic telemetry gaps simulated
```

### Key Patterns in Data

- **Temporal Coverage**: ~730 days of continuous daily observations
- **Multi-Regional**: 4 major Azure deployment regions
- **Service Diversity**: Compute and Storage workload types
- **Seasonality**: Embedded weekly, monthly, and holiday patterns
- **Realistic Noise**: Missing values simulating real-world telemetry gaps
- **Privacy Compliant**: Fully aggregated enterprise data, no customer-level information

### Sample Data Profile

```python
Total Usage Units: 46,471,918 units
Total Cost: $1,772,540.89
Average Utilization: 81.55%
Average Availability: 99.84%
Holiday Days: 551
```

---

## 🗺️ Project Milestones

### Timeline: 8 Weeks, 4 Major Milestones

```
Week 1-2: Data Foundation  →  Week 3-4: Feature Engineering  →  Week 5-6: Model Development  →  Week 7-8: Production Integration
```

---

### ✅ Milestone 1: Data Collection & Preparation (Weeks 1-2)

**Status**: ✅ **COMPLETED**

#### Objective
Compile and prepare historical and external datasets for modeling

#### Tasks Completed
- [x] Collected Azure Compute and Storage usage data with regional dimensions
- [x] Sourced external variables (holiday indicators, seasonal patterns)
- [x] Cleaned and validated datasets: addressed missing values, unified formats
- [x] Ensured data consistency and time-series readiness
- [x] Created initial derived features (utilization, cost metrics, temporal features)

#### Deliverables
✓ **Clean Dataset**: `azure_demand_cleaned.csv` (5,200 rows × 17 columns)  
✓ **Summary Report**: `milestone1_report.txt` with comprehensive data quality metrics  
✓ **Processing Script**: `milestone1_data_preparation.py` with full documentation

#### Key Results
- **100% Data Completeness**: All 978 missing values successfully imputed
- **No Duplicates**: Data integrity validated across timestamp-region-service combinations
- **Feature Enrichment**: Added 9 derived features for enhanced modeling capability
- **Ready for Modeling**: Time-series structure validated and optimized

---

### 🔄 Milestone 2: Feature Engineering & Data Wrangling (Weeks 3-4)

**Status**: 🔄 **IN PROGRESS**

#### Objective
Prepare the dataset for modeling through enrichment and transformation

#### Planned Tasks
- [ ] **Demand Pattern Analysis**
  - Identify usage trends, seasonal cycles, and anomalies
  - Analyze regional demand correlations
  - Study service-type specific behaviors
  
- [ ] **Advanced Feature Engineering**
  - Lag features (t-1, t-7, t-30, t-90, t-365)
  - Rolling statistics (7/14/30-day windows)
  - Exponential moving averages
  - Usage spike detection and quantification
  
- [ ] **Seasonality Encoding**
  - Day-of-week effects (weekday vs weekend patterns)
  - Monthly trends and quarter-end effects
  - Holiday proximity features
  - Seasonal decomposition (trend, seasonal, residual)
  
- [ ] **Capacity Metrics**
  - Utilization stress indicators
  - Over/under-provisioning flags
  - Capacity buffer efficiency scores
  - Regional capacity balance metrics
  
- [ ] **Dataset Transformation**
  - Reshape data into model-ready format
  - Normalize/standardize features where appropriate
  - Handle categorical encoding (one-hot, target encoding)
  - Split into training/validation/test sets

#### Expected Deliverables
- Engineered feature matrix optimized for time-series forecasting
- Feature importance analysis and selection report
- Correlation analysis and multicollinearity assessment
- Model-ready datasets with consistent schema

---

### 🎯 Milestone 3: Machine Learning Model Development (Weeks 5-6)

**Status**: 📅 **UPCOMING**

#### Objective
Build and validate models for accurate demand prediction

#### Planned Tasks
- [ ] **Baseline Model Development**
  - ARIMA/SARIMA for seasonal trends
  - Naive forecasting benchmarks
  - Simple moving averages
  
- [ ] **Advanced ML Models**
  - XGBoost regression (primary model)
  - Random Forest ensemble
  - LightGBM for performance optimization
  - Prophet for robust seasonality handling
  
- [ ] **Deep Learning Models** (If time permits)
  - LSTM for long-term dependencies
  - Temporal Convolutional Networks
  
- [ ] **Model Evaluation**
  - Comparative analysis using MAE, RMSE, MAPE
  - Forecast bias assessment
  - Directional accuracy validation
  - Region/service-specific performance metrics
  
- [ ] **Model Optimization**
  - Hyperparameter tuning (GridSearch/Bayesian optimization)
  - Cross-validation across time periods
  - Backtesting on historical data
  - Ensemble model development

#### Expected Deliverables
- Production-grade forecasting models with performance benchmarks
- Model comparison report with evaluation metrics
- Best model selection with justification
- Model documentation and deployment guidelines

---

### 🚀 Milestone 4: Forecast Integration & Capacity Planning (Weeks 7-8)

**Status**: 📅 **PLANNED**

#### Objective
Operationalize the model and integrate with Azure's provisioning ecosystem

#### Planned Tasks
- [ ] **Model Deployment**
  - Deploy models to production environment
  - Create real-time forecasting pipeline
  - Implement automated prediction workflows
  
- [ ] **Integration with Planning Tools**
  - Connect predictions with Azure capacity planning dashboards
  - Build decision support interfaces
  - Automate infrastructure action recommendations
  
- [ ] **Reporting & Visualization**
  - Create forecast dashboards
  - Generate automated reports
  - Surface forecast-driven insights
  
- [ ] **Monitoring & Maintenance**
  - Establish model performance monitoring
  - Implement drift detection mechanisms
  - Set up automated retraining logic
  - Create alerting for forecast anomalies

#### Expected Deliverables
- End-to-end operational forecasting system
- Integrated capacity planning dashboard
- Automated reporting pipeline
- Model monitoring and retraining framework

---

## 🛠️ Technical Stack

### Core Technologies

| Category | Tools & Libraries | Purpose |
|----------|------------------|---------|
| **Language** | Python 3.9+ | Primary development language |
| **Data Processing** | Pandas, NumPy | Data manipulation and analysis |
| **Visualization** | Matplotlib, Seaborn, Plotly | Exploratory analysis and reporting |
| **ML Framework** | Scikit-learn | Preprocessing, metrics, baseline models |
| **Forecasting** | XGBoost, LightGBM | Gradient boosting models |
| **Time-Series** | Statsmodels, Prophet | ARIMA, seasonal decomposition |
| **Deep Learning** | TensorFlow/PyTorch | LSTM networks (future) |
| **File Handling** | OpenPyXL, python-docx | Excel and document processing |

### Development Environment

```bash
Python >= 3.9
pandas >= 1.5.0
numpy >= 1.23.0
scikit-learn >= 1.2.0
xgboost >= 1.7.0
matplotlib >= 3.6.0
seaborn >= 0.12.0
statsmodels >= 0.14.0
openpyxl >= 3.1.0
```

---

## 📥 Installation

### Prerequisites

- Python 3.9 or higher
- pip package manager
- Git (optional, for cloning)

### Setup Instructions

```bash
# Option 1: Clone the repository (if using Git)
git clone https://github.com/yourusername/azure-demand-forecasting.git
cd azure-demand-forecasting

# Option 2: Download and extract ZIP
# Navigate to project directory
cd azure-demand-forecasting

# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Verify installation
python -c "import pandas, numpy, xgboost; print('✓ Installation successful!')"
```

### Dependencies (`requirements.txt`)

```txt
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
scikit-learn>=1.2.0
xgboost>=1.7.0
statsmodels>=0.14.0
openpyxl>=3.1.0
python-dateutil>=2.8.2
```

---

## 🚀 Usage

### Milestone 1: Data Preparation

```bash
# Run the data preparation script
python milestone1_data_preparation.py
```

**Outputs:**
- `azure_demand_cleaned.csv` - Cleaned and feature-enriched dataset
- `milestone1_report.txt` - Comprehensive data quality report

### Quick Start Example

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load cleaned dataset
df = pd.read_csv('azure_demand_cleaned.csv')
df['timestamp'] = pd.to_datetime(df['timestamp'])

# Basic analysis
print("Dataset Shape:", df.shape)
print("\nUtilization Summary:")
print(df.groupby('service_type')['utilization_rate'].describe())

# Visualize demand trends
plt.figure(figsize=(14, 6))
for region in df['region'].unique():
    region_data = df[df['region'] == region]
    plt.plot(region_data['timestamp'], region_data['usage_units'], 
             label=region, alpha=0.7)
plt.xlabel('Date')
plt.ylabel('Usage Units')
plt.title('Azure Demand Trends by Region')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()
```

---

## 📁 Project Structure

```
azure-demand-forecasting/
│
├── data/
│   ├── raw/
│   │   └── Azure_Enterprise_Realistic_Custom_Dataset.xlsx
│   ├── cleaned/
│   │   └── azure_demand_cleaned.csv
│   └── features/
│       └── (feature-engineered datasets - Milestone 2)
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_forecast_evaluation.ipynb
│
├── src/
│   ├── milestone1_data_preparation.py      # Data cleaning pipeline
│   ├── milestone2_feature_engineering.py   # Feature creation (upcoming)
│   ├── milestone3_model_training.py        # ML model development (upcoming)
│   └── milestone4_deployment.py            # Production integration (upcoming)
│
├── reports/
│   ├── milestone1_report.txt
│   └── (future milestone reports)
│
├── models/
│   └── (trained model artifacts - Milestone 3)
│
├── tests/
│   └── (unit tests for each module)
│
├── requirements.txt              # Python dependencies
├── README.md                     # This file
├── LICENSE                       # MIT License
└── .gitignore                    # Git ignore rules
```

---

## 📈 Current Progress & Results

### Milestone 1 Achievements

#### Data Quality Metrics
```
✓ Data Completeness: 100% (978 missing values imputed)
✓ No Duplicate Records
✓ Temporal Coverage: 730 days (Apr 2023 - Mar 2025)
✓ Geographic Coverage: 4 regions
✓ Service Coverage: 2 service types
✓ Feature Count: 17 (8 original + 9 derived)
```

#### Dataset Summary Statistics
```
Total Usage Units:     46,471,918 units
Total Cost:            $1,772,540.89
Average Utilization:   81.55%
Average Availability:  99.84%
Holiday Days Covered:  551
```

#### Feature Engineering (Basic)
- ✓ Utilization rate (usage/capacity %)
- ✓ Cost per unit efficiency
- ✓ Capacity buffer analysis
- ✓ Temporal features (year, month, quarter, day-of-week, day-of-month)
- ✓ Weekend flag

### Validation Results

| Check | Status | Details |
|-------|--------|---------|
| Missing Values | ✅ PASS | All imputed successfully |
| Data Types | ✅ PASS | Optimized for analysis |
| Date Continuity | ⚠️ MINOR | 648 records missing (some dates) |
| Capacity Constraints | ⚠️ REVIEW | 91 over-capacity violations (spike events) |
| Value Ranges | ✅ PASS | All within expected bounds |
| Duplicates | ✅ PASS | None found |

> **Note**: Capacity violations represent legitimate demand spikes that exceeded provisioned capacity—critical events for forecasting model to learn.

---

## 🎯 Success Metrics

### Project KPIs

| Metric | Target | Current Status |
|--------|--------|---------------|
| Forecast Accuracy (MAPE) | < 5% | TBD (Milestone 3) |
| Model Training Time | < 30 min | TBD (Milestone 3) |
| Data Completeness | 100% | ✅ **100%** |
| Feature Count | 25+ | 🔄 17 (expanding in M2) |
| Regions Covered | 4+ | ✅ **4 regions** |
| Time Horizon | 2+ years | ✅ **730 days** |

### Business Impact Projections

- **Cost Optimization**: Target 10-15% reduction in over-provisioning
- **Availability Improvement**: Maintain 99.9%+ SLA through better capacity planning
- **Planning Efficiency**: 80% reduction in manual forecasting effort
- **Financial Impact**: $120M+ annual savings potential (1% accuracy improvement)

---

## 🐛 Known Issues & Limitations

### Current Limitations

1. **Missing Data Points**: 648 date-region-service combinations missing (~12.5% of expected records)
   - **Impact**: Some dates don't have all 8 combinations (4 regions × 2 services)
   - **Mitigation**: Handled in Milestone 2 with interpolation and forecasting techniques

2. **Capacity Violations**: 91 instances where usage exceeded provisioned capacity
   - **Impact**: Indicates under-provisioning events or data quality issues
   - **Analysis**: These may be legitimate spike events requiring model attention

3. **Limited External Variables**: Currently only holiday flag available
   - **Future**: Add economic indicators, market trends, weather data

4. **Single Cost Model**: Using simplified cost calculation
   - **Future**: Incorporate actual Azure pricing tiers and regional cost variations

---

## 🤝 Contributing

Contributions, suggestions, and feedback are welcome! This is an internship project, but improvements are always appreciated.

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Add tests if applicable
5. Commit your changes (`git commit -m 'Add some improvement'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Azure Demand Forecasting Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 📞 Contact & Support

- **Project Maintainer**: Sangam Srivastav
- **Email**: sangamsri555@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/sangamsri/
- **Issues**: [GitHub Issues](https://github.com/Sangam919/azure-demand-forecasting/issues)

---

## 🙏 Acknowledgments

- Azure Supply Chain team for project guidance and domain expertise
- Microsoft Azure for cloud infrastructure insights
- Open-source data science community for tools and libraries
- Internship program mentors and supervisors

---

## 📚 References & Resources

### Related Documentation
- [Azure Architecture Best Practices](https://docs.microsoft.com/azure/architecture/)
- [Time Series Forecasting with Python](https://www.statsmodels.org/)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)

### Academic References
- Forecasting: Principles and Practice (Hyndman & Athanasopoulos)
- Applied Predictive Modeling (Kuhn & Johnson)
- Time Series Analysis and Its Applications (Shumway & Stoffer)

---

<div align="center">

**🎯 Current Milestone: 1/4 Complete ✅**

**⏰ Next Up: Feature Engineering & Data Wrangling (Weeks 3-4)**

---

**Built with ❤️ for Azure Supply Chain Optimization**

⭐ **Star this repo if you find it helpful!**

![Progress](https://img.shields.io/badge/Progress-25%25-yellow?style=for-the-badge)
![Milestone](https://img.shields.io/badge/Milestone-1%2F4_Complete-success?style=for-the-badge)

</div>
