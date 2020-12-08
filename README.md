# hotel-review-sentiment-topic-analysis
Sentiment Analysis and Topic Analysis on Trip Advisor Hotel Reviews

## 1. Introduction

This project uses a dataset of about 515,000 hotels’ reviews in Europe from Kaggle. The sufficiently large dataset would provide a more comprehensive analysis on the reviews of hotels across the different geographies in Europe. Within the dataset, there are critical information such as hotel names, addresses, nationality of the guests and most importantly the hotels’ reviews. In addition, the reviews provided by the guests were categorized under positive and negative comments. This would provide the ideal dataset for us to perform text analysis on the reviews to obtain further insights.

Data source: https://www.kaggle.com/jiashenliu/515k-hotel-reviews-data-in-europe

## 2. Sentiment Analysis
### 2.1 Text Preprocessing
* Tokenize of words to split a sentence into words. 
* Transforming all text into lower case. 
* Removing words from the stop-word list.
* Stemming words by removing suffixes using Porter Stemmer.  

### 2.2 Naïve Bayes Sentiment Polarity Classification
The following steps were performed to structure the raw data
* Positive reviews and negative reviews are extracted from the dataset. 
* Two empty lists were created, one for corpus and one for label (positive/negative). 
* Sentences of positive and negative reviews were broken into words using the pre-processing techniques mentioned above. Each sentence became a list of words and was appended to the corpus, followed by appending to the respective label (1 for positive and 0 for negative) accordingly. 
* Spit dataset randomly into train data (80%) and test data (20%). 
* A dictionary was created from the corpus of the train data. 
* Convert each sentence into a vector that shows word existence (1 if exist and 0 if not exist) using the created dictionary.  
* Form labeled data by combining vectors and labels. 
* The classifier was trained using the train dataset. 

### 2.3 Lexicon-based Sentiment Polarity Classification 
This method makes use of an existing lexicon (or dictionary) with words tagged as negative or positive.
To investigate the impact of positive and negative sentiment on reviewer score, we calculated positive score and negative score
* The positive score was calculated by counting the number of words in the review that matched the list of positive words. 
* Likewise, the negative score was calculated by counting the number of words in the review that matched the list of positive words. 
* The total score equals to positive score minus negative score. 
A review is classified as positive if total score is equal or larger than 0, and negative if total score is less than 0. 
To understand the impact of positive and negative sentiment on reviewer score, we ran a multi-linear regression analysis with positive score and negative score being the explanatory variables and reviewer score being the target variable. 

## 3. Topic Modeling
Methodologies
Result
