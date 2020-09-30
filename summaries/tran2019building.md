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

- In COLIEE-2019, the candidate cases are ≈2.7K-token long in average. The authors chose the approach of comparing the summaries of each query and its candidate cases. They, however, found that the summary of the query is not necessarily lexically similar to the summary of the candidate cases. Moreover, some candidate cases do not have summary at all.
- They came up with the idea of encoding the entire document into vector space embedding the properties of summarization, and called it **encoded summarization**.
  - This is a process of summarization for both the query and the candidates, for which they train a phrase scoring model for identifying important phrases which discuss contexts similar to those in the summary.
  - Given a document, its phrasal scores are estimated given its summary (extracted using indicators ‘Summary:’ and ‘Present:’) and paragraphs. The phrase scoring model is trained with the objective that summary contents are expected to have higher scores than paragraph contents.
  - From the phrase scoring model, they extract phrases to generate text summary for lexical matching with summary of the query since most of the candidate cases in COLIEE 2019 dataset do not have a summary.
- <ins>Phrase Scoring Model</ins>
  - The features of an n-gram phrase (window size containing n contiguous words of a sentence) are captured using a **convolutional neural layer** that takes as inputs the word embeddings of the given words (concatenated in a matrix). The phrase feature vector is then passed in a ReLU layer.
  - The features of a sentence is captured by applying **max-pooling** over all feature vectors of the n-gram phrases in the sentence (where max-pooling are operated over each dimension of vectors).
  - The features of a document is then captured by applying max-pooling over all feature vectors of the sentences in thee document.
  - Finally, they apply a **multilayer perceptron (MLP)** with one hidden and one output layer to compute the score (ranging from 0 to 1) of each n-gram phrase. The input is the concatenation of the feature vectors of the n-gram phrase, the sentence and the document, respectively.
  - Training process: 
  
