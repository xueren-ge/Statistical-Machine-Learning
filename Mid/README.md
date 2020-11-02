# Midterm Problem 3: Playing with classifiers
The Midterm is in **'ECE6254-Midtermv1.0.pdf'**. However, I just uploaded the Problem 3, the programming part.
If you are interested in the rest part (mainly mathmatical problems), please feel free to contact me.

I have to highlight that this part just programs **on the basis of math**. No just import packages. If there are 
any confusion about the principles, see **http://bloch.ece.gatech.edu/ece6254fa20/ece6254fa20_lectures.html**, my
instructor's website.

The scope contains 'KNN', 'Bayes', 'Gaussian Naive Bayes', 'LDA', 'Logistic Regression' and 'QDA'. In problem3,
I almost implemented all these following the fundemental mathmatical principles. Of course, the easiest way is to
import packages from sklearn. The corresponding results are shown below.

## [Q1] Generate 2 Guassian distribution dataset

Here, I generated 100 feature vectors in total according to the distribution
$\mathcal{P}(y=0) = \frac{1}{3}$, $\mathcal{P}(y=1)= \frac{2}{3}$, this means I the number of labeled 0 data is
33 and the number of labeled 1 is 67.

Besides, $p(x|y=0) \sim \mathcal{N}\left( \mu_{0} =[0,1]^{T}, \Sigma_{0}=\begin{bmatrix} 4 & 0\newline 0 & 2 \end{bmatrix} \right)$,
$p(x|y=1) \sim \mathcal{N}\left( \mu_{0} =[0,-2]^{T}, \Sigma_{0}=\begin{bmatrix} 1 & 0\newline 0 & 1 \end{bmatrix} \right)$, the generated 
data is shown in the sketch below.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q1.jpg /></div>

## [Q5] Bayes Classifier 
We all know that Bayes classifier is $h^{B}(x) = \mathop{argmax}\limits_{k} \eta_{k}(x)$. What I did is to calculate 
$\eta_{0}(x)$ and $\eta_{1}(x)$, then compare them. The larger is the predicted label. And the testing risk of Bayes classifier is 0.0973.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q2.jpg /></div>

## [Q6] K-NN Classifier
For KNN classifier, the only thing we should care is to set parameter k to avoid it underfitting or overfitting, in this example,
when I set k as 15, I found there are still islands, so in order not to overfitting, I set it as 10. So the decision boundary is smoother.
And the testing risk of KNN classifier is 0.1479. 
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q3.jpg /></div>

## [Q7] LDA Classifier
The assumption of LDA is **Given y, the feature vector have a Gaussian distribution $P_{x|y} \sim \mathcal{N}(\mu_{k},\Sigma)$**, Note that
$\Sigma$ is independent of $k$. This is extremely important because this is the only difference between LDA and Naive Bayes. In Naive Bayes,
we have the assumption that **Give $y$, the feature vector $\left\lbrace x_{i} \right\rbrace_{i=1}^{d}$ are independent**, we have **$P_{x|y} = \prod_{i=1}^{d}
P_{x_{i}|y}$**
And the testing risk of LDA classifier is 0.1843.
![LDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q4.jpg)

## [Q8] QDA classifier
![QDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q5.jpg)

## [Q9] Logistic Regression Classifier
![LDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q6.jpg)

## [Q10] Gaussian Naive Bayes Classifier
![GBN Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q7.jpg)
