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

## [Q3] Set K from 1 to 10 and find the tradeoff

## [Q4] Reduce the dimension

## [Q5] Use KNN to do prediction on reduced-dimensional data
