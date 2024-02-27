# Deep Learning Challenge

## Overview of the Analysis: 
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. 
Using machine learning techniques and a [dataset](https://static.bc-edx.com/data/dl-1-2/m21/lms/starter/charity_data.csv) containing more than 34,000 organizations that were funded by Alphabet Soup, a binary classifier was created to predict whether applicants will be successful if funded by Alphabet Soup.


## Results:

Data Preprocessing:

- The variable `IS_SUCCESSFUL`, which indicates whether the money was used effectively, was the target of the model.
- The `EIN` and `NAME` variables were removed from the input data because they are neither targets nor features.
- The rest of the variables in the dataset were the features of the model, including: application type, affiliation, use case, organization, income amount, status, special considerations, and the ask amount.

Compiling, Training, and Evaluating the Model:

The original model included:
- Neurons: 30
- Layers: 2 hidden and 1 output 
- Activation functions: relu in hidden layer, sigmoid in output layer
- Performance: Loss: 0.597, Accuracy: 0.706

The optimized model included:
- Neurons: 110
- Layers: 2 hidden and 1 output 
- Activation functions: relu in 1st hidden layer, sigmoid in last 2 layers
- Performance: Loss: 0.552, Accuracy: 0.727
   - The target model performance required an accuracy level of at least 75%, which wasn't achieved after 3 attempts to optimize the model. 
    - In the optimized model, I added 80 more neurons to better fit the dimensionality of the data. 
    - I ended up keeping the same number of layers, after running the model with one more extra layer did not have any noteworthy effect on the model's preformance.
    - I changed the activation function of 2nd hidden layer to sigmoid, which also improved the model's performance.
    - I increased the number of epochs from 50 to a 100.
    - I also lowered the cutoff data point for the rare bins in the `APPLICATION_TYPE` and the `CLASSIFICATION fields`. 
        - Interestingly, suppling the model with more complex data slightly improved its performance.
      - Below are images of the structure of the original and optimized model with their parameters.
      ![alt text](https://github.com/larabrry/deep-learning-challenge/blob/main/Images/original_model_parameters.png)
      ![alt text](https://github.com/larabrry/deep-learning-challenge/blob/main/Images/opmtimized_model_parameters.png)
   


## Summary:


- Overall,  I tried to increase the number of neurons and epochs, along with lowering the cutoff datapoint when binning the "rare" categorical variables to optimize the model. As a result, the optimized model performed with 72% accuracy which is slightly better than the 70% level of the original model. However, after multiple attempts, the goal of achieving an accuracy level of 75% and above was not met.
- Therefore, I would like to try a supervised learning model that utilizes the classification power of Support Vector Machines (SVMs) to solve this problem. SVMs might work well since the data has multiple features, and they might be able to better capture the relationship between all features. SVMs might also be able to handle the outliers of this dataset, like the ones in the `APPLICATION_TYPE` and the `CLASSIFICATION fields`. 