# knn-optimal-neighbor-number
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.datasets import <dataset>


X,y = <dataset>(return_X_y=True)

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=67)

optimized_N_N = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for number in optimized_N_N:
  knn = KNeighborsClassifier(n_neighbors=number)
  knn.fit(X_train, y_train)
  print('Number of neighbors: ' + str(number) + ' | Accuracy Percentage: ' + str(knn.score(X_test, y_test)))
