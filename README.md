# SMS Spam Collection

![SMS Spam Collection]([https://your-image-url.com](https://consumerinfo.my/wp-content/uploads/2019/10/WAYS-TO-STOP-SMS-SPAM-ON-iPhone-Android-HERES-HOW-1.jpg))

This repository contains the code and analysis for a binary classification project aimed at detecting SMS spam messages. Various baseline classifiers were evaluated on the dataset, and their performance metrics were compared to identify the best model for this specific task.

## Introduction

Text messages (SMS) have become a common medium of communication, but they can also be exploited by spammers to deliver unwanted and potentially harmful content. The goal of this project is to build a robust binary classifier that distinguishes between legitimate messages and spam, allowing users to filter out unwanted messages effectively.

## Dataset

The dataset used for this project is the SMS Spam Collection, consisting of labeled SMS messages, indicating whether they are spam or not. The dataset has been preprocessed and prepared for machine learning tasks.

## Models

The following baseline classifiers were evaluated for their performance in binary classification:

1. **Baseline Logistic Regression Model**
2. **Baseline Bernoulli Naive Bayes**
3. **Baseline Random Forest Classifier**
4. **Baseline Adaboost Classifier**
5. **Baseline Gradient Boost**
6. **Baseline XGBoost Classifier**

Each model was trained on a portion of the dataset and evaluated on both training and test data to measure accuracy and log loss.

## Evaluation

The models were evaluated using the following performance metrics:

- **Train Accuracy Score (%):** The accuracy of the model on the training dataset.
- **Test Accuracy Score (%):** The accuracy of the model on the test dataset.
- **Train Log Loss:** The log loss of the model on the training dataset.
- **Test Log Loss:** The log loss of the model on the test dataset.

The evaluation results were compared to identify the best-performing model for the SMS spam classification task.

## Conclusion

Based on the evaluation of the baseline classifiers, the following conclusions were made:

- The Logistic Regression model achieved the highest accuracy and the lowest log loss on both training and test datasets, making it the best-performing model for this task.
- The Random Forest model exhibited overfitting, and the Adaboost model had higher log loss values, suggesting potential for improvement.
- The Gradient Boost and XGBoost models performed well and are promising alternatives, deserving further experimentation.

## Usage

To use this repository and the trained models for your own SMS spam classification tasks:

1. Clone the repository:

2. Install the required dependencies.

3. Explore the Jupyter notebooks for data preprocessing, model training, and evaluation.

4. Utilize the trained models for your SMS spam classification.
