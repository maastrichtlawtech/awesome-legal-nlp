## Legal Information Retrieval with Generalized Language Models

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: J. Rossi et al.  
<ins>Date</ins>: 2019-06   
<ins>Tags</ins>:   
+++++++++++++++++++++++++++++++  


### Intro

- 


### Contributions

- 

***

### Approach 

- **BERT + MLP**: They take as input a query case and a candidate case and pass it to a pre-trained *BERT* model (bert-base-uncased) on top of which stands an additional binary classification layer (*MLP*) that classifies the given pair of cases as "Noticed" or "Not noticed". The ranking of documents is based on the score for the positive class.
- Problem: the documents from the training corpus are longer than 512 tokens. For this reason, they introduce a summarization of the texts in the corpus, as implemented in gensim using **TextRank**.

### Results and limitations

- Results: F1-score of 52.9%
- Limitations: 
  - One limitation of reducing a ranking problem to a pairwise relevance classification problem is that the system learns to have a score on the right side of the decision threshold (0.5 in the binary classification setting), instead of learning that the score of any sample from the negative class should be lower than the score of any sample from the positive class. While this limitation is addressed by systems from the Learning to Rank family, this paper did not use the associated techniques.
  - Pair-wise comparison with BERT is computationally expensive. According to the authors of sentence-BERT, finding which of the over 40 million existent questions of Quora is the most similar for a new question through a pair-wise comparison with BERT would take over 50 hours on a modern V100 GPU.
