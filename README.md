# Project4_DataSalaries
## Overview - Predicting Salaries in the Data Field
The goal of this project is to predict the salaries of individuals entering the data field using machine learning techniques. The dataset used in this project, sourced from ai-jobs.net, contains comprehensive information about individuals working in the data domain, including their experience level, employment type, job title, salary, location, and company size. With over 13,000 rows of data, this dataset offers a rich source of insights into salary trends in the data field.

## Results - 
* Data Preprocessing
  * List things we updated : The target variable selected for the model is the salary. We attempted to do this using both the 'salary_in_usd' column and a created 'salary_binned' column. When we created the salary_binned column, the bins are as followes:
    * Bin 1: 40000.0 - 132000.0
    * Bin 2: 132000.0 - 224000.0
    * Bin 3: 224000.0 - 316000.0
    * Bin 4: 316000.0 - 408000.0
    * Bin 5: 408000.0 - 500000.0
  * List more things : The features chosen for the model include all columns from the dataset except for the IS_SUCCESSFUL column which include:  APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT. These features provide valuable information that the model will utilize to make predictions
  * List more things: Several variables were identified for removal from the input data as they are neither targets nor features. These variables include the EIN and NAME columns, which are identifiers with no predictive value. Additionally, preprocessing steps were applied to the APPLICATION_TYPE and CLASSIFICATION columns. For APPLICATION_TYPE, values with frequencies below 500 were grouped into an 'OTHER' category to reduce dimensionality and improve model performance. Similarly, for CLASSIFICATION, categories with frequencies under 1800 were aggregated into an 'other' category to enhance the model's predictive capabilities.
* Compiling, Training, and Evaluating the Original Model
  * How many neurons, layers, and activation functions did you select for your neural network model, and why?
   * UPDATE Number of Neurons: The first hidden layer (layer_1) contains 80 neurons, and the second hidden layer (layer_2) contains 30 neurons.
   * UPDATE Number of Layers: The model consists of two hidden layers and one output layer, resulting in a total of three layers.
   * UPDATE Activation Functions: Both hidden layers utilize the ReLU (Rectified Linear Unit) activation function, while the output layer employs the sigmoid activation function.
* Were you able to achieve the target model performance?
  * UPDATE THIS No, I was not able to achieve the target model performance of over 75% accuracy. Despite making several optimization attempts, the model's accuracy remained below the desired threshold. My best-performing model achieved an accuracy of approximately 72%, still short of the target. The optimization attempts yielded the following results: Optimization 1 - Loss: 0.574, Accuracy: 0.721. Optimization 2 - Loss: 0.572, Accuracy: 0.720. Optimization 3 - Loss: 0.582, Accuracy: 0.719. While the models showed improvement during optimization, they still did not reach the desired level of accuracy. Further analysis and experimentation may be required to identify additional strategies for enhancing model performance.
* What steps did you take in your attempts to increase model performance?
  * UPDATE THIS In attempts to enhance model performance, I made several modifications. Initially, I refined the dataset by removing additional columns ('USE_CASE', 'STATUS', 'SPECIAL_CONSIDERATIONS') and adjusted the cutoff values for 'application_type' and 'classification'. In Optimization 1, I increased the units in the first and second hidden layers and updated the training epochs to 50. For Optimization 2, I introduced a third hidden layer and switched the optimizer to 'sgd'. In Optimization 3, I added a fourth layer with updated units and changed the activation functions of the third and fourth layers to 'ELU'. Additionally, I reverted the optimizer to 'adam' and extended the training epochs to 100.

## Summary 
UPDATE THIS The deep learning model showed moderate performance in classifying the dataset, achieving an accuracy of approximately 72%. While this accuracy indicates some success, it falls short of the desired 75%. Despite multiple optimization attempts, including adjustments to model architecture, dataset preprocessing, and training parameters, the desired accuracy level was not attained. To address this problem more effectively, I recommend exploring a boosting algorithm, such as XGBoost or LightGBM. Boosting algorithms are known to help the performance in handling tabular data classification tasks. They capture complex relationships in the data, handling categorical variables effectively, and mitigating overfitting through ensemble techniques. By leveraging the strengths of a boosting algorithms, we can potentially achieve higher classification accuracy and enhance predictive performance in this scenario.

### Reference 
The Global AI, ML, Data Science Salary Index for 2024. (2024, March). Retrieved from [https://ai-jobs.net/salaries/download/]
