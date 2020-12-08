![Baseball](https://www.goodfreephotos.com/albums/united-states/pennsylvania/pittsburgh/pittsburgh-pirates.jpg)

# A Formula for Success: <br>Predicting How to Win in Major League Baseball
<b>by Clifton Saul</b>

## Project Overview & Background

This project's task is to utilize previously developed skills in DATA 601 and build upon them by developing, testing, and evaluating a model, and packaging it in a final technical/presentation notebook. Specifically, this project will use a multiple linear regression model to predict a Major League Baseball (MLB) team's winning percentage given other features. In the notebook, the scenario involved is a general manager of a MLB franchise who wants to determine the team statistics which impact a team's winning percentage in hopes of fielding a more competitive roster.

This topic was chosen from the author's own personal interests in sports and out of curiosity after recently seeing a job posting for a data analyst role with the Baltimore Orioles MLB franchise. The job application included a question regarding the most important statistics in baseball. 

The data used in this project is freely available, and therefore this experiment is easily replicated. There are similar projects which use regression to predict the number of wins a sports team will achieve. While this project was not inspired by those, the author encourages others to visit some of those other individuals' work.


## Repo Content & Navigation

* <b>[Data](https://github.com/cmszip/DATA601-FinalProject/tree/main/Data)</b> - Folder containing datasets used in this project.
* <b>[Images](https://github.com/cmszip/DATA601-FinalProject/tree/main/Images)</b> - Folder containing images used in this project.
* <b>[Notebooks](https://github.com/cmszip/DATA601-FinalProject/tree/main/Notebooks)</b> - Folder containing the Jupyter notebooks used in this project.
  * <b>[Notebook 1 - Data Exploration & Cleaning](https://github.com/cmszip/DATA601-FinalProject/blob/main/Notebooks/Notebook%201%20-%20Data%20Exploration%20%26%20Cleaning.ipynb)</b> - Jupyter notebook where data was pulled, explored, and cleaned. 
  * <b>[Notebook 2 - Modeling](https://github.com/cmszip/DATA601-FinalProject/blob/main/Notebooks/Notebook%201%20-%20Data%20Exploration%20%26%20Cleaning.ipynb)</b> - Jupyter notebook where model was developed and refined. 
  * <b>[Notebook 3 - Technical Report & Summary Presentation](https://github.com/cmszip/DATA601-FinalProject/blob/main/Notebooks/Notebook%203%20-%20Technical%20Report%20%26%20Summary%20Presentation.ipynb)</b> - This is the summary notebook that provides a synopsis of the work in Notebooks 1 & 2 with few code blocks. 
* <b>[License](https://github.com/cmszip/DATA601-FinalProject/blob/main/LICENSE)</b> - MIT license and copyright.

## Motivation

Buying a car can be one of the most stressful experiences in a person's life. There is a ton of information to weigh, salespeople will push and pressure you, and knowing you can easily be taken advantage of can make the experience a painful one.

However, part of this problem stems from not having adequate information to objectively discern what is a fair deal. People should be able to determine if a given car is being listed at a fair price, and the author wants to provide a useful tool for people to be able to do that.

## Goals

Given the above motivation, the primary goal of this project is to build a model that will predict the win percentage of a MLB team given a set of chosen features. It will employ a multiple linear regression model to create an equation that can be used to determine a team and player's effectiveness in contributing to winning.

A secondary goal is a more personal one. This author hopes to build further experience developing, refining, and evaluating a model, but also to be able to present it to others. This model will be built using a dataset of baseball team statistics. Info on this dataset can be found below.


## Data Overview

Data was pulled from [Fangraphs.com](https://www.fangraphs.com/leaders.aspx?pos=all&stats=bat&lg=all&qual=0&type=8&season=2020&month=0&season1=2020&ind=0&team=0,ts&rost=&age=&filter=&players=0). More information on how to pull the same data can be found in [Notebook 1](https://github.com/cmszip/DATA601-FinalProject/blob/main/Notebooks/Notebook%201%20-%20Data%20Exploration%20%26%20Cleaning.ipynb).

Below is information on the dataset and the packages used in this project:

* <b>TeamStats_Combined</b>
 * 145 KB as CSV / 225.1 KB in Pandas
 * 450 rows
 * 64 columns
    * Column datatypes:
     * float64: 32
     * int64: 25
     * object: 7
  * 870 null values
  
This dataset was altered via data cleaning and feature engineering to become:
* <b>TeamStats_Combined_Cleaned</b>
  * 84.8 KB as CSV / 66.9 KB in Pandas
  * 450 rows
  * 19 columns
    * Column datatypes:
     * float64: 16
     * int64: 1
     * object: 2
  * 0 null values
    "Here is the individual player statistics dataset:\n",
    "* <b>PlayerStats_Batting</b>\n",
    "    * 215 KB as CSV / 392.7 KB in Pandas\n",
    "    * 2185 rows\n",
    "    * 23 columns\n",
    "        * Column datatypes:\n",
    "            * float64: 12\n",
    "            * int64: 7\n",
    "            * object: 4\n",
    "    * 1403 null values\n",
      
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
