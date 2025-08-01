---
layout: post
title: Data Science for Business
date: 2025-02-22 05:47 -0800
description: MGMT 657 Course Notes
author: khoa_pham
categories: [Programming Hub, Skill Tracks]
pin: false
math: true
mermaid: true
toc: true
comments: true
---

## Data Science Methods

**Supervised Learning** (Labeled data):
* **Classification (Predicting Categorical Values):** Logistic Regression, Decision Trees, Random Forests, k-NN, Support Vector Machines (SVM), Gradient Boosting (XGBoost, LightGBM, CatBoost), Neural Networks
* **Regression (Predicting Continuous Values):** Linear Regression, Decision Trees, Random Forests, Ridge Regression, Lasso Regression, Gradient Boosting (XGBoost, LightGBM, CatBoost), Neural Networks, k-NN *(rarely used)*

**Unsupervised Learning** (Unlabeled data):
* **Clustering (Grouping Similar Data):** k-Means, Hierarchical Clustering, DBSCAN
* **Similarity Matching (Finding Closest Matches):** Cosine Similarity, Euclidean Distance
* **Co-occurrence Grouping (Finding Items Bought Together):** Association Rule Mining (Apriori Algorithm)
* **Dimensionality Reduction (Simplifying Data):** Principal Component Analysis (PCA), t-SNE

### 1) Classical Statistics vs. Predictive Modeling
Q1: True or False: Determining the statistical significance of a linear regression model is an objective of classical statistics, but not of predictive modeling.

1. Classical Statistics: Focus on Explanation & Inference   
	In classical statistics, regression models are used to understand relationships between variables and test hypotheses.    

	**Suppose you build a linear regression model:** Testing the Effect of Advertising on Sales
	$$ \text{Sales} = \beta_0 + \beta_1 (\text{Advertising Spend}) + \epsilon $$

	A key goal in classical statistics is to determine whether Advertising Spend significantly affects Sales. You do this by:   
	* Checking the p-value for β₁ (Advertising Spend).    
	* If p-value < 0.05, we reject the null hypothesis (meaning the variable is statistically significant).    
	* If p-value > 0.05, Advertising Spend is not a significant predictor of Sales.    

	✅ Key Focus: Understanding which variables matter and whether they have a statistically significant effect.

2. Predictive Modeling: Focus on Accuracy & Performance   
    In predictive modeling, the primary goal is making accurate predictions rather than interpreting relationships.   

    **Suppose you build a predictive model using multiple features:** Predicting House Prices   
    $$ \text{House Price} = f(\text{Size}, \text{Location}, \text{Bedrooms}, \text{Bathrooms}, \text{Year Built}) $$

    In predictive modeling, we are less concerned about whether each individual predictor is statistically significant. Instead, we evaluate the model’s overall performance using:    
    * R² (coefficient of determination)   
    * Mean Squared Error (MSE)   
    * Root Mean Squared Error (RMSE)   
    * Cross-validation scores   

    Even if some variables have insignificant p-values, they might still improve the model’s predictive power. For example:   
    * Removing an “insignificant” variable might reduce accuracy if it still contributes useful patterns.    
    * Techniques like regularization (Lasso, Ridge Regression) are used to improve prediction quality rather than testing statistical significance.    

    ✅ Key Focus: Minimizing prediction error, not testing significance.



### 2) Causal Modeling   
Q2: What user interface makes customers more or less likely to purchase our products?

* Regression – Can model correlations but does not necessarily establish causation.   
* Similarity Matching – Identifies similar customers but does not determine UI impact on purchasing.   
* Profiling – Describes customer behaviors but does not infer causal effects.   
* **Causal Modeling** ✅    

> The question seeks to understand the cause-and-effect relationship between different user interface (UI) designs and customer purchase behavior.    
> **Causal modeling** helps determine whether changes in the UI directly influence the likelihood of a purchase.    
> Example Approach:     
> * A/B Testing: Show different UI designs to different user groups and compare purchase rates.   
> * Instrumental Variables: Control for confounding factors that might affect both UI exposure and purchase decisions.   
> * Difference-in-Differences (DiD): Compare purchase behaviors before and after a UI change across treatment and control groups.   



### 3) Classification   
Q3: Which customers are most likely to switch wireless providers?   

* Profiling - describes characteristics of customers who have already churned but does not predict future churners.   
* Co-occurrence Grouping - identifies items frequently purchased together but does not predict churn.   
* Clustering - groups customers based on similarities but does not classify or estimate churn probability directly. However, it can be a preprocessing step to segment customers before applying classification.   
* **Classification or class probability estimation** ✅   

> The goal is to predict which customers are likely to switch wireless providers, making this a supervised learning problem with a clearly defined target variable (churn or no churn).    
> **Classification** models estimate the probability of churn based on customer attributes and behaviors.    
> Example Approach:     
> * Logistic Regression or Decision Trees to classify customers into “likely to churn” vs. “not likely to churn.”
> * Random Forests or Gradient Boosting Models (GBM) for improved predictive accuracy.
> * Neural Networks for complex patterns in large datasets.



