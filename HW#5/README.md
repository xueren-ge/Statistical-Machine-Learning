# HW#5 Problem 1: Federalist papers

Actually it's a classical nature language processing -- **'Bag of Words'**. The main idea of 'Bag of Words'
is to consider the frequency of appearance of each word in dictionary. Note that the dictionary here is
total collection of appearance of words in training dataset. 

The model used to solve 'Bag of Words' is **'Naive Bayes'**. What I did in the programming is nothing but
calculate the postprior probability and compare with each other. Besides, I also used **'Lapalace Smoothing'** to 
eliminate the zero probability (when test dataset have words which never appear in training dataset).

The following logistic steps may help you understand 'Naive Bayes', for more details, please refer to
my instructor (Matthieu Bloch)'s website(http://bloch.ece.gatech.edu/ece6254fa20/ece6254fa20_lectures.html)

* Establish the dictionary
* Count the frequency of each word in each paper and form the feature vectors
* Compute MLE of paper classes
* Compute MLE of probability that word j occurs in class k across all papers
* Run classifier

Note that Lapalace Smoothing is used in step 4.
