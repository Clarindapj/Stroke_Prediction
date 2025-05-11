# Stroke_Prediction
Stroke Prediction with Machine Learning

[Click Here! Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)


## 🔎 1. Business Understanding
Worldwide, stroke ranks among the top causes of death and handicap. Early identification of those at high risk of stroke allows for quick intervention and may save lives. In medical classification tasks like this, both kinds of mistakes have major effects:

- False Negative (FN): Not recognizing a patient who will really suffer a stroke constitutes a false negative. This is risky since it implies lost chances for preventive care, so causing major health consequences or death.

- False Positives (FP): Wrongly forecasting a stroke risk for someone actually healthy. Unneeded worry, medical examinations, and higher healthcare expenses might all follow from this.

🎯 Given these hazards, the project’s main goal is to balance both kinds of mistakes. Thus, the main assessment tool is the F1-score since it harmonically balances recall (avoiding FN) and accuracy (avoiding FP). This strategy guarantees that the model is both sensitive to actual stroke situations and wary about false alerts, therefore offering the most practical value in a healthcare environment.

## 🔎 2. Data Understanding
Comprising 12 characteristics—including demographic (age, gender, geography), clinical (blood pressure, BMI, glucose), and lifestyle variables—the dataset holds 10,000 patient records. The target variable shows whether the patient had a stroke (1) or not (0). With stroke cases making up a tiny minority, the dataset is unbalanced. Initial investigation showed that stroke patients are more common in age, hypertension, and average glucose level. Especially in numerical variables like glucose and BMI, some characteristics show skewness and outliers that are handled during preprocessing.

## ✅ 3. Data Preparation
For consistency, feature names were standardized. Stratification was used to divide the data into training and testing sets, therefore preserving the original class distribution. Preprocessing consisted of dealing with missing values using median imputation, encoding categorical variables with one-hot encoding, and scaling numerical features using robust scaling to reduce the influence of outliers. To handle class imbalance, Synthetic Minority Over-sampling Technique (SMOTE) was applied to the training data, therefore guaranteeing the model can learn from both stroke and non-stroke situations.

## 🤖 4. Modeling

A variety of ensemble classifiers were considered which include Decision Tree, Random Forest, AdaBoost, Gradient Boosting, and XGBoost, all of which were assessed using five-fold cross validation with F1-score as the evaluation metric. The highest F1-score was obtained with Gradient Boosting while Random Forest was a close second. Further tuning of the hyperparameters of the Gradient Boosting model increased its F1-score confirming the model's appropriateness for the task. The modeling pipeline included the SMOTE technique and other preprocessing steps in order to maintain unbiased evaluation across all models. 

## 🔎 5. Evaluation  

The tuned Gradient Boosting model also achieved the highest F1-score of 0.62 on the test set, outperforming all other models. Analysis of the confusion matrix indicated a good balance between precision and recall, achieving optimal results for both false negatives and false positives. Analysis of the features used revealed Age, Average Glucose Level, and Hypertension as the top contributors. SHAP analysis provided meaningful explanations for each prediction which aided in clinical evaluations. The results confirm the practical usefulness of the model in detecting the risk of stroke at an earlier stage.

## ✨ 6. Deployment  

The highest-performing Gradient Boosting model, together with all preprocessing steps, was frozen for future deployments. This now allows for incorporation into the healthcare systems for real-time stroke risk assessment. Tracking for data drift and periodic retraining is suggested to sustain model accuracy. Addition of explainability frameworks and compliance with data privacy will enhance responsible and reliable deployment in clinical practice.

## ✨ 7. Recommendations

- F1-score is the most appropriate metric due to the medical impact of both FP and FN.
- Gradient Boosting, with proper preprocessing and SMOTE, provides the best performance.
- The workflow is modular, reproducible, and ready for real-world deployment.



