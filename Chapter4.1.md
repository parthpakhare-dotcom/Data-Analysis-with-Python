# 🌑 Model Development

This module called as the `Model Development` teaches us about the following topics:  
1) Simple and Multiple Linear Regression  
2) Model Evaluation using visuslization  
3) Polynomial regression and Pipelines  
4) R-squared and MSE for In-sample Evaluation  
5) Prediction and Decision making

The question that we will be answering here is:  
 **How can you determine a fair value for a used car?**  
 
## Model:  
A model or an estimator can be thought of as a mathematical equation used to predict a value given one or multiple values are provided.  
Eg: consider the independent variable `engine-size` is provided. Thus, using it, the value of a dependent variables like `price` can be predicted.  

The more **relevant** the data, the more accurate is the predicted value for the dependent variable. Eg, providing with multiple independent variables like `highway_mpg`, `engine-size`, 'curb-weight' etc. will lead to a more accurate predictiion of the `price`.  
Why the relevant data is important can be understood with the following example. Suppose there are two cars of the same type of manufacturing, thus, having similar characteristics like `highway-mpg`, `curb'weight', etc. However, it must be known that one is of Pink Color and other is of the Red. Thus, naturally it's seen that the pink is sold lesser. Hence, not mentioning that categorical factor will cause the model to extimate the same price for both which is not actually true, as more sold car has more value usually.  

In addition to gettiing more data, using different models like the simple linear regression, multiple linear regression and polynomial regression.
