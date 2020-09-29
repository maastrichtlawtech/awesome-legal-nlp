## IITP in COLIEE@ ICAIL 2019: Legal Information Retrieval using BM25 and BERT

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: B. Gain et al.  
<ins>Date</ins>: 2019-06  
<ins>Tags</ins>: `doc2vec`, `bm25`  
+++++++++++++++++++++++++++++++  


### Intro

- 


### Contributions

- 

***

### Task 1: 

#### Approaches

- **Doc2Vec**: For every query, they compute the Doc2Vec similarity between the base case and all of its candidates. Top 10 candidates whose similarity was greater than 90% of average score of top two are returned.
- **BM25**: compute BM25 score of all the candidate cases for every base case using gensim library. Then the top 10 candidates whose similarity is greater than 90% of average score of top two are returned.
- **Doc2Vec + BM25**: combine the scores obtained from the previous two models by multiplying them (so that only documents with high scores on both Doc2Vec and BM25 are ranked). Top 10 candidates whose similarity was greater than 80% of average score of top two are returned.

#### Results

- *Doc2Vec + BM25*: F1-score of 48.2%
- *BM25*: F1-score of 47.7%
- *Doc2Vec*: F1-score of 39.7%
