# 🎯 Employee Retention Prediction - Salifort Motors

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)

A comprehensive machine learning project predicting employee turnover using HR analytics data. This project demonstrates end-to-end data science workflow from exploratory analysis to model deployment recommendations.

## 📊 Project Overview

Salifort Motors HR department collected employee data but needed insights on retention factors. This project builds a predictive model to identify employees at risk of leaving and provides actionable recommendations for improving retention.

### Key Results
- **Model Accuracy**: 96.2%
- **Precision**: 87.0%
- **Recall**: 90.4%
- **Current Turnover Rate**: 16.6%
- **Dataset**: 14,999 employees, 10 features

## 🎯 Business Problem

**Challenge**: High employee turnover is costly due to recruitment expenses, training investments, lost productivity, and knowledge drain.

**Solution**: Build a machine learning model to:
1. Identify employees at risk of leaving
2. Uncover key factors driving turnover
3. Provide data-driven recommendations for HR

## 📁 Repository Structure

```
salifort-hr-analytics/
│
├── data/                          # Dataset files
│   └── HR_capstone_dataset.csv
│
├── notebooks/                     # Jupyter notebooks
│   └── HR_Analytics_Analysis.ipynb
│
├── reports/                       # Presentation and reports
│   └── Salifort_Motors_HR_Analytics_Portfolio.pptx
│
├── README.md                      # Project documentation (this file)
├── requirements.txt               # Python dependencies
└── .gitignore                     # Git ignore file
```

## 🔍 Key Findings

### Critical Insights
1. **Overwork Crisis**: All 145 employees with 7 projects left the company (100% turnover)
2. **Work Hours**: Employees worked an average of 201 hours/month (vs. normal 167 hours)
3. **Satisfaction Gap**: Employees who left had 0.44 avg satisfaction vs. 0.67 for those who stayed
4. **Promotion Rate**: Only 2.1% of employees were promoted in the last 5 years
5. **4-Year Anomaly**: Employees with 4-year tenure show unusually low satisfaction

### Top Predictive Features
1. **Last Evaluation Score** - Strongest predictor (100% importance)
2. **Number of Projects** - Second most important (92% importance)
3. **Tenure** - Years with company (63% importance)
4. **Overworked Status** - Working >175 hrs/month (41% importance)

## 🤖 Models Tested

| Model | Accuracy | Precision | Recall | F1-Score | AUC |
|-------|----------|-----------|--------|----------|-----|
| Logistic Regression | 82.0% | 79.0% | 82.0% | 80.0% | — |
| Decision Tree (Round 1) | 97.2% | 91.5% | 91.7% | 91.6% | 96.9% |
| Random Forest (Round 1) | 98.0% | 95.0% | 91.6% | 93.2% | 98.0% |
| Decision Tree (Round 2) | 95.9% | 85.7% | 90.4% | 87.9% | 95.9% |
| **Random Forest (Round 2)** ✓ | **96.2%** | **87.0%** | **90.4%** | **88.7%** | **96.5%** |

**Champion Model**: Random Forest (Round 2) with feature engineering

## 🛠️ Technical Implementation

### Data Processing
- Removed 3,008 duplicates (20% of data)
- Handled 824 outliers in tenure variable
- Encoded categorical variables (department, salary)
- Created binary 'overworked' feature (>175 hrs/month threshold)

### Feature Engineering
To prevent data leakage and ensure real-world applicability:
- **Removed**: `satisfaction_level` (may not be available for prediction)
- **Removed**: `average_monthly_hours` (detailed tracking may not exist)
- **Created**: `overworked` binary indicator from monthly hours

### Model Optimization
- **Strategy**: GridSearchCV with 4-fold cross-validation
- **Train/Test Split**: 75% / 25% (stratified)
- **Hyperparameter Tuning**: Exhaustive search over decision tree depth, leaf samples, and forest size

## 💡 Recommendations for HR

