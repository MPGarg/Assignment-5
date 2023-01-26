# Assignment-5

## Problem Statement

<img src="https://user-images.githubusercontent.com/120099863/214882850-b39d3b33-d282-4a11-8f07-33def24a9fcd.png" width=60% height=60%>

## Part 1 - Code Details

Code is divided in two files:
1. model.py [model](model.py): It contains model class that can adjust normalization as received in instantiation.
2. EVA8_Assigment_5.ipynb [notebook](EVA8_Assigment_5.ipynb): It contains code for execution of normalization techniques.

model.py is imported in EVA8_Assigment_5.ipynb after uploading in google drive. It contains class by name Net that takes type of normalization layer as argument while instantiating it.

1. BN for Batch Normalization
2. LN for Layer Normalization 
3. GN for Group Normalization (two groups)

EVA8_Assigment_5.ipynb contains main body of the code. It imports necessary libraries including model, datasets and dataloaders.

* train() function is called by passing model object and other parameters like value of Lambda. test() function is called simply by using model object and test dataloader.
* display_incorrect_pred() function is used to print misclassified images for model. These images are shown in 5x2 matrix for each of model.
* Loss (training & testing) and Accuracy (training & testing) are printed for comparing performance of normalization techniques

## Part 2 - Normalizarion Techniques

### 1. Batch Normalization

![image](https://user-images.githubusercontent.com/120099863/214893917-a54d8629-f420-4206-9606-f3326121beca.png)






