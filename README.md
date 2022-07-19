# CNN_ImageClassification

### Image and Character Classification Using Convolutional Neural Nets and Supervised Learning

With supervised learning, it is possible to automate classification tasks that would usually take 
too much time and effort. In these 2 projects, supervised learning is used to classify handwritten 
letters and animal pictures data sets. Having the labeled set, I'm supervised pre-training a model 
to improve the necessary classification task. 

## Classifying Animals

The model with a deeper network is trained to fit the data. As a deep CNN is used to evaluate and fit the data in the exercise, it was expected to see better classification results which can be verified with validation and test accuracy.

![image](https://user-images.githubusercontent.com/64362304/179812678-aaf397f5-4974-44a6-bb41-b9484163e013.png)

When using the deeper exercise model, performance of training and test set were expected to improve. However, a degradation of training accuracy is observed. This degradation in final training accuracy can be explained by the introduction of dropout layers in the new model which drops out some of the neurons to train the network in small pieces to prevent overfitting. This may cause the training accuracy to decrease while contributing to actual test accuracy to be higher with minimal overfitting. This is a favorable outcome as we are more concerned about testing accuracy instead of training accuracy. Additionally, as the layers increase, there are much more parameters (Figure below) to be considered which may cause the training accuracy to decrease while contributing to the actual testing results positively.

![image](https://user-images.githubusercontent.com/64362304/179814460-b22da5a5-e024-4410-ab41-00f49edb7bd5.png)

## HCR_WordFormation

### Data & Model Description

The project includes 3 data sets. Data Set 1, consisting of 372.450 28x28 sized images 
in total, is divided in 1:4 ratio and used as Testing Set 1 and Training Set respectively. Data Set 
2 contains 1356 34x34 sized images with a different structure and handwriting than Data Set 1. 
This set includes curved, italic, and several upside-down characters which create an unexpected
challenge for the network. Data Set 3 includes 14300 FDA approved drug/medication names and serves
as a dictionary for the search algorithm used in this project. 3 different data sets were used and comparison for 2 cases was performed to understand the network performance and behavior towards familiar and unfamiliar testing data.

Training Set: 297,960 handwritten letter images 28W x 28H (80%) 

Testing Set 1: 74,490 handwritten letter images 28W x 28H (20%) 

Testing Set 2: 1356 handwritten letter images 34W x 34H 

Dictionary: 14300 FDA approved drug names

In this project model where the kernel is a 3x3 square matrix with a stride of 2 was used. Pooling layers to summarize the features extracted and flatten layer to resize the dimensions of the input into the channel dimensions to create a flattened output array were also included after each convolutional layer. Finally, dense layers were used to create fully connected layers so that every output in the network depends on every input. No dropout layers were used to keep the network and all features intact.

Network was built, and training was performed. Total parameters, trainable parameters and non-trainable parameters were reported. For the network, convolutional, pooling, flatten and dense layers were used with ReLu and Softmax activation functions. To overcome overfitting and improve the model, early stopping and reduce learning were introduced to the network.

For the first case scenario, model was trained and tested with data set 1. On the other hand, as the second case scenario, model was re-trained with data set 1 and tested with data set 2. For both cases, results, accuracy, and loss curves were reported. To achieve better prediction rate, different monitoring variables and patience values were tested. Epoch, patience and monitored values that performed the best is shown in Table 1 below.

![image](https://user-images.githubusercontent.com/64362304/179812424-e27b18da-51e3-4488-9c75-ad3c39c2cd42.png)


