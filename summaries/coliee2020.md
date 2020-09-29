## The Competition on Legal Information Extraction/Entailment (COLIEE) - 2020

### Tasks description

- **Task 1 - The Legal Case Retrieval Task**: This task consists in finding which cases, in the set of candidate cases, should be "noticed" with respect to a given query case.
- **Task 2 - The Legal Case Entailment task**: Given a base case and an extracted specific fragment together with a second case that is relevant in respect to the base case, this task consists in determining which paragraphs of the second case entail that fragment of the base case.
- **Task 3 - The Statute Law Retrieval Task**: This task involves reading a legal bar exam question Q, and identifying of a subset of Japanese Civil Code Articles S1, S2,..., Sn from the entire Civil Code which are those appropriate for answering the question.
- **Task 4 - The Legal Question Answering Task**: Given a question Q, we have to retrieve relevant articles S1, S2, ..., Sn through phase one, and then we have to determine if the relevant articles entail "Q" or "not Q". The answer of this track is binary: "YES"("Q") or "NO"("not Q").

***

### Task 1 - The Legal Case Retrieval Task

1. <ins>Building legal case retrieval systems with lexical matching and summarization using a pre-trained phrase scoring model.</ins> (V. Tran et al., 2019)  
  - Approach:
  

2. <ins>Legal Information Retrieval with Generalized Language Models</ins> (J. Rossi et al., 2019)
  - Approach: 
    - **BERT + MLP**: They take as input a query case and a candidate case and pass it to a pre-trained *BERT* model (bert-base-uncased) on top of which stands an additional binary classification layer (*MLP*) that classifies the given pair of cases as "Noticed" or "Not noticed". The ranking of documents is based on the score for the positive class.
  - Problem: the documents from the training corpus are longer than 512 tokens. For this reason, they introduce a summarization of the texts in the corpus, as implemented in gensim using **TextRank**.
  - Results: F1-score of 52.9%
  - Limitations: 
    - One limitation of reducing a ranking problem to a pairwise relevance classification problem is that the system learns to have a score on the right side of the decision threshold (0.5 in the binary classification setting), instead of learning that the score of any sample from the negative class should be lower than the score of any sample from the positive class. While this limitation is addressed by systems from the Learning to Rank family, this paper did not use the associated techniques.
    - Pair-wise comparison with BERT is computationally expensive. According to the authors of sentence-BERT, finding which of the over 40 million existent questions of Quora is the most similar for a new question through a pair-wise comparison with BERT would take over 50 hours on a modern V100 GPU.


3. <ins>Legal Information Retrieval using BM25 and BERT</ins> (B. Gain et al., 2019)
  - Approaches:
    - **Doc2Vec**: For every query, we compute the Doc2Vec similarity between the base case and all of its candidates. Top 10 candidates whose similarity was greater than 90% of average score of top two are returned.
    - **BM25**: compute BM25 score of all the candidate cases for every base case using gensim library. Then the top 10 candidates whose similarity is greater than 90% of average score of top two are returned.
    - **Doc2Vec + BM25**: combine the scores obtained from the previous two models by multiplying them (so that only documents with high scores on both Doc2Vec and BM25 are ranked). Top 10 candidates whose similarity was greater than 80% of average score of top two are returned.
  - Results:
    - *Doc2Vec + BM25*: F1-score of 48.2%
    - *BM25*: F1-score of 47.7%
    - *Doc2Vec*: F1-score of 39.7%
    
4. <ins>Combining Similarity and Transformer Methods for Case Law Entailment</ins> (J. Rabelo et al., 2019)
  - Approach:
    - **Universal Sentence Encoder + cosine similarity**: they used of the Universal Sentence Encoder to generate a vector representation of both the base case and each candidate, followed by the calculation of a similarity score using a cosine measure.
  - Results: F1-score of 34.4%
