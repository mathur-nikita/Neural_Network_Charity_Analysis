# Neural_Network_Charity_Analysis

## Overview

### Purpose

Beks is a data scientist and programmer for Alphabet Soup, a philanthropic organization that has funded multiple groups in the last 20 years focusing on humanitarian efforts. She has been asked to predict which organizations are too high-risk to donate for dontations and which ones are good candidates.  From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years.  We will be helping Beks use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Results

### Data Preprocessing

As part of preprocessing the data, unique values for categorial variables (application types, classifications) were binned and transposed to numerical values via one-hot encoding.  The data was then standardized using Standard Scaler to reduce potential impacts of outliers and skewed data.

Binning of APPLICATION_TYPE:                     
![binning_application_type.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/binning_application_type.JPG)

Binning of CLASSIFICATION:                        
![binning_classification.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/binning_classification.JPG)

- The variable considered to be the target for our model is IS_SUCCESSFUL. 
- The variables considered to be the features for our model are:
  - APPLICATION_TYPE
  - AFFILIATION
  - CLASSIFICATION
  - USE_CASE
  - ORGANIZATION
  - STATUS
  - INCOME_AMT
  - SPECIAL_CONSIDERATIONS
  - ASK_AMT
- Variables considered neither targets nor features for our model have been removed from our data.  These variables are:
  - EIN
  - NAME

### Compiling, Training, and Evaluating the Model

For our target model performance, we want to hit an accuracy of 75%.  In all of our attempts, we were unable achieve the target model performance.  In the original model we used the following:
- Number of layers: 2
- Number of neurons: 80 in later one, 30 in layer 2
- Activation functions: all layers used a rectified linear activation function (ReLU) except for the output layer, which used a sigmoid function.  The sigmoid function was chosen because it results in binary output, which is what we need for our model (i.e. is a chosen organization a good candidate for donations or not).
![model_definition_original.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/model_definition_original.JPG)

  The results of the original model:          
  ![results_original_model.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/results_original_model.JPG)

Three attempts were made to increase the performance of our model.

1) Attempt 1 - added additional neurons to existing layers
![model_definition_attempt_1.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/model_definition_attempt_1.JPG)

  Results:                                       
  ![results_optimized_model_attempt_1.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/results_optimized_model_attempt_1.JPG)

2) Attempt 2 - added an additional hidden layer with 20 neurons
![model_definition_attempt_2.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/model_definition_attempt_2.JPG)

  Results:                                       
  ![results_optimized_model_attempt_2.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/results_optimized_model_attempt_2.JPG)

3) Attempt 3 - changed activation function for hidden layers
![model_definition_attempt_3.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/model_definition_attempt_3.JPG)

  Results:                                       
  ![results_optimized_model_attempt_3.JPG](https://github.com/mathur-nikita/Neural_Network_Charity_Analysis/blob/main/screenshots/results_optimized_model_attempt_3.JPG)

## Summary:

The attempts made to increase model performance yielded similar accuracy results as the original model, but all attempts had lower loss.  Some recommendations for fututre attempts:

1) We successfully binned the values in the APPLICATION_TYPE and CLASSIFICATION columns of our dataset, but we didn't attempt to bin any values in the ASK_AMT column which had the largest amount of unique values present.  Binning the ASK_AMT column values may help in model performance prior to standardizing the data.
2) A different model to use could be a Random Forest Model.  Random Forest Models, provided with the right amount of estimators, can provide similar results as a deep learning model in a fraction of the time.  This can help greatly in creating a model in less time with results we'd like.



