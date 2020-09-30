## Building Legal Case Retrieval Systems with Lexical Matching and Summarization using A Pre-Trained Phrase Scoring Model

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: V. Tran et al.  
<ins>Date</ins>: 2019-06  
<ins>Tags</ins>:   
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
