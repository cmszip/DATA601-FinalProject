![Baseball](https://www.goodfreephotos.com/united-states/pennsylvania/pittsburgh/pittsburgh-pirates.jpg.php)

# Carbuying Made Easy: <br>Predicting the Price of a Car Based on its Features 
<b>by Clifton Saul</b>

## Project Overview & Background

This project's task is to utilize previously developed skills in data exploration and analysis and build upon them by developing, testing, and evaluating a model. Specifically, this project will use a multiple linear regression model to predict the price of a car given its features. In the notebook, the scenario involved is a friend asking for help in predicting a fair price for a vehicle. By predicting a fair price for a vehicle given particular features, the friend can then evaluate if a listed price is above or below predictions for a similar vehicle.

This topic was chosen from the author's own personal interests in vehicles and out of curiosity after recently assisting a friend in purchasing a vehicle. The data used is freely available, and therefore this experiment is easily replicated. There are similar projects which use regression to predict prices of cars, houses, and other items available on Github currently. While this project was not inspired by those, the author encourages others to visit some of those other individuals' work.


## Repo Content & Navigation

* <b>[Data](https://github.com/cmszip/DATA601-Project1-Regression/tree/main/Data)</b> - Folder containing datasets used in this project.
  * <b>[auto_data.csv](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/Data/auto_data.csv)</b> - dataset of 201 automobiles pulled from IBM Cloud. Dataset can also be downloaded from [Kaggle](https://www.kaggle.com/statsakash/used-car-price-prediction).
* <b>[Images](https://github.com/cmszip/DATA601-Project1-Regression/tree/main/Images)</b> - Folder containing images used in this project.
* <b>[Notebooks](https://github.com/cmszip/DATA601-Project1-Regression/tree/main/Notebooks)</b> - Folder containing the Jupyter notebook used in this project.
  * <b>[Notebook 1 - Technical Notebook](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/Notebooks/Notebook%201%20-%20Technical%20Notebook%20-%20Cleaned.ipynb)</b> - Jupyter notebook where data was pulled, explored, and cleaned, and models were built and evaluated. 
* <b>[License](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/LICENSE)</b> - MIT license and copyright.

## Motivation

Buying a car can be one of the most stressful experiences in a person's life. There is a ton of information to weigh, salespeople will push and pressure you, and knowing you can easily be taken advantage of can make the experience a painful one.

![Stressed Out Car](https://www.confused.com/-/media/confused/articles/article-content-images/car-insurance/driving-stress-main.jpg?la=en-gb&hash=FD620795484988910AC1E8C32C671B2AF49C880B)

However, part of this problem stems from not having adequate information to objectively discern what is a fair deal. People should be able to determine if a given car is being listed at a fair price, and the author wants to provide a useful tool for people to be able to do that.

## Goals

Given the above motivation, the primary goal of this project is to build a model that will predict the price of a car based on some of its features. It will employ a multiple linear regression model to create an equation for people to use to determine a fair price for a car.

A secondary goal is a more personal one. This author hopes to build experience developing, refining, and evaluating a regression model. This model will be built using a dataset of vehicles. Info on this dataset can be found below.


## Data Overview

Data was pulled from IBM Cloud using Pandas. The code to do this can be found in the second code block of [Notebook 1](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/Notebooks/Notebook%201%20-%20Technical%20Notebook.ipynb). Alternatively, the data can be downloaded manually from [Kaggle](https://www.kaggle.com/statsakash/used-car-price-prediction). This dataset consists of 201 rows of vehicles and their features.

Below is information on the dataset and the packages used in this project:

#### Original Dataset 
The original dataset [auto_data.csv](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/Data/auto_data.csv) includes:
  * 201 rows
  * 29 columns:
    * Column datatypes:
      * float64: 11
      * int64: 8
      * object: 10
 
 This dataset was altered via data cleaning and feature engineering to include:
  * 187 rows
  * 51 columns
    * Column datatypes:
      * float64: 16
      * uint8: 35
      
#### Packages
Packages used to retrieve, clean, alter, and analyze the data, as well as build, refine, and evaluate the model included:
  * matplotlib
  * numpy
  * pandas
  * sklearn
    * LinearRegression
    * mean_squared_error
    * r2_score
    * RFE
    * StandardScaler
    * train_test_split
  * seaborn
 
## Summary

In summary, the resulting multiple linear regression model's equation to determine a car's price is:

<i><b>price</b> = 0.7246 + (0.4871 * curb-weight) - (0.3230 * aspiration_std) + (0.4062 * fuel-system_mpfi) - (0.3168 * make-quality_Budget) + (1.3541 * make-quality_Premium) - (0.5915 * num-of-cylinders_four)</i>

This model will account for 85.1% of the variance in the data while maintaining a low mean squared error of 0.149 with all variables being statistically significant.

A person can therefore make pricing decisions based on this model. If a person is more interested in a budget, midrange, or premium brand, he/she/they can account for this in the model as well. Importantly this allows a person to predict the expected price of a vehicle based on these features, which means he/she/they can determine if it is a good deal on a car or if it is overpriced.  

## Limitations
One limitation is that a decision was made to impute the median value of the column 'stroke' for four vehicles made by Mazda. It did not seem to effect the model, as 'stroke' was not an included feature in the model's final equation.

However, the main limitations are found in the dataset itself. Although the original dataset is over 200 vehicles, that isn't very large compared to the number of automobile models that are available in the US. Furthermore, there are some very popular US brands that are missing. Ford, Chrysler, Lincoln, Cadillac, and others are not included in the dataset. Having a more robust dataset would likely alter the model in ways that will benefit it, and by extension, the user.

## Contributors

Clifton Saul

## [License & copyright](https://github.com/cmszip/DATA601-Project1-Regression/blob/main/LICENSE) 

© Clifton M Saul Jr.
