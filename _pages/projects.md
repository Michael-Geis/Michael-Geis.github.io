---
title: "Selected Projects"
permalink: /projects/
author_profile: true
---

<a id="classifier"></a>

## Classifying arXiv Math Publications By Subject

The [arXiv](https://arxiv.org) is a large free repository hosting papers across many STEM disciplines. This project is multi-label classification model which predicts the relevant subject tags of a math paper based only on its title. The details of model development are explained below.

### Inference Pipeline

- #### Preprocessing
    - The title is retrieved from the input ID via a call to the arXiv API.
    - The title string is cleaned--inline LaTeX is removed, all accented characters are converted to their ASCII equivalents, LaTeX environments not enclosed by $ signs are removed.
- #### Huggingface Model
    - The model consists of a pretrained `bert-base-uncased` transformer and a single layer neural network 'classification head'. 
    - The input sentence (clean title) is encoded using this BERT model and its pooled output is run through the classification head. 
- #### Postprocessing
    - The classification head outputs a vector whose $$j^{th}$$ component is the probability that the $$j^{th}$$ label is relevant.
    - A minimum probability threshold required to predict a label is passed in and the vector of subject tag probabilities is converted into a list of english named subject tags.

#### Model Training

The huggingface model is an example of a "fine-tuned" model. The transformer model responsible for generating the vector representation of the input text is pretrained, and these weights are not modified. However, the classification head is trained on a dataset consisting of about 40,000 (title,label) pairs. This dataset was extracted from a random sample of 10% of all of the math articles contained in the [full arXiv kaggle dataset](https://www.kaggle.com/datasets/Cornell-University/arxiv)

<a id="recommender"></a>

## A Nearest-Neighbor Based Recommender System for Math Articles

This project returns the 5 most similar math articles to a provided article.

### Model Design
- We start with a chosen library of articles from which we make recommendations. Using their title and abstract, every article
is embedded in a vector space in such a way that papers pointing 'in the same direction' are similar in content. To make recommendations, the input article is embedded in the same way and its 5 nearest neighbors in the library are calculated.

- We use the [allenai-specter sentence transformer](https://www.kaggle.com/datasets/Cornell-University/arxiv) as our embedding model. This model has been pre-trained on a large corpus of scientific articles specifically for the task of detecting semantic similarity.

### Unsupervised Topic Modeling
- Additionally, we performed unsupervised topic modeling on our recommendation library using [BERTopic.](https://maartengr.github.io/BERTopic/index.html) BERTopic works by applying the [HDBSCAN.](https://hdbscan.readthedocs.io/en/latest/how_hdbscan_works.html) clustering algorithm on the embedded articles. A variant of tf-idf is then run on each cluster to extract the common topics present. Here is a picture of the embedding space after applying the [UMAP](https://umap-learn.readthedocs.io/en/latest/) dimension reduction. Keywords for the strongest topic clusters are shown on the right.

![Topic Modeling](/images/topicmodeling.png "Visualization of clusters and corresponding topics after dimension reduction.")


<a id="cs229"></a>

## Stanford CS229 "Intro to Machine Learning" Personal Notes and Problem Set Solutions

The following is a collection of notes and exercises written while following the Stanford CS 229 "Intro to Machine Learning" course. [Full repository of course materials can be found here.](https://github.com/maxim5/cs229-2018-autumn) All lectures are available on [YouTube.](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU)

- #### Problem Set 0
    - [Gradients and Hessians](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS0/PS0-1.ipynb)
    - [Positive Definite Matrices](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS0/PS0-1.ipynb)
    - [Eigenvectors and Eigenvalues](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS0/PS0-1.ipynb)
- #### Problem Set 1
    - [Logistic Regression & GDA](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS0/PS0-1.ipynb)
    - [Logistic Regression with Incomplete Positive-Only Labels](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS1/PS1-2.ipynb)
    - [Poisson Regression](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS1/PS1-3.ipynb)
    - [Convexity of Generalized Linear Models](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS1/PS1-3.ipynb)
    - [Locally Weighted Linear Regression](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS1/PS1-3.ipynb)
- #### Problem Set 2
    - [Training Stability of Logistic Regression](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-1.ipynb)
    - [Model Calibration](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-2.ipynb)
    - [Notes on Bayesian Statistics and the Bayesian Interpretation of Regularization](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-3.ipynb)
    - [The Kernel Trick: Construction of Mercer Kernels](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-4.ipynb)
    - [An Implementation of the Perceptron Classifier with the Kernel Trick](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-5.ipynb)
    - [Naive Bayes for Binary Text Classification](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-6.ipynb)
- #### Problem Set 3
    - [Properties of the Kullback-Liebler Divergence](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS2/PS2-6.ipynb)
    - [Kullback-Liebler Divergence, Fisher Information, and the Natural Gradient](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS3/PS3%20Solutions/PS3-3%20KL%20divergence%2C%20Fisher%20information%2C%20natural%20gradient.ipynb)
    - [Expectation Maximization Algorithm and a Semi-Supervised Variant](https://github.com/Michael-Geis/CS-229-F18-Solutions/blob/main/PS3/PS3%20Solutions/PS3-4%20Semi-supervised%20EM.ipynb)