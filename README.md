# Machine Learning Tutorial: Landslide Edition

![Build your own landslide susceptibility map](landslide_susceptibility.png?raw=true)

## Introduction
This repository is part of the Tuesday May 21 hands-on AI/ML Basics Tutorial. The goal is to learn the basics of machine learning through the process of building simple landslide models.

## Objectives

1. Build a logistic regression model and a random forest model for landslides in R.
2. Learn about training/testing and evaluating model performance.
3. Learn about hyperparameters and overfitting.
4. Learn how to add new datasets to an existing dataset to improve the models.
5. Build your own landslide susceptibility map using the random forest model.

## Prerequisites

Follow steps 2 (download QGIS) and 3 (Download RStudio) from [system-setup](https://github.com/UR-Field-Labs/system-setup) to ensure you have the right tools. Then follow the steps below to get the code and data for this workshop.
1. Download the folder **landslide-ml-tutorial** to your local computer from either [Github](https://github.com/UR-Field-Labs/landslide-ml-tutorial) (if you already have a GitHub account linked to the Field Lab organization), or from the [Google Drive](https://drive.google.com/drive/folders/1-0g0qZZr19hnuJg2leWoadXFVYUahFnC?usp=drive_link).
2. (Specifically for generating susceptibility map) If you did not download from the Google Drive in the last step, download the **terrain** folder [here](https://drive.google.com/drive/folders/1l_BDZlnwOz8s2z7qVb9rNnJSR0NGSLPH?usp=drive_link) and put it in the **data** folder downloaded from the previous step (inside **landslide-ml-tutorial** folder). This **terriain** folder is not on Github because of its large size, so we download it separately. Github is only meant for code, not large datasets.

Also think about what you could do with this framework to pursue your own questions - a wildfire model, a pollution model, ... ...

## Logistic Regression Model for Landslides in Ecuador 

We first learn about the basics of R and logistic regression as we build a model for landslides in Ecador. Open the [landslide_logistic_regression.Rmd](landslide_logistic_regression.Rmd) in RStudio and run each code block.

Logistic regression is a simple model that, given certain inputs, provides the probability of landslide as an output. It estimates the probability by looking at patterns in the data. It is like drawing a line through data (regression), except the y variable is transformed to be a probability (between 0 and 1).

There are certain exercises within the code. So make sure to do them.

## Random Forest Model for Landslides in Nepal 

We then build a random forest model for landslides in Ecador. Open the [landslide_randomforest.Rmd](landslide_randomforest.Rmd) in RStudio and run each code block.

A random forest model is a collection of decision trees. If you provide landslide input data and an indicator of landslide (yes/no), thena computer si capable of generating a decision tree to fit that data (e.g. if slope > 45, then landslide likely. If elevation > 1000 m then landslide likely...). A random forest is a collection of 100s of such decision trees. Given input data, the random forest asks each of its decision trees to gives its response, and then returns the popular vote (landslide yes/no).

Random Forests are one of the most versatile and robust machine learning models out there, and quite simple to build compared to the intense neural network models.

## How was landslide data generated for Nepal?

The landslide data is simply generated from terrain characteristics. The [MERIT](https://hydro.iis.u-tokyo.ac.jp/~yamadai/MERIT_DEM/) Digital Elevation Model (DEM) was used to obtain elevation, slope and curvature data. As it turns out, this data is sufficient to make a decent landslide prediction model.

The actual data generation was done with [data_prep.Rmd](data_prep.Rmd). The code collects landslides from the Global Landslide Catalog, then generates some non-landslide points, generates terrain data, and compiles the dataset. You can alter this R notebook to get suitable dataset for yourself.

