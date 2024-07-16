# Deep-Learning-Challenge - Requirements

**Pre-process the Data:**
- Created a dataframe containing the charity_data.csv data , and identified the target and feature variables in the dataset.
- Dropped the EIN and NAME columns.
- Determined the number of unique values in each column
- For columns with more than 10 unique values, determined the number of data points for each unique value
- Created a new value called Other that contains rare categorical variables
- Created a feature array, X, and a target array, y by using the preprocessed data
- Split the preprocessed data into training and testing datasets
- Scaled the data by using a StandardScaler that has been fitted to the training data

**Compile, Train and Evaluate the Model**
- Created a neural network model with a defined number of input features and nodes for each layer
- Created hidden layers and an output layer with appropriate activation functions
- Checked the structure of the model
- Compiled and trained the model
- Evaluated the model using the test data to determine the loss and accuracy
- Exported your results to an HDF5 file named AlphabetSoupCharity.h5

**Optimize the Model**
- Repeated the preprocessing steps in a new Jupyter notebook
- Created a new neural network model, implementing 3 model optimization methods
- Saved and export your results to an HDF5 file named AlphabetSoupCharity_Optimization.h5

# Report

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

# Data Preprocessing

**1. What variable(s) are the target(s) for your model?**

The target variable for the model is "IS_SUCCESSFUL". This variable represents the binary classification outcome of whether a charity donation was successful or not.

**2. What variable(s) are the features for your model?**

Feature Variables are all the listed variables in the model except "EIN" and "IS_SUCCESSFUL". 

**3. What variable(s) should be removed from the input data because they are neither targets nor features?**

"EIN" should be removed from the input data because it is neither a target nor a feature. Please note initial model was created removing "NAME" field but while optimizing the model, "NAME" variable was important in improving the accuracy of the model.

# Compiling, Training, and Evaluating the Model**

**1. How many neurons, layers, and activation functions did you select for your neural network model, and why?**

Tried different variations while optimizing the model but eventually selected the following parameters (Optimization 3) for my neural network model to get maximum accuracy possible.
- 2 Layers with **Layer 1: 16 nodes** and **Layer 2: 8 nodes**. Neuron counts were selected as powers of 2 to best utilize the resources available
- **Relu** is used as the activation function except for Output layer where **Sigmoid** is used. "Relu" Function works better for non-linear functions.

 <img src="https://github.com/user-attachments/assets/07f36124-0aa7-4e07-bd3c-a60c4b5e069c" width="900">


**2. Were you able to achieve the target model performance?**

Yes, achieved target model performance of `greater than 75%`. My optimization 3 resulted in **77.9% accuracy.**

<img src="https://github.com/user-attachments/assets/9230ab77-8f06-402c-b54c-bce48bc911cd" width="600">


**3. What steps did you take in your attempts to increase model performance?**

Steps taken across the 3 different model optimizations to increase model accuracy includes:
- Adding a column "NAME" back to the model
- Altered the number of bins for rare occurences in columns
- Changed the number of hidden layers, # nodes and activation functions
- Altered the number of epochs used to train the model

My model optimization 3 resulted in max accuracy of 77.9% higher than the targeted 75% due to the following steps:
- Added "NAME" Variable back to the model
- List of "NAME" with value counts < 10 were replaced
- List of "APPLICATION TYPES" with value counts < 500 were replaced
- List of "CLASSIFICATION TYPES" with value counts < 200 were replaced
- 2 layers with #nodes: 16 and 8 were selected
- "RELU" activation function was used for hidden layers with "Sigmoid" for the outer layer
- Number of Epochs was set to 40

# Summary

In summary, the neural network model leveraging TensorFlow and Keras was able to achieve an accuracy of 77.9% in classifying the success of organizations funded by AlphabetSoup Charity. Although the set of instructions provided for the initial model asked to drop off the "NAME" variable, inclusion of this variable was key to improving the model accuracy. Attempted 3 optimizations by changing columns, binning categorical variables, altering hidden layers and number of neurons, changing activation functions and # epochs. After such attempts, final model has been created with an accuracy of 77.9% which is beyond the targeted rate of 75%. Alternatively, I recommend using a different type of model, such as Random Forest Classifier or a Support Vector Machine (SVM) for handling such classification problems. These models are effective in binary classifications and may be able to achieve a higher accuracy without the need for too many optimization attempts. They are proven to better handle both numerical and categorical variables while accounting for data outliers and imbalanced datasets.
