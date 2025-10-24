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

## 🔄 Project Pipeline (CRISP-DM)

| Step                     | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **1. Business Understanding**   | Define objectives, stakeholders, and success metrics                        |
| **2. Data Understanding**       | Exploratory data analysis, data quality, patterns, correlations             |
| **3. Data Preparation**         | Cleaning, feature engineering (BMI, risk scores), preprocessing             |
| **4. Modeling**                 | Baseline: Logistic Regression, Decision Trees; Advanced: RF, XGBoost, NN    |
| **5. Evaluation**               | Metrics: Accuracy, Precision, Recall, F1, ROC-AUC; feature importance       |
| **6. Deployment**               | Implementation plan, monitoring KPIs, recommendations                       |

---

## 🔍 Exploratory Data Analysis (EDA)

**1. Univariate Analysis**
  - Distributions (histograms, box plots)
  - Statistics (mean, median, std)
  - Outlier detection
  - Missing values

**2. Bivariate Analysis**
  - Correlation heatmap
  - Smokers vs. non-smokers comparisons
  - Drinkers vs. non-drinkers (focus on liver enzymes)
  - Statistical tests (t-test, ANOVA)

**3. Multivariate Analysis**
  - PCA for dimensionality reduction
  - Clustering exploration
  - Feature interactions

**4. Feature Engineering**
  - BMI = weight / (height/100)²
  - Pulse Pressure = SBP - DBP
  - Cholesterol Ratio = Total Cholesterol / HDL
  - Liver Risk Score = f(AST, ALT, Gamma-GTP)
  - Age groups, BP categories, cholesterol levels

---

## 🤖 Modeling Strategy

| Task                | Description                                      |
|---------------------|--------------------------------------------------|
| **Classification**  | Smoking status (multi-class: 3 categories)       |
|                     | Drinking status (binary: Y/N)                    |
| **Clustering**      | Patient risk segmentation                        |
| **Evaluation**      | 5-fold cross-validation, Accuracy, F1, ROC-AUC   |
|                     | SHAP values for interpretability                 |
