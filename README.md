# Neural Network Charity Analysis
### Module 19: Neural Networks and Deep Learning Models

## Overview and Purpose 

The purpose of the project is to predict using different alterations of neural networks how successful and applicant to the charity company Alphabet Soup will be in their funding attempts. The data set is taken from Alphabet Soup’s business team, the data received is from a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

- EIN and NAME—Identification column
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively

### Tools and Resources

- Python
- Sickit-learn
- Tensorflow

## Results
Results on the performance of the deep learning model created for Alphabet Soup.

This project compromised of the following three steps:

- Preprocessing the data for the Neural Network
- Compile, Train and Evaluate the Model
- Optimizing the Model

Using a combination of these tools and resources to create a deep learning neural network. Helping us evaluate the data and make decision on the funding sources.

### Data Preprocessing

1. The variable that was considered the target for the model was the IS_SUCCESSFUL variable. This variable was the one used to determine if the campaign for Alphabet Soup was successful in raising funds or not. So, this is the logical target column for our model.
2. The variables that are not useful which are not considered either a target nor a feature is the EIN and NAME columns which are the title descriptions of the names of the charity selected. For the purpose of the deep learning model these are not useful because they have no values and therefore no impact on the result.
3. The variables that are considered features in the model are the remaining columns in the dataset, the remaining 40+ columns are all used as features to help the neural network come to a result for the target variable.

- The number of layers, neurons and activation functions were determined because trial and error were used to find the most relevant highest success mixture. But also, this number of neurons and layers is ideal to prevent the model from overfitting to this dataset.

### Compiling, Training, and Evaluating the Model

For the original version of the model the following parameters were used.

![Original Model](https://user-images.githubusercontent.com/88692025/149705460-8bc24cda-e69f-464f-947e-edcdf1229cc9.PNG)

- Two hidden node layers were used, first layer contained eighty neurons and the second layer contained 50 neurons.
- Total parameters and trainable parameters of 7.621
- The hidden layer utilized the Relu function
- The Output Later used the Sigmoid function
- The model was trained for one hundred epochs 

![Original Model Result](https://user-images.githubusercontent.com/88692025/149706038-9044091c-2657-474b-95dd-60079c24abe5.PNG)

The model had a performance accuracy of predicting the success of the campaign at 72.5%, the target model performance was slated at 75% or higher, the model was not able to achieve this accuracy level at this point, a few optimization attempts were made in order to get better results.

### Optimization Attempt #1
- Adjusting the input data to ensure that there are no variables or outliers that are causing confusion in the model, via Dropping more or fewer columns.
- Attempted this during data preprocessing, dropping a perceived unnecessary column to help optimize the model.

![Optimization Attempt 1](https://user-images.githubusercontent.com/88692025/149706286-47ef21dd-8125-49c6-bb08-56c973d4e4c4.PNG)

In this optimization attempt, the variable SPECIAL CONSIDERATIONS which was previously a feature variable was dropped because it is referring to whether or not the campaign had any special considerations which in my opinion does not have a huge impact on the success so I decided to drop the variable with the hopes that the overall model accuracy would increase marginally if not at 75% of above. The remainder of the model assumptions were same as the original and remained constant and unchanged.

![Optimization Result 1](https://user-images.githubusercontent.com/88692025/149706491-32b82978-6f86-4347-a858-bafa5afa19d4.PNG)

The Optimization attempt decreased the model accuracy by 0.1% from the original at 72.4% instead of 72.5%. This means the special considerations variable is relevant and determines that a slightly higher accuracy model is attained with its inclusion.

### Optimization Attempt #2
- Adding more neurons to a hidden layer and adding more Epochs.
- Attempted this during training of the model, more neurons, and higher epochs.

![Optimization Attempt 2](https://user-images.githubusercontent.com/88692025/149706754-f23e6431-b6a3-4ca5-b33b-a9ca63a91710.PNG)

In this Optimization attempt, the hidden layer neurons were increased from 80 to 120 in the first layer and then from 50 to 90 in the second layer. The number of epochs the model was trained for increased from 100 to 200. The remainder of the model assumptions were same as the original and remained constant and unchanged.

![Optimization Result 2](https://user-images.githubusercontent.com/88692025/149706930-c6d2cfaf-a80a-428b-b7d0-c7b597005ad8.PNG)

The Optimization attempt did not have any change on the model accuracy and retained the same accuracy of 72.5%, this means that more neurons in the hidden layers and more epochs in training did not increase overall model accuracy.

### Optimization Attempt #3
- Using different activation functions for the hidden layers.
- Attempted this during compiling of the model, changed the activation functions.

![Optimization Attempt 3](https://user-images.githubusercontent.com/88692025/149707096-afe34528-c17b-4761-ab04-3b7fc2cf9bba.PNG)

In this Optimization attempt, the hidden layer activation functions were changed, instead of the first layer and the second layer both being Relu, the first layer was changed to Sigmoid to match the final output layer which was also Sigmoid, the second hidden later was kept with Relu. The remainder of the model assumptions were same as the original and remained constant and unchanged.

![Optimization Result 3](https://user-images.githubusercontent.com/88692025/149707239-58b92513-8ca7-414e-ada5-c6c9c63cf1c4.PNG)

The Optimization attempt decreased the model accuracy by 0.1% from the original at 72.4% instead of 72.5%. This means the sigmoid function change in the first layer contributed to slightly lower accuracy model.

## Summary

Overall, after a few attempts and increasing the model accuracy above 75%, the original model accuracy of 72.5% could not be beaten, and the target of above 75% could not be met. The optimizations, dropping unnecessary column, adding epochs/hidden layers, and changing the activation function all either matched or lowered the overall model accuracy and did not help it reach above 75%. 
The recommendation in order to get better results trial and error of several iterations and combinations is needed. Making sure all variations are tested of the model variables and activation, epoch, hidden layer mix. Another recommendation would be to try SVM or Random Forrest models to try to get something higher than 75%.
