## Promise and Pitfalls of Extending Google’s PageRank Algorithm to Citation Networks

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: S. Maslov et al.  
<ins>Date</ins>: 2008-10  
<ins>Tags</ins>: `citation network`, `pagerank`    
+++++++++++++++++++++++++++++++  


### Intro

- The number of citations is the most commonly used metric for quantifying the importance of scientific publications. Some of the shortcomings of using citations as a universal measure of importance include the following:
  1. A citation from an obscure paper is given the same weight as a citation from a ground-breaking and highly cited work.
  2. Due to factors such as size of a field and disparate citation practices, the average number of citations per paper varies widely between disciplines.
  3. Many groundbreaking older articles are modestly cited once their results are incorporated into textbooks.
- These and related shortcomings of citation numbers are partially obviated by Google’s PageRank algorithm, which gives higher weight to publications that are cited by important papers and also weights citations more highly from papers with few references.
- Because of these attributes, PageRank readily identifies a large number of scientific “gems”: modestly cited articles that contain ground breaking results.


### PageRank for articles

- We can think of the set of articles and their citations as a network, with nodes representing articles and a directed link between two nodes representing a citation from a citing article to a cited article.
- In Google’s PageRank algorithm, a random surfer is partially placed at each node of this network and its position is updated as follows:
  1. with probability 1-*d*, a surfer hops to a neighboring node by following a randomly selected outgoing link from the current node; 
  2. with probability *d*, a surfer “gets bored” and starts a new search from a randomly selected node in the entire network. 
- This update is repeated until the number of surfers at each node reaches a steady value, the Google number. These nodal Google numbers are then sorted to determine the Google rank of each node.
- The PageRank of a paper is enhanced when it is cited by its scientific “children” that themselves have high PageRank and when these children have short reference lists. That is, children should be influential and the initial paper should loom as an important “father figure” to its children.
- The PageRank algorithm was originally developed to rank web pages that are connected by hyperlinks and not papers connected by citations. The most im portant differences between these two networks are:
  1. Unlike hyperlinks, citations cannot be updated after publication. The constraint that a paper may only cite earlier works introduces a time ordering to the citation network topology. This ordering makes aging effects much more important in citation networks than in the World-Wide Web.
  2. The habits of scientists looking for relevant scientific literature are also different from web surfers. Scientists often start literature searches with a paper of interest that they saw in a recent issue of a journal or heard presented at a conference. From this starting point a researcher typically follows chains citations that lead to progressively older publications.
- These observations led to modify the PageRank algorithm by initially distributing random surfers exponentially with age, in favor of more recent publications with a novel algorithm called CiteRank (Walker et al., 2007). This algorithm is characterized by just two parameters: *d* (the inverse of the average citation depth) and *t* (the time constant of the bias toward more recent publications at the start of searches)


