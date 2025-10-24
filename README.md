# 🏥 Health Risk Prediction: Smoking & Drinking Analysis
## Overview

Data science project to predict smoking/drinking behaviors and cardiovascular risk using medical health check-up data. Apply ML techniques for preventive healthcare interventions.
🎯 Project Goals

    Predict smoking status from clinical parameters

    Identify alcohol consumption using biomarkers

    Assess cardiovascular risk profiles

    Provide actionable recommendations for healthcare providers

## 📊 Dataset

24 features from medical health check-ups:
#### Demographics

    sex: Male/Female

    age: 20-65 years

#### Anthropometrics

    height: cm

    weight: kg

    waistline: waist circumference (cm) - obesity indicator

#### Sensory

    sight_left/right: vision (0.2-2.0, normal=1.0)

    hear_left/right: hearing (1=Normal, 2=Impaired)

#### Cardiovascular ⭐

    SBP: Systolic BP (mmHg, normal: 90-120)

    DBP: Diastolic BP (mmHg, normal: 60-80)

#### Metabolic ⭐

    BLDS: Blood glucose (mg/dL, normal: 70-100)

    tot_chole: Total cholesterol (mg/dL, optimal: <200)

    HDL_chole: Good cholesterol (mg/dL, optimal: >40/50)

    LDL_chole: Bad cholesterol (mg/dL, optimal: <100)

    triglyceride: Triglycerides (mg/dL, normal: <150)

#### Hematological

    hemoglobin: g/dL

    urine_protein: 1=Normal, 2-3=Elevated

    serum_creatinine: kidney function (mg/dL)

#### Liver Function ⭐

    SGOT_AST: AST (U/L, normal: 10-40)

    SGOT_ALT: ALT (U/L, normal: 7-56)

    gamma_GTP: Gamma-GT (U/L, normal: <55) - alcohol biomarker

#### Target Variables 🎯

    SMK_stat_type_cd: 1=Never, 2=Ex-smoker, 3=Current smoker

    DRK_YN: Y=Drinker, N=Non-drinker

## 🔄 Project Pipeline (CRISP-DM)

```
1. Business Understanding
   → Define objectives, stakeholders, success metrics

2. Data Understanding
   → EDA, data quality, patterns, correlations

3. Data Preparation
   → Cleaning, feature engineering (BMI, risk scores), preprocessing

4. Modeling
   → Baseline: Logistic Regression, Decision Trees
   → Advanced: Random Forest, XGBoost, Neural Networks
   → Clustering: K-Means for patient segmentation

5. Evaluation
   → Metrics: Accuracy, Precision, Recall, F1, ROC-AUC
   → Feature importance, clinical interpretability

6. Deployment
   → Implementation plan, monitoring KPIs, recommendations
```

## 🔍 EDA Structure
#### 1. Univariate Analysis
- Distributions (histograms, box plots)
- Statistics (mean, median, std)
- Outliers detection
- Missing values

#### 2. Bivariate Analysis

- Correlation heatmap
- Smokers vs. non-smokers comparisons
- Drinkers vs. non-drinkers (focus on liver enzymes)
- Statistical tests (t-test, ANOVA)

#### 3. Multivariate Analysis
- PCA for dimensionality reduction
- Clustering exploration
- Feature interactions

#### 4. Feature Engineering
- BMI = weight / (height/100)²
- Pulse_Pressure = SBP - DBP
- Cholesterol_Ratio = Total Cholesterol / HDL
- Liver_Risk_Score = f(AST, ALT, Gamma-GTP)
- Age groups, BP categories, cholesterol levels

## 🤖 Modeling Strategy

#### Classification Tasks:
- Smoking status (multi-class: 3 categories)
- Drinking status (binary: Y/N)

#### Clustering:
- Patient risk segmentation

#### Evaluation:
- 5-fold cross-validation
- Metrics: Accuracy, F1, ROC-AUC
- SHAP values for interpretability
