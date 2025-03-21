# credit-card-fraud-detection
# Credit Risk Modeling

## Overview
This project focuses on building a predictive model for credit risk using a dataset with a highly imbalanced distribution of defaulters and non-defaulters. The goal is to improve the identification of high-risk accounts for better financial decision-making.

## Approach
### Data Preparation
- **Data Loading**: Used Pandas to load the dataset.
- **Data Cleaning**:  
  - Dropped columns with 100% missing values.  
  - Imputed missing numeric values using the median.
- **Feature Engineering**:  
  - Aggregated transaction and bureau attributes into total, mean, and standard deviation metrics.  
  - Identified anomalies using the Isolation Forest algorithm.

### Handling Data Imbalance
- **Categorization**: Grouped small categories (fewer than 100 records) into an 'Others' category.
- **Resampling**:  
  - SMOTE (Synthetic Minority Over-sampling) to balance the dataset.  
  - Undersampling of the majority class.
- **Class Weights**: Adjusted class weights to improve minority class detection.

### Model Selection
Evaluated multiple models:
- **Logistic Regression** (Baseline Model)
- **Random Forest** (Ensemble Model)
- **XGBoost** (Gradient Boosting Model)

### Performance Metrics
- **Confusion Matrix**: Analyzed TP, TN, FP, FN rates.
- **Precision, Recall, F1-Score**: Focused on minority class detection.
- **ROC-AUC Score**: Evaluated overall model performance.

### Model Evaluation Results
| Model               | Accuracy | ROC-AUC |
|--------------------|----------|----------|
| Logistic Regression | 71%      | 0.77     |
| Random Forest      | 99%      | 0.999    |
| XGBoost           | 99%      | 0.998    |

**Key Insight:** Random Forest outperformed other models with the highest recall and accuracy, making it the optimal choice.

## Key Findings
- **Credit Risk Identification**: Lower transaction values and higher bureau inquiries are strong indicators of default risk.
- **Feature Engineering**: Aggregating transaction metrics and identifying anomalies enhanced data quality and predictive power.
- **Business Application**: Insights from this model help financial institutions implement effective risk mitigation strategies.
- **Scalability**: The approach taken allows scalability for similar imbalanced datasets.

## Conclusion
Random Forest was selected as the final model due to its robustness and superior performance. The combination of feature engineering and resampling techniques provides a reliable framework for credit risk modeling, helping financial institutions detect high-risk accounts early.

---

## How to Use
1. Clone the repository.
   ```bash
   git clone https://github.com/yourusername/credit-risk-modeling.git


Requirements
Python 3.x
Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn
