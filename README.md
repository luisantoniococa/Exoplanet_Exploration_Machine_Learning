# Exoplanet_Exploration_Machine_Learning
## Introduction
This project is based in exploratory data from a kaggle dataset.
The author of this dataset provided the following context
"The Kepler Space Observatory is a NASA-build satellite that was launched in 2009. The telescope is dedicated to searching for exoplanets in star systems besides our own, with the ultimate goal of possibly finding other habitable planets besides our own. The original mission ended in 2013 due to mechanical failures, but the telescope has nevertheless been functional since 2014 on a "K2" extended mission.

Kepler had verified 1284 new exoplanets as of May 2016. As of October 2017 there are over 3000 confirmed exoplanets total (using all detection methods, including ground-based ones). The telescope is still active and continues to collect new data on its extended mission."

#### for more information of the dataset please visit https://www.kaggle.com/nasa/kepler-exoplanet-search-results
## Overview
* My goal is to create a machine learning model that can classify based in the data if is a False Positive, Candidate or a Confirmed exoplanet.
The project consists in 3 parts. 
* The first one is using multiple resources to do a feature selection analysis. 
* Second part consist in the evaluation of different machine learning models and that provide different scores. 
* Third part is to vizualize some of the data for better understanding of the model. 

#### Project is going to me excecuted in Python and Jupyter notebooks.
#### The libraries used include, pandas, matplotlib, numpy, sklearn, TensorFlow 2.0

## Cleaning the data
* One of the first challenges was to clean the data and perform feature selection.

*Created a in64 column with the numerical values of the target column.
** FALSE POSITIVE: 0 
** CONFIRMED:      1
** CANDIDATE:      2

* It used the Correlation matrix with Pearson Correlation Coefficient to identify the multicolinearity
* values with a correlation higher than 0.6 in respect to other idependent variable were taked out. Most of them were the error recorded from some of the values.

![Correlation_matrix](https://github.com/luisantoniococa/Exoplanet_Exploration_Machine_Learning/blob/master/Correlation_matrix.png "Pearson Correlation Coeficient Matrix with Heatmap")

## Feature Selection

Created a in64 column with the numerical values of the target column.
* FALSE POSITIVE: 0 
* CONFIRMED:      1
* CANDIDATE:      2
