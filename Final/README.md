# Final Exam

## Problem 1: Least-Square Support Vector Regression

In this problem, we are asked to solve the quadratic optimization problems which are similar to SVM and SVR. However
they are not the same.

### Classcification

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
where, $\alpha$ is the Lagrangian Mutiplier, $\mathbf{M} = \Omega + \frac{1}{C} \mathbf{I}$, $\mathbf{I}$ is an identity matrix, and the components of
$\Omega$ are $\Omega_{ij} = y_{i}y_{j} \mathbf{x_{i}}^{T} \mathbf{x_{j}}$.

### regression

And for regression problem, the optimization problem is,
$$
\min\limits_{w,b,\xi} (\frac{1}{2} \mathbf{w}^{T} \mathbf{w} + \frac{C}{2} \sum\limits_{i=1}^{N} \xi_{i}^{2} ), \quad s.t. \quad \forall i \in
[1,N], y_{i} = \mathbf{w}^{T}\mathbf{x_{i}} + b + \xi_{i}
$$
And the regression problem is performed as,
$$
y(\mathbf{x}) = \mathbf{w}^{T}\mathbf{x} + b
$$

Similarly, use the KKT conditions, you will find that the optimization problem can also been written as,

$$
\begin{bmatrix}
0 & \mathbf{1}^T \newline
\mathbf{1} & \mathbf{M}
\end{bmatrix}
%
\begin{bmatrix}
b \newline
\mathbf{\alpha}
\end{bmatrix}
%
=\begin{bmatrix}
0 \newline
\mathbf{y}
\end{bmatrix}
$$
where, $\alpha$ is the Lagrangian Mutiplier, $\mathbf{M} = \Omega + \frac{1}{C} \mathbf{I}$, $\mathbf{I}$ is an identity matrix, and the components of
$\Omega$ are $\Omega_{ij} = \mathbf{x_{i}}^{T} \mathbf{x_{j}}$.

### Visualization of Regression Problem
#### Generate dataset
We consider a dataset consisting of 250 points $\lbrace x_{i} \rbrace$ uniformly sampled on the interval $[−7,7]$. 
The function to estimate is $f(x) = \frac{\sin(\pi x)}{(\pi x)}$, but we only get to observe $y_{i} = x_{i} + n_{i} $,
where $n_{i}$ is the realization of a zero-mean Gaussian noise with standard deviation $\sigma = 0.1$.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Final/Q1.jpg/></div>

#### Use from Sklearn.svm import SVR to solve optimization problem
use the hyperparameters epsilon=0.1, C=1e3, kernel=’rbf’ and gamma=0.25. And green line to indicate the prediction.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Final/Q2.jpg/></div>

#### Observe the Trend of Lagrangian Multiplier
Create a plot showing the absolute value of the 250 Lagrange multipliers in order of increasing magnitude
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Final/Q3.jpg/></div>

#### Write a classifier according to the optimization function above (matrix)
Implement a solver for the kernelized version of (7) using radial basis functions to implement (8).
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Final/Q4.jpg/></div>

#### Observe the Trend of Lagrangian Multiplier
Create a plot showing the absolute value of the 250 Lagrange multipliers in order of increasing magnitude.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Final/Q5.jpg/></div>

