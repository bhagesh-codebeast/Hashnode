## Day 1 : Introduction To ML Mystery

## Hi and Welcome
Today I learned some new terms, & their meanings w.r.t. **Machine Learning** (ML).
ML seems pretty intimidating in the first look... but that isn't enough to make us not want to do something right ?

> I'm going to stick till the end and learn as much as possible as fast as possible.

## Summary :

## A. **What Is Machine Learning? **

> [Machine Learning is the] field of study that gives computers the ability to learn without being explicitly programmed. —Arthur Samuel, 1959 

> A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E. —Tom Mitchell, 1997 

---

## B. **Types of Machine Learning Systems** 

#### 1. Supervised/Unsupervised Learning

i. **Supervised learning**

- k-Nearest Neighbors
- Linear Regression
- Logistic Regression
- Support Vector Machines (SVMs)
- Decision Trees and Random Forests 
- Neural networks

ii. **Unsupervised learning**

> **Clustering**
- K-Means 
- DBSCAN 
- Hierarchical Cluster Analysis (HCA) 


> **Anomaly detection and novelty detection**
- One-class SVM 
- Isolation Forest 


> **Visualization and dimensionality reduction** 
- Principal Component Analysis (PCA) 
- Kernel PCA 
- Locally Linear Embedding (LLE) 
- t-Distributed Stochastic Neighbor Embedding (t-SNE) 


> **Association rule learning** 
- Apriori 
- Eclat

iii. **Semisupervised learning **

iv. **Reinforcement Learning**


#### 2. Batch and Online Learning

i. **Batch learning **

ii. **Online learning **

#### 3. Instance-Based Versus Model-Based Learning 

i. **Instance-based learning **

ii. **Model-based learning **

---

## C. **Main Challenges of Machine Learning **

#### 1. Insufficient Quantity of Training Data 

#### 2. Nonrepresentative Training Data 

#### 3. Poor-Quality Data

#### 4. Irrelevant Features 

#### 5. Overfitting the Training Data 

#### 6. Underfitting the Training Data 

#### 7. Stepping Back 

---

## D. **Testing and Validating **

#### 1. Hyperparameter Tuning and Model Selection 

#### 2. Data Mismatch 

---

Example :

```

import numpy as np
import pandas as pd
import sklearn.linear_model
import matplotlib.pyplot as plt

# Loading data
oecd = pd.read_csv("oecd_bli.csv", thousands=',')

gdp_per_capita = pd.read_csv("gdp_per_capita.csv", thousands = ',', delimiter='\t', encoding = 'latin1', na_values = 'n/a')

# Preparing the data
country_stats = prepare_country_stats(oecd, gdp_per_capita)
X = np.c_[country_stats["GDP per capita"]]
Y = np.c_[country_stats["Life satisfaction"]]

# Visualize the data
country_stats.plot(kind = 'scatter', x='GDP per capita', y='Life satisfaction')

# Select a linear model 1. LinearRegression
model_1 = sklearn.linear_model.LinearRegression( )

# Train the model
model_1.fit(X,Y)

# make a prediction for Cyprus
X_1 = [[ 22587 ]] #Cyprus's GDP per capita
print(model.predict(X_1)) #outputs [[ 5.96 ]]

# Select a linear model 2. KNeighborsRegressor
model_2 = sklearn.linear_model.KNeighborsRegressor(n_neighbors=3)

# Train the model
model_2.fit(X,Y)

# make a prediction for Cyprus
X_1 = [[ 22587 ]] #Cyprus's GDP per capita
print(model.predict(X_1)) #outputs [[ 5.77 ]]

``` 



## Reference material :

- **Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow:** Concepts, Tools, and Techniques to Build Intelligent Systems - by **Aurelien Geron**