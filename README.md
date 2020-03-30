# Exoplanet_Exploration_Machine_Learning
## Introduction
This project is based in exploratory data from a kaggle dataset.
The author of this dataset provided the following context
"The Kepler Space Observatory is a NASA-build satellite that was launched in 2009. The telescope is dedicated to searching for exoplanets in star systems besides our own, with the ultimate goal of possibly finding other habitable planets besides our own. The original mission ended in 2013 due to mechanical failures, but the telescope has nevertheless been functional since 2014 on a "K2" extended mission.

Kepler had verified 1284 new exoplanets as of May 2016. As of October 2017 there are over 3000 confirmed exoplanets total (using all detection methods, including ground-based ones). The telescope is still active and continues to collect new data on its extended mission."

#### For more information of the dataset please visit https://www.kaggle.com/nasa/kepler-exoplanet-search-results
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

* Created a in64 column with the numerical values of the target column.
  + FALSE POSITIVE: 0 
  + CONFIRMED:      1
  + CANDIDATE:      2

* It used the Correlation matrix with Pearson Correlation Coefficient to identify the multicolinearity
* Values with a correlation higher than 0.6 in respect to other idependent variable were taked out. Most of them were the error recorded from some of the values.

![Correlation_matrix](https://github.com/luisantoniococa/Exoplanet_Exploration_Machine_Learning/blob/master/Correlation_matrix.png "Pearson Correlation Coeficient Matrix with Heatmap")

## Feature Selection/ Dimentionality Reduction
* Reduced the amount the features from 41 to 26 based in the multicolinearity and the pearson correlation matrix showed earlier.
* Created a few test to reduce the amount of features for the model. 
* Selected the Univariate Feature Selection (chi square test) score as our selector. 
* Based in their score, the following table shows the 15 values with the highest score.
![Selected_features](https://github.com/luisantoniococa/Exoplanet_Exploration_Machine_Learning/blob/master/selected_features_table.png "Selected features after the Chi Squared test")
Finally we created a pandas dataframe with the selected features and saved as cleaned_dataset.csv.

## Model Evaluation
Evaluated a several clasification models. The data was splited into X_test, y_test, X_train and y_train. Also the X data (features) was scaled using MinMaxScaler from sklearn. 

The trained models scores can be seen below. The score was obtained by evaluating the test data.

| Model      | Train score | Test score |
| --------- | ---------| -----:|
| Suport Vector Machine with GridSearch  | 0.8594316231165363 | 0.8569794050343249 |
| Logistic Regression     |   0.8359717718863247 | 0.8386727688787186 |
| Desicion tree classifier      |    - | 0.835812356979405 |
| Random Forest classifier     |   - | 0.8947368421052632 |

We were able to use the Hyperparameter Tuning when using the SVM and that helped attain a greater accuracy. 
#### Deep Neural Network 
It was also decided to train a Deep Neural Netowrk model and find out if the model could be improved.
The model had the following structure
* 200 epochs
* 15 input nodes, 3 output nodes
* 2 hidden layers with 50 and 70 nodes respectively
* Relu activation function
* Adam optimizer
* Categorical Crossentropy as a loss function
* Softmax as the final Squashing function
The model was trained focusing in accuracy
#### After 200 epochs, the model was tested/evaluated and got the final results
`
1748/1748 - 0s - loss: 0.3586 - accuracy: 0.8913
Loss: 0.35862062653224036, Accuracy: 0.8913043737411499`


## Conclusion
We were able to attain an accuracy close to 90 percent in 3 of our models. 
The best models included the Support vector machine (SVM), Random Forest and Deep neural Network (DNN). We saved the SVM and the DNN models in 2 different files. We were completed our goal of training the model and baing able to predict close to 90% of the data. 
