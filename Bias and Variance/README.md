# Bias and Variance

##  The Bias–Variance Decomposition
### Setup for analysis
* $\mathcal{h}: \mathcal{R}^d \to \mathcal{R}$: unknown target function
* Dataste $\mathcal{D} = \left\lbrace (x_i, y_i) \right\rbrace_{i=1}^{N}, x_{i} \in \mathcal{R}^{d}, y_{i} = \mathcal{h}(x_{i}) + \epsilon_{i} \in \mathcal{R}$
(regression, $\epsilon ~ \mathcal{N}(0, \sigma_{\epsilon}^{2})$)
* $\hat{h}_{D}: \mathcal{R}^{d} \to \mathcal{R}$: choice of function in $\mathcal{H}$ selected using $\mathcal{D}$
* Squared error for fixed $\hat{h_{D}}$ is,
$$
R(\hat{h}^{D}) = \mathcal{E}_XY \left\[ (\hat{h_{D}}(x) -Y)^{2}\right\]
$$
