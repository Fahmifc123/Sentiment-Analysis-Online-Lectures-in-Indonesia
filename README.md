# Sentiment Analysis “Online Lectures ("Kuliah Online” in Bahasa)"

## Introduction
<p align = "justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In this project I do sentiment analysis on the topic “online lectures  (“kuliah online” in bahasa)”. The purpose is to know what is the opinion twitter users in Indonesia about online lectures (“kuliah online”) activity in Indonesia, whether is more “contra” than “pro” or otherwise ? Therefore I do analysis and classification (negative, neutral or positive) on each user tweets about  “online lectures  (“kuliah online” in bahasa)” in Indonesia.
 <br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The data used in this project is 25.000 twitter data (tweets) that’s contain topic “kuliah online” which scraping with twitter scraping tool Twint (https://github.com/twintproject/twint). After that, I do preprocessing on tweets data and determine sentiment polarity of tweets with Indonesian Sentiment Lexicon (https://github.com/fajri91/InSet).  And the last, I do sentiment analysis using one of the types model recurrent neural network which is Long Short Term Memory (LSTM) and then do hyperparameters tuning to get the best hyperparameters and improve the accuracy of the model.
</p>

## Results
<p align = "justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Results from sentiment analysis using LSTM model is very good, the model can classify tweets sentiment well. The accuracy of model LSTM with best hyperparameters on validation data which has been determined is around 90%. The following is a train and val accuracy from model that  I built :
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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; From the picture above, model accuracy on test data (there are 4740 data) is very good which is around 91%. Can be seen on confusion matrix, the model can predict 2455 negative sentiments, 334 neutral sentiments and 1527 positive sentiments correctly. In the table below, there are some tweets with the sentiment polarity.
</p>

<p align="center"> 
 Sentiment analysis results on test data
 <img src="images/results on test data.png" /> 
 <br></br>
</p>

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Summary
The following is a summary of what was done in this project:

#### - Data Scraping
<p align = "justify"> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Scraping 25.000 tweets data that contain “kuliah online” using Twint. Twint is an advanced Twitter scraping tool written in Python that allows for scraping Tweets from Twitter profiles without using Twitter's API (https://github.com/twintproject/twint).
</p>
<p align="center"> 
 25.000 tweets data
 <img src="images/25k tweets data.png" /> 
 <br></br>
</p>
<br></br>

#### - Data Preprocessing
<p align = "justify"> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In this step I do preprocessing on tweets data, which is cleaning, casefolding, tokenizing, filtering dan stemming text and then delete duplicate or spam tweets. 
</p>
<p align="center"> 
 Preprocessed tweets data
 <img src="images/preprocessed tweets data.png" /> 
 <br></br>
</p>
<br></br>

#### - Determine Polarity of Tweets with Indonesian Sentiment Lexicon
<p align = "justify"> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Data that has been preprocessed, will determine the sentiment polarity by using Indonesia Sentiment Lexicon (https://github.com/fajri91/InSet) . Every word in the tweets will be determine the polarity values, and then the value is calculated to know what the tweets sentiment is  (negative, neutral or positive). By doing that, we no longer need to manually label sentiments to each data tweets (because there are to much tweets data). Here are some analysis and visualization on tweets data. 
</p>
<p align="center"> 
 <img src="images/piechart sentiment polarity.png" /> 
 <br></br>
 Comparasion sentiment polarity on tweets data
</p>
<br></br>

<p align="center"> 
 <img src="images/wordcloud positive and negative words.png" /> 
 <br></br>
 Word cloud of positive and negative words
</p>
<br></br>

<p align="center"> 
 Top 10 positive sentiments
 <img src="images/top 10 positive sentiments.png" /> 
 <br></br>
</p>
<br></br>

<p align="center"> 
 Top 10 negative sentiments
 <img src="images/top 10 negative sentiments.png" /> 
 <br></br>
</p>
<br></br>

<p align="center"> 
 <img src="images/count of tweets created.png" /> 
 <br></br>
 Count of tweets created (based on hours)
</p>
<br></br>

#### - Sentiment Analysis using Long Short Term Memory (LSTM)
<p align = "justify"> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In this step, I do sentiment analysis using LSTM with tweets data. Firstly, I do data processing by doing transform each text in texts in a sequence of integer. Afterthat do encoding on sentiment polarity / target variable  (negative : 0 , neutral : 1, positive : 2) and then do a data split with composition : train data 80% and test data 20%. Data that has been processed, will be used for sentiment analysis with Long Short Term Memory (LSTM) model. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; LSTM model architecture which I used in this project is one layer LSTM. Then, I do hyperparameters tuning with gridsearchCV to know best hyperparameters on model LSTM. Based on results of hyperparameters tuning, the best hyperparameters obtained is :

{'batch_size': 128, 'dropout_rate': 0.2, 'embed_dim': 32, 'epochs': 10, 'hidden_unit': 16, 'learning_rate': 0.001, 'optimizers': <class 'keras.optimizers.RMSprop'>}, <b> which is   the average accuracy is 0.916513 (+- 92%) </b>
</p>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Here is a results from sentiment analysis using Long Short Term Memory model :

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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; From the picture above, model accuracy on test data (there are 4740 data) is very good which is around 91%. Can be seen on confusion matrix, the model can predict 2455 negative sentiments, 334 neutral sentiments and 1527 positive sentiments correctly. In the table below, there are some tweets with the sentiment polarity.
</p>

<p align="center"> 
 Sentiment analysis results on test data
 <img src="images/results on test data.png" /> 
 <br></br>
</p>

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
For details you can check my code : [Sentiment Analysis 'Online Lectures' in Indonesia.ipynb](https://github.com/rifkyahmadsaputra/Sentiment-Analysis-Online-Lectures-in-Indonesia/blob/main/Sentiment%20Analysis%20'Online%20Lectures'%20in%20Indonesia.ipynb)
