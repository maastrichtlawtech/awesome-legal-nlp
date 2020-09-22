## Deep learning in law: early adaptation and legal word embeddings trained on large corpora

Authors: I. Chalkidis et al.  
Date: 2018-12  
Tags: `survey`, `legal word vectors`, `information retrieval`, `text classification`, `information extraction`

### Intro

- The application of Deep Neural Networks in legal analytics has increased significantly. Deep Neural Networks have been rapidly replacing rule-based approaches, dictionary-based models and traditional machine learning techniques, which in theirmajority require intensive manual feature engineering. The reason lies in the fact of their poor performance when dealing with the words polysemy, synonyms and the multiplicity of the way humans imprint and structure text. The above-said techniques fall short in capturing language semantics and complicated linguistic structures along with their long-distance relationships, as humans do.

- Traditionally, researchers incorporated manually crafted knowledge bases and patterns to capture legal concepts, terms of interest and synonyms that were defined beforehand. Many works relied on the structure of the legal documents to be able to segment and process text. Nevertheless, the presumed structure was not consistent across different laws and legislations. The language is heterogeneous, the legal concepts evolve and the maintenance of legal knowledge bases is tedious and expensive.

- Their primary focus is to explore the word feature representations that are commonly used to feed Neural Networks or capture semantic similarities among text snippets.


### Contributions

- In this survey, they discuss a representative selection of the most notable recent articles that incorporate Deep Learning methods, oriented to address different tasks on legal corpora. They particularly focus on three main fields: 
  - **text classification**: they present some representative works relevant with to the categorization of textual units, such as sentences, paragraphs, sections or even long documents;
  - **information extraction**: they review characteristic articles related to sequence labeling (tagging) tasks, such as chunking and named-entity recognition;
  - **information retrieval**: they sort works that tackle the problem of retrieving articles of interest out of a collection of legal documents or articles that entail a query.
- They also share pre-trained legal word embeddings model (called **Law2Vec**) based on the word2vec skip-gram model over large corpora of English legislations (123,000 documents).


### Text classification

#### Classifying sentential modality in legal language: a use case in financial regulations, acts and directives (O’Neill et al., 2017)

- 
  

