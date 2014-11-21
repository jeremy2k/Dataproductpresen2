


Course Project - Iris Species Prediction
========================================================
author: Jeremy
date: 2014-11-22

Introduction
========================================================

This Shiny application provides iris species prediction based on the machine learning package caret in R. The web application is deployed on [**shinyapps.io**](https://jeremy2k.shinyapps.io/shinyproject) and everyone can try it straight forward as follows: 

1. Input the iris information (sepal length, sepal width, petal length, petal width) in the input textbox on the left.  					  
2. Then click the submit button below.
3. This web application will automatically predict the corresponding iris species and return the results in bottom of the main panel. 


Training Data
========================================================
The training data is based on the iris data in R. And first let's do some exploratory analysis of all the variables in the figure on the right:

***

![plot of chunk unnamed-chunk-1](dataproduct-figure/unnamed-chunk-1.png) 

Machine Learning Algorithm
========================================================
The prediction algorithm implemented on Shiny server side is decision tree. The final decision tree model is shown below:

```
n= 150 

node), split, n, loss, yval, (yprob)
      * denotes terminal node

1) root 150 100 setosa (0.33333 0.33333 0.33333)  
  2) Petal.Length< 2.45 50   0 setosa (1.00000 0.00000 0.00000) *
  3) Petal.Length>=2.45 100  50 versicolor (0.00000 0.50000 0.50000)  
    6) Petal.Width< 1.75 54   5 versicolor (0.00000 0.90741 0.09259) *
    7) Petal.Width>=1.75 46   1 virginica (0.00000 0.02174 0.97826) *
```

Discussion
=======================================================

More complicated models are not used here due to the performance concern of all the web applications. Since it is impossilbe to keep users waiting for a long time before they can see the final results. Fianlly the prediction error details are attached as follows:



```
    cp Accuracy  Kappa AccuracySD KappaSD
1 0.00   0.9404 0.9100    0.02353 0.03548
2 0.44   0.7542 0.6456    0.16792 0.23787
3 0.50   0.5242 0.3037    0.14286 0.21463
```
