# Bias and Variance

##  The Bias–Variance Decomposition
### Setup for analysis
* $\mathcal{h}: \mathcal{R}^d \to \mathcal{R}$: unknown target function
* Dataste $\mathcal{D} = \left\lbrace (x_i, y_i) \right\rbrace_{i=1}^{N}, x_{i} \in \mathcal{R}^{d}, y_{i} = \mathcal{h}(x_{i}) + \epsilon_{i} \in \mathcal{R}$
(regression, $\epsilon \sim \mathcal{N}(0, \sigma_{\epsilon}^{2})$)
* $\hat{h}_{D}: \mathcal{R}^{d} \to \mathcal{R}$: choice of function in $\mathcal{H}$ selected using $\mathcal{D}$
* Squared error for fixed $\hat{h_{D}}$ is,
$$
R(\hat{h}^{D}) = E_{XY} \left\[ (\hat{h_{D}}(x) -Y)^{2}\right\]
$$

Thus, we can have ,
$$
E_{D} \left\[ R(\hat{h_{D}}) \right\] = \sigma_{\epsilon}^{2} + E_{x} \left\[ Var(\hat{h_{D}}(X))|X \right\]+E_{X} \left\[ Bias(\hat{h_{D}}(X))^{2}|X \right\]
$$
with,  $Var(\hat{h_{D}}(X)) = E_{D} \left\[ ( \hat{h_{D}}(X) - E_{D}\left\[ \hat{h_{D}}(X) \right\]   )^{2} \right\]$ and 
$Bias(\hat{h_{D}}(X)) = E_{D}\left\[ \hat{h_{D}}(X) \right\] - \mathcal{h}(X)$. Note that $\sigma_{\epsilon}^{2}$ is noise here.

## The Bias-Variance Tradeoff

The tradeoff is how much complexity you set for your model. As the model complexity increases, we have far and far away from the true model,
the bias increases but the variance is no doubt decreases. On the contrary, if the model complexity decreases, we are more and more close to
the model, the bias is getting small but the variance getting larger.

## Visualization

Here I generated the true model as $\mathcal{h}(x) = sin(\pi x$. And we consider two models here,
* $\mathcal{H_{0}}: h(x) = b$, horizontal line
* $\mathcal{H_{1}}: h(x) = ax + b$, any line
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Bias%20and%20Variance/F1.jpg /></div>


for any two point $(x_{0},y_{0}), (x_{1},y_{1})$ with $x_{1} > x_{0}$
* For $\mathcal{H_{0}}$, find the horizontal line with $b=\frac{x_{0}+x_{1}}{2}$
* For $\mathcal{H_{1}}$, find the line going through both points

<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Bias%20and%20Variance/F2.jpg /></div>

### Low variance with large bias

Here I run 1000 times for the first model $\mathcal{H_{0}}$, the results are shown below. Clearly, the variance is pretty small, all the horizontal
lines are restricted within $[-1,1]$. However, the bias is huge because you can see that the red line (Average) lies nearly in 0. It means generally,
all the model doesn't catch up the trend of target function $sin(\pi x)$.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Bias%20and%20Variance/F3.jpg /></div>

### Low bias with large variance

Similarly, I run 1000 times for the first model $\mathcal{H_{1}}$, and the variance is pretty huge, because the slope of line doesn't get constrained.
However, the bias is relatively small, because the average(red line) follows the trend of target function $sin(\pi x)$.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Bias%20and%20Variance/F4.jpg /></div>

### Regularization

Here, I used ridge regression to regularize the optimization. The results are obvious. You can see that the variance is smaller because all the
lines shown in x coordinates $[-1,1]$ are restricted within y coordinates $[-1,1]$. Meanwhile, the slope of the average (red line) is not 0 any more,
it starts to follow the trend of target function $sin(\pi x)$.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Bias%20and%20Variance/F5.jpg /></div>
