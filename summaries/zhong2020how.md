## How Does NLP Benefit Legal System: A Summary of Legal Artificial Intelligence

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: H. Zhong et al.  
<ins>Date</ins>: 2020-05  
<ins>Tags</ins>: `survey`  
+++++++++++++++++++++++++++++++  


### Intro

- Legal Artificial Intelligence (LegalAI) focuses on applying the technology of artificial intelligence, especially natural language processing, to benefit tasks in the legal domain. 
- Many tasks in the legal domain require the expertise of legal practitioners and a thorough understanding of various legal documents. Retrieving and understanding legal documents take lots of time, even for legal professionals. Therefore, a qualified system of LegalAI should reduce the time consumption of these tedious jobs and benefit the legal system. 
- Besides, LegalAI can also provide a reliable reference to those who are not familiar with the legal domain, serving as an affordable form of legal aid.


### Contributions

- In this paper, they describe the history, the current state, and the future directions of research in LegalAI.
- They illustrate the tasks from the perspectives of legal professionals and NLP researchers and show several representative applications in LegalAI.
- They conduct experiments and provide an indepth analysis of the advantages and disadvantages of existing works to explore possible future directions.

***

### 1. Methods and challenges

- Two types of methods in LegalAI:
  1. **Symbol-based methods**: apply interpretable hand-crafted symbols to legal tasks. More specifically, these methods utilize interpretable legal knowledge to reason between symbols in legal documents (like events and reltionships). The problem with interpretable symbolic methods is that they are not very effective.
  2. **Embedding-based methods**: aim at designing efficient neural models to achieve better performance. More specifically, these methods try to learn latent features from large scale data. The problem with embedding-based methods is that they cannot be interpreted, which may bring ethical issues to the legal system (such as gender bias and racial discrimination).
- Primary challenges for both embedding-based and symbol-based methods in LegalAI:
  1. *Knowledge Modelling*: Legal texts are well formalized, and there are many domain knowledge and concepts in LegalAI. How to utilize the legal knowledge is of great significance.
  2. *Legal Reasoning*: Although most tasks in NLP require reasoning, the LegalAI tasks are somehow different, as legal reasoning must strictly follow the rules well-defined in law.
  3. *Interpretability*: Decisions made in LegalAI usually should be interpretable to be applied to the real legal system. Otherwise, fairness may risk being compromised.


### 2. Embedding-based Methods

- Embedding-based methods, also called **representation learning**, emphasize on representing legal facts and knowledge in embedding space, and they can utilize deep learning methods for corresponding tasks.


#### 2.1. Concept embeddings

- *Knowledge modelling* via embedding is challenging for two reasons:
  1. The construction of the knowledge graph in LegalAI is complicated. In addition, different legal concepts have different representations and meanings under legal systems in different countries, which makes it challenging to construct a general legal knowledge graph.
  2. A generalized legal knowledge graph is different in the form with those commonly used in NLP. Existing knowledge graphs concern the relationship between entities and concepts, but LegalAI focuses more on the explanation of legal concepts.
  
#### 2.2. Pre-trained language models

- Although pre-trained language models have recently shown to be very effective for solving a number of language tasks, it may not lead to such satisfactory results when applied to legal tasks due to the specificity of legal texts which are often very different from open-domain texts.
- Legal domain-specific pre-trained language models provide a more qualified baseline system for the tasks of LegalAI.
- In the future, researchers can aim more at integrating knowledge into pretrained models, which can help the reasoning ability between legal concepts.


### 3. Symbol-based Methods

- Symbol-based methods, also called **structured prediction methods**, utilize legal domain symbols and knowledge for the tasks of LegalAI.

#### 3.1. Information Extraction

- Emphasizes on extracting valuable information from texts (includes *name entity recognition*, *relation extraction*, *event extraction*).
- To make better use of the particularity of legal texts, researchers try to use *ontology* or *global consistency* for named entity recognition in LegalAI.
- To extract relationship and events from legal documents, researchers attempt to apply different NLP technologies, including *hand-crafted rules*, *CRF*, joint models like *SVM, CNN, GRU* or *scale-free identifier network*.
- The extracted symbols have high benefist as they provide a legal basis as well as interpretability to legal applications. For example, identifying the relationship between the parties is vital in inheritance dispute, as those who have the closest relationship with the deceased can get more assets. Towards this goal, relation extraction in inheritance dispute cases can provide the reason for judgment results and improve performance.

#### 3.2. Legal Element Extraction

- The extraction of legal elements focuses on extracting *constitutive elements of crime* (e.g., whether someone is killed or something is stolen).



