# Data Cleaning using Python
The dataset is made up of **13580 rows** and **21 columns**. 7 of the columns are categorical (non-numeric values) and I worked on transforming those 7.

The dataset contained categorical variables (non-numeric data) and they had to be transformed to numbers in cases where the data had to be fed to machine learning models. This is because machine learning models only understand numbers. If though the dataset is to be cleaned and imported to SQL, you may need to only work on missing data.
 Data Cleaning usually entails: Dealing with Missing Values, Categorical Values and Misinterpreted data. I implemented all these 

## Dealing with Categorical Variables
  The Catgorical variables were transformed in 3 different ways namely: 
  * Dropping all Categorical Columns
  * One-hot Encoder
  * Label Encoder

### Dropping all Categorical Columns
Using this method, i dropped (deleted) every column that contained categorical variables. This is the least effective method because in cases where there are a lot of categorical columns, it may affect model perfomance.

### One-hot Encoder
Using this method, I called the `OneHotEncoder()` from the Sci-kit learn library `sklearn` and fed categorical columns with less than 10 unique values to it, transformed which consequently formed n columns where n = no of variables per columns  and then dropped the original categorical columns. 
After transforming, i fed to the `RandomForestRegressor()` model and got my model evaluated. 

### Label Encoder
I did the same as described above except in this case i called the `LabelEncoder()` instead. 


After using these 3 methods, i tested how each affected the accuracy of Random Forest Regressor model i built and I found out that the Label Encoder and One-Hot Encoder Methods performed best.

