## Building Legal Case Retrieval Systems with Lexical Matching and Summarization using A Pre-Trained Phrase Scoring Model

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: V. Tran et al.  
<ins>Date</ins>: 2019-06  
<ins>Tags</ins>: `cnn`, `mlp`  
+++++++++++++++++++++++++++++++  


### Intro

- Automatic legal document processing systems can speed up significantly the work of experts, which, otherwise, requires significant time and efforts. One crucial kind of such systems, automatic information retrieval whose systems, in place of experts, process over enormous amount of documents, for example, legal case reports and statute law documents, which are accumulated rapidly over time.


### Contributions

- Their approach is based on the idea that summarization is important for retrieval.
- On one hand, they adopt a summarization based model called encoded summarization which encodes a given document into continuous vector space which embeds the summary properties of the document.
- On the other hand, they extract lexical features on different parts of a given query and its candidates. They observe that by comparing different parts of the query and its candidates, they can achieve better performance.
- Furthermore, the combination of the lexical features with latent features by the summarization-based method achieves even better performance and leads to state-of-the-art results for the task on the benchmark of the COLIEE-2019 competition.

***

### Approach

In COLIEE-2019, the candidate cases are ≈2.7K-token long in average. The authors chose the approach of comparing the summaries of each query and its candidate cases. They, however, found that the summary of the query is not necessarily lexically similar to the summary of the candidate cases. Moreover, some candidate cases do not have summary at all.

#### Encoded Summarization 
- They came up with the idea of encoding the entire document into vector space embedding the properties of summarization, and called it **encoded summarization**.
- This is a process of summarization for both the query and the candidates, for which they train a phrase scoring model for identifying important phrases which discuss contexts similar to those in the summary.
- Given a document, its phrasal scores are estimated given its summary (extracted using indicators ‘Summary:’ and ‘Present:’) and paragraphs. The phrase scoring model is trained with the objective that summary contents are expected to have higher scores than paragraph contents.
- From the phrase scoring model, they extract phrases to generate text summary for lexical matching with summary of the query since most of the candidate cases in COLIEE 2019 dataset do not have a summary.
- <ins>Phrase Scoring Model</ins>
  - The features of an n-gram phrase (window size containing n contiguous words of a sentence) are captured using a **convolutional neural layer** that takes as inputs the word embeddings of the given words (concatenated in a matrix). The phrase feature vector is then passed in a ReLU layer.
  - The features of a sentence is captured by applying **max-pooling** over all feature vectors of the n-gram phrases in the sentence (where max-pooling are operated over each dimension of vectors).
  - The features of a document is then captured by applying max-pooling over all feature vectors of the sentences in the document.
  - Finally, they apply a **multilayer perceptron (MLP)** with one hidden and one output layer to compute the score (ranging from 0.0 to 1.0) of each n-gram phrase. The input is the concatenation of the feature vectors of the n-gram phrase, the sentence and the document, respectively.
  - Training process:
    - The main objective is the trained model should assign summary phrases with higher scores than document phrases if the summary belongs to the document and otherwise, assign summary phrases with lower scores than document phrases if the summary does not belong to the document.
    - This main objective is realized by comparing the mean scores of summary phrases and document phrases:
      1. Positive constraint: The mean score of summary phrases is higher than the mean score of document phrases;
      2. Negative constraint: The mean score of summary phrases is lower than the one of document phrases when the summary does not belong to the document.
      3. The maximum score of summary phrases is higher than the maximum score of document phrases (it is expected that there exists concise summary phrases which is typical and representative for the document but could not found in the document. Such summary phrases should get higher scores than document phrases).
      4. The minimum score of summary phrases is higher than the mean score of document phrases. Once again, to emphasize the importance of summary phrases, all summary phrases should get higher score than the average score of document phrases.
    - The loss function is composed from the four previous constraints.
- <ins>Document Vector Composition</ins>
  - Given a document, they first obtain its phrase scores and its internal representations (phrase level, sentence level and document level encodings). Then, they compose the document vector by weighting the document internal representations by its summary (thus "encoded summarization").
- <ins>Query-Candidate Relevance Vector</ins>
  - They compute the query-candidate relevance vector as the element-wise product of query vector and candidate vector.
- <ins>Generating Text Summary</ins>
  - In this phase, they generate a summary given a document by selecting and joining document phrases scored by the phrase scoring model.
  
  
#### Lexical Matching

- They perform multi-aspect lexical matching where they compare a query case with its candidates via different views:
  - Summary vs. Summary: Matching the summary of the query case with the summary of candidates.
  - Summary vs. Lead-sentences: Matching the summary of the query case with the opening of each paragraph of candidates.
  - Summary vs. Paragraphs: Matching the summary of the query case with the details of candidates.
  - Paragraphs vs. Summary: Matching the details of the query case with the summary of candidates.
  - Paragraphs vs. Lead-sentences: Matching the details of the query case with the opening of each paragraph of candidates.
  - Paragraphs vs. Paragraphs: Matching the details of the query case with candidates.
- Most of the candidates do not have a summary, thus, they generate a summary for each candidate by utilizing their encoded summarization method.
- They performed various kinds of text matching including: **n-gram, skip-gram, subsequence matching** formulas.


### Learning to Rank Candidates

- They formulate the task as ranking problem and devise the learning to ranking method to solve it.
- They utilize pair-wise ranking strategy: pairing each supporting case with an irrelevant case from the candidate list.
- They adopt Linear-SVM as the learning algorithm for solving the optimization problem. The final ranking model should assign high scores to supporting cases and low scores to non-noticed cases.


### Results

- The encoded summarization (ES) approach alone achieves lower performance than the best lexical combination (by far). Since the encoded summarization model is trained on only COLIEE 2018 dataset, some summary phenomena in COLIEE 2019 dataset may not be well captured.
- The combination of encoded summarization and lexical features does improve performance significantly. It shows that, even though the encoded summarization does not perform well alone, it still provides useful information for identifying relevant cases.
