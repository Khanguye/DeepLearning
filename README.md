# Deep Learning

**Summary**
---
Alphabet Soup data more than 34,000 organizations that have received various amounts of funding from Alphabet Soup over the years.
Within this dataset are a number of columns that capture metadata about each organization such as the following:

1. EIN and NAME—Identification columns
2. APPLICATION_TYPE—Alphabet Soup application type
3. AFFILIATION—Affiliated sector of industry
4. CLASSIFICATION—Government organization classification
5. USE_CASE—Use case for funding
6. ORGANIZATION—Organization type
7. STATUS—Active status
8. INCOME_AMT—Income classification
9. SPECIAL_CONSIDERATIONS—Special consideration for application
10. ASK_AMT—Funding amount requested
11. IS_SUCCESSFUL—Was the money used effectively

Using machine learning and neural network model building build a binary classifier that is capable of predicting whether or not an applicant will be successful 
if funded by Alphabet Soup using the features collected in the provided dataset.

**Objectives**
---
1. Import, analyze, clean, and preprocess a “real-world” classification dataset.
2. Select, design, and train a binary classification model of your choosing.
3. Optimize model training and input data to achieve desired model performance.

**Sources**
---
1. [charity_data.csv](charity_data.csv)
2. [AlphabetSoupChallenge.ipynb](AlphabetSoupChallenge.ipynb)

**Conclusion**
---

Epoch 49/50
25724/25724 [==============================] - 3s 120us/sample - loss: 0.3731 - accuracy: 0.8216
Epoch 50/50
25724/25724 [==============================] - 3s 115us/sample - loss: 0.3726 - accuracy: 0.8214

Model: "sequential"

|Layer (type)      |           Output Shape    |          Param #  | 
|-                 |-                          |-                  |
|dense (Dense)     |           (None, 441)     |          389844   | 
|dense_1 (Dense)   |           (None, 220)     |          97240    | 
|dense_2 (Dense)   |           (None, 1)       |          221      | 

Total params: 487,305
Trainable params: 487,305
Non-trainable params: 0

Test Result:
8575/8575 - 1s - loss: 76.0066 - accuracy: 0.7931
Loss: 76.00658843941314, Accuracy: 0.7931195497512817

I used two hidden layers in this DeepLearning model. The first hidden layer have 441 neurons that equals a half number of input parameters and the second hidden layer is 220 that equals a quarter of input parameters. I used one layers at first and the number neurons equals to input parameters, the accuracy did not return good. Then I added the second layer the same first layers. The accuracy was improved, but the performance very bad. Finally, I tuned up and adjusted by calibrating the number neurons. The number 441 neurons in first layer and 220 neurons in second layer are the best result in both the accuracy and the performance.

My model ran in 50 Epoch. Both the loss error and the accuracy were improved over each Epoch during the training. I used the model to run the test data and the accuracy was 79.3%. This is almost 5% more than the target accuracy require. In order to get the high performance accuracy, I did some preprocesses for the dataset like bucking Orginization (NAME), CLASSIFICATION, and ASK_ATM. I also removed two columns (EIN, STATUS) data that not contributed any data analysis for the dataset.

This problem is a classification problem. I can use the Random Forest Machine Learning to solve this problem becuase the final dataset has 882 column (features) that can be broken down by the Random Forest and voting process in Machine Learning to give the best result.