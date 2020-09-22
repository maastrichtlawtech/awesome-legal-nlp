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


### A. Text classification

#### Classifying sentential modality in legal language: a use case in financial regulations, acts and directives (O’Neill et al., 2017)

- Classical logic may be ineffective in classifying sentential modality as modality in legal language strongly relies on the use of modal verbs which have multiple functions and may also be misused in several occasions. These are strong indications that the context in each case is very important for deciphering the actual role of these modal verbs, hence a machine-learning approach seems more promising.
- The authors experimented with a training set consisting of 1297 annotated sentences including obligations, prohibitions, and permissions; while the gold standard test set was composed of 622 sentences. The documents were annotated by domain-experts.
- The authors experimented with various methods, including Logistic Regression, SVMs, AdaBoost, Gradient Boosting and Random Forests. Those methods were examined using two alternative feature representations:
  - Baselines: n-grams, POS tags and normalized tf-idf scores;
  - Sentence concatenations of word embeddings: Google embeddings (pre-trained from Google news articles) and legal embeddings (pre-trained over a corpus of 7,500 EU legislation documents).
- The authors also experimented with neural network methods including a Multi-Layer Perceptron (MLP) with 2 hidden layers, unidirectional and bidirectional LSTMs, followed by a fully-connected layer, multi-filter CNNs, and CNNs followed by LSTMs and a fully-connected hidden layer. All neural methods were examined using two alternative feature representations. First, only the Google vectors were considered. Second, the authors used their domain-specific pre-trained word and phrase embeddings, to feed LSTMs or CNNs.
- The conclusions are the following:
  - Classic ML algorithms were vastly overfitting the training set.
  - All Neural Networks (except the naive MLP) outperformed the classic ML algorithms by over 10% on average. This indicates the superiority of RNNs and more specifically LSTMs when dealing with complex language semantics.
  - BiLSTMs was the best-of method, outperforming the unidirectional LSTMs and naive CNNs approaches.
  - Providing domain-specific (legal) embeddings further improved the performance of the neural methods.
  

#### 
