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

What is the formula for a MLB team's success? Obviously, it's winning, because a team must win in order to become championship contenders. And obviously, winning is accomplished by scoring more runs than your opponent. But if you were a general manager of a baseball franchise, you would want to go beyond that to determine a more precise equation to field a consistently winning team. Then, based on this formula, a general manager should be able to determine a player's value in terms of contributing to a team's winning chances.

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

Here is the individual player statistics dataset:
* <b>PlayerStats_Batting</b>
  * 215 KB as CSV / 392.7 KB in Pandas
  * 2185 rows
  * 23 columns
    * Column datatypes:
     * float64: 12
     * int64: 7
     * object: 4
  * 1403 null values
      
#### Packages
Packages used to retrieve, clean, alter, and analyze the data, as well as build, refine, and evaluate the model included:
  * matplotlib: 3.2.2
  * numpy: 1.18.5
  * pandas: 1.0.5
  * sklearn: 0.23.1
    * LinearRegression
    * mean_squared_error
    * r2_score
    * RFE
    * StandardScaler
    * train_test_split
  * seaborn: 0.10.1
 
## Summary

In summary, the following answers were presented for the research questions:
* What features most significantly impact the winning percentage of a given Major League Baseball (MLB) team?
    * The features which most significantly impact winning percentage are home runs (HR), batting average (AVG), on-base percentage (OBP), home runs allowed per nine innings (HR/9), batting average allowed on balls in play (BABIP_y), ground ball percentage (GB%), and home runs allowed per fly ball (HR/FB).
* For those given features, to what extent do they impact a team's winning percentage?
    * From multiple linear regression models, the following formula was created:
    <div align="center"><i><b>W%</b> = 0.8092 + (0.1078 * HR) + (1.0229 * AVG) + (1.4072 * OBP) - (0.4279 * HR/9) - (2.0556 * BABIP_y) - (0.8026 * GB%) + (2.4894 * HR/FB)</i></div>
* Based on this, who has been the most valuable player in contributing to a team's winning percentage from 2017-2020?
    * It was calculated that Mike Trout contributed the most offensively toward his team's winning percentage. 

## Limitations
One limitation comes from baseball itself. We could only craft a model that accounted for 58.1% of data variance. There is a lot to baseball that impacts winning and losing. While you want your team to bat well, field well, and pitch well, no team is perfect. Players make mistakes in all phases of the game which can have a direct outcome on the result, especially in a close game. So this model cannot account for a higher amount of the data variance.

Additionally, one of the problems with sports predictions is that the rows are not truly independent of one another. The teams play each other, impacting each other's win percentages. For example, the Yankees will typically play the Orioles 19 times in a standard length season. Each time they play each other, they impact each other's win percentage. Thus, they aren't independent.

Another limitation is that the dataset of team statistics was only 450 rows. This was chosen as a precaution to prevent skewed data from the "steroid era" of baseball. But a larger dataset from multiple decades of seasons would be preferable. Additionally, a few features were removed due to many null values. Perhaps these features could have been important in determining the win percentage, but the decision was made to preserve as many rows/seasons as possible in the dataset.

## Contributors

Clifton Saul

## [License & copyright](https://github.com/cmszip/DATA601-FinalProject/blob/main/LICENSE) 

© Clifton M Saul Jr.
