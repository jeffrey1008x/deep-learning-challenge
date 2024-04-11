## Overview of the Analysis

In this assignment, we built a Neural Network model to decide if applicants funded by Alphabet Soup would use the funding effectively.
We train and test our model using previous funding records.
The model will predict the 'IS_SUCCESSFUL' column which is the label in this case.
The model will use the remaining columns except 'EIN' and 'NAME' as features since those 2 columns do not contain meaningful info.
Then we assign 75% of the data to train the model, and the remaining 25% for testing.
The model was trained using Neural Network from the tensorflow library.


## Results

* Data Preprocessing
The 'IS_SUCCESSFUL' column is the label we are trying to predict.
The remaining columns expect 'EIN' and 'NAME' are the features.
'EIN' and 'NAME' are removed from the features because they do not hold any meaningful info that could affect out label.

* Compiling, Training, and Evaluating the Model
In this case, I decided to use a tuner from the keras_tuner library to try a large variety of models with input combinations.
In the first layer, I gave the model choices from 1 to 40 neurons.
For the hidden layers, the model was allowed to choose between 1 to 6 hidden layers with each one having 1 to 20 neurons.
All layer except the last were given the choices to use wither 'relu','tanh' or 'sigmoid' as activation function.
'sigmoid' was used in the last layer since the result is binary.
A maximum number of 20 epochs was used.


## Summary

After 36 min of trials, the best accuracy we achieved was 0.7324 with a loss of 0.5534 with the following parameters:
 'activation': 'relu'
 'first_units': 29
 'num_layers': 4
 'units_0': 39
 'units_1': 29
 'units_2': 27
 'units_3': 9
 'units_4': 13
 'units_5': 5
 'tuner/epochs': 20
 'tuner/initial_epoch': 0
 'tuner/bracket': 0
 'tuner/round': 0

If I would use another model to solve this problem, I would recommend using Logistic Regression as our class work has demonstrated it is a powerful tool for classification problems.

