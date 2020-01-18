# Project 2 - Ames Housing Data and Kaggle Challenge

### Problem Statement

To create a model based to predict the housing price for a house seller in Ames Housing Dataset.

### Investigation
Project 2 presented us two datasets: train.csv and test.csv, describing the sale of individual residential property in Ames, Iowa from 2006 to 2010.

There are three jupyter notebooks for this project:
1. project_2_test-data_pre-model.ipynb - it contains the data cleaning and data EDA for the train data.
2. project_2_train-data_pre-model.ipynb - it contains the data cleanup and alignment with the train dataset for the test data.
3. project_2_modeling.ipynb - it contains the modeling, reporting and conclusion of the project.

First one needs to understand what a home buyer looks for. Generally, it encompasses the followings:
- How big is the house?
- How old is it?
- What's the house condition?
- How many bedrooms?
- How many bathrooms?
- How is the Kitchen> -> dummy from 'Kitchen Qual'
- Is the basement finished?  
- How big is the garage?
- Does it near amenities/park/busy roads?
- Is the neighbourhood safe?

Variables related to these set the basic features for exploring the data.

For numerical variables, correlation was also looked into to pick variables that shows linear relationship with SalePrice.
For categorical variables, boxplot were used to eliminate skewed distribution

### Procedures:
1. Data was cleaned first.  

Two datasets each have 81 columns which include 23 nominal, 23 ordinal, 14 discrete, and 20 continuous variables (and 2 additional observation identifiers).  

1.train.csv -- contains all of the training data for modeling, it has 2051 rows and 81 columns

2.test.csv -- contains the test data to test the model.  It has 879 rows and 80 columns. This is the data to make predictions.

There are missing data and abnormal data.  the dataset was cleaned first.  Corrupted column types were fixed.  

There are 4 columns which have more than 80% data missing, since that won't be much useful for model construction, I have dropped them.  Certain columns with less than: 61 missing observations (3% of the total observations), they were also dropped.  

Columns with missing observations in between 3% and 80% were looked into.  It turned out that 'Fireplace Qu' has about half of the data missing, because those properties do not have fireplace.  The same thing goes with variable 'Garage Qu' (properties do not have garage).  These NaN shouldn't be treated like other missing values, therefore they later on were given a rating corresponding to that, instead of imputation or deleting.  

The ordinal columns have a rating on the physical feature of the property, so rating encoding was performed for those selected ones.

Physical features such as garage, basement, and house have multiple variables describing their quality/conditions, a combined variable was created to describe them.  For example:
  `'hse_cond'` is a combined rating from 5 varibles: Overall Qual,Overall Cond, Exter Qual, Exter Cond, and Functional.
  `'garage_cond'` combines: Garage Cond, Garage Finish, and Garage Qua.  
  `'bsmt_gen_cond'` combine: BsmtFinType 1, BsmtFinType 2, Bsmt Cond, and Bsmt Qual

Dummy cols were created for the selected features such as 'Garage Type', 'MS Zoning', 'Condition 1' and 'Condition 2', etc.  

I'm particular interested to know if a property near busy road such as artery road and feeder road will have any negative effects on the housing price.  Same as for railroad and recreational amenity such as park and natural reserves.


### Type of Modeling
Four types of modeling methods were looked into: Linear Regression, Lasso, Ridge and ElasticNet regression.  The mean r2 score is compared and the best model was selected to regress the test data.


## Conclusion
The baseline model using 16 variabels produced acceptable predictions with r2 scores in the 0.80 range on train data. The Kaggle score is 32490.57052. The performance of all of them are similiar.  The second feature 

The  None-lineararity and homoscedasticity in the residual plot suggests that the target is not normally distributed (which is what we observed). Properties at two sides of the scale (very small or very big properties) will be under_estimated by the regression model.  

If time allows, we can run your target vector through a power transformation and see if that improves the results.

Based on the data available from the dataset, no information could be derived regarding the location desirability.  Column Neighborhood lists 28 neighborhood towns, but we don't have information as to which town is more prestige.  Usually this information can be derived from the average household income by areas, or simplily crime rate by area.  Without information like these, we are not able to rank the neighborhood, and that is a big piece of missing information to help build a more accurate model.

Lastly, the model revealed that the key variables that contributes to *higher* sale price are: `'Gr Liv Area`',`'hse_cond'`, `'kitchen_qu_num'`, followed by `'Lot Area'` and `'Garage Cars'`, this is common in all models.  Variabels that would affect sale price *negatively* are: `age`,and `'total_baths'` and `'Bedroom AgvGr'`, although the last two variables are unexpected.
