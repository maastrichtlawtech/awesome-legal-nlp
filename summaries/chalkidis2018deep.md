## Deep learning in law: early adaptation and legal word embeddings trained on large corpora

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: I. Chalkidis et al.  
<ins>Date</ins>: 2018-12  
<ins>Tags</ins>: `survey`, `legal word vectors`, `information retrieval`, `text classification`, `information extraction`  
+++++++++++++++++++++++++++++++


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
- The authors experimented with a training set consisting of ~1,900 annotated (by domain-experts) sentences including obligations, prohibitions, and permissions.
- The authors experimented with various methods, including Logistic Regression, SVMs, AdaBoost, Gradient Boosting and Random Forests. Those methods were examined using two alternative feature representations:
  - Baselines: n-grams, POS tags and normalized tf-idf scores;
  - Sentence concatenations of word embeddings: Google embeddings (pre-trained from Google news articles) and legal embeddings (pre-trained over a corpus of 7,500 EU legislation documents).
- The authors also experimented with neural network methods including a Multi-Layer Perceptron (MLP) with 2 hidden layers, unidirectional and bidirectional LSTMs, followed by a fully-connected layer, multi-filter CNNs, and CNNs followed by LSTMs and a fully-connected hidden layer. All neural methods were examined using two alternative feature representations. First, only the Google vectors were considered. Second, the authors used their domain-specific pre-trained word and phrase embeddings, to feed LSTMs or CNNs.
- The conclusions were the following:
  - Classic ML algorithms were vastly overfitting the training set.
  - All Neural Networks (except the naive MLP) outperformed the classic ML algorithms by over 10% on average. This indicates the superiority of RNNs and more specifically LSTMs when dealing with complex language semantics.
  - BiLSTMs was the best-of method, outperforming the unidirectional LSTMs and naive CNNs approaches.
  - Providing domain-specific (legal) embeddings further improved the performance of the neural methods.
  

#### Obligation and prohibition extraction using hierarchical RNNs (Chalkidis et al., 2018)

- They improved the state-of-art on sentence modality classification by proposing a more refined scheme of annotations that incorporate sub-sentence classification.
- The authors experimented with an in-house dataset of ~9,400 sections from the main bodies of a hundred randomly selected English service agreements. The sections were then split into ~45,100 sub-sentences annotated by law students.
- They used domain-specific pre-trained word embeddings and POS embeddings obtained by applying word2vec to ~750K and ~50K English contracts respectively, as well as token shape embeddings (e.g., all capital, all digit). Each token was represented by the concatenation of its word, POS and shape embeddings.
- They experimented with several LSTM-based methods.
- The conclusions were the following:
  - The self-attention mechanism led to an overall improvement compared to the plain BiLSTM.
  - The hierarchical model significantly outperformed the other methods.
  - The hierarchical model is faster to train than the previous ones, even though it had more parameters.
  
#### Inducing predictive models for decision support in administrative adjudication ([Branting et al., 2017](branting2017inducing.md))

- They experimented with predictive models for assisting Administrative Adjudication.
