# Heart Attack Prediction

## **Overview**

This project aims to address the significant public health concern of heart disease, a leading cause of death in the United States. Our objective is to develop predictive models for heart attack risks and investigate contributing factors. These models will be integrated into a self-testing app that provides personalized health analysis to educate users and increase awareness about heart health.

## **Business Problem**

**Heart Disease Statistics** : Approximately half of Americans face the risk of heart attacks highlighting the critical need for effective prevention strategies.

**Objective**: Build predictive models to:

* Estimate the probability of heart attacks.
  
+ Identify key contributing factors to heart health.
  
+ Develop a user-friendly app for self-assessment and recommendations.

## **Data and Features**

**Source**: The dataset is derived from the CDC’s Behavioral Risk Factor Surveillance System (BRFSS).

+	**Size**: 246,022 records and 40 features.
  
+	**Target Variable**: Binary classification of “HadHeartAttack”.
  
+	**Features**: Demographics, medical history, and health indexes (e.g., BMI, smoking status, sleep hours, history of stroke or angina).
  
## **Preprocessing**:

+	Addressed class imbalance using SMOTE (Synthetic Minority Oversampling Technique).
 
+	Dropped multicollinear features (e.g., WeightInKilograms due to correlation with BMI).
 
+	Reduced categorical complexity (e.g., transformed state into broader region categories).
 
+	Employed one-hot encoding and backward selection for feature refinement.

## **Models and Methodologies**

**Model 1**: Logistic Regression

+ **Performance**:
 	+ AUC: 0.945
  + F1 Score: 0.872
 
+ **Key Findings**:
	+ **Stroke**: Increases odds of heart attack by ~54%.
	+ **Sleep Hours**: Each additional hour reduces odds by ~12%.
   
+ **Feature Importance**: Leveraged interpretability through coefficient analysis.

**Model 2**: Explainable Boosting Machine (EBM)

+ **Description**:
	+ Combines accuracy of complex models with interpretability of Generalized Additive Models (GAMs).
 	+ Automatically detects interactions between features.

+ **Performance**:
	+ AUC: 0.951
 	+ F1 Score: 0.880

+ **Advantages**:
	+ Improved accuracy over Logistic Regression (+0.007 AUC).
 	+ Maintains explainability crucial for public health applications.


## **Causal Analysis**

To strengthen the model’s findings and explore causality:
+ Applied **Propensity Score Matching (PSM**):
	+ Balanced treatment and control groups to assess the causal impact of diabetes and stroke.
 	+ Treatment effects:
  	+ Stroke: Significant impact with an ATE of 0.054 (p < 0.001).
  	+ Diabetes: Weak significance (ATE = 0.016, p = 0.002).

+ Highlighted **Limitations**:
	+ Unmeasured confounders may introduce bias.
 	+ Assumptions of PSM restrict comprehensive causality proofs.


## **Results Summary**

+ **Logistic Regression**:
	+ AUC: 0.945
 	+ F1 Score: 0.872
+ **Explainable Boosting Machine (EBM)**:
	+ AUC: 0.951
 	+ F1 Score: 0.880

**EBM** outperformed Logistic Regression in **accuracy** and **interpretability**, making it the preferred model for integration into the self-testing app.

## Files:

The actual code with details about this project is in "**HEART_ATTACK_PREDICTION.ipynb**"
