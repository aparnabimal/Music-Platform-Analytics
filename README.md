# Music-Platform-Analytics

# Predicting Artist Success on a Music Platform

This project aims to identify factors that contribute to the success of artists on a music platform. It involves data analysis, exploration, and the development of predictive models to classify songs as successful or not.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
    - [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
    - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
    - [Feature Engineering](#feature-engineering)
    - [Model Selection and Evaluation](#model-selection-and-evaluation)
- [Key Findings](#key-findings)
- [Models](#models)
    - [Random Forest](#random-forest)
    - [Logistic Regression](#logistic-regression)
    - [Support Vector Machine (SVM)](#support-vector-machine-svm)
- [How to Use](#how-to-use)


## Project Overview

Understanding the factors influencing an artist's success on a music platform is vital for both artists and the platform itself. This project delves into user demographics, song attributes, and engagement metrics to uncover patterns and build predictive models that can help identify promising artists and songs. Data for this project was sourced from a real music platform (name withheld for confidentiality reasons). The dataset has been carefully anonymized and modified to remove any personally identifiable information (PII) or sensitive details that could compromise user privacy.

## Dataset

* **Source:** Data provided by the music platform (anonymized for privacy).
* **Description:**  The dataset includes tables about users (profiles, demographics), songs (attributes, genre), and user-song interactions (plays, likes, downloads).

## Methodology

### Data Cleaning and Preprocessing

*   Merged relevant tables (e.g., user profiles, song tags, genre information) to create comprehensive datasets.
*   Handled missing values using imputation (mode for categorical, mean for numerical).
*   Removed duplicate records and irrelevant/sensitive columns.
*   Transformed categorical variables into numerical representations using one-hot encoding.
*   Scaled numerical features to ensure they have similar ranges.

### Exploratory Data Analysis (EDA)

*   Analyzed user demographics (gender, location, occupation) and their distribution.
  ![User_Locations](https://github.com/user-attachments/assets/1930c442-7109-4866-9515-9e1a27632e14)

*   Examined song attributes (genre, upload platform) and their relationship to success.
*   Investigated user engagement metrics (plays, likes, downloads) for both users and songs.
*   Explored relationships between user profile classifications and artist success.

### Feature Engineering

*   Created a binary target variable (`Success`) based on the number of plays a song received.
*   Selected relevant features for model training based on EDA and domain knowledge.

### Model Selection and Evaluation

*   Split the data into training and testing sets.
*   Trained and evaluated multiple classification models:
    *   Random Forest
    *   Logistic Regression
    *   Support Vector Machine (SVM)
*   Utilized techniques like grid search, feature selection (RFE), and SMOTE to optimize model performance and address class imbalance.
*   Evaluated model performance using accuracy, precision, recall, F1-score, and confusion matrices.

## Key Findings

*  User Demographics:
  The platform has a significantly higher proportion of male users compared to female users. Most users identify as musicians, singers, or songwriters, suggesting a creator-heavy user base. The majority of users are located in the United States and the United Kingdom.

* Song Attributes:
  Songs uploaded via iOS devices generally receive more plays than those uploaded via the web. Acoustic is the most popular genre on the platform in terms of total plays.

* Artist Success:
  The majority of top-performing artists are not verified, indicating that verification status might not be a strong predictor of success. Successful artists tend to belong to a diverse range of user classifications, with a relatively even distribution across musicians, singers, songwriters, and producers.


## Models

### Random Forest

* An ensemble of decision trees, each trained on a random subset of the features and data. The final prediction is based on the majority vote of the trees. The model was initially trained with default hyperparameters. Further tuning was explored using GridSearchCV, but it did not lead to significant improvements in performance.

### Logistic Regression

* A linear model used for binary classification. It models the probability of a song being successful (1) or not (0) based on a linear combination of input features. The model was trained with class weights to address the imbalance between successful and non-successful songs. A Logistic Regression model with SMOTE oversampling and PCA for dimensionality reduction achieved the best performance among the models tested.

### Support Vector Machine (SVM)

* A model that finds the optimal hyperplane that separates the two classes (successful and non-successful songs) with the maximum margin. The model was trained with an RBF kernel and hyperparameter tuning was performed using GridSearchCV to find the optimal values for C (regularization parameter) and gamma (kernel coefficient).


## How to Use

1.  Clone this repository.
2.  Install the required dependencies (listed in `requirements.txt`).
3.  Run the Jupyter notebooks in the `notebooks/` directory.


