# Introduction

Postpartum, or peripartum depression is a mix of physical and mental changes that happen to many women after birth. It is classified as a major depression, and is diagnosable. Some symptoms that accompany Postpartum depression are depressed mood, mood swings, feelings of hopelessness or disconnect to your children, anxiety and panic attacks, and much more. According to the American Psychiatric Association, an estimated one in seven women experiences peripartum depression. This is a significant amount of women, and now more than ever they are coming forward and sharing the difficulties they are facing. One outlet women who have experiences with this is to post in the Reddit subreddit, “PostPartum_Depression”. Here they can share frustrations and ask for advice with any issues related to postpartum depression. As a group, we all know people who have struggled in some way with this issue, and we were interested in exploring the subreddit and see if we could find similarities between the posts. One common issue we found in many of the posts was 

#we fixed the downsample issue
#description of columns in dataframe
#what is the research question

# Data Cleaning

# Exploratory Data Analysis

To better visualize the test that we were working with we did a number of exploratory tests including creating word clouds, polarity, and assessing readability. 

In making a word cloud for posts classified as complaining about body image issues and post classified as not complaining about body image issues, it shows what words are commonly being used. This way we know that words like feel, like, and baby are commonly used in both classifications. We can then use this knowledge to choose what words we want to include in the model. 

When we look at polarity we can see that the most positive reviews are neutral and negative. This makes sense when we consider that this subreddit is about depression. We can also see that the posts with the lowest polarity are never negative. By running these tests we can see that the posts classified as complaining about body image issues are less positive than the other ones.

Finally we looked at the readability of the posts. All of the posts have similar readability scores and are written at about a 6th to 7th grade level. 

# Methods and Research

### To add pictures add the file to github then use this code where you want it to be ![plot](myimage.png)

To begin our model building, we split the data into test and training sets on an 80/20 split. We then decided to run it through Naive Bayes, logistic regression, gradient boosting, decision tree, and random forest classifying models. Given the graphic below, we decided to see how we could alter the random forest model to better predict our data. It’s area under the curve was the largest at .83 which gave us hope that we could use random forest classification to create an effective model. 

However, upon further looking into the results of the  model, we saw that while it was perfectly predicting the negative cases (posts without body-image issue words), it had a sensitivity of .12. While we tried to alter the threshold to optimize our results, we realized that to gain more sensitivity, we would have to sacrifice precision. 


We began altering the threshold of the random forest model to get a better sensitivity while still maintaining a reasonable specificity. We found that a threshold of .1 gave us a sensitivity of 0.85 and a specificity of 0.6. We were much happier with this result and the model’s improved ability to recognize posts with possible body image concerns. 

There are many advantages to the random forest classifier. It has less variance than other “tree” methods due to the independence of each tree from other trees in the method and takes various steps to ensure accuracy and avoid bias.  Each tree creates its model on a random sample from the training data. This uncorrelated forest performs predictions as a crowd, like a committee of decision makers. This avoids overfitting since the trees are independent from one another and creates a more robust model. The random forest method was also preferable because in our case, we didn’t have a huge dataset, so we could take the time to run a random forest. By using a tree method, we are still able to maintain the explainability and interpretability that they have to offer, but avoid the variation found in other methods. Once we fit the model to our liking, we were able to look at the important features of the model.

 
This graph shows which words were most important in the decision making process. Even comparing the important features of this model to another, like Bayes, we saw vital differences in features that just made more sense to how we thought it would predict. For example, our Naive Bayes model listed “feel” as its most important feature. This felt arbitrary to us because we assumed most people on the forum were indeed talking about their feelings, regardless of the topic. While we were sure this word would occur in our positive grouping of posts, we were disappointed to see it as the most important feature. However, in our fitted random forest model, “food” was the most important feature. This aligned with our expectations and it was cool to see that our model could pick that up. 

In response to the research question, “can we accurately predict which posts will discuss body image issues?” We are pleased with our outcome. Once you start applying the scientific method outside of a controlled setting, it is easy to get upset by results seeming insignificant or research not panning out the way you thought it would. Our biggest limitations in this research were that we did not have data on the people posting that we could draw conclusions from, we had to rely on the words only. Because of this, we had to focus on the question of the content of the posts and not on the state of mind of the posters. We chose words that we thought would indicate the type of post we were trying to identify, but there are likely many manifestations of these feelings that we probably missed out on just due to our target variable definition. Another limitation we faced with text data on a forum is that there was slang and typos that the lemmatization process could not fully account for. As we ran our model, it became difficult to decide which words we should take out (beyond the stop words used initially) because we wanted to preserve the process but also get informative results. There are certainly more features we could have removed to extract more meaningful words, but we decided to trust the process where we were at and decipher why the words we ended up with would be most informative in the model’s predicting process. 

# Conclusion

In conclusion, we were able to find the most important word to predict post that contain complaints about negative body image issues but the model was uninterpretable and our model does contain some limitations. The most important words in order of importance were, feel, like, im, time, baby, get, want, know, day, even, would, go, dont, one, husband, month, make, cry, and could. One limitation of our model is that it is classified based off of the words in the post but we have no data on the actual person. Another limitation is that we can only predict the contents of the posts and not if someone actually have body image issues. Finally, our last limitation is that our best model is uninterpretable. 


