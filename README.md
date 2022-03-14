# Neural_Network_Charity_Analysis

## Overview

### Purpose

Beks is a data scientist and programmer for Alphabet Soup, a philanthropic organization that has funded multiple groups in the last 20 years focusing on humanitarian efforts. She has been asked to predict which organizations are too high-risk to donate for dontations and which ones are good candidates.  From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years.  We will be helping Beks use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Results

### Data Preprocessing

As part of preprocessing the data, unique values for categorial variables (application types, classifications) were binned and transposed to numerical values via one-hot encoding.  The data was then standardized using Standard Scaler to reduce potential impacts of outliers and skewed data.

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

For our target model performance, we want to hit an accuracy of 75%.  In all of our attempts, we were unable achieve the target model performance.

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
- What steps did you take to try and increase model performance?


## Summary:

The attempts made to increase model performance yielded similar accuracy results as the original model, but all attempts had lower loss.  Some recommendations for fututre attempts:

1) We successfully binned the values in the APPLICATION_TYPE and CLASSIFICATION columns of our dataset, but we didn't attempt to bin any values in the ASK_AMT column which had the largest amount of unique values present.  Binning the ASK_AMT column values may help in model performance prior to standardizing the data.
2) 