### 4) Clustering   
Q4: Which of the following business questions is best suited to unsupervised analytics techniques?

* Use a machine-learning algorithm to predict house prices based on square footage, location etc. -> Regression   
* Determine whether or not a customer will make a purchase after viewing an advertisement. -> Classification   
* Predict the sentiment of a customer based on a tweet or product review. -> Classification
* **Identify segments of the customer population based on: gender, location, age, education, income bracket, and so on.** -> Clustering ✅  

> This question involves grouping customers based on their characteristics without predefined labels, making it a clustering problem, a key technique in unsupervised learning. The goal is to find natural groupings in the data that can help with targeted marketing, personalization, or customer behavior analysis.   
> * K-Means Clustering – Group customers into distinct segments based on demographic attributes.
> * Hierarchical Clustering – Build a tree-like hierarchy of customer groups.
> * DBSCAN – Detect clusters with varying densities, identifying core customer groups.



### 5) Hypothesis Testing
Q5: Are store profits significantly higher during the month of December than during the rest of the year?

* Clustering - Groups data based on similarities but does not test significance.   
* Database querying - Retrieves data but does not perform statistical analysis.   
* Predictive Modeling - Forecasts future profits but does not determine significance of past trends.   
* **Hypothesis Testing** ✅   

> The question asks whether store profits in December are significantly higher than the rest of the year, which requires statistical inference to compare two groups (December vs. other months).     
> **Hypothesis testing** helps determine if the observed difference in profits is statistically significant or due to random variation.   
> Example Approach:   
> * Two-sample t-test: Compare average profits in December vs. other months.
> * ANOVA (if comparing multiple months): Analyze variance across all months.
> * p-value & confidence intervals: Determine statistical significance.




## Supervised Segmentation
### 1) Supervised Segmentation Process
Q1: The process of supervised segmentation is referred to as "supervised" for what reason?

* There is a process or method used to achieve an outcome. - True, but not the primary reason for calling it "supervised."   
* The variable being predicted is categorical rather than numerical. - Supervised segmentation can be used for both categorical (classification) and numerical (regression) targets.   
* The analyst controls every part of the segmentation process. - The algorithm, not the analyst, determines the best splits based on data patterns. Analysts may tune parameters but do not manually control every decision.   
* **The target variable is known and is considered during the segmentation process.** ✅   

> The term “supervised” in supervised segmentation refers to the fact that the segmentation process is guided by a known target variable (also called the dependent variable or outcome). This means that the algorithm uses labeled data, where the correct outcome is already provided, to determine the best splits that improve predictive accuracy.

Q2: Which of the following would **not** be an outcome of a supervised segmentation process?

* Identification of informative attributes for predicting a target variable. - A key outcome of supervised segmentation is finding which features contribute most to predicting the target.   
* Eliminating variables that are unimportant for predicting the target variable. - Unimportant variables (those with little predictive power) can be removed to improve model efficiency and accuracy.   
* Measuring how much each variable reduces the uncertainty in estimating the target variable. - Decision trees, for example, measure how much each split (feature) reduces uncertainty using entropy or Gini impurity.   
* **Identifying new target variables to predict based on the collection of features in the data.** ✅

> Supervised segmentation does not identify new target variables—it works with an already defined target and does not determine what should be predicted. Instead, it focuses on finding the best predictors for an existing target.


### 2) Entropy   
Q3: Which of the following measures is minimized in order to determine the best partition at each stage of a classification tree algorithm?

* Momentum – Relevant in optimization techniques (e.g., gradient descent) but not in decision trees.   
* Average distance – Used in clustering algorithms (e.g., K-means) but not in classification trees.   
* Minimum distance – Relevant in nearest neighbor classification (e.g., KNN), not decision trees.   
* **Entropy** ✅   

> Entropy measures the level of disorder or impurity in a dataset. The lower the entropy, the purer the node, meaning that most instances in that node belong to the same class.    
> * The decision tree algorithm chooses splits that result in child nodes with the lowest possible entropy, leading to better classification.   

### 3) Tree Induction
Q4: True or False: The method of tree induction can only be used in the context of classification problems involving a binary target variable and cannot be used to predict numerical outcomes.

False. Tree induction is a flexible method that can be used for both classification and regression problems:   
1. Classification Trees   
* Used when the target variable is categorical (e.g., “Yes” or “No,” “Spam” or “Not Spam”).
* The tree splits data to maximize class purity using criteria like Gini impurity or entropy (information gain).
* Can handle binary and multi-class classification problems.

2. Regression Trees   
* Used when the target variable is numerical (continuous values).
* Instead of entropy or Gini impurity, the tree minimizes the variance or uses Mean Squared Error (MSE) as a splitting criterion.
* Example: Predicting house prices based on features like square footage and location.



