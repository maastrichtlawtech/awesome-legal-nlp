## Legal Information Retrieval with Generalized Language Models

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: J. Rossi et al.  
<ins>Date</ins>: 2019-06  
<ins>Tags</ins>: `information retrieval`, `bert`   
+++++++++++++++++++++++++++++++

### Intro

- They focus on the Task 1 of the COLIEE 2019 competition: the **Legal Case Retrieval Task**. 
- In this task, a given court case is considered as a query to retrieve supporting cases (also named ’noticed cases’), which support the decision taken in the query case. Each query case is given a collection of potential supporting cases (also named ’candidate cases’), these collections are provided labeled for the training dataset, and unlabelled for the unknown test dataset.

### Contributions

- Introduced new method to identify text pairwise relevance, which combines text summarizing and a generalized language model (BERT) in order to assess pairwise relevance.
- They translate this retrieval task into a ranking problem, which they formulate as a pairwise relevance classification problem.


### Methodology

- They form a pairwise semantic latent representation of the query case and the candidate case, that they submit to a Multi-Layer Perceptron.
- More precisely, they take as input a query case and a candidate case and pass it to a pre-trained BERT model (*bert-base-uncased*) on top of which stands an additional binary classification layer (MLP) that classifies the given pair of cases as "Noticed" or "Not noticed". The ranking of documents is based on the score for the positive class.
- Problem: the documents from the training corpus are longer than 512 tokens. For this reason, they introduce a summarization of the texts in
the corpus, as implemented in gensim using TextRank.


### Results

- The recall for BERT systems is also lower than the BM25 baseline.
- Limitations of reducing a ranking problem to a pairwise relevance classification problem: the system learns to have a score on the right side of the decision threshold (0.5 in the binary classification setting), instead of learning that the score of any sample from the negative class should be lower than the score of any sample from the positive class. While this limitation is addressed by systems from the Learning to Rank family, this paper did not use the associated techniques.
- They did not establish a new sota for this task.
