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

You can clearly see that there is a tradeoff between the optimization function. By adjusting $\lambda$, we can decide whether to focus on
minimizing the loss function or finding a regression function.

## Visualization

To illustrate 2 point in the Why Overfitting section, I generate 5 point according to target function $f(x) = x^{2} + n$, where, 
$n \sim \mathcal{N} (0, \sigma = 0.1)$, and $x \in [-1,1]$. Note that $n$ is the noise here. As is shown in the sketch below,
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q1.jpg /></div>

Then I set degree to 6, since we only have five points, there exists a degree six polynomial that predicts exactly the
value of all five training point. This is an example where our regression is effectively learning the noise in the model.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q2.jpg /></div>

I set polynomial of degree to 1 and get regression results for twenty randomly sampled sets of five points. Clearly, if 
we doesn't use regularization, there's a huge variance in predictor, suggesting that we have an unstable prediction that does not 
generalize well.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q3.jpg /></div>

Still run the 3rd experiment but here I used ridge regression. Note that ridge regression just penalizes $\beta$ in the function,
it doesn't penalize the offset $\beta_{0}$. Compared with 3rd experiment, you can find the variance is getting smaller, actually, 
all the straight lines seem to forward towards certain degrees. More generally, the scope is constrained. That's how regularization
helps. And there are many ways to regularize, such as **Tikhonov regularization**, **LASSO regularization** and etc. Note that 
kernelization can be achieved.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Regression%20and%20Regularization/Q4.jpg /></div>

## Some Regularization
### Tykhonov Regularization
We introduce a penalty term to 'regularize' the vector $\theta$,
$$
\theta = \mathcal{argmin_{\theta}} \lVert y-X\theta\rVert_{2}^{2} + \lVert \Gamma \theta \rVert_{2}^{2}
$$
We can solve this optimization problem by Lagrangian, the solutions turn to
$$
\hat{\theta} = (X^TX+\Gamma^T\Gamma)^{-1}X^Ty
$$
Special case: If $\Gamma = \sqrt{\lambda}I$, and the first column first row element is set to 0, This means we don't penalize the
offset $\beta_{0}$, we only penalize $\beta$. This is so-called **'Ridge Regression'**.
Note that Tykhonov Regularization is a shrinking estimator.

### LASSO Regularization
Instead of using norm 2, here we use norm 1
$$
\hat{\theta} = \mathcal{argmin_{\theta}} \lVert y-X\theta\rVert_{2}^{2} + \lVert \Gamma \theta \rVert_{1}
$$
The main benefit to introduce norm 1 is that the solution promotes **sparsity**.
