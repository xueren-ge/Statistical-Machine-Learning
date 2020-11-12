# Dimensio Reduction
## PCA
### Idea is to find approximation of data as
$$
x_{i} \approx \mu + \mathbf{A}\theta_{i}
$$
where, $k<<d$ and $A$ has orthonormal columns ($A^TA = I$)

### Definition of PCA
Principal COmponent Analysis consists in solving the problem,
$$
\mathcal{arg}min\limits_{\mu, \mathbf{A}, \theta_{i}} \sum\limits_{i=1}^{N} \lVert x_{i}-\mu-\mathbf{A}\theta_{i} \rVert_{2}^{2}
$$

### Lemma
Assume \mu and \mathbf{A} are fixed, then, we can have,
$$
\theta_{i} = \mathbf{A}^T (x_{i} - \mu)
$$

### Lemma
Assume $\mathbf{A}$ is fixed and $\theta_{i} = \mathbf{A}^{T}(x_{i}-\mu)$, then we have,
$$
\mu = \frac{1}{N} \sum\limits_{i=1}^{N} x_{i}
$$

### Lemma
One possible choice of $\mathbf{A}$ is 
$$
\mathbf{A} = [u_{1},\ldots, u_{k}]
$$
where, $u_{i}$ is the eigenvectors corresponding to the $k$ largest eigenvalues of $S = \sum\limits_{i=1}^{N} x_{i}x_{i}^{T}$.

For specfic proof of three Lemma, please see notes.
