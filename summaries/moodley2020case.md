##

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: K. Moodley et al.  
<ins>Date</ins>: 2020-05  
<ins>Tags</ins>: `legal research`, `software platform`    
+++++++++++++++++++++++++++++++  


### Intro

- In recent years, EU law has become increasingly digitised and published in online databases such as EUR-Lex and HUDOC. However, the main barrier inhibiting legal scholars from analysing this information is lack of training in data analytics.
- Current legal analytics software are dominated by the commercial sector. In addition, most systems focus on search of legal information but do not facilitate advanced visualisation and analytics. On the contrary, free to use systems that do provide such features are either too complex to use for general legal scholars, or are not rich enough in their analytics tools.


### Contributions

- In this paper, they motivate the case for building a software platform that addresses the mentioned limitations.
- In particular, it will look at how this infrastructure can be created to prepare data automatically, and apply data analysis methods, such as Natural Language Processing (NLP) and network analysis, to case law on behalf of the legal scholar.
- Such software can provide a powerful platform for visualising and exploring connections and correlations in EU case law, as well as inspire and answer new research questions in empirical legal research.

***

### 1. Potential of technology for legal research

- Case law traditionally relies on **human analysis**, that is analysis without software or other technical aid. Legal researchers manually search, read, and interpret court decisions. In this process, technological assistance is commonly available in the form of online search facilities (keyword search in electronic case law databases).
- **Case synthesis** is the method commonly applied by legal researchers and law students when analysing court decisions. This method essentially entails that case outcomes are compared with the facts of the cases, with the purpose of explaining the differences in outcomes by the differences in facts. As a result of the high cognitive workload involved in this type of reasoning, case law is commonly analysed based on a relatively small number of cases, at least compared to the whole body of case law that is available. Data science methods enable computers to consider vastly more cases than human scholars.
- With respect to case law, various **research questions** may be raised, including:
  - What are the cases surrounding the landmark cases?
  - Which clusters of decisions can be distinguished?
  - Are there other landmark cases that have remained undetected in the literature?
- Answering questions such as those presented above requires a variety of **analytical methods**, ranging from network analysis, statistical methods to NLP. There are at least three important reasons **why such research has not yet taken off**:
  1. Firstly, proper data infrastructures are not readily available to automatically find, extract and prepare legal information for analysis by software. Technologies such as web scraping, in principle, allow this information to be automatically extracted in larger volumes from public case law websites. However, these technologies have not been integrated into software that legal scholars can easily use to retrieve and prepare the information they need for analysis.
  2. Secondly, existing software platforms that provide access to legal information generally only focus on searching and browsing, neglecting to include functions for analysing the information using cutting-edge data science methods.
  3. Thirdly, those systems that do provide some features for analysing, exploring and visualising patterns in the information, do not provide interfaces that are user-friendly for non-data science experts in the legal domain.
  

### 2. Computational tools addressing legal research

- Data analytics has been a profitable enterprise for many **corporate organisations** in the last decade. The result is that, by far, available software for supporting analysis (not purely search) of legal information is predominantly developed by commercial enterprises.
- Their **criteria** for selecting the analytics tools to survey are:
  1. the tools should have a graphical user interface (because the goal is to enable legal scholars with no programming or technical experience to use the platform); 
  2. the tool should be capable of analysing case law texts specifically; 
  3. the user interface should provide a visual way for representing results from its analysis.
- Existing tools include:
  - <ins>ROSS Intelligence</ins>
    - Software research engine that uses artificial intelligence to semi-automate legal research, claiming to make it more efficient and less expensive.
    - Its data sources include a comprehensive body of case law texts originating in the United States Supreme Court, Circuit Courts of Appeals, District Courts, Bankruptcy Courts, State Supreme and Appellate courts.
    - To use ROSS, the user types in a natural language question (eg “What is the standard for gross negligence in New York after 2004?”) and submits it to the system. ROSS then uses NLP to “understand” or interpret the question using its proprietary algorithms. The jurisdiction and time range, for example, are identified (“New York” and “after 2004”). Thereafter, it searches the body of case law using the identified information to find a list of passages in the text that are relevant to the question. It also looks at citation graphs of the cases to identify other relevant case passages to “read”. Once the final list of texts is retrieved, the texts are ordered according to relevance using a combination of machine learning algorithms.
  - <ins>LexPredict</ins>
    - The data sources used by LexPredict all concern case law and legislation originating from the US.
    - The LexPredict platform splits its functionality across multiple commercially licensed software applications including: LexSemble, CounselTracker, and LexReserve.
    -  LexPredict also develops publicly available open-source software such as LexNLP and ContraxSuite. LexNLP focuses on recognising specific types of information from legal text (date, parties, citations, references to courts, copyrights, etc), while ContraxSuite is build upon LexNLP and is used to analyse text in legal documents and provides dashboards and visual plots about patterns it identifies in legal texts. While the source code for the technologies underlying ContraxSuite is made publicly available, the source code for the complete software platform itself (with its graphical user interface) is not publicly available.
  - <ins>OpenLaw</ins>
    - Software platform (website) that provides similar search and retrieval functions to EUR-Lex, with the added benefit of having amore intuitive and user-friendly search interface.
  - <ins>ConsumerCases</ins>
    - Software that allows search and retrieval of legal documents, and beyond this, automatic annotation of the text with relevant entities (using NLP).
    - With the click of a checkbox one can see the main entities (eg dates, legal persons, organisations, courts, articles cited etc) highlighted in the text.
    - However, the task of identifying relationships or connections between cases is still left up to the user.
  - <ins>UM/NLeSC</ins>
    - Case law analytics application developed to analyse Dutch case law.
    - The data was imported from Rechtspraak.nl and the tool helps the user perform network (citation) analysis on the cases.
  - <ins>EUCaseNet</ins>
    - Web-based software platform to perform analysis on EU case law specifically.
    - The tool facilitates network analysis on the full body of case law from the Court of Justice of the EU.
- Discussion: their main findings are that while the majority of the current platforms are dominated by the commercial sector, other platforms focus almost exclusively on search and retrieval of legal documents, and most platforms focus on case law from a single national database. From the above, they derive the need to develop software that:
  1. is more user-friendly and accessible for the general legal scholar; 
  2. performs advanced visual analysis of case law integrated from multiple national databases; 
  3. is open-source, FAIR and designed for both researchers and students alike;
  4. generates insights that are reproducible and shareable with other researchers and students.


### 3. Proposing a research engine for legal data analytics

