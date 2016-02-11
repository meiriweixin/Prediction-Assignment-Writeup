# Prediction-Assignment-Writeup

                                      How I built the model

Step I. [Data Cleaning]
After loading the data, one needs to check the data first.

I noticed the training data set has 19,622 observations and 160 columns. 
I checked the data: first column is the row number, which must be removed later.
Many columns have a large amound of NA or blank values, which also must be cleaned before build the model. 
Since the data contain both NA and blank values, I set na.string= c(“NA”, “ ”, “NAN”, “”) when reading the data, 
so that all these cases will be taken as NA values. Columns with more than 40% NA vlaues are removed. 
Luckly, after remove columns with more than 40% NA values, all left columns have no NA values.

Step II. [Feature Selection]
Selecting the right features in your data can mean the difference between mediocre performance with long training times and 
great performance with short training times. 

I first remove those highly correlated variables.

Then, I remove those redundant features using the Caret package.  
Feature selection is fulfilled using the recursive feature elimination method in the Caret package. 
A Random Forest algorithm is used on each iteration to evaluate the model.
The results show use top 4 features are enough to build a good prediction model.

Step II. [Build the Predictive Model]
In the end, a Random Forest algorithm is used based only on top 4 features.
