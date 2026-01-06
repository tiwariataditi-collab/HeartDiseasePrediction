Heart Disease Prediction using Logistic Regression

Project Overview-----
This project aims to predict the 10-year risk of Coronary Heart Disease (CHD) in patients by analyzing clinical, behavioral, and demographic data. Using the renowned Framingham Heart Study dataset,
the project implements a machine learning pipeline that includes data cleaning, exploratory analysis, and a classification model to identify high-risk individuals.

Dataset Description----
The dataset consists of 4,238 records of patients from Framingham, Massachusetts. Each record contains 15 features that are potential risk factors for heart disease:

Demographics: Gender (male), Age (age), and Education.

Behavioral Factors: Current smoking status (currentSmoker) and intensity (cigsPerDay).

Medical History: Use of blood pressure medication (BPMeds), history of stroke (prevalentStroke), hypertension (prevalentHyp), and diabetes (diabetes).

Current Medical State: Total cholesterol (totChol), Blood pressure (sysBP and diaBP), Body Mass Index (BMI), Heart rate (heartRate), and Glucose levels.

Target Variable: TenYearCHD (Binary: 1 = Risk, 0 = No Risk).

Technical Workflow---
1. Data Cleaning & Preprocessing
~To ensure model accuracy, the notebook performs several preprocessing steps:
~Missing Value Imputation: Identified null values in critical columns like glucose, BMI, and totChol. Numerical gaps were filled using median imputation to prevent data bias.
~Feature Selection: Removed the education column as it lacked clinical relevance to cardiovascular risk.
~Scaling: (Optional but recommended) Prepared features for the Logistic Regression algorithm to ensure variables with larger ranges (like cholesterol) don't dominate the model.

2. Exploratory Data Analysis (EDA)
Statistical summaries were generated to understand the distribution of the data. A Correlation Heatmap was created to visualize how different variables interact.
Insight: There is a strong correlation between Systolic and Diastolic blood pressure, as well as between age and the likelihood of CHD.

3. Predictive Modeling
The project utilizes Logistic Regression, an ideal algorithm for binary classification tasks in medical diagnostics. The model calculates the probability of a patient
belonging to the "at-risk" category based on the sigmoid function.

Accuracy and Performance Metrics---
~The model achieves a baseline accuracy of approximately 85%. However, in medical diagnostics, we look deeper into the following:
~Precision: Measures how many predicted "At-Risk" cases were actually correct.
~Recall (Sensitivity): Crucial for heart disease—it measures the model's ability to find all actual "At-Risk" patients.
~F1-Score: The harmonic mean of precision and recall, providing a balanced view of model health.

2. Confusion Matrix---
~The confusion matrix reveals how the model categorized the test data:
~True Negatives: Correctly identified healthy patients.
~True Positives: Correctly identified patients at risk of CHD.
~False Negatives: Patients the model missed (the most critical area for improvement in healthcare models).

3. Feature Importance (Coefficients)---
~Logistic Regression allows us to see which factors increase the "odds" of heart disease. Based on the model coefficients:
~Age: Every year increase significantly raises the probability of CHD.
~Systolic Blood Pressure (sysBP): Identified as a primary physical driver of risk.
~Cigarettes Per Day: Shows a direct linear relationship with increased cardiovascular risk.
~Glucose: Higher blood sugar levels correlate with a higher risk of a 10-year CHD event.

4. ROC-AUC Curve---
~The Receiver Operating Characteristic (ROC) curve was used to visualize the trade-off between the True Positive Rate and False Positive Rate. An AUC (Area Under the Curve) near 0.70 - 0.75 indicates
 that the model has a good ability to distinguish between patients who will develop heart disease and those who won't.
~The model highlights Age, Systolic Blood Pressure, and Cigarettes Per Day as significant predictors of long-term heart disease.

Key Findings----
~The model highlights Age, Systolic Blood Pressure, and Cigarettes Per Day as significant predictors of long-term heart disease.
~Data preprocessing, specifically handling missing glucose and blood pressure data, significantly impacts the model's reliability.

Conclusion---
The results demonstrate that while the model is highly accurate at identifying healthy patients, the Recall for high-risk patients can be further improved by incorporating more
data or exploring advanced techniques like SMOTE for class imbalance. This project serves as a robust proof-of-concept for automated cardiovascular screening.
