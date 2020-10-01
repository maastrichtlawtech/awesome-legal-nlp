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

### Methods and challenges

- Two types of methods in LegalAI:
  1. **Symbol-based methods**: apply interpretable hand-crafted symbols to legal tasks. More specifically, these methods utilize interpretable legal knowledge to reason between symbols in legal documents (like events and reltionships). The problem with interpretable symbolic methods is that they are not very effective.
  2. **Embedding-based methods**: aim at designing efficient neural models to achieve better performance. More specifically, these methods try to learn latent features from large scale data. The problem with embedding-based methods is that they cannot be interpreted, which may bring ethical issues to the legal system (such as gender bias and racial discrimination).
- Primary challenges for both embedding-based and symbol-based methods in LegalAI:
  1. *Knowledge Modelling*: Legal texts are well formalized, and there are many domain knowledge and concepts in LegalAI. How to utilize the legal knowledge is of great significance.
  2. *Legal Reasoning*: Although most tasks in NLP require reasoning, the LegalAI tasks are somehow different, as legal reasoning must strictly follow the rules well-defined in law.
  3. *Interpretability*: Decisions made in LegalAI usually should be interpretable to be applied to the real legal system. Otherwise, fairness may risk being compromised.


### Embedding-based Methods

- 
  
  