### 1. Cap Project Workload 📊
- Limit employees to maximum 5 concurrent projects
- Monitor and redistribute workload proactively
- Critical finding: All employees with 7 projects left

### 2. Address Overwork Culture ⏰
- Set realistic hour expectations (≤175 hrs/month)
- Implement fair overtime policies or compensation
- Track and reward efficiency, not just hours worked

### 3. Promote High Performers 🎓
- Target 4-year employees with retention programs
- Increase promotion rate (currently only 2.1%)
- Create clear advancement pathways

### 4. Improve Feedback Culture 💬
- Align performance evaluations with employee satisfaction
- Regular check-ins for high-performing employees
- Address dissatisfaction before it leads to turnover

## 📈 Expected Business Impact

| Metric | Expected Improvement |
|--------|---------------------|
| Turnover Reduction | 20-30% |
| Annual Cost Savings | $500K+ |
| Retention Rate Improvement | 5-7% |
| HR Process Efficiency | +40% |

## 🚀 Next Steps

1. Deploy model in production environment
2. Create monthly risk reports for HR team
3. Build real-time monitoring dashboard
4. Conduct A/B testing on intervention strategies
5. Collect feedback and retrain model quarterly
6. Investigate 4-year tenure satisfaction dip

## 💻 Technologies Used

**Languages & Libraries:**
- Python 3.8+
- pandas, numpy - Data manipulation
- matplotlib, seaborn - Visualization
- scikit-learn - Machine learning
- XGBoost - Gradient boosting
- pickle - Model serialization

**Tools:**
- Jupyter Notebook
- Git/GitHub
- GridSearchCV for hyperparameter tuning

## 📋 Installation & Usage

### Prerequisites
```bash
Python 3.8 or higher
pip package manager
```

### Setup
```bash
# Clone the repository
git clone https://github.com/Anees-ul-Mujtaba/salifort-hr-analytics.git
cd salifort-hr-analytics

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook notebooks/Salifort_Motors_Capstone_project_lab.ipynb
```

### Running the Analysis
1. Open the Jupyter notebook
2. Run cells sequentially to reproduce the analysis
3. Model will be saved as pickle file for deployment

## 📊 Dataset Information

**Source**: Salifort Motors HR Department  
**Size**: 14,999 employees (after removing duplicates)  
**Features**: 10 variables including satisfaction levels, performance scores, workload metrics

### Variables
- `satisfaction_level` - Employee job satisfaction [0-1]
- `last_evaluation` - Performance review score [0-1]
- `number_project` - Number of projects assigned
- `average_monthly_hours` - Hours worked per month
- `tenure` - Years with company
- `work_accident` - Workplace accident occurrence (0/1)
- `left` - **Target variable**: Employee departed (0/1)
- `promotion_last_5years` - Recent promotion (0/1)
- `department` - Employee department
- `salary` - Salary category (low/medium/high)

## 🎓 Skills Demonstrated

**Data Science:**
- Exploratory Data Analysis (EDA)
- Statistical Analysis
- Feature Engineering
- Machine Learning (Classification)
- Model Evaluation & Selection
- Data Visualization

**Machine Learning:**
- Logistic Regression
- Decision Trees
- Random Forests
- GridSearchCV Optimization
- Cross-validation
- Handling Imbalanced Data

**Business Intelligence:**
- Stakeholder Communication
- Data-Driven Recommendations
- Insight Generation
- Strategic Planning

## 📧 Contact

**Anees ul Mujtaba**  
- LinkedIn: https://www.linkedin.com/in/anees-ul-mujtaba/
- Email: aneesrathore4@gmail.com
- Portfolio: https://github.com/Anees-ul-Mujtaba

## 🙏 Acknowledgments

- Dataset provided as part of Google Advanced Data Analytics Professional Certificate
- Project completed as capstone for data science program
- Analysis framework based on PACE methodology (Plan, Analyze, Construct, Execute)

**⭐ If you found this project helpful, please consider giving it a star!**
