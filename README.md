# Neural_Network_Charity_Analysis

## Overview of the analysis: 
- Non-profit organization, Alphabet Soup, a philanthropic foundation dedicated to helping organizations that protect the environment, improve people’s well-being and unify the world. Alphabet Soup has raised and donated over 10 billion dollars over the past 20 years. This money has been used in lifesaving technoligies andn organize reforcestation groups around the world. Beck is in charge of data collection and analysis of the entire organization. Her job is to analyze the impact of each donation and vet petential recipients. This helps enure that the foundation’s money is being used effectively. Not every donation the comany makes is impactful. Some organziation will take the money and disappear. The presidient ask Beck to evaluate which company is worth donating to and which are too high risk. He wants a mathmatical data driven solution that can do this accurately. This problem is too complex for the statistical and machine learning models, but a well-designed and trainied deep learning neural network will be a better suit. 

- In this project, we will use Machine Learning, Neural Networks and , to evaluate the successfulness of a charity campaign . We have a list of organization's names and information. Each organization is asked for a donation of different amount. We processed the data first by deleting useless columns, like name and EIN No. of the organziations. We used Python TensorFlow library to evaluate all types of input data and produce a clear desciion making result. When we followed the default steps to process the data, we get 72% correct rate in testing data. We optimized the code in three ways and finally get 75.1% accuracy in the 3rd attempt.

## Results: 


## 1. Data Preprocessing
    - What variable(s) are considered the target(s) for your model?
    'IS_SUCCESSFUL' column

    - What variable(s) are considered to be the features for your model?
    Every other columns except for 'IS_SUCCESSFUL' column

    - What variable(s) are neither targets nor features, and should be removed from the input data?
    -Column 'EIN' and column 'Name'

## 2. Compiling, Training, and Evaluating the Model
### How many neurons, layers, and activation functions did you select for your neural network model, and why?
    
When we dropped the EIN and Name columns, and use OneHotEncoder to process the data, we have 43 features for each item. So we chose about 2 times of the features for the unit number. Therefore, as the screenshot shows below, the input layer has 80 units and the hidden layer has 30 units.

![00](Images/D2.png)


### Were you able to achieve the target model performance?
![001](Images/Deliverable_2.png)

### What steps did you take to try and increase model performance?
- We tried several attempts to increase the accuracy number. The first two attempts were focus on increase or decrease the neurons and layers of the machine learning model. Although we did see an increase the accuracy number of the final testing data, the amount is tiny.

- In the 3rd attempt, we went back to the data processing step. We first deleted one more column 'STATUS' because only 5 out of 30000+ in 'STATUS' is '0', the rest are all '1'. But this change didnt' increase the accuracy number of our test result at all. It actually decreased the accuracy. 

- Therefore, we changed our mind from deleting more columns to adding back columns to add more parameters. This time, we added back the 'NAME' column and reduced the unique values of 'NAME' from 19568 to 30. This increased our total input parameters from 44 to 74, which correspondingly increased the unit number in each layer of the machine learning model. 


#### Attempt 1: Increase units number in each layers

![010](Images/Attempt1_addmoreneurons.png)

![01](Images/Attempt1_result.png)


#### Attempt 2: Delete the 2nd Hidden layer and keep only one hidden layer

![020](Images/attempt_2.png)

![02](Images/attempt2_result.png)


#### Attempt 3:

![03a](Images/3rdAttempt-Name.png)

![03b](Images/3rdAttempt-ParaNo.png)

![03c](Images/3rdAttempt_result.png)


## Summary: 

- The final attempt successfully increased the testing accuracy to 75.1%, which hit our target of over 75% accuracy rate. However, the data processing progress was very manual and time-consuming. We bucketed the amount of unique values for the catergory column 'NAME' several times, from 10 to 30, and finally got over 75% accuracy when we tried 30 unique values in 'NAME' and replaced everything else with "Others".

Considering the steps and the amount of manual work to increase the accuracy in this deep learning model, we recommend that some other models might also be able to provide a similar accuracy with fewer steps and less data processing, like random forest classifer and other decision tree models.