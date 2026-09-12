# AI-Based Personalized Diet & Recovery Planner

## 📌 Overview

The **AI-Based Personalized Diet & Recovery Planner** is a Data Science
and Data Engineering project focused on transforming raw patient and
daily-tracking data into clean, validated, and ML-ready datasets.

The project covers data cleaning, clinical standardization, validation,
feature engineering, longitudinal aggregation, and preparation of
datasets for downstream AI/ML applications.

## 🎯 Objectives

-   Clean and preprocess patient and daily-tracking datasets
-   Handle missing values and duplicate/inconsistent data
-   Standardize categorical and datetime fields
-   Validate values against realistic clinical ranges
-   Maintain consistency between patient and tracking datasets
-   Engineer useful features for downstream ML models
-   Produce final ML-ready datasets for AI/ML team handover

## 🛠️ Tech Stack

-   **Language:** Python
-   **Data Processing:** Pandas, NumPy
-   **Data Science:** Data Cleaning, EDA, Feature Engineering
-   **Validation:** Data Quality Checks, Referential Integrity
    Validation
-   **Data Format:** CSV
-   **Documentation:** PDF Reports, Markdown

## 📂 Project Structure

``` text
AI-Diet-Recovery-Planner/
│
├── Datasets/
│   ├── raw/
│   │   ├── patients_expanded.csv
│   │   └── daily_tracking_expanded.csv
│   │
│   └── processed/
│       ├── processed_patients.csv
│       └── processed_tracking.csv
│
├── Notebooks/
│   ├── 01_data_cleaning_and_validation.py
│   └── 02_feature_engineering_pipeline.py
│
├── Reports/
│   ├── Missing_Value_Report.pdf
│   ├── Preprocessing_Report.pdf
│   ├── Feature_Engineering_Report.pdf
│   ├── Cleaned_Dataset_Report.pdf
│   └── DataScience_Final_Handover_Report.pdf
│
├── requirements.txt
└── README.md
```

## 🔬 Workflow

### Phase 1 --- Data Cleaning & Clinical Standardization

-   Domain-aware missing value imputation
-   Datetime normalization
-   Categorical text standardization
-   Blood pressure decomposition
-   Clinical range and boundary validation

### Phase 2 --- Feature Engineering & Integration

-   Cross-dataset `patient_id` validation
-   BMI calculation and categorization
-   Age-group categorization
-   Longitudinal aggregation of tracking data
-   Categorical encoding
-   Scaler evaluation

## 🧹 Data Cleaning

Different imputation strategies were used depending on the data type and
domain.

### Categorical Data

Medical histories, allergies, food restrictions, surgeries, and clinical
notes were handled using `"None"` where the absence of an entry
represented no reported condition.

### Numerical Data

Median imputation was used for physiological and nutritional
measurements to reduce the effect of skewed values and outliers.

## ✅ Clinical Range Validation

Values outside defined realistic boundaries were identified and
filtered.

The validation covered:

-   Calories and macronutrients
-   Blood glucose
-   Heart rate
-   Systolic and diastolic blood pressure
-   Sleep hours
-   Daily steps

## ⚙️ Feature Engineering

### Blood Pressure

The composite `blood_pressure` value is split into:

``` text
blood_pressure → systolic_bp + diastolic_bp
```

### BMI

BMI is calculated from height and weight and categorized into:

-   Underweight
-   Normal
-   Overweight
-   Obese

### Age Groups

Patient age is transformed into structured demographic groups.

### Longitudinal Features

Daily tracking data is aggregated to create:

-   `Avg_Blood_Sugar`
-   `Avg_Daily_Steps`
-   `Avg_Sleep_Hours`

## 🔗 Referential Integrity

The relationship between the patient master dataset and daily tracking
dataset is validated using `patient_id`.

The project verifies that tracking records reference valid patient
records and checks for orphaned tracking records before relational
merging.

## 📊 Final Feature Set

Important engineered features include:

  Feature             Type          Description
  ------------------- ------------- ---------------------------------
  `age`               Numerical     Patient age
  `gender`            Categorical   Encoded patient gender
  `height_cm`         Numerical     Height measurement
  `weight_kg`         Numerical     Weight measurement
  `BMI`               Numerical     Derived Body Mass Index
  `BMI_Category`      Categorical   BMI classification
  `Age_Group`         Categorical   Structured age group
  `Avg_Blood_Sugar`   Numerical     Average daily blood glucose
  `Avg_Daily_Steps`   Numerical     Average daily steps
  `Avg_Sleep_Hours`   Numerical     Average sleep duration
  `systolic_bp`       Numerical     Parsed systolic blood pressure
  `diastolic_bp`      Numerical     Parsed diastolic blood pressure

## 🤖 Downstream Applications

The processed datasets are prepared for potential downstream modules
such as:

1.  **Personalized Diet Recommendation**
    -   Uses dietary preferences, disease tags, allergies, and caloric
        requirements.
2.  **Recovery Trajectory Prediction**
    -   Uses longitudinal daily tracking indicators for regression and
        time-series analysis.
3.  **Clinical Risk Stratification**
    -   Can support classification-based identification of high-risk
        glycemic or blood-pressure patterns.

## 🚀 How to Run

### 1. Clone the Repository

``` bash
git clone https://github.com/AbhiYewale96/AI-Diet-Recovery-Planner.git
cd AI-Diet-Recovery-Planner
```

### 2. Install Dependencies

``` bash
pip install -r requirements.txt
```

### 3. Run Data Cleaning

``` bash
python Notebooks/01_data_cleaning_and_validation.py
```

### 4. Run Feature Engineering

``` bash
python Notebooks/02_feature_engineering_pipeline.py
```

## 📄 Reports

The project includes detailed reports covering:

-   Missing Value Analysis
-   Data Preprocessing
-   Feature Engineering
-   Cleaned Dataset Summary
-   Data Science Final Handover

## 📌 Project Outcome

The final output consists of cleaned, validated, feature-engineered
datasets that are structured for downstream machine learning and AI
applications.

## 👨‍💻 Author

**Abhishek Yewale**

B.Tech Information Technology\
MGM University

------------------------------------------------------------------------

⭐ If you find this project useful, consider giving the repository a
star.
