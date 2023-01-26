# Assignment-5

## Problem Statement

<img src="https://user-images.githubusercontent.com/120099863/214882850-b39d3b33-d282-4a11-8f07-33def24a9fcd.png" width=60% height=60%>

## Part 1 - Code Details

Code is divided in two files:
1. model.py [model](model.py): It contains a model class that can adjust normalization as received in instantiation.
2. EVA8_Assigment_5.ipynb [notebook](EVA8_Assigment_5.ipynb): It contains code for execution of normalization techniques.

model.py is imported in EVA8_Assigment_5.ipynb after uploading in google drive. It contains a class by name Net that takes a type of normalization layer as argument while instantiating it.

1. BN for Batch Normalization
2. LN for Layer Normalization 
3. GN for Group Normalization (two groups)

EVA8_Assigment_5.ipynb contains the main body of the code. It imports necessary libraries including the model, datasets and dataloaders.

* train() function is called by passing a model object and other parameters like value of Lambda. test() function is called simply by using a model object and test dataloader.
* display_incorrect_pred() function is used to print misclassified images for models. These images are shown in a 5x2 matrix for each model.
* Loss (training & testing) and Accuracy (training & testing) are printed for comparing performance of normalization techniques

## Part 2 - Normalizarion Techniques

### 1. Batch Normalization

![image](https://user-images.githubusercontent.com/120099863/214893917-a54d8629-f420-4206-9606-f3326121beca.png)

This normalization works per channel. For each channel in the layer mean & variance is calculated and values are normalized.

In image (shown above) for layer N, it will have 4 mean values and 4 variance values for each channel. All yellow, red, orange & green parts of Layer 1 will get accumulated as per colour and mean/variance will be calculated.

### 2. Layer Normalization

![image](https://user-images.githubusercontent.com/120099863/214896159-9421d9f5-2d65-4fd5-afef-ea0135f619dd.png)

This normalization works per image (batch size). For each image in batch mean & variance will be calculated. All channel values for that iamge are accumulated to calculate mean & variance. 

For image 1 calculation will cover all of these fields:

![image](https://user-images.githubusercontent.com/120099863/214896794-38ccc8be-89cf-4531-9fbc-ab4c179eaf58.png)







