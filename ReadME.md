## End to End ML Project
## create environment
```
conda activate
conda create -p venv python==3.8
conda activate venv\
```
## install all necessary libraries
```
pip install -r requirements.txt
```

```
Approach for the project
Data Ingestion :

In Data Ingestion phase the data is first read as csv.
Then the data is split into training and testing and saved as csv file.
Data Transformation :

In this phase a ColumnTransformer Pipeline is created.
for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
This preprocessor is saved as pickle file.
Model Training :

In this phase base model is tested . The best model found was catboost regressor.
After this hyperparameter tuning is performed on catboost and knn model.
A final VotingRegressor is created which will combine prediction of catboost, xgboost and knn models.
This model is saved as pickle file.
Prediction Pipeline :

This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.
Flask App creation :

Flask app is created with User Interface to predict the gemstone prices inside a Web Application.
```