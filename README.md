Dataset

The project uses the Bank Customer Churn dataset from Kaggle under the name Banking_Churn.

The dataset contains 10,000 customer observations and includes variables such as:

Credit score
Country
Gender
Age
Tenure
Account balance
Number of banking products
Credit card ownership
Active membership
Estimated salary
Customer churn status

The target variable is churn, where:

0 = Customer stayed
1 = Customer churned
Requirements

The project was developed in Python using Jupyter Notebook.

Recommended Python version:

Python 3.10 or later

Main Python libraries:

pandas
numpy
matplotlib
scikit-learn
imbalanced-learn
xgboost
lightgbm
catboost
shap
jupyter

Installation

1. Download or extract the project folder

Extract the submitted ZIP archive to a local directory.

2. Open a terminal or command prompt

Navigate to the project directory:

cd Bank-Customer-Churn-Prediction


3. Install the required packages


Install the main packages manually:

pip install pandas numpy matplotlib scikit-learn imbalanced-learn xgboost lightgbm catboost shap jupyter


Running the Project

Open:

Bank_Customer_Churn_Prediction.ipynb

Run the notebook cells sequentially from top to bottom.

It is recommended to use:

Kernel → Restart Kernel and Run All Cells

to reproduce the full analysis from the beginning.

Data File Location

The notebook expects the dataset to be located in the data Path.

Example:

DATA_PATH = Path("C:/data")
df = pd.read_csv(DATA_PATH / "Banking_Churn.csv")

If the path is changed, update the corresponding Data_Path in the notebook.

Analysis Workflow

The notebook follows the following sequence:

Load and inspect the dataset
Perform exploratory data analysis
Clean and preprocess the data
Encode categorical variables
Split data into training and testing sets
Standardize numerical features
Establish a Logistic Regression baseline
Apply SMOTE to address class imbalance
Train and evaluate six classification algorithms
Compare model performance
Perform stratified 5-fold cross-validation
Select the final model
Explain predictions using SHAP
Segment customers according to churn risk and estimated value
Develop customer retention recommendations
Generate an executive visualization dashboard
Model Evaluation

The models are evaluated using:

Accuracy
Precision
Recall
F1-score
ROC-AUC

Because the target variable is imbalanced, model selection is not based on Accuracy alone. Recall, F1-score, ROC-AUC, and business implications are also considered.

Reproducibility

Random seeds are specified throughout the analysis using:

random_state = 42


SMOTE is applied only to training data, and during cross-validation it is included within the training pipeline to prevent data leakage.

The test dataset remains untouched during model training.

Main Results

The strongest-performing models were the gradient boosting algorithms.

CatBoost achieved the highest mean ROC-AUC during 5-fold cross-validation, while LightGBM achieved the highest average F1-score and Accuracy.

SHAP analysis identified the most influential churn predictors as:

Age
Number of banking products
Active membership
Account balance
Tenure

Customer segmentation was then used to combine predicted churn risk with estimated customer value and recommend targeted retention strategies.

Notes

Customer value in this project is an estimated proxy based on available variables rather than an actual customer lifetime value calculation.

The dataset does not include transaction histories, customer profitability, complaint history, satisfaction measures, or marketing-response data. These limitations are discussed in the project report.

Authors

Ross Kelleher | Student #: 01385848 

Taha Anouar   | Student #: 101416333   

Allan Moloney | Student #: 10139654
