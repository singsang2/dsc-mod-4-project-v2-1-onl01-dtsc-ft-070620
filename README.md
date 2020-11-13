
# This Repository Contains

- **Jupyter Notebook**: This notebook, <a href="https://github.com/singsang2/dsc-mod-4-project-v2-1-onl01-dtsc-ft-070620/blob/master/Tweet_sentiment_analysis.ipynb">Tweet_sentiment_analysis.ipynb</a>, has Twitter sentiment analysis.

- **Presentation**: This <a href="https://github.com/singsang2/dsc-mod-4-project-v2-1-onl01-dtsc-ft-070620/blob/master/Tweet_sentiment_analysis.pptx">presentation</a> contains an "Executive Summary" that gives a brief overview of your problem/dataset, and each step of the data science process.

- **Datasets**: This <a href="https://github.com/singsang2/dsc-mod-4-project-v2-1-onl01-dtsc-ft-070620/tree/master/datasets">folder</a> contains all the datasets used in this project.

- **Models**: This <a href="https://github.com/singsang2/dsc-mod-4-project-v2-1-onl01-dtsc-ft-070620/tree/master/models">folder</a> contains all the models trained and used in this project.

- **Additional Codes**: This <a href="https://github.com/singsang2/dsc-mod-4-project-v2-1-onl01-dtsc-ft-070620/tree/master/src">folder</a> contains any other codes that were used for this project.

# Introduction

<img src='images/wordcloud_pos_neg.png'>

    *Major vocabularies used in positive sentiments and negative sentiments.

## Business Model

Consumers' voices are getting much attention by big companies not only because their opnions matter, but also their reach of their voice is expanding due to growth of social media platforms such as Facebook, Instagram and Twitter. Thus, it is imperative to monitor and analyze how consumers are responding to one's product not only for customer service purpose, but also to analyze their trends.

In this project, we will deal with a portion of what we have mentioned above. We will focus on identifying negative sentiments of Google, Apple and Android products from Twitter data.

### Goals
The goal of this project is to produce a model that can efficiently

[1] identify tweets with negative sentiments towards a product (ex. Apple, Google, or Android products), and
-  By identifying negative tweets, a company can provide relatively quick feedback to the customers which will improve brand's image and credibility.
        
[2] correctly categorize tweets into negative, neutral and positive sentiments.
- By cumulating various sentiments about a company's various products, a company could read and predict people's trend.

[Extra] We will also train a model that can identify which product a tweet is mentioning.
- A company/brand usually has more than just one product (ex. Apple), so by correctly identifying which product tweets are mentioning, it will be more beneficial to the company be aware of their products review by people.

## Data


 [1]. The main dataset comes from CrowdFlower via data.world. <a href="https://data.world/crowdflower/brands-and-product-emotions">Data Link</a>

 [2]. Amazon and Best Buy electronics review dataset. <a href="https://www.kaggle.com/datafiniti/amazon-and-best-buy-electronics">Data Link</a>

 [3]. Amazon electronics review dataset: <a href="https://www.kaggle.com/datafiniti/consumer-reviews-of-amazon-products">Data Link</a>
            

# Models

## Binary Model

The following methods were used to prepare our binary classification text data:

    [1] NLTK - TF-IDF vectorizer
    [2] spaCy - TF-IDF vectorizer
    [3] spaCy - word2vec word embedding.
    
Then either `MultinomialNB` or `LogisticRegression` were used to train the model.



## Multiclass Model

The following methods were used to prepare our multiclass classification text data:

    [1] spaCy - TF-IDF vectorizer
    [2] TextBlob - sentiment analyzer
    [3] spaCy - word2vec word embedding.
    [4] Added additional datasets from Amazon and Best Buy
    
Then either `MultinomialNB` or `LogisticRegression` were used to train the model.



# Model Evaluation

## Binary Model

The following table shows the top 5 model that performed for binary classification.

<img src='images/binary_model_report.png' width='700'>

Logistic Regression model using word embedding did the best in terms for negative recalls; however it does have a longer average time to fit and predict the result signifcantly.

<img src='images/computing_time.png' width='500'> <img src='images/negative_recalls.png' width='500'>

The best model was using `MulticlassNB` with spaCy's word embedding.

<img src='images/binary_word_emb.png' width='500'>

- Overall Test Accuracy: 81%

- Overall Test Recall (weighted): 81%

- Negative Sentiment Recall: 74%

## Multiclass Model

The best model was using MulticlassNB with spaCy's word embedding.

<img src='images/multi_word_emb.png' width='500'>


- Overall Test Accuracy: 60%

- Overall Test Recall (weighted): 60%

- Negative Sentiment Recall: you 71%

# Conclusion

Our final models can

    [1] Binary Sentiment
        * Most 81% accuracy with 76% negative sentiment recall
    [2] Multiclass Sentiment
        * 60% accuracy with 71% negative sentiment recall 
    [EXTRA] Product Predictor
        * 91% of accuracy

## Recommendations
We would recommend the following:

[1] **Use binary sentiments (positive and negative)**
   - Multiclass not only complicates the model itself, but also it dilutes negative and positive sentiments together, therefore, we recommend using binary sentiment classification model
    
[2] **For the best negative recall model:** *logistic regression word-embedding model*
   - this is the best model to flag negative sentiments but it does take some time to train; however, as long as the train is well-done, implementing the model should not cause significant calculation cost. (Further study should be done)

[3] **For the fastest computing model:** *Naive Bayes' TF-IDF model with SMOTE*
   - this model also did a great job in identifying negative sentiments, but it uses SMOTE which is not recommended in NLP analysis.

# Future Direction

[1] Further data acquisition:
Due to imbalance in data, our model suffered. Acquiring similar datasets with more balanced classes would increase our model's performance and reliability.

[2] Real time Twitter analysis
Have this model refined and put in a production so that it can monitor tweets real time and analyze and negative flags about any particular product.

[3] Research various costs between models
Different models have different strengths and weaknesses, and we believe researching different costs including computing and labor costs using different models would allow us to choose a better model

[4] Try different NLP techniques
There are so many different NLP techniques and they are growing due to works of so many different research entities. It would be very valuable to try different approach including skip-gram and even deep learning NLP for this project.



```python

```
