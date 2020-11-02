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
![Generated dataset](<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q1.jpg /></div>)

## [Q5] Bayes Classifier 
![Bayes Classifier](<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q2.jpg /></div>)

## [Q6] K-NN Classifier
![KNN Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q3.jpg)

## [Q7] LDA Classifier
![LDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q4.jpg)

## [Q8] QDA classifier
![QDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q5.jpg)

## [Q9] Logistic Regression Classifier
![LDA Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q6.jpg)

## [Q10] Gaussian Naive Bayes Classifier
![GBN Classifier](https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q7.jpg)
