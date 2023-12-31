# Deep Learning Challenge

## Background

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

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

## Instructions

### Step 1: Preprocess the Data
Using your knowledge of Pandas and scikit-learn’s StandardScaler(), you’ll need to preprocess the dataset. This step prepares you for Step 2, where you'll compile, train, and evaluate the neural network model.

Start by uploading the starter file to Google Colab, then using the information we provided in the Challenge files, follow the instructions to complete the preprocessing steps.

Read in the charity_data.csv to a Pandas DataFrame, and be sure to identify the following in your dataset:
What variable(s) are the target(s) for your model?
What variable(s) are the feature(s) for your model?
Drop the EIN and NAME columns.

Determine the number of unique values for each column.

For columns that have more than 10 unique values, determine the number of data points for each unique value.

Use the number of data points for each unique value to pick a cutoff point to bin "rare" categorical variables together in a new value, Other, and then check if the binning was successful.

Use pd.get_dummies() to encode categorical variables.

Split the preprocessed data into a features array, X, and a target array, y. Use these arrays and the train_test_split function to split the data into training and testing datasets.

Scale the training and testing features datasets by creating a StandardScaler instance, fitting it to the training data, then using the transform function.

### Step 2: Compile, Train, and Evaluate the Model

Using your knowledge of TensorFlow, you’ll design a neural network, or deep learning model, to create a binary classification model that can predict if an Alphabet Soup-funded organization will be successful based on the features in the dataset. You’ll need to think about how many inputs there are before determining the number of neurons and layers in your model. Once you’ve completed that step, you’ll compile, train, and evaluate your binary classification model to calculate the model’s loss and accuracy.

Continue using the file in Google Colab in which you performed the preprocessing steps from Step 1.

Create a neural network model by assigning the number of input features and nodes for each layer using TensorFlow and Keras.

Create the first hidden layer and choose an appropriate activation function.

If necessary, add a second hidden layer with an appropriate activation function.

Create an output layer with an appropriate activation function.

Check the structure of the model.

Compile and train the model.

Create a callback that saves the model's weights every five epochs.

Evaluate the model using the test data to determine the loss and accuracy.

Save and export your results to an HDF5 file. Name the file AlphabetSoupCharity.h5.

### Step 3: Optimize the Model
Using your knowledge of TensorFlow, optimize your model to achieve a target predictive accuracy higher than 75%.

Use any or all of the following methods to optimize your model:

Adjust the input data to ensure that no variables or outliers are causing confusion in the model, such as:
- Dropping more or fewer columns.
- Creating more bins for rare occurrences in columns.
- Increasing or decreasing the number of values for each bin.
- Add more neurons to a hidden layer.
- Add more hidden layers.
- Use different activation functions for the hidden layers.
- Add or reduce the number of epochs to the training regimen.
Note: If you make at least three attempts at optimizing your model, you will not lose points if your model does not achieve target performance.

Create a new Google Colab file and name it AlphabetSoupCharity_Optimization.ipynb.

Import your dependencies and read in the charity_data.csv to a Pandas DataFrame.

Preprocess the dataset as you did in Step 1. Be sure to adjust for any modifications that came out of optimizing the model.

Design a neural network model, and be sure to adjust for modifications that will optimize the model to achieve higher than 75% accuracy.

Save and export your results to an HDF5 file. Name the file AlphabetSoupCharity_Optimization.h5.

### Step 4: Write a Report on the Neural Network Model
For this part of the assignment, you’ll write a report on the performance of the deep learning model you created for Alphabet Soup.

The report should contain the following:

#### Overview of the analysis: Explain the purpose of this analysis.

The goal of this analysis is to create a deep learning binary classifier that predicts the success rate of funding applicants for Alphabet Soup, a nonprofit organization. The dataset provided contains information on over 34,000 organizations, including application details, industry affiliations, government classification, funding use cases, income classification, funding amount requested, and fund utilization.

