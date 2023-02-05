# [Day 01: Breast Cancer Wisconsin (Diagnostic) Data Set](LogisticRegression.ipynb)

## Title: Classification of Breast Cancer Diagnosis using Logistic Regression

### Objective: 
The goal of this project is to develop a machine learning model that can accurately classify the diagnosis of breast cancer as either benign or malignant based on various diagnostic measurements.

### Dataset Description: 
The Breast Cancer Wisconsin (Diagnostic) Data Set consists of 569 instances, each of which contains 30 features related to the diagnosis of breast cancer. The features include measures such as the radius, texture, perimeter, and area of the mass, as well as various other diagnostic measurements. The target variable is binary, with values of 0 for benign and 1 for malignant.

### What is Logistic Regression: 
Logistic regression is a statistical method used for binary classification tasks. It models the relationship between the independent variables and the binary dependent variable by estimating the probability of the dependent variable being in a certain class. The logistic regression model outputs a probability score, which can then be thresholded to make the final binary prediction.

The logistic regression model aims to model the probability of the dependent variable, Y, taking on a particular class (e.g. benign or malignant in the case of the breast cancer diagnosis problem). Let X be a vector of independent variables that are used to predict Y. The logistic regression model is expressed as:

$P(Y=1|X) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_p X_p)}} = \frac{1}{1 + e^{-\boldsymbol{\beta}^T\boldsymbol{X}}}$

where $\beta_0$ is the intercept, $\beta_1, \beta_2, ..., \beta_p$ are the coefficients for each independent variable, X, and $\boldsymbol{\beta}^T\boldsymbol{X}$ is the dot product of the coefficient vector and the independent variable vector. The expression on the right-hand side of the equation is known as the logistic function, which maps any real number to the range [0, 1], making it suitable for modeling probabilities.

Once the coefficients have been estimated, the logistic regression model can be used to predict the probability of Y taking on a particular class. A threshold, such as 0.5, can then be applied to the predicted probability to make the final binary prediction.

### Advantage of using Logistic Regression on this Dataset: 

Logistic regression is well suited for binary classification problems, making it a suitable choice for the task of classifying the diagnosis of breast cancer. Additionally, logistic regression is relatively simple and computationally efficient, making it a good choice for small- to medium-sized data sets like the Breast Cancer Wisconsin (Diagnostic) Data Set. The interpretability of the model's coefficients also makes it easy to understand the relative impact of each feature on the final prediction.

### Result and Conclusion

![alt](report/output.png)
The first row represents the actual benign cases. Out of these, 148 were correctly classified as benign, and `0 were incorrectly classified as malignant`. The second row,represents the actual malignant cases. Out of these, `4 were incorrectly classified `as benign, and 76 were correctly classified as malignant.

In this particular case, the classifier has a high accuracy of `97.5% (148 + 76) / (148 + 76 + 4 + 0)`. However, this accuracy score may not be representative of the classifier's performance when it comes to real-world applications.

In conclusion, for cancer prediction, it's crucial to consider both accuracy scores and the distribution of false negatives and false positives. A high accuracy score alone may not be enough to guarantee that the classifier is providing reliable results. It's important to focus on reducing the number of `false negatives`, and to ensure that the classifier is providing an adequate number of `true positives`.

For cancer prediction, a high number of false negatives (FN) is particularly concerning. A false negative refers to a case where the classifier predicts the class label as benign, even though the actual class label is malignant. In this confusion matrix, there are 4 false negatives. This means that there are 4 cases where the classifier has missed a malignant tumor, which could have serious consequences for the patient.

In comparison, false positives (FP) are not as concerning, as they refer to cases where the classifier predicts a malignant tumor when the actual class label is benign. In this confusion matrix, there are 0 false positives.