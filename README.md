#  Identifying Patient Level-Risk Factors to Predict and Prevent Readmissions

##  Project Overview
Worldwide, hospital readmission is a major concern reflecting gaps in care quality and resulting in financial penalties. This project utilizes a data-driven approach to identify key patient profile-based risk factors related to readmissions and proposes targeted strategies to reduce preventable 30-day hospital readmissions.

##  Dataset Details
* **Source Dataset:** diabetic_data_QMH_Club_Fest_2025.
* **Volume:** Over 100,000 patient records.
* **Dimensionality:** 50 initial variables encompassing patient demographics, medical history, visit details, and treatment information.
* **Target Variable:** readmitted_binary (Classified as "Yes" for <30 days readmission, and "No" for >30 days or NO).

##  Data Preparation & Feature Engineering
* **Handling Missing Values:** Missing values coded as '?' were systematically converted to NA format. Mode imputation was employed to retain the maximum number of records.
* **Variable Selection:** Variables with extremely high missing rates, such as Weight (97% missing), payer_code (52% missing), and medical_speciality (53% missing) were removed. Ultimately, 17 statistically significant variables were selected for modeling.
* **Categorical Mapping:** Numeric codes for key variables like admission_type_id, discharge_disposition_id, and admission_source_id were mapped to meaningful categorical labels for clarity. Primary diagnoses were grouped into major categories like Circulatory, Respiratory, and Diabetes.

##  Exploratory Data Analysis (EDA) & Hypothesis Testing
* **Overall Readmission Rate:** The target variable revealed an approximately 11.1% 30-day readmission rate, highlighting a severe class imbalance.
* **Statistical Testing:** Conducted Chi-Square Test of Independence for categorical variables and Welch Two Sample t-test for numeric variables, utilizing a significance level of p < 0.05.
* **Key Results:** Prior inpatient history, number of diagnoses, number of medications, insulin changes, and age were found to be highly significant predictors. Variables like gender, race, and A1C results were not significant predictors of early readmission.

##  Predictive Modeling
* **Models Implemented:** Logistic Regression, Ridge Regression, and Random Forest.
* **Data Split:** The data was split into 75% training (76,325 records) and 25% testing (25,441 records).
* **Model Evaluation:** The Comprehensive Logistic Model achieved an overall accuracy of 88.82%. However, the models showed poor sensitivity (1.41%) due to the heavy class imbalance, indicating they are more useful for identifying risk factors rather than predicting specific individual readmissions.

##  Key Findings & High-Risk Patient Profile
* **Dominant Predictor:** Prior inpatient history stands out as the most powerful predictor, dramatically increasing readmission odds with each visit.
* **High-Risk Profile:** Older individuals with a history of inpatient/emergency visits, multiple diagnoses, numerous medications, specific primary conditions (e.g., Circulatory), recent insulin changes, and those discharged to settings other than home independently represent the highest risk group.

##  Strategic Recommendations
Based on the identified risk factors, we propose the following targeted interventions:
1. **Higher Utilizer Case Management:** Implement intensive case management and mandatory post-discharge calls for patients with >=1 prior inpatient admission.
2. **Structure Transitional Care:** Ensure "Warm Hand-offs" and guaranteed <24hr first visits for home health for patients not discharged to home.
3. **Clinical Complexity Review:** Require pharmacist-led medication reconciliation for patients with high number_diagnoses (>7), num_medications (>16), or any insulin changes.
4. **Age-Stratified Support:** Enhance caregiver involvement and provide simplified discharge materials for patients older than 70.

##  Project By: Team Missing Values
* MD. Intekhab Hossain Niaz
* Farhana Islam Shahaly
* Riyaz Uddin Ahmed# Hospital-Readmission-Analysis