### 4) Regression Trees and MSE
Q5: What is the metric used to evaluate the accuracy of a regression tree?
* p-value – Used in hypothesis testing, not for evaluating regression models.
* Confidence Interval – Provides a range for estimation but doesn’t measure accuracy directly.
* F-statistic – Used in ANOVA and regression significance testing, not for measuring prediction accuracy.
* Mean Squared Error (MSE) ✅

> For regression trees, the goal is to predict continuous numerical values, so accuracy is evaluated based on how close the predictions are to the actual values. The most commonly used metric for this is Mean Squared Error (MSE).


## Logistic Regression
### 1) Log-Odds (Logit Function)
Q1: What is the purpose of the logit function in logistic regression?
Logistic regression works by transforming the probability into log-odds, which allows it to be modeled linearly.

$$ \log \left( \frac{p}{1 - p} \right) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + … + \beta_n X_n $$



Q2: True or False: It would be appropriate to use a logistic regression model to classify a product's price range as low, moderate, or high.   
> False. Logistic regression is used for binary classification (e.g., Yes/No, 0/1). If you need to classify a product’s price range into three categories (Low, Moderate, High), this is a multi-class classification problem, which standard logistic regression cannot handle.
> Instead, you should use:
> * Multinomial Logistic Regression (an extension of logistic regression for multi-class problems).
> * Ordinal Logistic Regression (if the categories have a natural order, like Low < Moderate < High).
> * Decision Trees, Random Forests, or Neural Networks, which can handle multi-class classification as well.



### 2) Confusion Matrix
Q3: The primary tool used to evaluate the performance of a logistic regression model is
* The RMSE – Used for regression models, not classification models.
* The R-squared value - Measures the proportion of variance explained by the model, not classification performance.
* The MSE - Measures the average squared difference between predicted and actual values in regression models.
* **The confusion matrix** ✅

> A confusion matrix is the primary tool used to evaluate the performance of a logistic regression model since it is a classification model. It provides a detailed breakdown of true positives, true negatives, false positives, and false negatives, which are crucial for calculating metrics like accuracy, precision, recall, and F1-score.


### 3) Evaluation Metrics
Q4: Given the following confusion matrix, calculate the model's accuracy, error rate, precision, recall, specificity, and F1-score.

| Actual/Predicted  | Responder   | Non-responder |   
|-------------------|-------------|---------------|   
| Responder         |11           | 1             |  
| Non-responder     |2            | 10            |   

Accuracy: The proportion of correct predictions among all predictions made.   
$$ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} = \frac{11 + 10}{11 + 10 + 2 + 1} = \frac{21}{24} $$   

Error Rate: The proportion of incorrect predictions among all predictions made.   
$$ \text{Error Rate} = \frac{FP + FN}{TP + TN + FP + FN} = \frac{2 + 1}{11 + 10 + 2 + 1} = \frac{3}{24} $$   

Precision: The proportion of true positive predictions among all positive predictions made.   
$$ \text{Precision} = \frac{TP}{TP + FP} = \frac{11}{11 + 2} = \frac{11}{13} $$    

Recall (Sensitivity): The proportion of true positive predictions among all actual positive instances.   
$$ \text{Recall (Sensitivity)} = \frac{TP}{TP + FN} = \frac{11}{11 + 1} = \frac{11}{12} $$    

Specificity: The proportion of true negative predictions among all actual negative instances.   
$$ \text{Specificity} = \frac{TN}{TN + FP} = \frac{10}{10 + 2} = \frac{10}{12} $$   

F1-Score: The harmonic mean of precision and recall, providing a balanced measure of model performance.   
$$ \text{F1-Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} = 2 \times \frac{\frac{11}{13} \times \frac{11}{12}}{\frac{11}{13} + \frac{11}{12}} = 2 \times \frac{\frac{121}{156}}{\frac{143}{156}} = 2 \times \frac{121}{143} $$



### 4) Misclassification Rate
Q5: True or False: A classification model's misclassification rate on the validation set is a better measure of the model's predictive ability on new data than its misclassification rate on the training set.

The misclassification rate (or error rate) on the validation set is a better measure of the model’s predictive ability on new data compared to its performance on the training set. This is because:   
1.	Training Set Performance – The model learns patterns from the training set, and a low error rate here may indicate overfitting (i.e., the model memorizes the training data instead of generalizing well).
2.	Validation Set Performance – The validation set represents unseen data, simulating how the model will perform on real-world or new data. A low misclassification rate on the validation set suggests the model generalizes well.
3.	Overfitting vs. Generalization – If a model has a low error rate on the training set but a high error rate on the validation set, it is likely overfitting. The validation set helps detect this issue.
* Overfitting: Model performs well on training data but poorly on unseen data.
* Underfitting: Model performs poorly on both training and unseen data.
* Generalization: Model performs well on both training and unseen data.