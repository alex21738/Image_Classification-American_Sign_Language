# Chocolate-lab

## Outline

- Dataset Introduction

- EDA

- Model

- CNN

- Insights

- Further exploration

## Project Goal

The goal for this project is to categorize giving American sign languages correctly to their matching English letters.

## Data Collection

The data was collected from Kaggle, originally uploaded by Kaggle account tecperson 2018. The data is composed by training csv with shape (27455, 785) and testing csv with shape (7172, 785). All are pixel values that gerenate 28x28 images.

## EDA

The graphic below shows distributions of letters in training set.
![Distributions_of_letters_in_training_set.png](Distributions_of_letters_in_training_set.png)

The graphic below shows distributions of letters in test set.
![Distributions_of_letters_in_test_set.png](Distributions_of_letters_in_test_set.png)

The graphic below is an example image transfered from training set csv.

![example_image.png](example_image.png)

## Data Prepping

- Create labels for both training set and testing set.

- Turn both training set and testing set into matrix(reshape), flatten, and standardize(devide by 255).

- Train validate split for training set.

- Set number of classes to 25 (26 letters - 2(no J,Z) +1(label))

- Trun train_label, validate_label into single row matrixes.

## MLP

### Sigmoid

- Acc: 0.29, Epochs = 15

![acc_sigmoid.png](acc_sigmoid.png)

