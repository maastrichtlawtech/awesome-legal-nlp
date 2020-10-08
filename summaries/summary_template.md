## Bringing PageRank to the citation analysis

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: N. Ma et al.  
<ins>Date</ins>: 2007-08  
<ins>Tags</ins>: `citation analysis`, `pagerank`   
+++++++++++++++++++++++++++++++  


### Intro

- Although, the number of citations gives a direct approximation of a paper’s importance, we may still experience some situations when citations do not seem to provide a full picture of the academic prestige of a paper. 
- While most of the citation analyses have been based on how many times the papers were cited, we are thus motivated to study from another perspective which concerns more about who actually cited the papers and the prestige they have transferred to the cited papers. And the Google’s PageRank algorithm is such an existing metric used for the evaluation of Web pages.


### Contributions

- The paper attempts to provide an alternative method for measuring the importance of scientific papers based on the Google’s PageRank, which offers a more integrated picture of the publications’ influence in a specific field.
- In this paper, they firstly calculate the PageRanks of scientific papers, then analyze the distributional characteristics in detail and finally compare with the traditionally used number of citations.

***

### The PageRank algorithm

- In such complex networks as World Wide Web, an important attribute of a node is the in-degree (out-degree); namely the number of inbound (outbound) links on the node.
- The in-degree of a given page could be considered as an approximation of a page’s importance or quality. The PageRank algorithm extends this idea by not counting the inbound links from all pages equally, but by normalizing via both the importance and the number of outbound links of the neighboring pages.
- In this respect, the PageRank value could serve as a better measure of importance, as it incorporates the paper’s visibility and authority at the same time by taking both the number of citations and prestige of the citing papers into account.


### Conclusions

- The PageRank algorithm provides a meaningful extension to the traditionally used number of citations for individual papers or aggregation of papers at different levels.
- The citation network of scientific publications is an important resource that would provide additional information compared to the traditional citation analysis.
- The PageRank is an objective measure of its citation importance that corresponds well with people’s subjective idea of importance. Because of this correspondence, PageRank is an excellent way to prioritize the influence of research papers suffering from relatively lower citations, therefore excavating the potential influence of scientific publications.
- A meaningful advantage of PageRank is that it could largely eliminate the flattery of academic influence caused by author self-citations. It is somewhat reckless to completely ignore the effect of author self-citations, as there probably are some thoughtful considerations and instructive nexus when authors cite their previous works. In this case, the PageRank algorithm treats the author self-citations with more consciousness.
- However, the robustness of PageRank algorithm with respect to the free parameter d is still under discussion. They choose d = 0.5 based on Chen’s empirical study that most scientists normally follow an order of 2 citation links in a citation network.
