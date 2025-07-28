66# Heart Disease Prediction: Exploratory Data Analysis (EDA) and Machine Learning


## Overview

This project performs detailed **Exploratory Data Analysis (EDA)** and predictive modeling on the **UCI Heart Disease dataset**. The dataset contains medical features from real patients, and the goal is to predict the presence or absence of heart disease using machine learning techniques.

This README covers the entire data exploration process, insights drawn from various plots, and outlines the next steps towards developing ML models.

---

## Dataset Details

- **Source**: [UCI Machine Learning Repository - Heart Disease Dataset](https://archive.ics.uci.edu/ml/datasets/heart+Disease)
- **Instances**: 303 patient records (Cleveland subset)
- **Features**: 13 clinical attributes including age, sex, chest pain type, blood pressure, cholesterol, max heart rate, and others.
- **Target**: Binary classification, where 0 = no disease, 1 = presence of heart disease (simplified from original multi-class labels)

---

## Exploratory Data Analysis (EDA)

### 1. Data Loading and Cleaning

- Loaded the data from UCI repository.
- Replaced missing values represented by '?' with `NaN`.
- Converted relevant columns (`ca` and `thal`) to numeric types.
- Dropped rows with missing values to ensure clean analysis.

### 2. Target Variable Distributio

- The dataset shows a mild class imbalance.
- More patients have heart disease (target=1) than not (target=0) after binarization.
- This imbalance should be considered in later modeling stages.

### 3. Univariate Analysis

#### Numeric Features Distribution

- **Age**: Majority between 40 and 60 years.
- **Cholesterol and Blood Pressure**: Right-skewed with some outliers indicating higher risk.
- **Oldpeak** (ST depression): Most low values, with a tail for higher risk patients.

<img width="1220" height="913" alt="image" src="https://github.com/user-attachments/assets/706985f3-38d1-449c-8efa-e0357f5fcd6f" />


#### Categorical Features Distribution

- **Sex**: More males than females.
- **Chest Pain Type (`cp`)**: Most common type is asymptomatic or atypical angina.
- **Thalassemia and Vessel Count (`thal`, `ca`)**: Shows reasonable spread and some missing data initially.

<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/869e81e8-48d8-4121-8089-1a881b3c7b32" />


### 4. Bivariate Analysis

- Boxplots show heart disease presence associates with:
  - Slightly older age
  - Lower max heart rate (`thalach`)
  - Higher ST depression (`oldpeak`)
- Countplots by target reveal:
  - Heart disease more common in males
  - Certain chest pain types and exercise-induced angina strongly linked with disease presence

<img width="562" height="455" alt="image" src="https://github.com/user-attachments/assets/ad448e5d-cd04-4b51-8ea8-ca6ac8e14e5d" />


### 5. Correlation Analysis

- Correlation heatmap reveals:
  - `thalach` and `oldpeak` moderately correlated with heart disease.
  - Some inter-feature correlations suggesting possible multicollinearity but mostly independent.

<img width="819" height="725" alt="image" src="https://github.com/user-attachments/assets/39271f49-fbe9-4b91-a476-72214f464d0e" />


### 6. Multivariate Analysis

- Pairplots comparing subsets of features help visualize clustering of patients by disease status.
- Revealed complex interactions not captured in univariate plots, motivating feature engineering.

<<img width="1301" height="1275" alt="image" src="https://github.com/user-attachments/assets/ab19db96-5546-44e3-8145-8bb785bbe485" />
---

## Key EDA Insights

- **Interactions Matter**: Combo of chest pain type with exercise-induced angina indicates particularly high-risk groups.
- **Asymptomatic Patients**: Other features like ECG results and thalassemia have more predictive power in patients with no chest pain.
- **Age Modulates Risk Factor Importance**: Cholesterol predicts risk more in younger patients, while other features dominate in older individuals.
- **Outliers Tell Stories**: High ST depression values correspond to severe cases, not just noise.
- **Some Features Have Limited Predictive Power Alone**: Blood pressure and cholesterol ranges overlap in healthy and diseased patients, suggesting the need to consider interactions.

---

## Next Steps

1. **Data Preprocessing**
   - Impute or better handle missing values rather than dropping.
   - Encode categorical variables (one-hot or label encoding).
   - Scale numeric features.

2. **Feature Engineering**
   - Create combined features (e.g., `cp` × `exang`).
   - Derive ratios like max heart rate to age.

3. **Model Training**
   - Split dataset into training/test sets.
   - Develop baseline (Logistic Regression) and advanced models (Random Forest, SVM).
   - Use cross-validation and hyperparameter tuning.

4. **Model Evaluation**
   - Use accuracy, precision, recall, F1-score, and ROC-AUC.
   - Analyze confusion matrix for false positives/negatives.

---

## How to Run

1. Open and run the Jupyter Notebook or Google Colab:
   - `Heart_Disease_EDA.ipynb`
2. Follow the code to reproduce all analyses and visualizations.
3. Proceed to preprocessing and modeling notebooks/scripts.

---

## Technologies & Libraries

- Python 3.x
- pandas, numpy for data handling
- matplotlib, seaborn for visualization
- scikit-learn for modeling



Thank you for reviewing this project. The detailed EDA presented here reveals nuanced insights into heart disease predictors and sets the foundation for effective machine learning models.


