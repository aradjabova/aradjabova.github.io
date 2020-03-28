---
layout: post
title:      "Multi-Class Classification - power of bins"
date:       2020-03-28 01:34:58 +0000
permalink:  multi-class_classification_-_power_of_bins
---


Classification models are supervised learning machine learning that make predictions based on the training data values that are inputed into the model  We use many different classification models, such as Random Forest, AdaBoost, GradientBoost, XGBoost and etc. Each is a different way of taking the inputed values from the data to find the class from that data by training the models. 

Classification models that have less classes to identify (with good data) have a better chance of finding the correct classes than a classification model with many classes to find.  So in order to build the best models, for multi-class classification models we bin the class into smaller targets for the model to be able to predict.  
In the Chicago car crash dataset, there are more than 40 targets when creating a model to predict the primary contributor of the car crash. When the model has so many targets to predict, not only is it computationally expensive, it is not as accurate. In order of reduce the number of classes in the Chicago car crash dataset, we can separate them into 3 different classes: sober, influenced(drug/alcohol), environment. The accuracy of the models skyrockets because of the decrease in the amount of classes the models need to predict.

<image src="https://journals.plos.org/plosone/article/file?id=10.1371/journal.pone.0196836.g006&type=large" width=800>

Bins are a powerful tool that is often overlooked especially while building a classification model. Multi-class classification models are built in order to predict multiple (more than 2) classes. An essential part to ensure the best model is created is to make sure that there are not class imbalances (meaning the number of each class is very different), to remedy this we can use SMOTE. SMOTE will return a subset of the data where the classes are balanced. When the classes are balanced the models can be trained to identify the classes accurately.


