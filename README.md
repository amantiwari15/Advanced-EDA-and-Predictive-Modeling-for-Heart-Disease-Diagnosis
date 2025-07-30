# Heart Disease Prediction: Exploratory Data Analysis

![Heart Health Banner](https://placehold.co/1200x300/d1e5f0/333333?text=Heart+Disease+Data+Analysis)

**Project Status: Completed** | **Author: [Aman Tiwari]** | 

This repository contains a detailed Exploratory Data Analysis (EDA) of the Cleveland Heart Disease dataset from the UCI Machine Learning Repository. The goal of this analysis is to uncover patterns and relationships within the data to better understand the factors that contribute to the presence of heart disease.

---

## 📋 Table of Contents
1.  [About the Project](#about-the-project)
2.  [Dataset](#dataset)
3.  [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4.  [Key Findings & Visualizations](#key-findings--visualizations)
5.  [Technologies Used](#technologies-used)
6.  [How to Use](#how-to-use)
7.  [Conclusion](#conclusion)

---

## 🎯 About the Project

This project performs a deep dive into a classic medical dataset to identify key predictors of heart disease. Through a systematic process of data cleaning, transformation, and visualization, we aim to answer critical questions such as:
- Which demographic and clinical factors are most strongly associated with heart disease?
- What do the distributions of key health metrics like cholesterol and blood pressure look like?
- How do different types of chest pain relate to a heart disease diagnosis?

The insights gained from this EDA serve as a crucial foundation for building an accurate machine learning model for heart disease prediction.

---

## 💾 Dataset

The data was sourced from the **UCI Machine Learning Repository - Cleveland Heart Disease dataset**.

- **Source**: [UCI Heart Disease Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data)
- **Instances**: 303
- **Attributes**: 14

### Attribute Information:
1.  **age**: Age in years
2.  **sex**: (1 = male; 0 = female)
3.  **cp**: Chest pain type (0-3)
4.  **trestbps**: Resting blood pressure (in mm Hg)
5.  **chol**: Serum cholesterol in mg/dl
6.  **fbs**: Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)
7.  **restecg**: Resting electrocardiographic results (0-2)
8.  **thalach**: Maximum heart rate achieved
9.  **exang**: Exercise induced angina (1 = yes; 0 = no)
10. **oldpeak**: ST depression induced by exercise relative to rest
11. **slope**: The slope of the peak exercise ST segment
12. **ca**: Number of major vessels (0-3) colored by fluoroscopy
13. **thal**: Thallium stress test result (1 = normal; 2 = fixed defect; 3 = reversible defect)
14. **target**: Diagnosis of heart disease (0 = no disease; 1 = disease). *Note: Original values > 1 were converted to 1.*

---

## 📊 Exploratory Data Analysis (EDA)

The analysis followed a structured approach to ensure the data was well-understood and prepared for modeling.

1.  **Data Loading**: Loaded the dataset directly from the UCI repository, assigning appropriate column names.
2.  **Initial Inspection**: Checked the data's shape, data types (`.info()`), and summary statistics (`.describe()`).
3.  **Data Cleaning**:
    - Handled missing values (represented as '?') by imputing the `ca` and `thal` columns with their respective **modes**.
    - Corrected the data types for `ca` and `thal` to integer.
4.  **Target Variable Transformation**: Converted the multi-class `target` variable (values 0-4) into a binary variable where `0` represents "No Disease" and `1` represents "Disease".
5.  **Univariate Analysis**: Analyzed individual features using histograms for numerical data and countplots for categorical data to understand their distributions.
6.  **Bivariate & Multivariate Analysis**: Investigated relationships between features and the target variable using boxplots, countplots with `hue`, a correlation heatmap, and a pairplot.

---

## 📈 Key Findings & Visualizations

### 1. Distribution of Numerical Features
Histograms revealed the underlying distributions of key clinical measurements. The plot below visualizes these distributions.
- `age` and `thalach` (max heart rate) have roughly normal distributions.
- `trestbps` (blood pressure) and `chol` (cholesterol) are right-skewed, with some high-value outliers.
- `oldpeak` (ST depression) is heavily skewed, with most patients having a value of 0.

![Histograms of Numerical Features]<img width="1490" height="990" alt="image" src="https://github.com/user-attachments/assets/61219cb3-151a-4911-8c9e-b95ee1d51a6b" />


### 2. Frequency of Categorical Features
Countplots showed the composition of the dataset, highlighting imbalances such as a higher number of male patients.

![Countplots of Categorical Features]<img width="1790" height="1190" alt="image" src="https://github.com/user-attachments/assets/760a60ee-f44d-4760-bf78-d3367457bf84" />


### 3. Numerical Features vs. Heart Disease
Boxplots provided critical insights into which factors are strong predictors.
- **Higher `thalach` (Max Heart Rate)** is strongly associated with a **lower** probability of heart disease.
- **Higher `oldpeak` (ST Depression)** is a strong indicator of the **presence** of heart disease.

![Boxplots of Numerical Features vs. Target]<img width="1489" height="990" alt="image" src="https://github.com/user-attachments/assets/122df42f-34bb-4149-a74d-305177f2cad0" />


### 4. Categorical Features vs. Heart Disease
Splitting countplots by the target variable revealed clear patterns.
- **Chest Pain (`cp`)**: Patients with chest pain type 0 (typical angina) are far more likely to have heart disease.
- **Exercise Induced Angina (`exang`)**: The presence of exercise-induced angina (`exang=1`) is strongly linked to a positive diagnosis.
- **Sex**: Males in this dataset have a higher prevalence of heart disease compared to females.

![Countplots with Hue]<img width="1789" height="1190" alt="image" src="https://github.com/user-attachments/assets/1ef14fff-2778-45c1-8581-d1bcc5395248" />


### 5. Correlation Matrix
The heatmap visually summarizes the linear relationships between all numerical features.
- `target` shows the strongest **negative correlation with `thalach` (-0.42)** and the strongest **positive correlations with `oldpeak` (0.43) and `ca` (0.39)**.
- This confirms our findings from the boxplots and highlights the most influential features for a predictive model.

![Correlation Heatmap]<img width="1047" height="836" alt="image" src="https://github.com/user-attachments/assets/b197c63c-c901-4ba5-8c2c-29fdccff8936" />


### 6. Pair Plot Analysis
The pair plot provides a matrix of scatter plots to visualize the pairwise relationships between key numerical features, colored by the presence or absence of heart disease.
- It helps identify which combinations of features are most effective at separating the two classes.
- The plots for `thalach` vs. `age` and `thalach` vs. `chol` show some separation, confirming that `thalach` is a powerful discriminating feature.

![Pairplot of Key Features]<img width="1054" height="1023" alt="image" src="https://github.com/user-attachments/assets/32ce3b2b-c268-406e-b01a-c074a74679c8" />




---

## 💻 Technologies Used
- **Python 3**
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Matplotlib**: For basic plotting.
- **Seaborn**: For enhanced statistical visualizations.
- **Jupyter Notebook**: As the development environment.

---

## 🚀 How to Use

To replicate this analysis, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone (https://github.com/amantiwari15/Advanced-EDA-and-Predictive-Modeling-for-Heart-Disease-Diagnosis/tree/main)
    cd [Advanced-EDA-and-Predictive-Modeling-for-Heart-Disease-Diagnosis]
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
 
4.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook "Machine_Learning_CA1 (2).ipynb"
    ```

---

## 🏁 Conclusion

This Exploratory Data Analysis successfully identified several key factors strongly associated with the presence of heart disease. The most significant predictors appear to be:
- **Max Heart Rate (`thalach`)**
- **ST Depression (`oldpeak`)**
- **Number of Major Vessels (`ca`)**
- **Chest Pain Type (`cp`)**
- **Exercise-Induced Angina (`exang`)**

These insights are invaluable for feature selection and engineering in the subsequent phase of building a predictive machine learning model. The clear patterns discovered demonstrate the potential for a model to accurately distinguish between patients with and without heart disease.
