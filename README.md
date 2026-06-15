# Naive-Bayes-Model-Evaluation

# Naive Bayes Classification – NBA Player Longevity Prediction

## Project Overview

This project uses a **Gaussian Naive Bayes classifier** to predict whether an NBA player will remain in the league for at least five years. The analysis is based on engineered NBA performance metrics and demonstrates how probabilistic machine learning models can support scouting and talent evaluation decisions.

The project focuses on model development, performance evaluation, interpretation of assumptions, and communication of findings for basketball operations stakeholders.

---

## Dataset

The dataset contains NBA player statistics and engineered performance variables.

### Target Variable

* **target_5yrs**

  * 1 = Player remained in the NBA for at least five years.
  * 0 = Player did not remain in the NBA for at least five years.

---

## Objectives

The objectives of this project are to:

* Build a Gaussian Naive Bayes classification model.
* Evaluate model performance using business-relevant metrics.
* Visualize prediction results with a confusion matrix and ROC curve.
* Analyze the independence assumption underlying Naive Bayes.
* Identify the most influential features associated with player longevity.
* Provide recommendations for NBA scouting departments.

---

## Tools and Libraries

The project was implemented using:

* Python
* Pandas
* NumPy
* Seaborn
* Matplotlib
* Scikit-learn

---

## Methodology

### 1. Data Exploration

* Loaded the engineered NBA dataset.
* Examined dataset dimensions and variables.
* Verified the target variable.
* Checked class distribution.

### 2. Correlation Analysis

A correlation heatmap was generated to examine relationships among player statistics and identify potential multicollinearity.

### 3. Data Preparation

* Defined predictor variables (**X**) and target variable (**y**).
* Split the data into training and testing sets.
* Used stratified sampling to preserve class balance.

### 4. Model Development

A **Gaussian Naive Bayes** classifier was trained using Scikit-learn.

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()
model.fit(X_train, y_train)
```

---

## Model Evaluation

The following metrics were used:

* Accuracy
* Precision
* Recall
* F1-score
* Classification Report
* Confusion Matrix
* ROC Curve
* Area Under the Curve (AUC)

### Business Interpretation

#### Precision

Precision measures how many players predicted to have long NBA careers actually became successful.

High precision helps reduce the risk of investing resources in players who become busts.

#### Recall

Recall measures how many successful long-term players were correctly identified.

High recall reduces the likelihood of overlooking talented prospects.

---

## Feature Influence Analysis

Differences in average feature values between the two classes were used to identify the most influential variables associated with player longevity.

Common predictors include:

* Minutes played
* Points scored
* Rebounds
* Assists
* Shooting efficiency metrics

---

## Independence Assumption

Gaussian Naive Bayes assumes that predictor variables are conditionally independent.

This assumption is not entirely realistic in basketball analytics because many statistics are naturally correlated. Examples include:

* Points scored and minutes played.
* Field goals made and total points.
* Rebounds and blocks.

Despite this limitation, Gaussian Naive Bayes provides a strong baseline model due to its speed, simplicity, and interpretability.

---

## Strengths

* Fast training and prediction.
* Computationally efficient.
* Easy to interpret.
* Provides a strong baseline classifier.
* Useful for preliminary scouting evaluations.

---

## Limitations

* Assumes feature independence.
* May not capture complex interactions among player statistics.
* More advanced models may achieve higher predictive performance.

---

## Recommendations

NBA teams should use the model as a decision-support tool rather than a replacement for traditional scouting.

Recommended workflow:

1. Use the model to identify promising prospects.
2. Combine predictions with expert evaluations.
3. Investigate players with high predicted probabilities.
4. Compare performance with advanced models such as:

   * Logistic Regression
   * Random Forest
   * XGBoost

---

## Visualizations Included

* Correlation Heatmap
* Confusion Matrix Heatmap
* ROC Curve
* Feature Importance Bar Chart

---

## Repository Structure

```
.
├── naive_bayes_nba_.ipynb
├── README.md
└── extracted_nba_players_data.csv
```

---

## Conclusion

The Gaussian Naive Bayes model provides an effective and interpretable approach for predicting NBA player longevity. Although the independence assumption is imperfect for basketball statistics, the model delivers valuable insights and can serve as a useful screening tool for scouting departments when combined with expert judgment.
