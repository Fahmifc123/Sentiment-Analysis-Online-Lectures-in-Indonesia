# Sentiment Analysis “Online Lectures ("Kuliah Online” in Bahasa)"

## Introductions
<p align = "justify">
&nbsp;&nbsp;&nbsp; In this project I do sentiment analysis on the topic “online lectures  (“kuliah online” in bahasa)”. The purpose is to know what is the opinion twitter users in Indonesia about online lectures (“kuliah online”) activity in Indonesia, whether is more “contra” than “pro” or otherwise ? Therefore I do analysis and classification (negative, neutral or positive) on each user tweets about  “online lectures  (“kuliah online” in bahasa)” in Indonesia.
 
The data used in this project is 25.000 twitter data (tweets) that’s contain topic “kuliah online” which scraping with twitter scraping tool Twint (https://github.com/twintproject/twint). After that, I do preprocessing on tweets data and determine sentiment polarity of tweets with Indonesian Sentiment Lexicon (https://github.com/fajri91/InSet).  Data that has been determined, will be used for sentiment analysis with model recurrent neural network which is Long Short Term Memory (LSTM). 
</p>

## Results

Results from sentiment analysis using LSTM model is very good, the model can classify tweets sentiment well. The accuracy of model LSTM with best hyperparameters which has been determined is around 90%. The following is a train and val accuracy from model that  I built :

<p align="center"> <img src="images/train and val accuracy.png" /> </p>
