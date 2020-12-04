# Final Exam

## Problem 1: Least-Square Support Vector Regression

In this problem, we are asked to solve the quadratic optimization problems which are similar to SVM and SVR. However
they are not the same.

For classification, we optimization problem is,

$$
\min\limits_{w,b,\xi} = (\frac{1}{2} \mathbf{w}^T \mathbf{w} + \frac{C}{2} \sum\limits_{i=1}^{N} \xi_{i}^{2}), s.t. \quad \forall i \in
[1,N], \quad y_{i} (\mathbf{w}\mathbf{x_{i}}) = 1 - \xi_{i}
$$
And the classification problem is performed as,
$$
y(\mathbf{x}) = sign(\mathbf{w} \mathbf{x} + b)
$$
