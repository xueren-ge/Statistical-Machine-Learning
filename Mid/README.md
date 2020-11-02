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
$\Sigma$ is independent of $k$. This is extremely important because this is the only difference between LDA and Naive Bayes. 

In Naive Bayes, we have the assumption that **Give $y$, the feature vector $\left\lbrace x_{i} \right\rbrace_{i=1}^{d}$ are independent**, 
we have **$P_{x|y} = \prod_{i=1}^{d} P_{x_{i}|y}$**.

In Naive Bayes, if the distribution conforms to Gaussian ditribution, then **the mean and covariance matrix must both be class independent**
However, in LDA, **the mean is class dependent but covariance matrix is class independent**

Here, I calculated the Maximum Likelihood Estimator(MLE) of LDA parameter, and have that,
$$
\hat{\pi_{k}} = \frac{N_{k}}{N}
$$
$$
\hat{\mu_{k}} = \frac{1}{N_{k}} \sum\limits_{i:y_{i}=k} x_{i}
$$
$$
\hat{\Sigma} = \frac{1}{N} \sum\limits_{k=1}^{K-1} \sum\limits_{i:y_{i}=k} (x_{i}-\hat{\mu_{k}})(x_{i}-\hat{\mu_{k}})^{T}
$$
Then, we just use these paramater to plug into the Bayes Classifier. And we have,
$$
h^{LDA}(x) = \mathop{argmin}\limits_{k} (\frac{1}{2}(x-\hat{\mu_{k}})(x-\hat{\mu_{k}})^{T}-\ln \hat{\pi_{k}})
$$
And the testing risk of LDA classifier is 0.1843.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q4.jpg /></div>

## [Q8] QDA classifier
A QDA classifier is similar to an LDA classifier, but the **covariance matrices of the generative distributions are now allowed to depend on the class label**.
And the testing risk of QDA classifier is 0.1078.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q5.jpg /></div>


## [Q9] Logistic Regression Classifier
For logstic regression, things seem to be a little complicated. Since in this problem, data conforms to Gaussian distribution.
In tools of Maximum Likelihood Estimator(MLE), we can deduce 2 parameter $\hat{w}$ and $\hat{b}$.
$$
\hat{w} = \hat{\Sigma}^{-1} (\hat{\mu_{1}} - \hat{\mu_{0}})
$$
$$
\hat{b} = \frac{1}{2} \hat{\mu_{0}}^{T} \hat{\Sigma}^{-1} \hat{\mu_{0}} - \frac{1}{2} \hat{\mu_{1}}^{T} \hat{\Sigma}^{-1} \hat{\mu_{1}} + \frac{1}{2} \ln
\frac{\hat{\pi_{1}}}{\hat{\pi_{0}}}
$$
Note that $\hat{\mu_{0}}, \hat{\mu_{1}}, \hat{\pi_{0}}, \hat{\pi_{1}}, \hat{\Sigma}$ is caculated according to MLE of LDA.

And the testing risk of Logistic Regression classifier is 0.1182.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q6.jpg /></div>

## [Q10] Gaussian Naive Bayes Classifier
About Gaussian Naive Bayes, i still highlight that the basic assumption **Give $y$, the feature vector $\left\lbrace x_{i} \right\rbrace_{i=1}^{d}$ are independent**, we have **$P_{x|y} = \prod_{i=1}^{d} P_{x_{i}|y}$**.

Beyond this, I also calculated the MLE of Gaussian Naive Bayes Classifier. There are two parameters here,
$$
\pi_{k} = \frac{N_{k}}{N}
$$
where, $N_{k} = |\left\lbrace i \in [1,N]: y_{i}=k \right\rbrace| = \sum\limits\_{i=1}^{N} \mathcal{l} \left\lbrace y_{i}=k \right\rbrace$, $\mathcal{l}$ here is
the loss function (Here I used Indicator function as loss function).
$$
\hat{P_{x_{j}|y}(\ell|k) = \frac{N_{\ell,k}^{(j)}}{N_{k}}}
$$
where, $N_{\ell,k}^{(j)} = | \left\lbrace x:y=k and x_{j}=\ell \right\rbrace  |$

Then we just plug into the Bayes classifier, we have Naive Bayes Estimator,
$$
h^{NB}(x) = \mathop{argmax}\limits_{k} \hat{\pi_{k}} \prod\limits_{j=1}^{d} \hat{P_{x_{j}|y}}(x_{j}|k)
$$

<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/Mid/Q7.jpg /></div>
