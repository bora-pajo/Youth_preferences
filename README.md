# Youth_preferences
This statistical exploration is done on a dataset collected from young adults (ages 18-22) on various topics.

Almost everything that captures this group age is included from their weight, height, exercise patterns, sports, movie preferences, 
food preferences, fiction authors preferences. In addition information is collected about parents' education level and income.

The dataset includes over 100 variables and has 163 participants. 

The libraries used:

```python
import numpy as np
import pandas as pd
import matplolib.pyplot as plt
import csv
```


```python
from sklearn.linear_model import LogisticRegression #for logistic regression
from sklearn.pipeline import Pipeline #to assemble steps for cross validation
from sklearn.preprocessing import PolynomialFeatures #for all the polynomial features
from sklearn import svm #for Support Vector Machines
from sklearn.neighbors import NearestNeighbors #for nearest neighbor classifier
from sklearn import tree
from sklearn.tree import DecisionTreeClassifier #for decision tree classifier
from sklearn.naive_bayes import GaussianNB  #for naive bayes classifier
from scipy import stats #for statistical info
from sklearn.model_selection import train_test_split # to split the data in train and test
from sklearn.model_selection import KFold # for cross validation
from sklearn.grid_search import GridSearchCV  # for tuning parameters
from sklearn.neighbors import KNeighborsClassifier  #for k-neighbor classifier
from sklearn import metrics  # for checking the accuracy 
from time import time
```
