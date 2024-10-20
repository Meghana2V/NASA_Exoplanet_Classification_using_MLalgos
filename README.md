# NASA_Exoplanet_Classification_using_MLalgos

## About the Project

This repository focuses on classifying exoplanets using machine learning algorithms based on NASA data. The dataset used for this project is derived from the NASA Exoplanet Archive, which provides comprehensive information on confirmed and candidate exoplanets from various missions and ground-based surveys.

## Libraries used

- Numpy and Pandas
- sklearn
- Vizualizations: Matplotlib and seaborn

## Models used

- KNN
- Random forest
- XGBoost

## Data Overview

- **Source** : NASA Exoplanet Archive
- **Data Size** : The dataset contains over **9,000 observations, with over 50 features** capturing the characteristics of stars and planetary systems.
- **Data Impurity** : The dataset contains incomplete entries, including missing data points and noise, which required significant preprocessing.

## Data Preprocessing and Imputation

The following steps were applied to clean and prepare the data:

- **Missing Data Handling** : Missing values were imputed using statistical methods like mean, median, and mode imputation. In some cases, k-nearest neighbors (KNN) imputation was applied for better accuracy.
- **Normalization** : Numerical features were normalized to bring all variables into comparable ranges, aiding the training of models like KNN and Random Forest.
- **One-Hot Encoding** : Categorical variables were transformed into binary vectors using one-hot encoding to make them suitable for machine learning algorithms.

## Statistical Inferences

- **Correlation Analysis** : Features like star mass, radius, and orbital period were found to have significant correlations with the target variable. The correlations are observed before and after scaling and normalizing the data.
- Here’s a list of only the strong correlations (values of 50 and above) based on the data:

	- koi_time0bk_err1: koi_time0bk_err2: 99
	- koi_insol_err1: koi_insol_err2: 75, koi_insol: 80
	- koi_model_snr: koi_depth: 57
	- koi_period_err2: koi_time0bk_err2: 54
	- koi_prad_err2: koi_prad_err1: 71, koi_prad: 99
	- koi_prad_err1: koi_prad_err2: 71, koi_impact: 76, koi_prad: 77
	- koi_prad: koi_prad_err2: 99, koi_prad_err1: 77, koi_impact: 65
	- koi_slogg: koi_srad: 64, koi_srad_err1: 63, koi_srad_err2: 52
	- koi_srad_err1: koi_srad: 74, koi_srad_err2: 65, koi_slogg: 63
	- koi_fpflag_co: koi_fpflag_ec: 53


- **Imbalanced Classes** : The dataset was imbalanced, with fewer exoplanets than non-exoplanets, which influenced model selection and metric focus. I have tried to keep it the same way following the general occurrence pattern.

## Feature Extraction

Feature selection is done using random forest to get the top 20 features, none of the features have a significant importance: <br>
&emsp;&emsp;- koi_score :                             0.254637<br>
&emsp;&emsp;- koi_fpflag_nt :                         0.088215<br>
&emsp;&emsp;- koi_fpflag_co :                       0.059576<br>
&emsp;&emsp;- koi_fpflag_ss :                       0.053821<br>
&emsp;&emsp;- koi_model_snr :                       0.041159<br>
&emsp;&emsp;- koi_prad :                            0.035769<br>
&emsp;&emsp;- koi_steff_err1 :                      0.035551<br>
&emsp;&emsp;- koi_time0bk_err2 :                    0.029971<br>
&emsp;&emsp;- koi_duration_err1 :                   0.027774<br>
&emsp;&emsp;- koi_duration_err2 :                   0.026122<br>
&emsp;&emsp;- koi_time0bk_err1 :                   0.023284<br>
&emsp;&emsp;- koi_duration :                        0.021682<br>
&emsp;&emsp;- koi_prad_err1 :                       0.019334<br>
&emsp;&emsp;- koi_insol_err1 :                      0.016868<br>

## Models and Metrics

The following models were applied in this project:

- **Random Forest** : Selected for its robustness and ability to handle a large number of features.
- The Random forest has 35 estimators with 10 minimum sample splits: RandomForestClassifier(min_samples_split=10, n_estimators=35, oob_score=True,random_state=0)
- **K-Nearest Neighbors (KNN)** : Used due to its simplicity and effectiveness for smaller datasets.
- Initially computed for 12 neighbors and then the best N values are estimated
- **XGBoost** : Chosen for its superior performance in handling tabular data and its ability to handle class imbalance effectively.

## Model Performance Metrics

- **Random Forest** : for all the three encoded categories
- Classification Report: precision, recall, f1-score, support


        |   0    |   0.91    |  0.95    |  0.93     | 1005 	|
        |   1    |   0.52    |  0.49    |  0.51     |  449	|
        |   2    |   0.76    |  0.07    |  0.12     |  459	|
  
- **KNN** : Accuracy = 79% overall Precision = % Recall = % f1-Score = %
- **XGBoost** : Accuracy = 88% overall Precision = % Recall = % f1-Score = %

## Model Selection Rationale

XGBoost emerged as the best-performing model due to its ability to handle class imbalances and feature importance calculations. Random Forest was chosen for its interpretability and robustness, while KNN provided a baseline for performance comparison.

## Analysis Summary

XGBoost outperformed other models, achieving the highest precision and recall metrics. The preprocessing steps, including one-hot encoding and normalization, improved model performance. Overall, the models achieved high accuracy in classifying exoplanets, though further optimization and fine-tuning of hyperparameters may yield even better results.
