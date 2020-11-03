# HW#2 Problem 2: Learning tradeoff on MNIST dataset

Tradeoff is espically important in machine learning. It's balance between underfitting and overfitting.  Overfitting means
your model just remembers the training dataset, when encountering unseen samples, it has no ability to do prediction.
On the contrary, underfitting means your model not fits data so good, its generate ability is not good.
Actually, we have proved PAC Learnibility mathmatically. 

In Problem2, we are asked to play with MNIST dataste using KNN. By adjusting parameter 'k', you can roughly think that
you are using different hypothesis. The main tasks are as follows,

## [Q1] Load the MNIST dataset

  Just load in '8' and '9' labeled dataset. As is shown in the picture,
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%232/Q1.jpg /></div>

## [Q2] Run KNN with K=4 and compute the empirical risk

  Here, I selected first 3000 pictures as my training dataset and subsequent 4000 pictures as test dataset. And I calculated the ratio of each class’s total amounts. As is shown in the table, the ratio fluctuates around 50%. Hence, classes contain roughly the same number of images.
  
<table style="width:100%" text-align: center>
  <tr>
    <th width=10%, bgcolor=yellow >Label</th>
    <td>'8'</td>
    <td>'9'</td>
  </tr>
   <tr>
    <th width=10%, bgcolor=yellow >Ratio</th>
    <td> 0.487</td>
    <td> 0.513</td>
  </tr>
</table>

After computation, Empirical Risk is: 0.008333333333333333, and Test Risk is: 0.01575. There are some examples which are incorrectly classified, which shows in Figure below. As we can see from these incorrectly classified samples, it’s even hard for people to distinguish these figures. And the handwriting is very sloppy, the strokes are either crossed (b) or twisted together (c). Some part of figure even exceeds the range (d). Thus, it’s difficult to extract some distinct feature, which indicates that it’s difficult to classify.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%232/Q2.jpg /></div>

## [Q3] Set K from 1 to 10 and find the tradeoff

We can see the tradeoff between underfitting and overfitting.

When K is set under 2, the trending of test risk goes up because it’s overfitting but the trending of Empirical Risk continues going down. The KNN classifier just memorizes the training dataset thus Empirical Risk is smaller but when on testing dataset, its performance is not as good as expected. For example, when k=1, the nearest point is itself, which means that it just memorizes the training dataset.

When K is set below 2, the trending of Test Risk and Empirical Risk both goes down because it’s underfitting. We haven’t trained the best model h∗ from our training dataset.

So, the tradeoff point is to set K=2, where the Test Risk is the local minimal and Empirical Risk is fairly small.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%232/Q3.jpg /></div>

## [Q4] Reduce the dimension

Here I used Isomap transformation.
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%232/Q4.jpg /></div>

## [Q5] Use KNN to do prediction on reduced-dimensional data

Figure shows testing dataset that are correctly classified using the Isomap transformed learned earlier.
After calculation, the ratio of correctly classified data is: 0.98425
<div align=center><img src =https://github.com/masqueraderx/Statistical-Machine-Learning/blob/main/HW%232/Q5.jpg /></div>
