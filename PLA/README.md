# This section focuses on Perceptron Learnign Algorithm(PLA)

If we have a linearly separarable dataset, we can always identify a separating hyperplane to separate them.
The principle of this algorithm is the following.

* start from a guess ![equation](https://latex.codecogs.com/gif.latex?\theta)
* For ![equation](https://latex.codecogs.com/gif.latex?j&space;>&space;1), iterate over the data points (in any order) 
and update

$$
\theta^{j+1} = \left\lbrace
\begin{array}{lr}
\theta^{j} + y_{i}x_{i}, & \textrm{if } y_{i} \neq sgn(\theta^{(j)^{T}} x_{i}) \newline
\theta^{j}, & \textrm{else}
\end{array}
\right.
$$
