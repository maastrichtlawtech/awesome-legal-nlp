## BERT-PLI: Modeling Paragraph-Level Interactions for Legal Case Retrieval

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: Y. Shao et al.  
<ins>Date</ins>: 2020-05  
<ins>Tags</ins>:   
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
- We conduct extensive experiments on the benchmark of the relevant case retrieval task in COLIEE 2019, and show that their proposed method outperforms existing solutions.

***
