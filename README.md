# loan-default-prediction
This is the solution from Zindi to predict the likelihood customer defaulting paying back the loan.

# Overview and objectives:
Imagine a bank looking to reduce risks and improve decision-making in its loan approval process.  This financial institution seeks to understand its customers better and reduce the risks of loan defaults. Using data from its extensive lending history, the challenge is to predict whether a customer will default on a loan based on various factors like loan amount, repayment expectations, loan type, disbursement details, and customer history.
The dataset includes critical features such as whether a loan is new or repeat, the lender's portion of funding, and repayment deadlines. With this information, the goal is to build a predictive model that identifies high-risk borrowers and ensures responsible lending. This solution will not only help minimize losses but also foster a more secure financial ecosystem for both the bank and its customers.

# ETL process
Data extraction:
Datasets (training and testing) in CSV format collected from the Zindi website. To ease efficient data handling and avoid daily upload limits, these datasets were uploaded to Google Drive and then connected to Google Colab. The Pandas library imported into the Collab environment to enable the loading and manipulation of the CSV files.

# Transformation:
training and testing datasets successfully loaded using pandas. Date changed from object to datetime format so that month and year extracted. Subsequently, the date column dropped.
Next, both object and categorical entries in the datasets were encoded using Label Encoder. This encoding process transformed categorical variables into numerical values, making them suitable for machine learning models. Following this, standardization was applied to the numerical features using Min Max Scaler. This scaling method ensured that all features were normalized to a common range, typically between 0 and 1. This step is particularly crucial for algorithms such as XGBoost, as it helps mitigate any bias that could arise from differing feature scales, thus enhancing the model’s performance and generalization capability.

Subsequently, the XGBoost model was initialized, and a set of hyperparameters was defined for optimization. Using GridSearchCV, the model underwent a comprehensive search to identify the best combination of parameters, such as the number of estimators, maximum depth, and learning rate. Cross-validation with multiple folds was then performed to assess the model’s stability and to ensure that it generalized well across different subsets of the data. The best-performing model from the grid search was selected for further evaluation.
Metrics: F1- Score

# Run time:
Run time for the entire notebook 5 minutes.

# Performance Metrics:
●	The metrics of the train dataset 
●	F1 -score=0.996
●	The best hyperparameters given by 5-fold cross-validation were Col sample by tree: 0.8, learning rate: 0.1, max depth: 5, n estimators: 2000, subsample: 1.0.
●	The solution submitted first placed me on rank: 334 with public score: 0.683908045 and private score of 0.658981748 but the code was modified later after competition closed and got best solution of public score:0.698224852 and private score 0.668020304.
●	Error analysis: Model is overfitting. 
