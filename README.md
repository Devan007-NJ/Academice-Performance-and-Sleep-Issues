# 📊 Sleep Patterns & Academic Performance Prediction

## 📌 Project Overview
This project analyzes how **sleep habits and lifestyle factors** influence **academic performance** among students.  
Using a **Random Forest Regression model**, we predict students’ academic performance based on **ordinal survey responses** related to sleep quality, stress, fatigue, and daily habits.

The project focuses on:
- Careful **ordinal encoding** of survey data
- Clean **exploratory analysis**
- Building a **robust regression model**
- Interpreting results using appropriate regression metrics

---

## 🎯 Problem Statement
Students often experience irregular sleep patterns that affect their concentration, productivity, and academic outcomes.  
The goal of this project is to **model the relationship between sleep-related factors and academic performance** and quantify how accurately performance can be predicted from these variables.

---

## 🧠 Dataset Description
The dataset consists of student survey responses with **ordinal and categorical features**, including:

- Sleep quality
- Sleep duration
- Daytime fatigue
- Difficulty concentrating
- Class absenteeism due to sleep
- Stress related to academics
- Caffeine intake
- Physical activity
- Academic performance (target variable)

All ordinal responses were **manually mapped** to numeric scales while preserving their semantic order.

---

## 🔄 Data Preprocessing
Key preprocessing steps:
- Trimmed and standardized text responses
- Applied **custom ordinal mappings** for each question
- Handled missing values after encoding
- Converted categorical variables (e.g., gender, year of study) to numeric form
This ensured the dataset was **model-ready and free of encoding bias**.

---

## 🤖 Model Used
### **Random Forest Regressor**
### **XGBoostRegressor**

From the two models we can see that XGBoost performed slighlty better than RandomForest with its MAE differing by 0.02
The **results** from plotting both models are:
- The model is very accurate on low ordinal scales (0-3)
- Model becomes unstable on high ordinal values due to skewed data
- Log transformation greatly helps in decreasing the gap of prediction between the ordinal scales
- Previous MAE pre-transformation was around 0.25-0.55 but has decreased with log transformation
- Sample weights have also been provided to the XGBoost for better results
### Model Configuration
```python
RandomForestRegressor(
    max_depth=6,
    random_state=100
)
XGBoostRegressor(n_estimators=250,
    max_depth=8,
    random_state=100,
    learning_rate=0.25,
    subsample=0.9
)
