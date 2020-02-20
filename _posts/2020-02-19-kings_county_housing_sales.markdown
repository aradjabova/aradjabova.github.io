---
layout: post
title:      "Kings County Housing Sales"
date:       2020-02-20 01:12:59 +0000
permalink:  kings_county_housing_sales
---


For this analysis, we were asked to work with the  King County House Sales dataset.

Using the OSEMN methodology to complete this analysis and create a model regression of the data to predict the price of the houses 

While cleaning the data, there were many obstacles and choices. There were 2 columns/features that had missing data; ultimately it was my choice to not use those features as I thought it would impact my results or I would have fewer data. Another column had a few placeholders (‘?’) that would impact my data. The column of square foot basement had those place holders; to combat that I had to change those placeholders to zero. I believe if they are unsure of if/how big the basement is, it is safer to assume that they do not have one. After some more thorough cleaning, my data was ready for me to explore and create questions to look into.
![missing_bar.png](attachment:missing_bar.png)

A great way of visualizing the columns' relationships with one another was the use of the scatter matrix and the heat map. As you can see the scatter matrix plots each column value against the corresponding column value. Using this, we can see points plotted between columns and in the diagonal of the matrix we can see a histogram of each column. The scatter plots are a great way to visualize the different types of data and easy way of determining if the data is categorical (point are all vertical) or continuous (scattered/or linear/etc). The histograms are a great way of quickly checking the normality of the values. As you can see, most of the data is semi-normal, most of the data is only skewed with a high kurtosis on one side. Also, the histogram shows the categorical columns very distinctly; as well as shows the distinct not normal features in the data
![download.png](attachment:download.png)


The heat map is an amazing tool to use when looking for a correlation between different features. As shown below, we have the absolute correlation of all the features in our data. This is a wonderful tool to see which features have the best correlation between each other and against the price (which is what will be trying to predict).

![download%20%281%29.png](attachment:download%20%281%29.png)


After exploring and visualizing our data, I can start to purpose different questions about what features can be used to predict the price. While exploring, the use of categorical data, such as; the number of bedrooms,  grade, condition, seems to have a great indication of price. Also, continuous columns such as square foot living/ living15/lot/above/basement also have some degree of impact on the price.

This is an example of our grade columns vs the price. As you can see, the categorical data is displayed by the individual values in the column. The top grades 9 -12 have a higher ability in predicting the price of the house.
![grade_tran_box.png](attachment:grade_tran_box.png)

This graph shows the continuous column/feature of the square foot above (which is the square footage of the house not including the basement). This shows how there is some kind of linear relationship between the bigger the house the higher the price of it.
![trans_cor_price_sqftliving.png](attachment:trans_cor_price_sqftliving.png)

One of the models that I created using the square foot of the house aside from the basement and the square footage of the basement. Below are the results of the model:

The model below shows that there is an 89% predictability between these two columns. The coefficients show that there is not much difference between the best fit coefficient. The model also shows that the residuals are not that much skewed of 0.156 which is closer to normal and kurtosis of 2.950 (normal distributions have a 3). A huge assumption of multi-linear regression is not to have multicollinearity. The condition number indicates the low probability of the regression model having multicollinearity.
![Q3%20model.png](attachment:Q3%20model.png)


Multicollinearity is the ability of one feature to predict another. For example, if the square footage of the house would go up, then the square footage of the basement would go up. This could influence the results of the regression model predictability. That is not the case with these features, below is a scatter plot of the square footage of the house against the square footage of the basement with a hue of the prices. As you can see, as the space of the house goes up there is no indication that the space of the basement goes up as well. 
![Q3%20no%20multi%20above%20base.png](attachment:Q3%20no%20multi%20above%20base.png)


Another assumption of linear regression is the normality of the residuals. Below is a graph of the distribution of residuals of the model. As you can see, the residuals look fairly normal.
![Q3%20distribution.png](attachment:Q3%20distribution.png)

The below graph tests for the homoscedasticity, which is the third assumption of linear regression models. This means that the dependent variable (price) variability is equal across values of the independent variables (the features). The best way to test this is to plot them on a scatter plot. If the scatter plot is a cone shape then the regression is heteroscedasticity, else the scatter plot will be horizontal. As you can see the graph shows that I have met the assumption.
![Q3%20residuals.png](attachment:Q3%20residuals.png)

Below is another graph created to check for the normality of the residuals against the normal distribution line. As you can see most of our predicted values are on the line, with a few exceptions
![Q3%20qqplot.png](attachment:Q3%20qqplot.png)


This project was a tough challenge, but with the continuous process of cleaning and exploring the data, there becomes clear paths to choose, question and further explore. When creating the linear regression models, a big part of it is checking that the models meet all the mandatory assumptions.






