# This section focuses on Perceptron Learnign Algorithm(PLA)

If we have a linearly separarable dataset, we can always identify a separating hyperplane to separate them.
The principle of this algorithm is the following.

* start from a guess ![equation](https://latex.codecogs.com/gif.latex?\theta)
* For ![equation](https://latex.codecogs.com/gif.latex?j&space;>&space;1), iterate over the data points (in any order) 
and update

$$
\theta^{j+1} = \left\lbrace
\begin{array}{lr}
\theta^{j} + y_{i}x_{i},\quad \textrm{if } y_{i} \neq sgn(\theta^{(j)^{T}} x_{i}) \newline
\theta^{j}, \qquad\quad\quad \textrm{else}
\end{array}
\right.
$$

## Generate Dataset
First, I generate 2-dimensional Gaussian distribued classes, which each contains 50 points.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/PLA/data.jpg /></div>

## Initialize $\theta$
In the Picture below, I initialized $\theta^{0}$, and the classifier looks awful. Because it's nearly
vertical to the whole plane.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/PLA/before.jpg /></div>

## Use formula update $\theta$
After the final iteration, the classifier looks not so bad, as is indicated in sketch below
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/PLA/after.jpg /></div>
