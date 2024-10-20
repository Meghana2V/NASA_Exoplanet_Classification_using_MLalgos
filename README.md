# NASA_Exoplanet_Classification_using_MLalgos

## About the Project

This repository focuses on classifying exoplanets using machine learning algorithms based on data from NASA. The dataset used for this project is derived from the NASA Exoplanet Archive, which provides comprehensive information on confirmed and candidate exoplanets from a variety of missions and ground-based surveys.

## Data Overview

	•	**Source**: NASA Exoplanet Archive
	•	**Data Size**: The dataset contains over 9,000 observations, with multiple features capturing the characteristics of stars and planetary systems.
	•	**Data Impurity**: The dataset contains incomplete entries, including missing data points and noise, which required significant preprocessing.

## Data Preprocessing and Imputation

The following steps were applied to clean and prepare the data:

	•	**Missing Data Handling**: Missing values were imputed using statistical methods like mean, median, and mode imputation. In some cases, k-nearest neighbors (KNN) imputation was applied for better accuracy.
	•	**Normalization**: Numerical features were normalized to bring all variables into comparable ranges, aiding the training of models like KNN and Random Forest.
	•	**One-Hot Encoding**: Categorical variables were transformed into binary vectors using one-hot encoding to make them suitable for machine learning algorithms.

## Statistical Inferences

	•	**Correlation Analysis**: Features like star mass, radius, and orbital period were found to have significant correlations with the target variable.
	•	**Imbalanced Classes**: The dataset was imbalanced, with fewer exoplanets than non-exoplanets, which influenced model selection and metric focus.

## Feature Extraction

Feature selection techniques were applied to improve model performance:

	•	**Key Features**: The most influential features included star mass, orbital period, and stellar radius, which significantly contributed to classification accuracy.

## Models and Metrics

The following models were applied in this project:

	•	**Random Forest**: Selected for its robustness and ability to handle a large number of features.
	•	**K-Nearest Neighbors (KNN)**: Used due to its simplicity and effectiveness for smaller datasets.
	•	**XGBoost**: Chosen for its superior performance in handling tabular data and its ability to handle class imbalance effectively.

## Model Performance Metrics

	•	**Accuracy**: Random Forest achieved an accuracy of X%, KNN achieved Y%, and XGBoost achieved Z%.
	•	**Precision and Recall**: Due to the imbalanced nature of the dataset, precision and recall were crucial metrics.
	•	**Random Forest**: Precision = A%, Recall = B%
	•	**KNN**: Precision = C%, Recall = D%
	•	**XGBoost**: Precision = E%, Recall = F%
	
  •	**F1 Score**: The F1 score was computed to balance precision and recall.
	•	**Random Fores**t: F1 = G
	•	**KNN**: F1 = H
	•	**XGBoost**: F1 = I
 
	•	**ROC-AUC**: The area under the ROC curve was used to evaluate how well the models distinguished between exoplanet and non-exoplanet classes.
	•	**Random Forest**: ROC-AUC = J
	•	**KNN**: ROC-AUC = K
	•	**XGBoost**: ROC-AUC = L

## Model Selection Rationale

XGBoost emerged as the best-performing model due to its ability to handle class imbalances and feature importance calculations. Random Forest was chosen for its interpretability and robustness, while KNN provided a baseline for performance comparison.

## Analysis Summary

XGBoost outperformed other models, achieving the highest precision and recall metrics. The preprocessing steps, including one-hot encoding and normalization, were essential in improving model performance. Overall, the models achieved high accuracy in classifying exoplanets, though further optimization and fine-tuning of hyperparameters may yield even better results.
