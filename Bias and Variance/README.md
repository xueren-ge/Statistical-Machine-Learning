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
E_{D} \left\[ R(\hat{h_{D}) \right\] = \sigma_{\epsilon}^{2} + E_{x} \left\[ Var(\hat{h_{D}(X)})|X \right\]+E_{X} \left\[ Bias(\hat{h_{D}}(X))^{2}|X \right\]
$$
with,  $Var(\hat{h_{D}(X)}) = E_{D} \left\[ ( \hat{h_{D}}(X) - E_{D}\left\[ \hat{h_{D}}(X) \right\]   )^{2} \right\]$ and
$Bias(\hat{h_{D}(X)}) = E_{D}\left\[ \hat{h_{D}}(X) \right\] - \mathcal{h}$

