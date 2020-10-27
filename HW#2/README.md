# HW#2 Problem 2: Learning tradeoff on MNIST dataset

Tradeoff is espically important in machine learning. It's balance between underfitting and overfitting.  Overfitting means
your model just remembers the training dataset, when encountering unseen samples, it has no ability to do prediction.
On the contrary, underfitting means your model not fits data so good, its generate ability is not good.
Actually, we have proved PAC Learnibility mathmatically. 

In Problem2, we are asked to play with MNIST dataste using KNN. By adjusting parameter 'k', you can roughly think that
you are using different hypothesis. The main tasks are as follows,

* [Q1] Load the dataste
* [Q2] Run KNN with K=4 and compute the empirical risk
* [Q3] Set K from 1 to 10 and find the tradeoff
* [Q4] Reduce the dimension
* [Q5] Use KNN to do prediction on reduced-dimensional data
