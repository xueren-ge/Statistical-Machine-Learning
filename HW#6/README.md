# HW#6 Problem 2: Solvers for logistic regression

There are two code files in this folder. HW#6 sketch.ipynb is not related to Problem 2.

Given data $\left\lbrace (\tilde{x_{i}}, y_{i})\right\rbrace_{i=1}^{N}$, the likelihood function $L(\theta) = \prod_{i=1}^{N} P_{\theta}(y_{i}|\tilde{x_{i}}) $
where, $\tilde{x} \in \mathcal{R}^{d+1}$, one more dimension is add 1 to $d$-dimension feature vector.

And the loglikelihood is $\ell(\theta) = \sum\limits_{i=1}^{N}[y_{i} \theta^{T} \tilde{x_{i}} - \ln (1+e^{\theta^{T} \tilde{x_{i}} }) ]$, If we take the deravitive 
with respect to $\theta$, namely $\nabla_{\theta} \ell(\theta) = 0$, we can have,
$$
\sum\limits_{i=1}^{N} \tilde{x_{i}} (y_{i}-\frac{1}{1+exp(-\theta^{T}\tilde{x_{i}})}) = 0
$$
Clearly, $\tilde{x_{i}} \in \mathcal{R}^{d+1}$ but $y_{i}-\frac{1}{1+exp(-\theta^{T}\tilde{x_{i}})} \in \mathcal{R}$. We can $d+1$ variables but $d$ functions.
Such problem can be solved by numerical methods.

In Gradient descent.ipynb, we mainly uses three numerical methods to compute MLE of Logistic Regression(LR).

* Gradient Descent

  Manually setting step size, in every iteration, we use the whole training dataset to update the parameter of LR.
It's advantage is it's more precise to compute the gradient but it's slow.
  
* Newton's Method

  Mathmatically speaking, it's the most precise way to compute the gradient because it deduced the stepsize
which is so called 'Hessian Matrix'. Compared with other 2 methods, it's huge slow in in terms of speed 
but it's the most precise.

* Stochastic Gradient Descent
  
  Instead of using the whole traning dataset to compute gradient, it randomly picks up a data from traning dataset
and uses it to compute gradient. You will find the descendent process is quite fluctuating and we have to set 
extraly a parameter to avoid it jumping out of the iteration loop too early. Technically speaking, it needs more
iterations to converge but it's fast in terms of speed. Actually it's suitable for real-time learning.
