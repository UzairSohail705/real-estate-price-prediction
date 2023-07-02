## Introduction
We will apply regression models to predict real estate prices. It will be a multi-variate analysis with features such as location, size, number of bathrooms and bedrooms. 

## Methodology

### Data Cleaning
First of all, data cleaning and processing is performed. Some features are dropped which are not needed for the analysis, such as area type, availability and balcony. Then we check
for null values and remove all null values since their count is not large. 

### Feature Engineering
After that, we move on to feature engineering. The number of bedrooms is stored in the variable size but it's not in integer type. We find the number of bedrooms by splitting and storing
the first token in a new variable named bhk. The total_sqft variable also has some inconsistencies, some values are stored as a range rather than as a float. A function is defined to access
only those values which are not float, so that we can take the average of their range to make the data consistent. 

A new feature is added called Price per square foot to explore the anomalies in the data. The variable Locations is examined which is a categorical variable. We applied dimensionality 
reduction technique here to reduce number of locations. Any location which has less than 10 values is stored in Others. 

### Outlier Removal
Next, we perform outlier removal using business knowledge. Generally, the minimum value of square feet/bedrooms is around 300 so we remove all those rows which don't fit in the criteria. 
Similarly, all the outliers in the price/square feet column are removed using mean and standard deviation. Only those values are kept which are 1 standard deviation away from the mean. 
When performing EDA, it's observed that there are some locations which have lower price with 3 bedrooms as compared to 2 bedrooms, which does not make business sense so all those cases
are also removed as outliers. Outliers are also removed based on number of bathrooms/number of rooms. 

### Model Building
One hot encoding is done to store every unique location in a separate column. A train-test split is done to train the linear regression model. We also performed K-fold cross validation
to measure accuracy of our linear regression model. 

### Model Testing
Finally, we compare this model with different models such as Lasso () and Decision Tree to find the best model. Hyperparamter tuning is also done to find the best possible combination.
All of this comparison has been done using GridSearchCV. 

## Tools/Methods/Analyses:
-Linear Regression

-Outlier Removal

-One hot encoding

-K-fold cross validation

-GridSearchCV

-Hyperparameter tuning
