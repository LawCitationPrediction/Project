# Law Citation Prediction

## AC209b Advanced Topics in Data Science, Spring 2021

### Group Number 6

* Xin Zeng
* Yujie Cai
* Jiahui Tang
* Yingchen Liu

## Overview

In this project, we would use a dataset from Harvard Law School Case Law Access Project. The main data sets we used here for modeling are the latest case metadata and text for each case by the jurisdiction in North Carolina. The data basically consisted of two parts: header and opinion. We performed a PCA analysis to determine whether we should use the header as a predictor. We then conduct various data preprocessing methods to handle text data.

We then describe our modeling approach and go over the logical description of modeling decisions and process following the order of baseline model, improved baseline models (LexNLP, Topic Modeling, Word2Vec), Text Classification Method (FFNN / LSTM / BERT with FFNN/LSTM in the Appendix: Models), BERT for Document Similarity, and lastly, our proposed LawPairBERT Model.

Our LawPairBERT model has two versions, one with BERT Embedding and another one with both BERT and Graph Embedding. Our LawPairBERT model has many advantages which overcomes the problems and concerns of other models we experiment. LawPairBERT model could directly captures the citation relationship among each pair of law cases. And it achieves high accuracy in predicting both true and false condition of citation. Moreover, through the Pairs Representation we designed using Imbalanced Random Concatenation, we could reduce computational cost while remaining high accuracy. We regard it as a good contribution and treat it as our final deliverable model.

## Visulization of Our Proposed LawPairBERT Model

Version 1 - BERT Embedding:

<a href="url"><img src="https://github.com/LawCitationPrediction/Project/blob/main/img/version1.png" align="center" height="500" ></a>

Version 2 - Combined BERT and Graph Embedding:

<a href="url"><img src="https://github.com/LawCitationPrediction/Project/blob/main/img/version2.png" align="center" height="500" ></a>

## Performance Analysis

Different representations have distinct performance. In our project, representations of words have low accuarcy and high computational cost. And it's hard to capture the pair representations.

In the table below, we compare the Performance of our LawPairBERT models. BERT embedding tend to perform better than the combined embeddings of both BERT and Graph in predicting pairs with citation relationship. However, combined embedding is better in predicting overall accuracy. And, as our expectation, using recall as the early stopping boosts the accuracy for predicting the true citation, while reducing the overall accuracy among different labels.

<a href="url"><img src="https://github.com/LawCitationPrediction/Project/blob/main/img/performance.png" align="center" height="500" ></a>
