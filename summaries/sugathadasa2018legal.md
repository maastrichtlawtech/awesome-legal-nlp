## Legal Document Retrieval using Document Vector Embeddings and Deep Learning

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: K. Sugathadasa et al.  
<ins>Date</ins>: 2018-07  
<ins>Tags</ins>: `tf-idf`, `graph network`  
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
- Prior legal cases are often mentioned in legal cases as case law references.
- They defined the inverted *index structure*, where for each document is associated a list of documents which were referenced in that text. This mapping from each document, to other documents which refer to the original document, is called the *mention map* (M).
- The listing of mentions and references of other legal cases was a non-trivial Information Extraction (IE) task. 
  - The first problem was the lack of a standard and proper naming convention for the legal case names. This problem was solved by regular expression-based Information Extraction.
  - The second problem was the legal name reference using abbreviations of the case name in the text body. To solve this problem, extensive searching on the Findlaw Search Engine was done, and mention names were matched with the legal case document names.
- The *mention map* is the base component of their study. From there, they implemented three unique document vector models, each of which was used to train a neural network:
  - **doc2vec<sub>NV</sub>** (Node2Vec Model) 
  - **doc2vec<sub>SSM</sub>** (Sentence Similarity Model)
  - **doc2vec<sub>NN</sub>** (Mapper Neural Network Model) 


#### 1. doc2vec<sub>NV</sub>

- The doc2vec<sub>NV</sub> model was created using the **node2vec algorithm**, which is a scalable feature learning technique for networks inspired by the word2vec model. It learns continuous representations for nodes in any (un)directed or (un)weighted graph.
- The input for this algorithm was an Edgelist, which contained the list of edges generated from the *mention map*.
- The output was a vector space that contains a set of feature vectors for the list of documents in the legal text corpus.


#### 2. doc2vec<sub>SSM</sub>
- <ins>Sentence Similarity Graph Network</ins>
  - They created a sentence similarity graph network using the semantic similarity measures between sentences by the TextRank algorithm.
  - They created a *document corpus*, which is a subset of the entire text corpus, where we picked the *k* most important sentences in each of the documents, from the sentence similarity graph network.
- <ins>Text Preprocessing</ins>
  - They pre-processed the *document corpus* to clean the text of unwanted characters and common words, in order to obtain the optimal size for the final vocabulary.
  - In the linguistic preprocessing step, they used lemmatizing and case-folding to lowercase.
- <ins>Document Base Vector Creation</ins>
  - They ran **TF-IDF** on the document corpus and built a TF-IDF weight matrix T between the terms and documents.
  - They defined GTF-IDF (Global Term Frequency- Inverse Document Frequency) as an extension of TF-IDF.
  - They then defined V' by sorting the vocabulary V by descending order of GTF-IDF values, and obtained the common base vector template B so that B is a word vector of lenght *p*, such that the *p* number of words that are most significant to the domain D (thus the first *p* elements of the sorted V') are contained in B.
- <ins>Sentence Similarity Based Document Vector Representation</ins>
  - Next, they created a vector representation for documents in the text corpus.
  - For the *j*th document, the *k* most important sentences are picked from the sentence similarity graph network.
  
The vector representation of a document is a *p*-dimensional vector, representing the most important *p* terms from the context on the entire text corpus.


#### 3. doc2vec<sub>NN</sub>
- The Mapper Neural Network model doc2vec<sub>NN</sub> was trained using the both models: doc2vec<sub>NV</sub> and doc2vec<sub>SSM</sub>.

