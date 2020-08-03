---
layout: post
title: How to Choose a Machine Learning algorithm from the Command Line
tags: [Machine Learning]
excerpt: When creating machine learning applications, there are many algorithms that can be used for a particular problem. The best one is usually determined by trying out several and comparing their results. Command line applications can be used to choose which algorithms to train on, and even tune the hyperparameters of the said algorithms.
---

### Introduction

When creating machine learning applications, there are many algorithms that can be used for a particular problem. The best one is usually determined by trying out several and comparing their results. Command line applications can be used to choose which algorithms to train on, and even tune the hyperparameters of the said algorithms.

In this tutorial, you will build a tool that allows training on different machine learning algorithms from the command line. You'll use the Titanic dataset to predict whether a passenger died or not.

## Prerequisites
An understanding of basic terms used in machine learning: target, label, features, dataset, model, algorithm, examples and cross-validation.

## Step 1 — Import the modules and libraries

You'll use [argparse](https://docs.python.org/3/library/argparse.html) as a command line tool, train the data on [scikit-learn](https://scikit-learn.org/stable/index.html) algorithms and manipulate the data with [pandas](https://pandas.pydata.org/). Import these modules and libraries:

```python
import argparse
import numpy as np
import pandas as pd

from sklearn.ensemble import GradientBoostingClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.linear_model import SGDClassifier
from sklearn.model_selection import cross_val_score
```

## Step 2 — Load and transform the data

First, download the data from [Kaggle](https://www.kaggle.com/c/titanic/data?select=train.csv).

Next, create a function called `transform_data()` to load the data and transform it into a format suitable for the models.

Load the data:

```python
dataset = pd.read_csv('/path/to/your/download/train.csv')
```

Fetch the target column from the dataset:

```python
y = dataset.Survived
```

Next, you need to select the features from the dataset. For this tutorial, select only the numerical features. In real-world applications, the categorical data is usually transformed into numerical but that's out of the scope of this tutorial.
The line below selects only the numerical features and drops the target column:

```python
X = dataset.select_dtypes(include=np.number).drop('Survived', axis=1)
```

Next, fix the missing values in the dataset. There are several ways to deal with missing data. For this tutorial, replace the missing data with the mean:

```python
X = X.fillna(X.mean())
```

At this point, `transform_data()` should look like this:

```python
def transform_data():
  dataset = pd.read_csv('/path/to/your/download/train.csv')
  y = dataset.Survived
  X = dataset.select_dtypes(include=np.number).drop('Survived', axis=1)
  X = X.fillna(X.mean())

  return X, y
```

## Step 3 — Create the command-line tool
Predicting whether a passenger died or not is a classification problem so you need to train the data on classification algorithms. For this tutorial, you can train on three different scikit-learn algorithms(RandomForestClassifier, GradientBoostingClassifier and SGDClassifier). You will choose the algorithm to train on from the command line.

Create a function named `choose_algo()` to contain the command command line code.
In `choose_algo()`, create a parser object with the following code:

```python
parser = argparse.ArgumentParser(description="Choose an algorithm")
```
You need to add an argument to the parser object. For this case, it is the name of the algorithm you'd like to train on:

```python
parser.add_argument('model_name', help="The name of the algorithm to train on. Either random_forest, gradient_boosting or sgd")

```

Next, fetch the arguments provided in the command-line:

```python
args = parser.parse_args()
```

Finally, create a model based on the name of the algorithm provided in the command line:

```python
if args.model_name == 'gradient_boosting':
  model = GradientBoostingClassifier(n_estimators=100)
elif args.model_name == 'sgd':
  model = SGDClassifier(random_state=42)
else:
  model = RandomForestClassifier(n_estimators=100, random_state=42)
```

At this point, your `choose_algo()` function should look like this:
```python
def choose_algo():
  parser = argparse.ArgumentParser(description="Choose an algorithm")
  parser.add_argument('model_name', help="The name of the algorithm to train on. Either random_forest, gradient_boosting or sgd")
  args = parser.parse_args()

  if args.model_name == 'gradient_boosting':
    model = GradientBoostingClassifier(n_estimators=100)
  elif args.model_name == 'sgd':
    model = SGDClassifier(random_state=42)
  else:
    model = RandomForestClassifier(n_estimators=100, random_state=42)

  return model
```

## Step 4 — Training the model
To train the model, all you need to do is fit the data on the model.
```python
if __name__ == "__main__":
  X, y = transform_data()
  model = choose_algo()
  model.fit(X, y)
  scores = cross_val_score(model, X, y, cv=15)
  print(scores.mean())
```
The second-last line in the code above evaluates the score of the model by cross-validation. This score is for every example in the dataset. The last line prints out the mean score of all examples.

## Step 5 — View the documentation of the command line application
Based on the app description, the arguments and the help string you defined in step 3, `argparse` automatically creates documentation for your command line application.

View the documentation by adding a `--help` flag to the command that runs your code:
```bash
$ python titanic.py --help
```
The output will be:
```
usage: titanic_argparse.py [-h] model_name

Choose a Machine Learning algorithm

positional arguments:
  model_name  The name of the scikit-learn model to train. Either
              random_forest, gradient_boosting or sgd

optional arguments:
  -h, --help  show this help message and exit

```

## Step 6 — Choose the algorithm
Run the application, making sure to provide name of the algorithm you'd like to train on. For example, to train on RandomForestClassifier:

```
$ python titanic.py random_forest
```
The output will be the score of the model:
```
0.7108662900188324
```

## Conclusion
In this tutorial, you built a command line tool to choose machine learning algorithms. Next, you can extend its functionality to allow hyperparameter tuning from the command line.