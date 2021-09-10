# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  Capstone Project: Acne detection using Convolutional Neural Network 
---

## Problem Statement
Our company are launching new specialised product line to target the acne skin consumers in addition to the normal skin product in the market. The management decided to enhance the shopping experience by having a system to detect acne using consumer's image. Our task as a data science team is to build a Convolutional Neural Network (CNN) model and make predictions to determine the skin type - Acne or non-acne with photos. 

The dataset contains a total of 2156 images. Out of which, 1010 images are acne while 1150 images are non-acne. The dataset are then divided into 60-20-20 for train, validation and test respectively. 
The directory are organised as follows:

|Folder|Variable Type |No of images|
|---|---|---|
|Train|Non-Acne|690|
|Train|Acne|610|
|Validation|Non-Acne|230|
|Validation|Acne|200|
|Test|Non-Acne|230|
|Test|Acne|200|

The model will then be evaluated based on accuracy and recall score. The objective of the model is to get a high accuracy and f1 score.

## Executive Summary
The general workflow for this project as shown below:
+ Data Collection and Pre-processing
+ Exploratory data analysis (EDA)
+ Modelling and evaluation
+ Conclusion and recommendation
+ Limitation and future development

## Modelling and evaluation
|Dataset|Accuracy| F1 score |True Positives|False Positive|True Negatives|False Negatives|
|---|---|---|---|---|---|---|
|Train|0.99| 0.99 |686|4|606|4|
|Validation|0.97| 0.98 |225|5|195|6|
|Test|0.98| 0.98 |228|2|192|8|


The metrics on the training set is to observe how well the model progress in terms of its training while metrics on the validation set is a measure of the quality of the model and its ability to make new predictions for unseen data. 

Initally, the training loss is higher because it was artificially made harder for the model to give the right answers by introducing data augmentation to the train data. However, during validation all of the units are available, so the network has its full computational power - and thus it might perform better than in training. Towards the end of the training, the accuracy of the train and validation becomes similar, the difference between the losses became similar too. 

As the dropout is set at 50%, some information about each image is lost due to disabling neurons and the subsequent layers attempt to construct predictions basing on incomplete representations. This resulted a fluctuation of losse shown in the graph. 

In conclusion, the model has an accuracy of 99% on the training set and 97% on the validation set. This means that the model can perform with ~97% on new data. 

## Conclusion and Recommendation
The model has an accuracy of 97% on validation data and 98% on test data while the f1 score for validation data and test data are 98%. The model has a train score of 99% for both accuracy and f1 score. There is no overfitting issue for the model as the dropout rate of 50% was introduced in the CNN model. 

Haar cascade was used in the preprocessing of the image data to crop out faces from the images. It was observed that some of the image failed to detect the faces, hence the model was training with both the faces and background as the noise. It was recommended to use other deep learning model for face detection in the pre-processing stage to improve the quality of model. 

As for the dataset, there is an imbalance data on the skin tones in the dataset as there is lesser dark skin tone in the dataset. The study from University of California San Francisco [[source]](https://www.ucsf.edu/news/2016/06/403401/darker-skin-stronger-skin-says-new-view-human-skin-color#:~:text=%E2%80%9CWork%20in%20our%20lab%20has,%2C%20MD%2C%20professor%20of%20dermatology) suggests that dark skin have a stronger skin barrier, hencce this may suggest why there are lesser acne dark skin photo found. This is the limitation of the model. Alternatively, we are proposed to increase synthetic data for dark skin in order to make up for the imbalance dataset. 

In conclusion, the model has high accuracy and f1 score however, it is not able to work well with darker skin tone which can be further improve. 

## Limitation and future work
The limitation of the model are : 
1. Face detection
2. Dark skin tone

In order to overcome the limitation, we suggest to include the following work for future development: 
1. Face detection can be improved by using MTCNN library
2. Increase darker skin tone image
3. SMOTE  
4. Collection more images

With the proposed future plan, the model will then be deployed using Flask. 


