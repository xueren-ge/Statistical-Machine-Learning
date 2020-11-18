# Dimension Reduction
In this module, it introduces serveral common methods about dimension reduction.
* PCA
* MDS
* Isomap
* Locally Linear Embedding(LLE)

What people usually do to test your method is to use Swiss Roll.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/Swiss_Roll.jpg /></div>

Here, I used handwritten images to do some visualization about different dimension reduction methods. I generated more than 1000 samples which are 64 dimensional. Note that there are 5 classes.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/digits.jpg /></div>


## PCA
### Idea is to find approximation of data as
$$
x_{i} \approx \mu + \mathbf{A}\theta_{i}
$$
where, $k<<d$ and $A$ has orthonormal columns ($A^TA = I$). PCA mainly looks for the maximum variance.

### Definition of PCA
Principal COmponent Analysis consists in solving the problem,
$$
\mathcal{arg} \min\limits_{\mu, \mathbf{A}, \theta_{i}} \sum\limits_{i=1}^{N} \lVert x_{i}-\mu-\mathbf{A}\theta_{i} \rVert_{2}^{2}
$$

### Lemma
Assume $\mu$ and $\mathbf{A}$ are fixed, then, we can have,
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

### Visualization of PCA

I use PCA to reduce the dimension to 2, you can clearly see in each class, even with 2 dimension, it's clearly separated because
the 2 dimension consists of most infomation.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/PCA.jpg /></div>


## MDS
### Dissimilarity Matrix
A dissimilarity matrix $\mathcal{D}=[d_ij] \in \mathbb{R}^{NxN}$ satisfies,
$$
\forall i,j, d_ij \geq 0, d_ij = d_ji, d_ii
$$
In MDS, the goal is to find dimension $k << d$ and $\left\lbrace x_{i} \right\rbrace_{i=1}^{N} \in \mathbb{R}^{k}$ s.t. $\rho(x_i, x_j) \approx d_ij$

### Algorithm
Assume $D$ is completely known and  $\rho(x_i, x_j) = \lVert x-y \rVert_{2}$. The algorithm is to create embedding $X \in \mathbb{R}^{KxN}$
* Form $B=-\frac{1}{2}HD^{2}H$ where $H=\Iota-\frac{1}{N}\mathbb{1}\mathbb{1}^T$
* Compute eigen decomposition $B=V \Lambda V^T$
* Return $X = (V_k \Lambda_{k}^{\frac{1}{2}})^T$

### Visualization of MDS
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/mds.jpg /></div>

## Isomap
### Visualization of Isomap
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/Isomap.jpg /></div>

## LLE
### Visualization of LLE
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Dimension%20Reduction/lle.jpg /></div>
