# Deep-Learning-Challenge: Report

**Overview of the Analysis**

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. Used the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup. Received a CSV file containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special considerations for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively

# Results

**Data Preprocessing**

- What variable(s) are the target(s) for your model?
The target variable for the model is "IS_SUCCESSFUL". This variable represents the binary classification outcome of whether a charity donation was successful or not.

- What variable(s) are the features for your model?
Feature Variables are all the listed variables in the model except "EIN" and "IS_SUCCESSFUL". 

- What variable(s) should be removed from the input data because they are neither targets nor features?
"EIN" should be removed from the input data because it is neither a target nor a feature. Please note initial model was created removing "NAME" field but while optimizing the model, "NAME" variable was important in improving the accuracy of the model.


