# Employee Attrition Analysis

## Table of Contents
- [Overview](#overview)
- [Data Preprocessing](#data-preprocessing)
- [Data Analysis](#data-analysis)
- [Model Building](#model-building)
- [Results](#results)
- [Conclusion](#conclusion)

## Overview
This project focuses on analyzing employee attrition using a dataset (`employees.csv`). The dataset contains both categorical and numeric features, and the goal is to predict whether an employee will leave the company (target feature: `leave`). The analysis involves data characterization, preprocessing, visualization, and building a predictive model using `HistGradientBoostingClassifier`.

## Data Preprocessing
### Steps:
#### Handling Missing Values:
- Replaced missing `career_years` with the median.
- Replaced missing `education_level` and `work_from_home` with the mode.

#### Handling Negative Values:
- Replaced negative `company_years` with `0`.

#### Standardizing Categorical Values:
- Unified values in `education_level` (e.g., "UG Degree" → "Undergrad Degree").
- Unified values in `hiring_source` (e.g., "Direct Hire" → "Direct").
- Unified values in `travel_frequently` (e.g., "Y" → "Yes", "N" → "No").

#### Dropping Irrelevant Columns:
- Removed `employee_id` as it is not useful for analysis.

## Data Analysis
### Key Insights:
#### Target Variable (`leave`):
- The dataset is imbalanced, with more employees staying than leaving.

#### Categorical Features:
- Employees in the Sales department and Junior job levels are more likely to leave.
- Employees hired through referrals are less likely to leave.

#### Numeric Features:
- Younger employees, those with lower salaries, and shorter tenures are more likely to leave.
- Employees with longer commuting distances are more likely to leave.

## Model Building
### Model Used:
- `HistGradientBoostingClassifier`: Suitable for handling both categorical and numeric features.

### Steps:
1. Encoded categorical features using `LabelEncoder`.
2. Split the dataset into training and testing sets (70:30 ratio).
3. Trained the model and evaluated its performance.

## Results
### Model Performance:
- **Accuracy**: 84%

#### Classification Report:
- Precision, recall, and F1-score were higher for the majority class (employees staying).
- The model struggled with the minority class (employees leaving), indicating room for improvement.

#### Feature Importance:
- Dropping less impactful features like `department` and `age` resulted in a slight decrease in accuracy (81%), suggesting these features contribute to the model's performance.

## Conclusion
The analysis highlights key factors influencing employee attrition, such as job level, salary, and commuting distance. The predictive model performs well but could be improved by addressing class imbalance and refining feature selection. Future work could involve experimenting with other algorithms and techniques to enhance performance.
