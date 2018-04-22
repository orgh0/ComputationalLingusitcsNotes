# Vector Semantics

## Topics
- Word2Vec
- SKipgram
- CBow
- Glove

## Introduction
- Vector semantics are used to measure the similarity of words
- It's a mathematical model to represent the universe of entities and the measure of similaties between the entities
- Applications: Plagurism Detectors

## Inutition of distributional word semantics
- 2 words are similar if they have same word contexts


## What are the kinds of Vector models ?
- Sparse vector representations
	* 1. Mutual-information weighted word co-occurrence matrices
- Dense vector representation
	* Singular Value Decomposition
	* Neural Network Model (skipgram and CBOW)
	* Brown Clusters

## Words and Co-occurence Matrix Method
- Term-Document matrix : number of times a word occurs in a document
- Term-Term matrix : number of times a word occurs with another word
- Instead of making vectors for entire documents, could be made for smaller size corpus as well such as para. window of +- 4 words.
- But these matrix's are very sparse
- The shorter the window size the more syntactic is the representation
- The longer the window size the more semantic the representation


## Positive Pointwise Mutual Information (PPMI)
- Frequency Methods are very skwed
- Rather have a measure that ask wether a context word is particularly informative about the target word.
- Ranges from -inf to +inf
- PMI is biased towards infrequent words, a solution is to give rare words slightly higher frequency

## Measuring similarity
- Dot product is a good method, it gives a higher value if both have high values in the same dimension

## Dense Vectors
- PPMI vectors are short and sparse
- Alternately we could learn vectors which are short and dense
- Shorter vectors are easier to use as features in machine

## Methods for getting shorter vectors
- Singular Value Decomposition 
- Neural Network Method (skipGram, Cbow)
- Brown Clustering

## Neural Network Method
- Learning Embedding as a part of a word prediction process

### SkipGram
- Predict each neighbouring word in context of a window of 2C words
- from the current word -c to +c
- Each word is expressed as a one hot vector of all the words in the document
- Input Embedding v, in the input matrix W, coloum i is 1Xd embedding v for word i in the vocab
- Output Embedding v', row i of the matrix W' id a dX1 vector embedding for the word i in the vocab
- Predicting the context given the word
- works well with small amount of data, represents well even the rare words or phrases

### CBOW
- Embeddings capture relational meaning vec(king) - vec(man) + vec(woman) = vec(queen)
- The task in hand is to predict the word given it's context
- Several times faster, slightly better frequeny with frequent words
	
