# Image Classification -- American Sign Language

## Outline

- Dataset Introduction

- EDA

- Model

- CNN

- Insights

- Further Exploration

## Project Goal

The goal of this project is to correctly predict a letter from the American Sign Language alphabet from an image of a hand gesture. This includes all letters expect for 'J' and 'Z' becasue those signs require movement. 

## Data Collection

The data was collected from Kaggle, originally uploaded by Kaggle account tecperson 2018 (https://www.kaggle.com/datamunge/sign-language-mnist). The data is in CSV files and each row represents one image and each colomn represents the grey scale for a single pixel of that image. Turning each row into a matrix we can generate images size 28X28. The files are already split into training and test sets. The training set contains 27455 images and the testing set has 7172 images. 

## EDA

The graphic below shows distributions of letters in the training set.
![Distributions_of_letters_in_training_set.png](Pictures/Distributions_of_letters_in_training_set.png)

The graphic below shows distributions of letters in the test set.
![Distributions_of_letters_in_test_set.png](Pictures/Distributions_of_letters_in_test_set.png)

The graphic below is an example image transfered from training set csv.

![example_image.png](Pictures/example_image.png)

## Data Prepping

- Create labels for both training set and testing set.

- Turn both training set and testing set into matrix(reshape), flatten, and standardize(divide by 255).

- Split the training set into training set and validating set.

- Set number of classes to 25 (26 letters - 2(no J,Z) +1(label))

- Trun train_label, validate_label into single row matrixes.

## MLP

### Sigmoid

- Test set Accuracy: 0.29, Epochs = 15

![acc_sigmoid.png](Pictures/acc_sigmoid.png)

### Softmax

- Test set Accuracy: 0.59, Epochs = 15

![acc_softmax.png](Pictures/acc_softmax.png)

### Hypertuned Softmax

- Test set Accuracy: 0.63, Epochs = 15

![acc_hypertuned_softmax.png](Pictures/acc_hypertuned_softmax.png)

## CNN 2D

- Adopt 3 different layers of convolution 2D and Maxpooling 2D

- Dropout 10% of observations

- Save model for future usage

- Test set accuracy: 0.81, Epochs: 18

![acc_cnn.png](Pictures/acc_cnn.png)

## Extracting Feature Map

- Extract model layer outputs

- Create a model for displaying the feature maps

- Extract Layer Names for Labelling

- Post-process the feature to make it visually palatable
 
 The graphics below show the transformation of Conv2D --> Max Pooling2D for each 3 layers.
 
 - Layer 1:
 
 ![Conv2D_1.png](Pictures/Conv2D_1.png)
 ![Max_Pooling2D_1.png](Pictures/Max_Pooling2D_1.png)
 
 - Layer 2:
 
 ![Conv2D_2.png](Pictures/Conv2D_2.png)
 ![Max_Pooling2D_2.png](Pictures/Max_Pooling2D_2.png)
 
 - Layer 3:
 
 ![Conv2D_3.png](Pictures/Conv2D_3.png)
 ![Max_Pooling2D_3.png](Pictures/Max_Pooling2D_3.png)
 
 ## Confusion Matrix
 
 - Create a 24X24 confusion matrix for each letter.
 
 - Calculate False Nagative error % to get top letters most misclassified to other letters.
 
 - Calculate False Positive error % to get top letters most misclassified by other letters.
 
 The graphic below shows the confusion matrix.
 ![confusion_matrix.png](Pictures/confusion_matrix.png)
 
 ## Insightful Analysis
 
 - 'R', 'T', and 'V' were the most miss predicted
 - Other signs were incorrectly predicted as 'U' and 'T' most often
 ![amer_sign2.png](Pictures/amer_sign2.png)
 
 ## Further Exploration
 
- Use larger pictures 

- Adopt heat maps to show activation features on an image

- Implement pre-trained data to increase our accuracy

- Involve data augmentation to see if we can increase our accuracy

 ## Powerpoint Link
 
 - https://docs.google.com/presentation/d/1g4U47n2K-JUqWbb6WHiNGrnX8CKCCoSTPpEsJ8coptc/edit?usp=sharing
