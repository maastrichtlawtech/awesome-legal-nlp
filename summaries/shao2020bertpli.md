## BERT-PLI: Modeling Paragraph-Level Interactions for Legal Case Retrieval

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: Y. Shao et al.  
<ins>Date</ins>: 2020-05  
<ins>Tags</ins>: `bert`  
+++++++++++++++++++++++++++++++  


### Intro

- Precedents (case laws) are a primary source of laws in the common law system, which is fundamental for a lawyer’s court preparations. With the rapid increase of digitized legal documents, it takes great efforts of legal practitioners to search for relevant cases manually. Given this situation, an automatic retrieval system that identifies relevant prior cases will greatly alleviate the heavy document works. Therefore, case law retrieval is an important research issue for both IR and legal communities.
- The legal case retrieval task, which aims to identify relevant prior cases given a query case, the legal case retrieval task is different from traditional ad-hoc text retrieval in several aspects, including the length of query and candidate texts, the definition of relevance, and the accessibility of legal datasets. Therefore, existing methods developed for IR tasks face a few serious challenges in this task, such as:
  - **Challenge 1**: Both the query and candidate cases involve extreme long texts. It is challenging for representation learning methods to represent the long document well in a limited semantic space, and it is also difficult for the matching function learning methods to construct and aggregate matching signals.
  - **Challenge 2**: The definition of relevance in the legal scenario is somehow beyond the general definition of topical relevance. Relevant cases are those that can support the decision of the current case, which usually involve similar situations and suitable statutes. Therefore, it is crucial to identify the similarities in the aspects of legal issues and legal processes of the cases, which calls for semantic understanding of whole documents.
  - **Challenge 3**: Collecting a large dataset for this task can be challenging if not impossible. For one thing, downloading large-scale legal documents is restricted in many law systems. For another, it is quite expensive to obtain accurate relevance judgments since it requires expert knowledge in the legal do
main. The lack of data brings obstacles to the training process of deep neural models.


### Contributions

- They propose BERT-PLI, a novel model that utilizes BERT to capture the semantic relationships at the paragraph-level and then infers the relevance between two cases by aggregating paragraph-level interactions.
- They conduct extensive experiments on the benchmark of the relevant case retrieval task in COLIEE 2019, and show that their proposed method outperforms existing solutions.

***

### Related work

- In the past decades: bag-of-words IR models were used, including **VSM**, **BM25** and **LMIR**, which are widely applied in search systems and are mostly based on term-levl matching.
- Since the mid-2000s, **LTR** (Learning to Rank) methods which are driven heavily by manual feature engineering, have been well studied and utilized by commercial web search engines as well.
- In recent years, the development of **deep learning** has also inspired applications of neural models in IR. Generally, the methods can be categorized into two types:
  1. *methods of representation learning*: queries and documents are represented in the latent space by deep learning models, and the query-document relevance score is calculated based on their latent representations with a vector space scoring function, e.g., cosine similarity. Various neural network models have been applied to this task (e.g., DSSM, CNNs and RNNs), but most of the model structures are not designed for representing long documents (it is difficult for CNN models to represent the complex global semantic information while RNN models tend to forget important signals when dealing with a long sequence).
  2. *methods of matching function learning*: first construct a matching matrix or capture local interactions based on the word-level matching, and then use neural networks to discover the high-level matching patterns and aggregate the final relevance score. Although these models work well for ad-hoc text retrieval, where the query is quite short, their performances are restricted in the scenario of legal case retrieval due to its quadratic time and memory complexity in constructing the whole interaction matrix.
- Recently, some works have shed light on the application of BERT to ad-hoc retrieval by modeling evidence in query-sentence or query-passage pairs.


### Method

- Multi-stage pipeline inspired by the cascade framework, consisting of three stages:
  - **Stage 1**: they select top-K candidates from the initial candidate corpus with respect to the query case q according to **BM25** scores. 
    - This stage inevitably hurts both recall and precision, but allows to reduce computational cost compared to using BERT on all candidate cases.
  - **Stage 2**: they fine-tune the **BERT** model on a sentence pair classification task with the legal case entailment dataset of COLIEE-2019. 
    - Fine-tuning on this task enables BERT to infer the supportive relationships between paragraphs, which is useful for the legal case retrieval task. 
    - They fine-tune all parameters of BERT on a sentence pair classification task in an end-to-end fashion. 
    - The input is composed of the decision paragraph of a query case and a candidate paragraph in the relevant case. The text pair is separated by the [SEP] token and a [CLS] token is prepended to the text pair. 
    - As for the output, they feed the final hidden state vector corresponding to the first input token ([CLS]) into a classification layer. In this task, they use a fully-connected layer to do binary classification, optimizing a cross-entropy loss.
  - **Stage 3**: BERT-PLI conducts relevance prediction with the fine-tuned BERT (Stage 2) among the selected candidates (Stage 1).
    - To tackle the challenge brought by long and complex documents, they first break a document into paragraphs.
    - For each paragraph in the query document *q* and the candidate document *d*, they construct a paragraph pair as the input of the fine-tuned BERT.
    - The final hidden state vector of the [CLS] token is viewed as the aggregate representation of the input paragraph pair. 
    - In that way, they get an interaction map of paragraphs, in which each component models the semantic relationship between the query paragraph and the candidate paragraph.
    - For each paragraph of the query, they capture the strongest matching signals with the candidate document using the max-pooling strategy in the interaction map (i.e., max-pooling over all the [CLS] token representations of the input pairs for a given query paragraph). For a given query document, they then have a sequence of N (number of paragraphs in query document *q) vectors resulting from the max-pooling operation.
    - They then use a RNN structure (they explore both LSTM and GRU) to further encode the representation sequence. The attention mechanism is also employed to infer the importance of each position. They can then get the document-level representation via attentive aggregation.
    - Finally, Finally, the document-level representation is passed through a fully connected layer followed by a softmax function to make prediction.
    
### Results

- They compared their model with three types of baselines:
  - Traditional bag-of-words retrieval models: VSM, BM25 and LMIR.
  - Deep retrieval models: ARC-II and MatchPyramid (two matching function learning models).
  - Top 2 teams in COLIEE-2019 competition:
    - JNLP: trained a supervised summarization model based on COLIEE 2018’s dataset and applied the model to encoding the case document into a continuous vector. They combined such the summary embeddings with lexical matching features, calculated by ROUGE and learned the document rankings via RankSVM.
    - ILPS: generated summaries by the TextRank algorithm first and assessed pairwise relevance by a carefully fine-tuned BERT model, combined with oversampling strategies.
