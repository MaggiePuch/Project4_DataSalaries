# Project4_DataSalaries
## Overview - Predicting Salaries in the Data Field
The goal of this project is to predict the salaries of individuals entering the data field using machine learning techniques. The dataset used in this project, sourced from ai-jobs.net, contains comprehensive information about individuals working in the data domain, including their experience level, employment type, job title, salary, location, and company size. With over 13,000 rows of data, this dataset offers a rich source of insights into salary trends in the data field. Linked below is our website for our tableau visualizations. 

https://public.tableau.com/app/profile/kevin.shaw5642/viz/Project4Book_17102021417060/Story1?publish=yes 

## Results - 
* Data Preprocessing
  * The target variable selected for the model is the salary. We attempted to do this using both the 'salary_in_usd' column and a created 'salary_binned' column. When we created the salary_binned column, the bins are as followes:
    * Bin 1: 40000 - 132000
    * Bin 2: 132000 - 224000
    * Bin 3: 224000 - 316000
    * Bin 4: 316000 - 408000
    * Bin 5: 408000 - 500000
  * The features chosen for the model include the following columns:  experience_level, job_title, employee_residence and company_size.
  * Several variables were identified for removal from the input data as they are neither targets nor features. These variables include the 'salary_currency', 'company_location' and the extra 'salary' column as they were identified as having no predictive value. Preprocessing steps included dropping rows with 'work)year' > 2022, trimming the 'salary_in_usd' column to remove outliers, reallocating 'remote_ratio' workers that are 50 (hybred) to 100 (office), updating 'job_title' and 'employee_residence' so values with frequencies below 500 were grouped into an 'OTHER' category to reduce dimensionality and improve model performance
* Compiling, Training, and Evaluating the Original Model
   * Number of Neurons: The first hidden layer (layer_1) contains 128 neurons, and the second hidden layer (layer_2) contains 64 neurons.
   * Number of Layers: The model consists of two hidden layers and one output layer, resulting in a total of three layers.
   * Activation Functions: Both hidden layers utilize the ReLU (Rectified Linear Unit) activation function, while the output layer employs the softmax activation function.
* Were you able to achieve the 75% or greater on your model?
  * No, we were not able to achieve an accuracy over 75%. Despite making several optimization attempts, the model's accuracy remained below the desired threshold. Our first attempts achieved an accuracy of approximately 42%. The optimization attempts yielded the following results: Optimization 1 - Loss: , Accuracy: . Optimization 2 - Loss: , Accuracy: . Optimization 3 - Loss: , Accuracy: . While the models showed improvement over time, they still did not reach the desired level of accuracy. 
* What steps did you take in your attempts to increase model performance?
  * We atttempted to use multiple estimates , activation functions, and parameters with our machine learning models, as well as model optimizers.
  * We tried used multiple scalers on our data.
  * We modified the data to increase/decrease the number of columns used with the model.
  
    While we strived for increased performance with our modifications, the highest accuracy achieved was 60%. Which leads us to the conclusion that our dataset in it’s current state is unable to achieve the goal set out for our machine learning model.  

## Summary 
In conclusion, while our model provides a foundation for predicting salaries in the data industry, we recognize the need for additional data to enhance its accuracy and robustness. Despite the dataset's size, we believe that the model's accuracy could be significantly improved with more granular and comprehensive data, particularly from specific states or regions. We found that the lack of data diversity may have led to bias and limited the model's ability to generalize well to unseen data. Future efforts will focus on acquiring more data, especially from specific states or regions, to better capture the variability in salaries within the data industry. We remain optimistic that with a more extensive and diverse dataset, our model can achieve higher accuracy and better serve its intended purpose of assisting individuals in understanding and negotiating salaries in the data field.

### Reference 
The Global AI, ML, Data Science Salary Index for 2024. (2024, March). Retrieved from [https://ai-jobs.net/salaries/download/]
