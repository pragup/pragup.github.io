---
title: 'Sentence Classification in Simple Worlds'
date: 2017-04-23
permalink: /posts/2017/04/sentence-classification/
tags:
  - cool posts
  - category1
  - category2
---
ABSTRACT
----------
Convolution Neural Networks are typically used in computer vision problems like image classification. Most of the computer vision systems todays at its core are based on CNNs from photo tagging to self driving cars. 
However we are going to look at the application of CNNs in NLP(Natural Language Processing).

BACKGROUND
----------

### Natural Language Processing ###
* Natural language is designed to make human communication efficient. As a result,
    * We omit a lot of “common sense” knowledge, which we assume the hearer/reader possesses.
    * We keep a lot of ambiguities, which we assume the hearer/reader knows how to resolve.
* This makes EVERY step in NLP hard.
    * Ambiguity is a “killer”!
    * Common sense reasoning is pre-required.

### Word Embedding(or Word Vectors) – ###
* **Discrete representation-** The vast majority of statistical NLP work regards, words as atomic symbols: hotel, conference, motel . In vector space terms, this is a vector with one 1 and everything else is zeroes. Every word is orthogonal to one another like $𝑤_{ℎ𝑜𝑡𝑒𝑙} \cdot 𝑤_{𝑚𝑜𝑡𝑒𝑙}  =0$. Hence word similarity is not captured. Representing words as atomic symbols, leads to data sparsity, and usually means that we may need more data in order to successfully train statistical models. 
* **Continuous representation-** We can embed words in $𝑅^𝐷$ with D≤V such that semantically close words are likewise `close' in $𝑅^𝐷$. It will capture distributional similarity. One of the most successful ideas of modern statistical NLP.
	* **Count Based Models-** To make  neighbors  represent words, it uses count based co-occurrence matrix $\in 𝑅^{𝑉 × 𝑉}$. For example: LSA, LDA etc. It can be embed into $\in 𝑅^{𝐷×𝑉)}$  using SVD. Computational cost for SVD scales quadratically for $D×𝑉$ matrix: $O(𝐷𝑉^2)$ flops. Bad for millions of words or documents. Hard to incorporate new words or documents. 
* **Direct prediction Models–** Here the idea is directly learning lower vector representation. For example: Feed forward neural language model, recurrent neural language model, Log-Linear language model(Continuous bag of words model, Continuous skip gram model). One of the most popular one is word2vec which based on Log-Linear language model. Word2vec instead of capturing co-occurrence counts directly, it predicts surrounding words of every word Fig.1 @fig:SentClassificationFigure1. Word2vec representation is pretty good in capturing syntactic  and semantic relationship between words like: $𝑤_{𝑏𝑖𝑔}−𝑤_{𝑏𝑖𝑔𝑔𝑒𝑟}  \approx 𝑤_{𝑠𝑙𝑜𝑤}−𝑤_{𝑠𝑙𝑜𝑤𝑒𝑟}$, $𝑤_{𝑓𝑟𝑎𝑛𝑐𝑒}−𝑤_{𝑝𝑎𝑟𝑖𝑠} \approx 𝑤_{𝑘𝑜𝑟𝑒𝑎}−𝑤_{𝑠𝑒𝑜𝑢𝑙}$. But not necessarily unique.  
![First Figure 1]( https://pragup.github.io/images/Sentence-Classification-Figure_1.png )

You can have many headings
======

Aren't headings cool?
------