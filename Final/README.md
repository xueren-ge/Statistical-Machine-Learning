# Final Exam

## Problem 1: Least-Square Support Vector Regression

In this problem, we are asked to solve the quadratic optimization problems which are similar to SVM and SVR. However
they are not the same.

For classification, we have optimization problem,
$$
\min\limits_{w,b,\xi} = (\frac{1}{2} \mathbf{w}^T \mathbf{w} + \frac{C}{2} \sum\limits_{i=1}^{N} \xi_{i}^{2}), \quad s.t. \quad \forall i \in
[1,N], \quad y_{i} (\mathbf{w}^{T} \mathbf{x_{i}} + b) = 1 - \xi_{i}
$$
And the classification problem is performed as,
$$
y(\mathbf{x}) = sign(\mathbf{w}^{T}\mathbf{x} + b)
$$

And for regression problem, the optimization problem is,
$$
\min\limits_{w,b,\xi} (\frac{1}{2} \mathbf{w}^{T} \mathbf{w} + \frac{C}{2} \sum\limits_{i=1}^{N} \xi_{i}^{2} ), \quad s.t. \quad \forall i \in
[1,N], y_{i} = \mathbf{w}^{T}\mathbf{x_{i}} + b + \xi_{i}
$$
And the regression problem is performed as,
$$
y(\mathbf{x}) = \mathbf{w}^{T}\mathbf{x} + b
$$
