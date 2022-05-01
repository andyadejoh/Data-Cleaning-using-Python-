# Data Cleaning using Python
The dataset is made up of **13580 rows** and **21 columns**. 7 of the columns are categorical (non-numeric values) and 4 contain missing values. I worked on transforming these colummns.

The dataset contained categorical variables (non-numeric data) and I had to transform them to numbers so the machine learning model understnads the data. If though the dataset is to be cleaned and imported to SQL, you may need to only work on missing data. Data Cleaning usually entails: Dealing with Missing Values, Categorical Values and Misinterpreted data. I implemented all these 

## Dealing with Categorical Variables
  The Catgorical variables were transformed in 3 different ways namely: 
  * Dropping all Categorical Columns
  * One-hot Encoder
  * Label Encoder

### Dropping all Categorical Columns
Using this method, i dropped (deleted) every column that contained categorical variables. This is the least effective method because in cases where there are a lot of categorical columns, it will affect model perfomance.

### One-hot Encoder
Using this method, I called the `OneHotEncoder()` from the Sci-kit learn library `sklearn` and fed categorical columns with less than 10 unique values to it then transformed which consequently formed n new columns where n = no of variables per columns  and then dropped the original categorical columns. 
After transforming, i fed to the `RandomForestRegressor()` model and got my model evaluated. 

### Label Encoder
I did the same as described above except in this case, i called the `LabelEncoder()` instead. 


After using these 3 methods, i tested how each affected the accuracy of Random Forest Regressor model i built and I found out that the Label Encoder and One-Hot Encoder Methods performed best.

## Handling Missing Values
I handled missing values using 2 methods:
* Dropping columns with missing values
* Using `SimpleImputer()`

### Dropping columns with missing values
Using this method, i dropped (deleted) every column that contained missing values. This is the least effective method because in cases where there are a lot of columns with missing values, it will affect model perfomance.

### Using `SimpleImputer()`
Using this method, I called the `SimpleImputer()` using the mean strategy from the Sci-kit learn library `sklearn` and fed columns with missing values to it. After the dataset was fit to it, it generated a mean for each column and transformed each column by replacing the missing or null values with the mean. After transforming, i fed to the `RandomForestRegressor()` model and got my model evaluated. 

After model was evaluated, the `SimpleImpuer()` performed better. 


