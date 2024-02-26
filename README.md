# Deep Learning Challenge

## Overview of the Analysis: 
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. 
Using machine learning techniques and a CSV containing more than 34,000 organizations that were funded by Alphabet Soup, a binary classifier was created to predict whether applicants will be successful if funded by Alphabet Soup.


## Results: Using bulleted lists and images to support your answers, address the following questions:

Data Preprocessing:

- The variable 'IS_SUCCESSFUL', which indicates whether the money was used effectively, was the target of the model.
- The 'EIN' and 'NAME' variables were removed from the input data because they are neither targets nor features.
- The rest of the variables in the dataset were the features of the model, including: application type, affiliation, use case, organization, income amount, status, special considerations, and the ask amount.

Compiling, Training, and Evaluating the Model:
The original model included:
- neurons: 30
- layers: 2 hidden and 1 output 
- activation functions: relu in hidden layer, sigmoid in output layer
- preformance: Loss: 0.597, Accuracy: 0.706

The optimized model included:
- neurons: 110
- layers: 2 hidden and 1 output 
- activation functions: relu in 1st hidden layer, sigmoid in last 2 layers
- preformance: Loss: 0.552, Accuracy: 0.727

The target model performance required an accuracy level of at least 75%, which wasn't achieved after 3 attempts
to optimize the model. 
In the optimized model, I added 80 more neurons to better fit the dimensionality of the data. 
I ended up keeping the same number of layers, after running the model with one more extra layer did not have any
noteworthy effect on the model's preformance.
I changed the activation function of 2nd hidden layer to sigmoid, which also improved the model's preformance.
I lowered the cutoff data point for the rare bins in the APPLICATION_TYPE and the CLASSIFICATION fields. 
    Interestingly, suppling the model with more complex data slightly improved its preformance.
Finally, I increased the number of epochs from 50 to a 100.




How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take in your attempts to increase model performance?

## Summary:


 Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.