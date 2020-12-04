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

Use the KKT conditions, you will find that the optimization problem can also been written as,

$$
\begin{bmatrix}
0 & \mathbf{y}^T \newline
\mathbf{y} & \mathbf{M}
\end{bmatrix}
%
\begin{bmatrix}
b \newline
\mathbf{\alpha}
\end{bmatrix}
%
=\begin{bmatrix}
0 \newline
\mathbf{1}
\end{bmatrix}
$$
where, $\alpha$ is the Lagrangian Mutiplier, $\mathbf{M} = \Omiga + \frac{1}{C} \mathbf{I}$, $\mathbf{I}$ is an identity matrix, and the components of
$\Omiga$ are $\Omiga_{ij} = y_{i}y_{j} \mathbf{x_{i}}^{T} \mathbf{x_{j}}$

And for regression problem, the optimization problem is,
$$
\min\limits_{w,b,\xi} (\frac{1}{2} \mathbf{w}^{T} \mathbf{w} + \frac{C}{2} \sum\limits_{i=1}^{N} \xi_{i}^{2} ), \quad s.t. \quad \forall i \in
[1,N], y_{i} = \mathbf{w}^{T}\mathbf{x_{i}} + b + \xi_{i}
$$
And the regression problem is performed as,
$$
y(\mathbf{x}) = \mathbf{w}^{T}\mathbf{x} + b
$$
