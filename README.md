# Sentiment Analysis “Online Lectures ("Kuliah Online” in Bahasa)"

## Introductions
<p align = "justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In this project I do sentiment analysis on the topic “online lectures  (“kuliah online” in bahasa)”. The purpose is to know what is the opinion twitter users in Indonesia about online lectures (“kuliah online”) activity in Indonesia, whether is more “contra” than “pro” or otherwise ? Therefore I do analysis and classification (negative, neutral or positive) on each user tweets about  “online lectures  (“kuliah online” in bahasa)” in Indonesia.
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The data used in this project is 25.000 twitter data (tweets) that’s contain topic “kuliah online” which scraping with twitter scraping tool Twint (https://github.com/twintproject/twint). After that, I do preprocessing on tweets data and determine sentiment polarity of tweets with Indonesian Sentiment Lexicon (https://github.com/fajri91/InSet).  Data that has been determined, will be used for sentiment analysis with model recurrent neural network which is Long Short Term Memory (LSTM). 
</p>

## Results
<p align = "justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Results from sentiment analysis using LSTM model is very good, the model can classify tweets sentiment well. The accuracy of model LSTM with best hyperparameters which has been determined is around 90%. The following is a train and val accuracy from model that  I built :
</p>

<p align="center"> 
 <img src="images/train and val accuracy.png" /> 
 <br></br>
 Train and val accuracy
</p>

<p align = "justify"> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Can be seen from the picture above, train and val accuracy are not fluctuating and overfitting, so it can be said the model can classify    sentiment quite well. After the model is compiled, that model will be implemented on test set which has been partitioned before.
</p>

<p align="center"> 
 <img src="images/accuracy test data and confusion matrix.png" /> 
 <br></br>
 Model  accuracy on test data and confusion matrix
</p>

<p align = "justify"> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; From the picture above, model accuracy on test data (there are 4740 data) is very good which is around 91%. Can be seen on confusion matrix, the model can predict 2455 negative sentiments, 334 neutral sentiments and 1527 positive sentiments correctly. In the below picture there are some tweets with the sentiment polarity.
</p>

<p align="center"> 
 <img src="images/results on test data.png" /> 
 <br></br>
 Sentiment analysis results on test data
</p>

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
