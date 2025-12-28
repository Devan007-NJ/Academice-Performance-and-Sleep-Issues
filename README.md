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

Random Forest was chosen because:
- It handles **non-linear relationships** well
- It works effectively with **ordinal-encoded features**
- It is robust to noise common in survey data
- Requires minimal assumptions about data distribution

### Model Configuration
```python
RandomForestRegressor(
    max_depth=6,
    random_state=100
)
