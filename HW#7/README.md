# HW#7 Problem 1: Support vector regression

Note that in this assignment the programming part is **Q[26] - Q[29]**

Mathmatically speaking, this assignment focuses on **contrained optimization problems**. The mathmatical theories
you should master is basics about **Convex Optimization**, such as Lagrangian, KKT conditions, primal, dual problems and etc.

## [Q25] Set up the SVR classifier
  Note that C is the penalty factor, it shows the tradeoff between finding a hyperplane and minimizing the misclasscification,
If C is small, we put more weight on finding a hyperplane. Otherwise, we put more weight on minimizing the misclasscification.

## [Q26] Set the model with parameter = 100
Note that it draws the support vector and maximum maigin hyperplane.
![Q26](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%237/Q26.jpg)

## [Q27] Set the model with parameter = 50
Actually, you can find that with this parameter(50), the algorithm never converges. In order to
solve this problem, I set the maximum iterations, in the picture below you can clearly it still
hasn't converged.
![Q27](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%237/Q27.jpg)

## [Q28] Set the model with parameter = 190
In this situation, you will find the maximum margin hyperplane is two far from the data.
Actually, it's underfitting, it's not a good model because this classifier can't do prediction very well.
![Q28](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%237/Q28.jpg)

## [Q29] Set the model with parameter = 250
In this situation, there's even no support vector because the model is underfitting. Similarly, it's not
a good model because this classifier can't do prediction very well.
![Q29](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%237/Q29.jpg)
