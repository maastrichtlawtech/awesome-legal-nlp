##

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: M. van Opijnen et al.  
<ins>Date</ins>: 2017-03  
<ins>Tags</ins>: `relevance`  
+++++++++++++++++++++++++++++++  


### Intro

- The number of legal documents published online is growing exponentially, but accessibility and searchability have not kept pace with this growth rate. An overload of information (particularly if of low-quality) carries the risk of undermining knowledge acquisition possibilities and even access to justice.
- To limit the role of LIR within daily legal practice to just finding the court decisions relevant to the case at hand underestimates the complexities of the law and of legal information seeking behaviour. Any legal information retrieval system built without sufficient knowledge, not just of the actual legal information needs but also of the ‘juristic mind’, is apt to fail.
- The concept of ‘relevance’ is crucial to legal information retrieval, but because of its intuitive understanding it goes undefined too easily and unexplored too often.


### Contributions

- They discuss a conceptual framework on relevance within legal information retrieval, based on a typology of relevance dimensions used within general information retrieval science, but tailored to the specific features of legal information.
- This framework can be used for the development and improvement of legal information retrieval systems.

***

### 1. Legal Information Retrieval

#### Inference vs. querying

- They highlight two types of information systems: **legal expert systems (LES)** and **legal information retrieval (LIR)**.
- LIR starts where LES isn’t able to provide an answer. And notwithstanding the improvements AI & Law brings to LES, there will always be questions left and relevant documents to be discovered, since the lack of any final scheme is inherent to the legal domain.

#### 

### Conclusions

- Relevance, the basic notion of information retrieval is a thoroughly human notion and as all human notions, it is somewhat messy.
- Because most LIR systems are designed by retrieval specialists without comprehensive domain knowledge, sometimes assisted by domain specialists with too little knowledge of retrieval technology, users are often disappointed by their relevance performance.
- 4 main conclusions:
  1. Retrieval engineering is focused too exclusively on algorithmic relevance, but it has been proven sufficiently that without domain specific adaptations every search engine will disappoint legal users. All dimensions of relevance have to be considered explicitly while designing all components of LIR systems: document pre-processing, (meta)data modelling, query building, retrieval engine and user interface.
  2. The ‘isness’ concept is overlooked too often. Finding a work — and not (just) the related works — is an often-used functionality for jurists, but misunderstood by system developers.
  3. Domain relevance is an underdeveloped concept. While there is a tendency to publish ever more legal information, especially court decisions, without tagging it as to its juristic value, information overkill will become a serious threat to the accessibility of such databases. Performance on other relevance dimensions will suffer if the problem of domain relevance isn’t tackled sufficiently.
  4. The gap between LIR systems and user needs is still substantial. For a full understanding of their search needs just taking stock of their wishes is not going to suffice, since legal professionals are not capable of describing the features of a system that does not yet exist. To understand the juristic mindset, it is of the utmost importance to follow meticulously their day-to-day retrieval quests. It will for sure reveal interesting insights that can be used to improve the relevance performance of LIR systems.
