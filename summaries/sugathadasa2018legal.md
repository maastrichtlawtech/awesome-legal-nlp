## Legal Document Retrieval using Document Vector Embeddings and Deep Learning

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: K. Sugathadasa et al.  
<ins>Date</ins>: 2018-07  
<ins>Tags</ins>:   
+++++++++++++++++++++++++++++++  


### Intro

- This study targets the information retrieval for the legal domain. Specifically, it focuses on the process of representing legal case documents into different vector spaces.
- The legal domain contains considerable amount of domain specific jargon where the etymology lies with mainly Latin and English, which makes the information retrieval (IR) task multilingual. To complicate this fact, in certain cases, the meaning of the words and context differs by the legal officers’ interpretations.


### Contributions

- Developed three novel models which incorporate vector space representations of the legal domain, where document vector generation was done in two different mechanisms and as an ensemble of the above two.
- Proposed a system that includes a page ranking graph network with TF-IDF to build document embeddings by creating a vector space for the legal domain. 


***

### Methodology

- Dataset: they collected over 2,500 legal case documents from the FindLaw websiteusing multi-threaded webcrawlers.
- Implemented three unique document vector models, each of which is used to train a neural network.
  - **Document Relevance Mention Map**:  
    - Prior legal cases are often mentioned in legal cases as case law references.
    - They defined the inverted *index structure*, where for each document is associated a list of documents which were referenced in that text.
    - The listing of mentions and references of other legal cases was a non-trivial Information Extraction (IE) task. 
      - The first problem was the lack of a standard and proper naming convention for the legal case names.
