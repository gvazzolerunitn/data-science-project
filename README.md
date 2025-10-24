# 🏥 Health Risk Prediction: Smoking & Drinking Analysis

Data science project to predict smoking/drinking behaviors and cardiovascular risk using medical health check-up data. Apply ML techniques for preventive healthcare interventions.
## 🎯 Project Goals
- Predict smoking status from clinical parameters
- Identify alcohol consumption using biomarkers
- Assess cardiovascular risk profiles
- Provide actionable recommendations for healthcare providers


## 📊 Dataset Overview

The dataset contains 24 variables collected from medical check-ups. Below is a table listing each variable, its description, and value/unit:

| Variable             | Description                                         | Values/Units                        |
|----------------------|-----------------------------------------------------|-------------------------------------|
| **sex**              | Sex                                                 | Male / Female                       |
| **age**              | Age                                                 | 20-65 years                         |
| **height**           | Height                                              | cm                                  |
| **weight**           | Weight                                              | kg                                  |
| **waistline**        | Waist circumference (obesity indicator)             | cm                                  |
| **sight_left/right** | Vision (left/right)                                 | 0.2-2.0 (normal=1.0)                |
| **hear_left/right**  | Hearing (left/right)                                | 1=Normal, 2=Impaired                |
| **SBP**              | Systolic blood pressure ⭐                           | mmHg (normal: 90-120)               |
| **DBP**              | Diastolic blood pressure ⭐                          | mmHg (normal: 60-80)                |
| **BLDS**             | Blood glucose ⭐                                     | mg/dL (normal: 70-100)              |
| **tot_chole**        | Total cholesterol ⭐                                 | mg/dL (optimal: <200)               |
| **HDL_chole**        | HDL cholesterol (good) ⭐                            | mg/dL (optimal: >40/50)             |
| **LDL_chole**        | LDL cholesterol (bad) ⭐                             | mg/dL (optimal: <100)               |
| **triglyceride**     | Triglycerides ⭐                                     | mg/dL (normal: <150)                |
| **hemoglobin**       | Hemoglobin                                          | g/dL                                |
| **urine_protein**    | Urine protein                                       | 1=Normal, 2-3=Elevated              |
| **serum_creatinine** | Serum creatinine (kidney function)                  | mg/dL                               |
| **SGOT_AST**         | AST (liver function) ⭐                              | U/L (normal: 10-40)                 |
| **SGOT_ALT**         | ALT (liver function) ⭐                              | U/L (normal: 7-56)                  |
| **gamma_GTP**        | Gamma-GT (alcohol biomarker) ⭐                      | U/L (normal: <55)                   |
| **SMK_stat_type_cd** | Smoking status (target)                             | 1=Never, 2=Ex-smoker, 3=Current     |
| **DRK_YN**           | Alcohol consumption (target)                        | Y=Drinker, N=Non-drinker            |

⭐ = key variables for cardiovascular/metabolic/liver risk


---

## 🔄 Project Pipeline

### 1. Data Loading & Initial Exploration
- Loaded 991,000+ medical records with 24 features
- No missing values detected
- Identified categorical variables: sex, drinking status, smoking status, hearing, urine protein

### 2. Exploratory Data Analysis (EDA)

**Target Distribution:**
- Smoking: Never (70.6%), Ex-smoker (16.8%), Current (12.6%)
- Drinking: Non-drinker (61.4%), Drinker (38.6%)

**Key Findings by Feature:**

*Smoking-related:*
- **SBP**: +2.4 mmHg in smokers (⭐⭐ moderate predictor)
- **HDL cholesterol**: -6.4 mg/dL in smokers (⭐⭐⭐ strong predictor)
- **LDL cholesterol**: minimal difference (⭐ weak predictor)
- **Waistline**: +5.2 cm in smokers (⭐ limited predictor)

*Drinking-related:*
- **Gamma-GTP**: +77% in drinkers (⭐⭐⭐⭐⭐ PRIMARY predictor)
- **Triglycerides**: +17.5% in drinkers (⭐⭐⭐ strong predictor)
- **AST**: +7.2% in drinkers (⭐⭐ supporting predictor)
- **ALT**: +13.7% in drinkers (⭐⭐ secondary predictor)

### 3. Data Preparation

**Label Encoding:**
- Sex: Male/Female → 0/1
- Drinking status: Y/N → 1/0

**Feature Engineering (14 new features):**
- Cardiovascular ratios: HDL/LDL ratio, BP ratio, total cholesterol
- Liver indicators: liver enzyme score, AST/ALT ratio, GTP/AST ratio
- Body composition: BMI, waist-height ratio
- Risk scores: cardiovascular risk, metabolic syndrome score
- Interactions: age-BP interaction, age-cholesterol interaction
- Binary indicators: hearing problems

**Correlation Analysis:**
- Generated heatmap for all features
- Identified top 15 correlated features for each target variable

**Train-Test Split:**
- 70% training / 30% test
- Stratified sampling to preserve class distributions

### 4. Modeling

**Task 1: Smoking Status Classification**
- Logistic Regression with GridSearchCV (C, solver, class_weight)
- Random Forest with GridSearchCV (n_estimators, max_depth, class_weight)
- 10% subsampling for hyperparameter tuning
- 2-fold cross-validation

**Task 2: Drinking Status Classification**
- Logistic Regression with GridSearchCV
- Random Forest with GridSearchCV
- Same optimization strategy as Task 1

### 5. Evaluation

**Metrics Used:**
- Accuracy score (primary metric)
- Confusion matrices
- Visual comparison via bar charts

**Feature Importance Analysis:**
- Logistic Regression coefficients (top 15)
- Random Forest feature importances (top 15)
- Separate analysis for smoking and drinking models

---

## 📈 Key Results Summary

**Best Performing Models:**
- Random Forest outperformed Logistic Regression for both tasks
- Strong accuracy achieved through engineered features
- Feature importance confirmed EDA insights

**Critical Features:**
- **Smoking**: HDL cholesterol, cardiovascular risk, age interactions
- **Drinking**: Gamma-GTP, liver enzyme score, triglycerides

**Clinical Implications:**
- Routine medical check-ups contain sufficient information to identify risky behaviors
- Liver enzymes are highly discriminative for alcohol consumption
- Cardiovascular markers effectively distinguish smoking status
