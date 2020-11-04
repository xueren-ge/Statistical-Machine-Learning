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
