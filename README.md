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

## Part 2 - Normalization Techniques

### 1. Batch Normalization

![image](https://user-images.githubusercontent.com/120099863/214893917-a54d8629-f420-4206-9606-f3326121beca.png)

This normalization works per channel. For each channel in the layer mean & variance is calculated and values are normalized.

In image (shown above) for layer N, it will have 4 mean values and 4 variance values for each channel. All yellow, red, orange & green parts of Layer 1 will get accumulated as per colour and mean/variance will be calculated.

Image below shows how mean is calculated for channel:

![image](https://user-images.githubusercontent.com/120099863/214910909-1bc89b4a-9cd3-4b7b-a586-7c1b777e9973.png)

### 2. Layer Normalization

![image](https://user-images.githubusercontent.com/120099863/214896159-9421d9f5-2d65-4fd5-afef-ea0135f619dd.png)

This normalization works per image (batch size). For each image in batch mean & variance will be calculated per layer. All channel values for that image are accumulated to calculate mean & variance.

For image 1 calculation will cover all of these fields:

![image](https://user-images.githubusercontent.com/120099863/214896794-38ccc8be-89cf-4531-9fbc-ab4c179eaf58.png)

### 3. Group Normalization

![image](https://user-images.githubusercontent.com/120099863/214897217-78a3fb1f-2fd5-4f2e-9e6c-901762e09a54.png)

This normalization works per image (batch size) but channels are split as required for the number of groups. For each image in batch mean & variance will be calculated by grouping channels (based on group number) per layer. All channel values for that image are accumulated as per their group to calculate mean & variance.

For image 1 calculation will cover all of these fields (2 group example):

![image](https://user-images.githubusercontent.com/120099863/214898927-fa1e8711-3e1d-41ab-a5ca-593897c1559f.png)

## Part 3 - Findings for Normalization Techiniques

* Acurracy for Training & Testing for all 3 are as follows:

![image](https://user-images.githubusercontent.com/120099863/214904720-0bb692c2-10fd-44d6-90bf-64c2600e0726.png)

* Batch Normalization + L1 is giving best test accuracy. Layer Normalization is close to batch normalization but Group Normalization is not giving good results.
* LN has more training accuracy and less test accuracy than BN+L1. Thus implying BN+L1 is working better in this scenario as it has more scope for improvement.
* Training loss for BN+L1 is quite high compared to other two normalizations
* Test loss is maximum for GN, followed by LN & lowest for BN+L1

## Part 4 - Graphs

Graphs showing Training/Test Loss/Accuracies:

![image](https://user-images.githubusercontent.com/120099863/214904574-f7498987-4d3a-41df-8a77-b1da248b570b.png)

## Part 5 - Misclassified Images

### Batch Normalization and L1

![image](https://user-images.githubusercontent.com/120099863/214909626-77f5b491-92d5-4037-a1c7-b75d4d7b506c.png)

### Layer Normalization

![image](https://user-images.githubusercontent.com/120099863/214909777-099c12b6-b6cd-4e54-a31e-ccc515b35211.png)

### Group Normalization

![image](https://user-images.githubusercontent.com/120099863/214909921-bee741c6-b60a-45f4-a3d8-69c6c2d85bfb.png)







