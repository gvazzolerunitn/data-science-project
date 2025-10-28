# 🔬 Predictive Modeling of Lifestyle Risks

> **Machine learning approach for identifying individuals with risky lifestyle behaviors using clinical biomarkers**

## 🎯 Objective

This project aims to identify individuals with risky lifestyles (smoking and alcohol consumption) based on objective biomedical data, supporting preventive medicine approaches. By leveraging clinical biomarkers, we develop predictive models that help healthcare providers identify at-risk patients before lifestyle-related complications arise.

### Key Goals
- **Feature Engineering**: Transform raw clinical measurements into meaningful composite biomarkers
- **Alcohol Prediction**: Classify alcohol consumption using liver enzymes and metabolic indicators  
- **Smoking Prediction**: Identify smoking status through cardiovascular and hematologic markers
- **Model Comparison**: Evaluate Logistic Regression, Random Forest, and LightGBM performance

## 📊 Dataset Overview

This dataset is collected from **National Health Insurance Service in Korea**. All personal information and sensitive data were excluded.

**The purpose of this dataset is to:**
- Analysis of body signal
- Classification of smoker or drinker

### Dataset Structure

| Column | Description |
|--------|-------------|
| `sex` | male, female |
| `age` | round up to 5 years |
| `height` | round up to 5 cm [cm] |
| `weight` | [kg] |
| `sight_left` | eyesight (left) |
| `sight_right` | eyesight (right) |
| `hear_left` | hearing left, 1(normal), 2(abnormal) |
| `hear_right` | hearing right, 1(normal), 2(abnormal) |
| `SBP` | Systolic blood pressure [mmHg] |
| `DBP` | Diastolic blood pressure [mmHg] |
| `BLDS` | BLDS or FSG (fasting blood glucose) [mg/dL] |
| `tot_chole` | total cholesterol [mg/dL] |
| `HDL_chole` | HDL cholesterol [mg/dL] |
| `LDL_chole` | LDL cholesterol [mg/dL] |
| `triglyceride` | triglyceride [mg/dL] |
| `hemoglobin` | hemoglobin [g/dL] |
| `urine_protein` | protein in urine, 1(-), 2(+/-), 3(+1), 4(+2), 5(+3), 6(+4) |
| `serum_creatinine` | serum (blood) creatinine [mg/dL] |
| `SGOT_AST` | SGOT (Glutamate-oxaloacetate transaminase) AST (Aspartate transaminase) [IU/L] |
| `SGOT_ALT` | ALT (Alanine transaminase) [IU/L] |
| `gamma_GTP` | γ-glutamyl transpeptidase [IU/L] |
| `SMK_stat_type_cd` | **Smoking state**: 1(never), 2(used to smoke but quit), 3(still smoke) |
| `DRK_YN` | **Drinker or Not** |

## 🧪 Methodology

### Feature Engineering
Creation of composite biomarkers that capture complex physiological relationships:
- **BMI & WHtR**: Body composition indicators
- **De Ritis Ratio**: AST/ALT ratio for liver condition assessment
- **Pulse Pressure**: Arterial stiffness indicator
- **Cholesterol Ratios**: Cardiovascular risk markers

### Machine Learning Pipeline
- **Robust Preprocessing**: Handles missing values with median imputation
- **Advanced Models**: LightGBM integration alongside traditional algorithms
- **Class Balancing**: Optimized handling of imbalanced smoking categories
- **Feature Importance**: Comparative analysis across model types