The analysis involves preprocessing the data by removing unnecessary columns, encoding categorical variables, and splitting the dataset into training and testing sets. A neural network model is then designed, trained, and evaluated for its loss and accuracy. Optimization techniques such as adjusting input data, modifying network architecture, activation functions, and training epochs are applied to improve the model's performance.

The ultimate objective is to achieve a predictive accuracy higher than 75%. Once optimized, the model is saved as an HDF5 file for future use.

#### Results: 

##### Data Preprocessing

* What variable(s) are the target(s) for your model?
  
  The target variable for the model is IS_SUCCESSFUL, displaying whether a charity donation was successful or not.

* What variable(s) are the features for your model?
  
  The feature variables for the model are the rest of the columns in the DataFrame, excluding IS_SUCCESSFUL
  
* What variable(s) should be removed from the input data because they are neither targets nor features
  
  I believe that EIN (Employee Identification Number) does not contain relevant information for our predictive model, hence left out this variable from the feature and target selection. 
  
Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why? 

For this neural network model, I chose four hidden layers with 40,80, 40, and 5 neurons respectively. After several iterations and tests with different numbers of neurons and layers, this combination produced the best results in terms of accuracy and loss. For the activation functions, I chose ReLU for the first hidden layer to introduce non-linearity in the model and improve its performance. I selected sigmoid for the second, tanh for the third and soft-max for the fourth to increase accuracy of the model. For the final output layer, I used sigmoid activation function to ensure the output is between 0 and 1, which is needed for binary classification.

<img width="945" alt="Screenshot 2023-07-19 at 1 58 21 AM" src="https://github.com/svafaeva93/deep-learning-challenge/assets/124627601/53fb01f2-d55c-4e77-906f-3d0579a6fc57">

Were you able to achieve the target model performance?

Yes, I was able to develop a successful deep neural network model using TensorFlow and Keras to predict if an Alphabet Soup-funded organization would be successful. Through several iterations for the optimal model, I was able to achieve a predictive accuracy higher than 75%, with a final accuracy score of 78.12%. This model could be a valuable tool for Alphabet Soup in selecting the applicants with the best chance of success in their ventures.

<img width="578" alt="Screenshot 2023-07-19 at 2 01 39 AM" src="https://github.com/svafaeva93/deep-learning-challenge/assets/124627601/3884e18f-287d-4069-8273-6e1df1c0c304">

What steps did you take in your attempts to increase model performance?

During the optimization process, the EIN column was dropped as it was not relevant. However, keeping the NAME column improved model accuracy. To refine the data, a cutoff value was chosen, and names occurring less than 10 times were replaced with "Other". A similar approach was applied to the CLASSIFICATION column, where categories with fewer than 1000 occurrences were replaced with "Other". The resulting binning was verified for accuracy.

<img width="590" alt="Screenshot 2023-07-19 at 2 04 23 AM" src="https://github.com/svafaeva93/deep-learning-challenge/assets/124627601/e91be88a-ec22-4c1b-b4d5-05c8f9ddd438">

<img width="624" alt="Screenshot 2023-07-19 at 2 05 17 AM" src="https://github.com/svafaeva93/deep-learning-challenge/assets/124627601/4ce93314-69cf-4027-8f6a-951f6d3c5873">

### Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

The deep learning model using TensorFlow and Keras achieved a 78% predictive accuracy in classifying the success of Alphabet Soup-funded organizations. The model underwent various optimization attempts, including column dropping, categorical variable binning, and adjusting layers and activation functions. While the target accuracy of 75% was eventually reached, it required significant optimization efforts.

To improve classification, alternative models like Random Forest Classifier or Support Vector Machine (SVM) can be explored. These models handle both numerical and categorical variables, outliers, and imbalanced datasets effectively. Considering these alternatives may offer a potential solution to enhance classification performance.

### Step 5: Copy Files Into Your Repository
Now that you're finished with your analysis in Google Colab, you need to get your files into your repository for final submission.

