# This section focuses on Perceptron Learnign Algorithm(PLA)

If we have a linearly separarable dataset, we can always identify a separating hyperplane to separate them.
The principle of this algorithm is the following.

* start from a guess ![equation](https://latex.codecogs.com/gif.latex?\theta)
* For ![equation](https://latex.codecogs.com/gif.latex?j&space;>&space;1), iterate over the data points (in any order) 
and update

    $$
    \mathop{min}_{w,b} \frac{1}{2} \left\| \mathbf{w} \right\|_2^2, \quad s.t. \left\{
        \begin{array}{lr}
            \mathbf{w^{T}} \mathbf{x_{i}} +b -y_{i} - \epsilon \leq 0\\
            -\epsilon - \mathbf{w^{T}} \mathbf{x_{i}} - b +y_{i} \leq 0   
        \end{array}
        \right.
    $$
