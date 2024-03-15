# Fraud-Detection

## Table of Contents
1. [Introduction](#Introduction)
2. [File Structure](#FileStructure)
3. [Installing](#Installing)
4. [Feature Documentations](#FeatureDocumentations)
5. [Key Results](#KeyResults)
6. [Future Improvement](#FutureImprovement)
7. [Authors](#Authors)
8. [License](#License)

<a name="Introduction"></a>
## Introduction

The digital age has ushered in an era of unparalleled convenience in financial transactions, with credit cards standing at the forefront of this revolution. However, the shadow of credit card fraud looms large, presenting a significant challenge to the integrity of digital finance. In recent years, the sophistication and frequency of fraudulent activities have escalated, leading to considerable financial losses worldwide. This project is conceived as a direct response to the urgent need for advanced fraud detection mechanisms capable of navigating the complex landscape of credit card transactions.

One of the paramount challenges in developing effective fraud detection models is the inherent imbalance present in transactional data. Legitimate transactions vastly outnumber their fraudulent counterparts, making it exceedingly difficult for predictive models to accurately identify the latter without generating a prohibitive number of false positives. This imbalance not only complicates the task of model training but also skews performance metrics, potentially giving a misleading impression of a model's effectiveness.

In this project, we focus on tackling the challenges posed by imbalanced datasets. Our approach encompasses a thorough exploration of various algorithms, including logistic regression, decision trees, and ensemble methods. We aim to leverage these techniques not merely as tools for pattern recognition but as means to understand and address the imbalance intrinsic to our data.

To counteract the issues of dataset imbalance, an ideal approach is implementing and comparing several strategies, such as undersampling the majority class, oversampling the minority class, and utilizing advanced synthetic data generation techniques like SMOTE (Synthetic Minority Over-sampling Technique). But due to the sheer size of this dataset, oversampling method makes the model too computationally expensive to train, so I only conducted undersampling in this project.

A significant portion of our project is dedicated to fine-tuning our models to achieve an optimal balance between sensitivity (recall) and precision. This involves adjusting the predictive threshold of our models. Through rigorous validation and testing, we aim to develop a model that not only excels in identifying fraudulent transactions with high accuracy but also minimizes the inconvenience to legitimate users by reducing false positives.

The [original datasets](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data).

<a name="FileStructure"></a>
## File Structure
Each of the following project steps is completed in a separate notebook:
- [EDA and Data Preprocessing](https://github.com/YimingZ13/Fraud-Detection/blob/main/fraud_detection_EDA_preprocessing.ipynb): `fraud_detection_EDA_preprocessing.ipynb`
- [Modelling](https://github.com/YimingZ13/Fraud-Detection/blob/main/fraud_detection_modelling.ipynb): `fraud_detection_modelling.ipynb`

<a name="Installing"></a>
## Installing
There are no special packages needed for this project, most of packages come with the Anaconda distribution of Python 3.

<a name="FeatureDocumentations"></a>
## Feature Documentations
`creditcard.csv`:
- `Time`：Number of seconds elapsed between this transaction and the first transaction in the dataset
- `V1`-`V28`: May be result of a PCA Dimensionality reduction to protect user identities and sensitive features(v1-v28)
- `Amount`: Transaction amount
- `Class`: 1 for fraudulent transactions, 0 otherwise
  
<a name="KeyResults"></a>
## Key Results
- The best performed model was Logistic Regression with RandomUnderSampler.
- When we increase the predicting threhold, the precision increases but the recall started to drop. This means fewer legitimate transactions are incorrectly flagged, but more fraudulent transactions might be missed.
- Here is the trade-off when increasing the threshold, the model risks missing fraudulent transactions, which can have significant implications and damage customer trust. On the other hand, if the precision is too low, then we risk impacting customer experience. A model too sensitive to fraud (low threshold) may frequently interrupt users with authetication challenges or block transactions, potentially leading to frustration and churn.
- Financial institues should consider associated with false positives and false negatives. Ajust the threshold to minimize the total cost.

<a name="FutureImprovements"></a>
## Future Improvements
- Implementing oversampling method (e.g. SMOTE) and compare with the undersampling method, see if the model that is trained on a larger size of data would perform better.
- Building business metrics to compare the associated costs of adjusting predicting threshold and determine the optimal one for our goal.

<a name="Authors"></a>
## Authors
Yiming Zhao | [LinkedIn](https://www.linkedin.com/in/yiming-zhao13/)

<a name="License"></a>
## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
