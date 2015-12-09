# Machine Learning

# Objectives
Students will be able to
- explain the linear regression model
- explain the k-nearest neighbors model very technically
- explain the popular data science algorithms conceptually to a layman
- use the scikit-learn library to generate predictive models
- explain the datascience ecosystem and terminology
- tie their pandas, sklearn, and plotting knowledge together

# Agenda
1. What is data science? (40m)
2. Intro to linear regression (45m)
3. Boston Housing Data Analysis (45m)
4. Linear regression practice on new data set (45m)
5. Intro to classification (15m)
6. Technical explanation of kNN via worksheet (if necessary) (30m)
7. Classification on cancer data with kNN (45m)
8. Group reading and discussion of logistic regression and random forest (60m)
9. How to use logistic regression classifier (30m)
10. Classification exercise on new dataset, using many different models (60m)

# What is Data Science
*Think/Pair/Share*: What is data science? What are some examples of datascience applications

## Areas of prediction (Supervised learning)
1. Recommendation engines
2. Spam detection
3. Translation
4. Sentiment Analysis
5. Automatic categorization of documents
6. Computer vision

## Areas of unsupervised learning
1. Clustering analysis (market/customer segmentation)
2. Anomaly detection
3. Dimensionality reduction (compressing images or compressing our feature set)

## AI products
1. [x.ai](http://x.ai)
2. [Netflix](http://netflix.com)

## Example applications
1. Tailoring Netflix recommendations to each user
2. Classifying dermatoscopies of lesions as either malignant or benign
3. Using computer vision to teach cars to self-drive

## Terminology
- model
- training
- features
- target
- cross-validation

# Linear Regression
## Definition
Pair/Sahre: Google linear regression. what is it?

## Technical explanation
Use the linear equation in 2 features with housing price prediction example to understand the intuition of the model and a tiny data set on which we calculate the loss of two linear regressions and determine which is better.

Refer to [this worksheet]()

- How do we compute the linear regression model?
- What is the loss function?
- How does this look in 2 variables? How about 1,000?
- How do we evaluate the fit of the model?

# The Boston Housing Data Set
- [Here](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/Boston_Housing.csv) is our data set.
- [Here](https://archive.ics.uci.edu/ml/machine-learning-databases/housing/housing.names) is the description of the data.

## Exercise: Pre-Analysis (with Partner)
1. What is the data about?
2. What are columns? (What are the features?)
3. What are we trying to predict? (what is the target?

## Exercise: Prepping for Data Science (Solo)
0. Download and read in the data.
1. Use pandas's built-in descriptive statistics method to get a statistical summary of the data.
2. Plot CRIM against MEDV. Bonus points if you use Plot.ly.
3. Generate the remaining 12 plots (ZN against MEDV, ..., LSTAT against MEV)
4. Which feature looks to be most predictive of MEDV(read: correlated to MEDV)?

# Intro to Sklearn
Sci-kit learn is a powerful and easy-to-use Python library of machine learning and statistical algorithms.

Let's google "Scikit learn" and look at the docs page.

## Exercise (With Partner)
Google around for scikit learn linear regression model, read the relevant documentation, and find example usage.

## Let's Analyze Together
0. Let's separate the data into feature and target.
1. Let's separate the feature and target into training and validation set.
2. Let's fit the [linear regression model](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) using 3 columns.
3. Let's plot the linear regression model.
4. Let's plot the predictions.
5. Let's measure the accuracy.
6. Let's see which columns were most predictive.
7. Let's use [`cross_val_predict`](http://scikit-learn.org/stable/modules/generated/sklearn.cross_validation.cross_val_predict.html) as a shortcut to get the predicted values.
8. Let's use [`cross_val_score`](http://scikit-learn.org/stable/modules/generated/sklearn.cross_validation.cross_val_score.html) as a shortcut for the R^2 values. What does `cv` do?

## Exercise (With Partner)
0. Run the regression using all of the feature columns.
1. How does the model improve/worsen?

# Data set practice
[Here](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/health_data.csv) is a dataset with the following columns:

- Age
- Years spent receiving their education
- Income divided by 10,000
- Number of visits to the doctor in the previous year

## Exercises (with Partner)
0. Use the first three columns to predict the number of doctors visits with a linear regression model.
1. Build a linear model that only takes age and education years as the input.
2. then a linear model that takes just the age and the income.
3. Which model fits the data better?

# Intro to Classification
## Terminology
- classification
- regression

*Question*: what are some examples of classification applications?

# k-Nearest Neighbors classification algorithm
- simple, intuitive model
- works well when there aren't too many different features
- works well when the scale of each feature is similar (why?). we'll see this in our example.

## Technical overview
- [kNN in one dimension](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/worksheets/worksheet_1_kNN.pdf)
- [kNN in multiple dimensions](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/worksheets/worksheet_2_kNN.pdf)

# Cancer prediction using kNN
- [Here's](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/breast-cancer.csv) a description of our dataset.
- [Here's](https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.data) the dataset.

## Exercise: Pre-Analysis (Solo)
0. Read the dataset description. What is this dataset about?
1. Read in the dataset with pandas.
2. Separate into feature and target

## Let's Analyze Together
1. Use cross val to run [`KNeighborsClassifier`](http://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
2. Plot these values of n_neighbors 2, 3, 4, 5, 10 against accuracy score. How did it do?
3. Let's describe the data.
4. Let's normalize the data using [`normalize`](http://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.normalize.html)
5. Try KNeighbors again for the different values of n_neighbors. How did it do? Which value of n_neighbors was best?
6. Let's manually use `train_test_split` and compare the predicted values with the true values in the test set to more concretely see the output of the model.

## Tuning the Model
- Every data science model (algorithm) has parameters you can tune to improve the accuracy of the model.
- For kNN, what can/did we tune?

# Popular Classification Algos
## Reading Exercise 1: Logistic Regression
0. Read this article [What is logistic regression](http://qr.ae/Rb5ADS) by yourself.
1. Get into groups of 2-3 and discuss and try to explain the algo to each other and identify points of confusion.
2. Let's go through it together.

## Reading Exercise 2: Random Forest
0. Read this article [How do random forests work in layman's terms?](http://qr.ae/Rb5Al2) by yourself.
1. Get into groups of 2-3 and discuss and try to explain the algo to each other and identify points of confusion.
2. Let's go through it together.

# Using Logistic Regression
Let's go back to our cancer dataset.

## Let's Analyze Together
0. Look up the docs of logistic regression sklearn
1. Import and fit the logistic regression classifier
2. How do the results compare to kNN?

## Exercise (with Partner)
0. How can you tune the model? What parameters do you have available? (hint: look at the docs and examples on sklearn)
1. Tune those parameters. How does the accuracy change? Which is the best choice of parameters?

# Final Practice
[Here's]() a dataset about X.

## Exercise (with Partner)
0. Read in the data
1. Identify the features and the target
2. Run a kNN model. Tune it to find the best choice of `k`.
3. Run a logistic model. Tune it.
4. Run a random forest model and tune it.
5. Which performed the best?

# Next Steps
- Data Science part time course
- [Gallery of ipython notebookes](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks)
- Coursera on Machine Learning by Andrew Ng
- [Kaggle](https://www.kaggle.com/competitions)