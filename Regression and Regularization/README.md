# Regression and Regularization

This chapter focuses on regression problem. As for principle of regression, I omit it here because I 
want to pay more attention to the overfitting problem.

## What Overfitting?

Overfitting describes the situation when fitting the data well on longer ensures that the out-of-sample, namely,
generalization error is small. To be more specfic, when the model complexity increases (especially model degree),
the bias curve (empirical risk, or to say your training model may approaches the true model) is getting smaller and
smaller, but the variance curve (true risk) is getting larger and larger.

## Why Overfitting.
* when there are too many degrees of freedom in model (the model learns the noise, not target function $f$).
* When hypothesis set contains simpler functions than targer function $f$ but few samples
To illustrate 2 point above, I generate 5 point according to target function $f(x) = x^{2} + n$, where, 
$n ~ \mathcal{N} (0, \sigma = 0.1)$
