# Regression and Regularization

This chapter focuses on regression problem. As for principle of regression, I omit it here because I 
want to pay more attention to the overfitting problem.

## What is Overfitting?

Overfitting describes the situation when fitting the data well on longer ensures that the out-of-sample, namely,
generalization error is small. To be more specfic, when the model complexity increases (especially model degree),
the bias curve (empirical risk, or to say your training model may approaches the true model) is getting smaller and
smaller, but the variance curve (true risk) is getting larger and larger.

## Why Overfitting?
* when there are too many degrees of freedom in model (the model learns the noise, not target function $f$).
* When hypothesis set contains simpler functions than targer function $f$ but few samples

## How to prevent Overfitting?
The answer is no doubt regularization. Except for optimizing the loss function, regularization also adds a penalty to
the optimization problem. It has the following form:
$$
\hat{\beta}, \hat{\beta_{0}} = \mathop{argmin}\limits{\beta,\beta_{0}} = \sum\limits_{i=1}^{N} \mathcal{L}(y_{i}-\beta^{T}x_{i}+\beta_{0})
+\frac{\lambda}{2} ||\beta||^{2}_{2}
$$
Note that $\mathcal{L}$ is general loss function, it can be SSE, mean absolute error, Huber loss, $\epsilon$-insensitive loss. 

To illustrate 2 point in the Why Overfitting section, I generate 5 point according to target function $f(x) = x^{2} + n$, where, 
$n \sim \mathcal{N} (0, \sigma = 0.1)$, and $x \in [-1,1]$. Note that $n$ is the noise here. As is shown in the sketch below,
![skecth](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q1.jpg)

Then I set degree to 6, since we only have five points, there exists a degree six polynomial that predicts exactly the
value of all five training point. This is an example where our regression is effectively learning the noise in the model.
![skecth](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q2.jpg)

