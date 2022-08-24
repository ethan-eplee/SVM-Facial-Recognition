# Facial Recognition using SVM

 - [Project Description](#Project-Description)
 - [Data Sources](#Data-Sources)
 - [Executive Summary](#Executive-Summary)
 - [Notebook Contents](#Notebook-Contents)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusion & Recommendations](#Conclusion-&-Recommendations)
 

## Project Description
In this short project, we will be using the Support Vector Machines (SVM) algorithm to predict faces. We will be using the Labeled Faces in the Wild dataset from Scikit-Learn, which consists of thousands of various public figures photos. 

Ultimately, we want to see how well a SVM classifies faces, the steps involved and how to evaluate the model. Going through these steps will also give us a good introduction to the principals behind SVMs, as well as the disadvantages and challenges.

--- 
## Data Sources
We will primarily be using the Labeled Faces in the Wild dataset (from sklearn.datasets import fetch lfw_people). External data sources are not used.

---
## Executive Summary
Using the faces data from the dataset, we use SVM and PCA to fit a model to predict the labels. Because each image contains 62 x 47 or nearly 3000 pixels, we would have to use a preprocessor to get rid of some features.

In this case we use a Principal Component Analysis (PCA) to extract the 150 components from about 3000 features, before passing these through the SVC to do the classification.

A GridSearch was also done to find the best hyperparameters of C (which controls margin hardness) and gamma (controls size of rbf kernel). Upon getting the best estimator for our model, we run it on the test data for evaluation. Through the classification report and confusion matrix, we are able to get a sense of how well the model is doing.

---

## Evaluation
We are able to get an accuracy score of about 80%. This is still considered acceptable, but for a real-world facial recognition task, photos are not usually cropped so nicely. A more complex algorithm would have to search for the faces and extract features independent of the pixellation.

---
## Conclusion
SVMs are a powerful classification method. They are compact models and take up very little memory. Once the model is trained, predictions can occur very quickly.

Because SVMs are affected only by points near the margin, they tend to work well with high dimensional data. Most other algorithms fit poorly when there are more features than data samples.

However results are dependent on the choice of C, which must be chosen properly through cross-validation. As datasets grow, the computational cost is expensive.

Generally, SVMS are used only when simpler and faster methods are insufficient. Otherwise this algorithm tends to give good results.