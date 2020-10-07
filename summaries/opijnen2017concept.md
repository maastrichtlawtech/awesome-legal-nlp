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

#### Characteristics of legal information

1. **Volume**: The volume of legal materials is impressive. This holds true for public repositories (like case law databases) as well as for private repositories (e.g. case file within law firms or courts).
2. **Document size**: Compared to other domains, legal documents tend to be quite long.
3. **Structure**: many legal documents do not have any (computer readable) structure at all.
4. **Heterogeneity of document types**: In the legal sphere, a variety of document types exist (e.g., legislation and court decisions, parliamentary documents, contracts, loose-leaf commentaries, case-law notes, etc).
5. **Self-contained documents**: Documents in the legal domain are not just ‘about’ the domain, they actually contain the domain itself, the object to be retrieved embodies the object itself. (e.g., a statute is not merely a description of what the law is, it constitutes the law itself).
6. **Temporal aspects**: Legislative texts and amendments follow one another and may overlap. One recurrent challenge is to retrieve the applicable law in respect to the timeframes covered by the events subject to regulation.
7. **Importance of citations**: In most other scientific domains, citation indexes exist for academic papers while in the legal domain, citations are a more integral part of text and argumentation. Besides, citations can be explicit or implicit and they can express a whole variety of different relationships. And in general, most citations are poorly formatted and not computer readable.
8. **Legal terminology**: Legal terminology has a rich and very specific vocabulary, characterized by synonymy, ambiguity, polysemy and definitions that are very precise and vague at the same time.
9. **Audience**: Legal information is queried by a wide variety of audiences (scholars, judges, lawyers, notaries, library staff or legal aid workers) that have completely different work roles that influence their information needs.
10. **Personal data**: Many legal documents contain personal data.
11. **Multilingualism and multi-jurisdictionality**: Civil law jurisdictions have a variety of languages. As a result, European or international legal information retrieval poses very specific problems because of the strong relationship between jurisdiction and language.
12. **Scatteredness of legal resources**: Legal information is to be found in a variety of resources, scattered in a complex way, with different access regimes, technical formats and interfaces.


### Conclusions

- Relevance, the basic notion of information retrieval is a thoroughly human notion and as all human notions, it is somewhat messy.
- Because most LIR systems are designed by retrieval specialists without comprehensive domain knowledge, sometimes assisted by domain specialists with too little knowledge of retrieval technology, users are often disappointed by their relevance performance.
- 4 main conclusions:
  1. Retrieval engineering is focused too exclusively on algorithmic relevance, but it has been proven sufficiently that without domain specific adaptations every search engine will disappoint legal users. All dimensions of relevance have to be considered explicitly while designing all components of LIR systems: document pre-processing, (meta)data modelling, query building, retrieval engine and user interface.
  2. The ‘isness’ concept is overlooked too often. Finding a work — and not (just) the related works — is an often-used functionality for jurists, but misunderstood by system developers.
  3. Domain relevance is an underdeveloped concept. While there is a tendency to publish ever more legal information, especially court decisions, without tagging it as to its juristic value, information overkill will become a serious threat to the accessibility of such databases. Performance on other relevance dimensions will suffer if the problem of domain relevance isn’t tackled sufficiently.
  4. The gap between LIR systems and user needs is still substantial. For a full understanding of their search needs just taking stock of their wishes is not going to suffice, since legal professionals are not capable of describing the features of a system that does not yet exist. To understand the juristic mindset, it is of the utmost importance to follow meticulously their day-to-day retrieval quests. It will for sure reveal interesting insights that can be used to improve the relevance performance of LIR systems.
