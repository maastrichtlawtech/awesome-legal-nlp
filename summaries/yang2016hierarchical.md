## Hierarchical Attention Networks for Document Classification

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: Z. Yang et al.  
<ins>Date</ins>: 2016-06  
<ins>Tags</ins>: `document classification`, `attention network`  
+++++++++++++++++++++++++++++++

### Intro

- Traditional approaches of text classification represent documents with sparse lexical features, such as n-grams, and then use a linear model or kernel methods on this representation. More recent approaches used deep learning, such as convolutional neural networks and recurrent neural
networks based on long short-term memory (LSTM) to learn text representations.
- In this paper we test the hypothesis that better representations can be obtained by incorporating knowledge of document structure in the model architecture. The intuition underlying our model is that not all parts of a document are equally relevant for answering a query and that determining the relevant sections involves modeling the interactions of the words, not just their presence in isolation.


### Contributions

- Their primary contribution is a new neural architecture for document classification, the **Hierarchical Attention Network** (HAN) that is designed to capture two basic insights about document structure:
  1. it has a hierarchical structure that mirrors the hierarchical structure of documents; 
  2. it has two levels of attention mechanisms applied at the word and sentence-level, enabling it to attend differentially to more and less important content when constructing the document representation.
