# Passenger Satisfaction Classification Models - Buckeye Airlines, Inc.

This project focuses on developing, evaluating, and comparing classification models to predict **customer satisfaction** for Buckeye Airlines, Inc. (BAI). The goal is to identify passengers "at risk" of dissatisfaction and provide tailored financial incentives to improve their experience.

## Project Objectives

The **objectives** of this assignment are:
- Solve a business problem by creating, evaluating, and comparing three classification models to provide business value for stakeholders.
- Experiment with built-in classification models in **scikit-learn**.
  
BAI leadership has requested analysis on whether the data collected from passenger surveys can be used to predict customer satisfaction effectively. The ultimate goal is to implement targeted interventions (e.g., offering $75 gift cards) to passengers likely to be dissatisfied, with the potential of improving overall satisfaction.

### Business Problem

Buckeye Airlines wants to improve customer satisfaction rates. On average, a dissatisfied customer costs the airline **$450** in lost future revenue. Since BAI processes approximately **100,000** bookings per year, an incremental improvement in customer satisfaction could have a significant financial impact. The leadership is considering offering a **$75** incentive to customers at risk of dissatisfaction, which has been shown to be effective **35%** of the time.

## Dataset

The dataset used for this analysis is a modified version of the **Passenger Satisfaction** dataset:
- The dataset was adapted from [Kaggle's Customer Satisfaction Dataset](https://www.kaggle.com/datasets/johndddddd/customer-satisfaction).
- The dataset file is named: **satisfaction_teb1_for_post.xlsx**.
- Errors such as duplicates, missing values, and erroneous entries have been introduced for this exercise.

**NOTE**: Since you have already pre-processed this dataset in the previous assignment, you can either use the original clean dataset from that assignment or redo the work in this step.

### Problem Statement

You are tasked with predicting the likelihood of customer dissatisfaction to allow BAI to offer tailored financial incentives to at-risk passengers. The satisfaction of a customer is the **target attribute** (`satisfaction_v2`) that you will be predicting.

**Assumption**: The existing survey data is based on **previous** flights. However, in this exercise, assume that future passengers will fill out similar surveys **before** their flight, and their responses will serve as input for your prediction models.

## Tasks Overview

### 1. Cost Model Development

Before building classification models, you need to develop a **cost model** based on the problem statement. You will create a table that outlines the costs and benefits of offering a financial incentive to a customer based on their predicted dissatisfaction.

| Actual "At Risk" | Predicted "At Risk" | Incentive Benefit | Incentive Cost | Net Benefit (Benefit - Cost) |
|------------------|---------------------|-------------------|----------------|-----------------------------|
| False            | False               | $0                | $0             | $0                          |
| False            | True                | $0                | -$75           | -$75                        |
| True             | False               | -$450             | $0             | -$450                       |
| True             | True                | $450              | -$75           | $375                        |

This cost model will help evaluate the effectiveness of the classification models in terms of business value.

### 2. Model Development

Developed three classification models to predict customer satisfaction:
1. **K-Nearest Neighbors (KNN) Classifier**: A simple but effective classification model.
2. **Decision Tree**:  models from **scikit-learn**
3. **Random Forest**

### 3. Model Evaluation

Evaluate the models using the following metrics:
- **Accuracy**: The percentage of correct predictions.
- **Confusion Matrix**: To identify the number of true positives, true negatives, false positives, and false negatives.
- **Cost-Benefit Analysis**: Use the cost model to calculate the **net benefit** per customer and per year based on the predictions from each model.
  
### 4. Functions and Reusability

Given the repetitive nature of some tasks, it is recommended to create reusable functions for:
- Loading and cleaning the dataset.
- Training and evaluating each model.
- Visualizing the results, such as plotting confusion matrices.

### 5. Results Communication

As the Director of Data Science at BAI, you will present your findings to the Board of Directors (BOD). It is essential to communicate your goals, thought process, and results clearly:
- **What you are trying to achieve** and **why**.
- **What actions you took** (e.g., building models, evaluating them).
- **What results you obtained** and their implications for the business.

## Requirements

The following Python libraries are required to perform the analysis:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn openpyxl
