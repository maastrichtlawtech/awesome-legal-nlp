## CLAUDETTE: an automated detector of potentially unfair clauses in online terms of service


+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: M. Lippi et al.  
<ins>Date</ins>: 2019-02  
<ins>Tags</ins>: `machine learning`, `nlp`, `terms of service`, `unfair clauses`  
+++++++++++++++++++++++++++++++  


### Intro

- Consumers rarely read the contracts they are required to accept. The biggest lie on the Internet is “I have read and agree to the terms and conditions”. Virtually every app we install and website we browse have their own Terms of Service (ToS), i.e. contracts governing the relation between providers and users, establishing mutual rights and obligations. However, we are not necessarily aware of what we just agreed upon.
- There are reasons why many consumers do not read or understand ToS, as well as privacy policies or end-user license agreements (EULA). Such documents can be overwhelming to the few consumers who actually venture to read them. Another problem is that even if consumers did read the ToS thoroughly, they would have no means to influence their content: the choice is to either agree to the terms offered by a web app or simply not use the service at all.
- European consumer law aims to prevent businesses from using so-called “unfair contractual terms” in contracts they unilaterally draft and require consumers to accept. According to the Unfair Contract Terms Directive (UCTD), a “term” or “clause” (i.e., a sentence, statement on or paragraph expressing a contractual norm that specifies parties rights and obligations) is unfair if, “contrary to the requirement of good faith, it causes a significant imbalance in the parties rights and obligations arising under the contract, to the detriment of the consumer”.
- Law regarding such terms applies also to the ToS of on-line platforms. In spite of it all, such platforms’ owners do use in their ToS unfair contractual clauses notwithstanding European law, and regardless of consumer protection agencies, which have the competence, but not necessarily the resources, to fight against such unlawful practices.


### Contributions

- They propose a machine learning-based method and tool for partially automating the detection of *potentially* unfair clauses (contractual provisions). Note that they focus on focus on potentially unfair clauses as from a legal standpoint, a given clause can be deemed unfair with absolute certainty only if a competent institution, such as a national court having refereed to the European Court of Justice, has ruled in that sense.
- In particular, they offer a sentence classification system able to detect full sentences, or paragraphs containing potentially unlawful clauses.
- Such a tool could improve consumers’ understanding of what they agree upon by accepting a contract, as well as serve consumer protection organizations and agencies, by making their work more effective and efficient, by helping them scan and monitor a large number of documents automatically.


***

### Unfair contractual terms

- According to Unfair Terms in Consumer Contracts, a contractual term is unfair if:
  1. it has not been individually negotiated; and
  2. contrary to the requirement of good faith, it causes a significant imbalance in the parties’ rights and obligations, to the detriment of the consumer.
- Here are some examples of potentially unfair clauses often appearing in the terms of on-line services: 
  1. establishing jurisdiction for disputes in a country different than consumer’s residence; 
  2. choice of a foreign law governing the contract; 
  3. limitation of liability; 
  4. the provider’s right to unilaterally terminate the contract/access to the service; 
  5. the provider’s right to unilaterally modify the contract/the service. 
  6. requiring a consumer to undertake arbitration before the court proceedings can commence; 
  7. the provider retaining the right to unilaterally remove consumer content from the service, including in-app purchases; 
  8. having a consumer accept the agreement simply by using the service, not only without reading it, but even without having to click on “I agree/I accept”.
- There are two mechanisms to prevent the use of unfair contractual terms: *individual* and *abstract* control of fairness.
  - *Individual* control of fairness: takes place when a consumer goes to court. If a court finds that a clauses is unfair, it will consider that the clause is not binding on the consumer. However, most consumers do not take their disputes to courts.
  - *Abstract* control of fairness: in each EU Member State, consumer protection organizations have the competence to initiate judicial or administrative proceedings, to obtain the declaration that clauses in consumer contracts are unfair. **But the national implementations of abstract control differ in various ways**.


### Corpus annotation

- The training corpus consists of 50 relevant on-line consumer contracts, i.e., ToS of well-known online platforms (Google, Netflix, Spotify, etc.). A further test set consisting of 10 additional contracts was tagged.
- They focused on the 8 different categories of unfair clauses mentioned previously. In order to mark the different degrees of (un)fairness, they appended a numeric value to each tag, with 1 meaning *clearly fair*, 2 *potentially unfair*, and 3 *clearly unfair*. Some clauses might have multiple tags. The categories of clause unfairness are:
  1. *Jurisdiction*: stipulates what courts will have the competence to adjudicate disputes under the contract. Jurisdiction clauses giving consumers a right to bring disputes in their place of residence were marked as clearly fair, whereas clauses stating that any judicial proceeding takes a residence away (i.e. in a different city, different country) were marked as clearly unfair.
  2. *Choice of law*: specifies what law will govern the contract, meaning also what law will be applied in potential adjudication of a dispute arising under the contract. Clauses defining the applicable law as the law of the consumer’s country of residence were marked as clearly fair. In every other case, the choice of law clause was considered as potentially unfair.
  3. *Limitation of liability*: stipulates that the duty to pay damages is limited or excluded, for certain kinds of losses and under certain conditions. Clauses that explicitly affirm non-excludable providers’ liabilities were marked as clearly fair. Clauses that reduce, limit, or exclude the liability of the service provider were marked as potentially unfair when concerning broad categories of losses or causes of them, such as any harm to the computer system because of malware or loss of data or the suspension, modification, discontinuance or lack of the availability of the service. Clause meant to reduce, limit, or exclude the liability of the service provider for physical injuries, intentional damages as well as in case of gross negligence were marked as clearly unfair.
  4. *Unilateral change*: specifies the conditions under which the service provider could amend and modify the terms of service and/or the service itself. Such clauses were always considered as potentially unfair.
  5. *Unilateral termination*: gives provider the right to suspend and/or terminate the service and/or the contract. Unilateral termination clauses that specify reasons for termination were marked as potentially unfair. whereas clauses stipulating that the service provider may suspend or terminate the service at any time for any or no reasons and/or without notice were marked as clearly unfair.
  6. *Contract by using*: stipulates that the consumer is bound by the terms of use of a specific service, simply by using the service, without even being required to mark that he or she has read and accepted them. Such clauses are always marked as potentially unfair.
  7. *Content removal*: gives the provider a right to modify/delete user’s content, including in-app purchases. Clauses that indicate conditions for content removal were marked as potentially unfair, whereas clauses stipulating that the service provider may remove content in his full discretion, and/or at any time for any or no reasons and/or without notice nor possibility to retrieve the content were marked as clearly unfair.
  8. *Arbitration*: requires or allows the parties to resolve their disputes through an arbitration process, before the case could go to court. Clauses stipulating that the arbitration should (1) take place in a state other than the state of consumer’s residence and/or (2) be based not on law but on arbiter’s discretion were marked as clearly unfair. Clauses defining arbitration as fully optional would have to be marked as clearly fair.
 
 
### Machine learning methodology

-  The study focuses two different tasks:  
  - A detection task, aimed at predicting whether a given sentence contains a (potentially) unfair clause;
  - A classification task, aimed at predicting the category an unfair clause belongs to.
- <ins>Detecting potentially unfair contract clauses</ins>:
  - The problem is addressed as a binary sentence classification task. 
  - Such a task could be tackled by treating sentences independently of one another (*sentence-wide classification*) or by taking into account the structure of the document, in particular the sequence of sentences, so as to perform a *collective classification*. The potential advantage of the latter approach becomes apparent if we observe that unfair clauses often span across consecutive sentences in a document.
  - For sentence-wide classification, they compare Support Vector Machines (SVMs) with Convolutional Neural Networks (CNNs) and Long-Short Term Memory Networks (LSTMs).
  - For collective classification, they rely on structured Support Vector Machines, and in particular on SVM-HMMs, which combine SVMs with Hidden Markov Models.
  - They used three different approaches for sentence representation:
    1. bag-of-words (BoW);
    2. consituency parse tree;
    3. word-embeddings.
  - Results:
    - The best classifier in terms of F1 results to be a combination of eight SVMs, each considering a single unfairness category as the positive class, whereby a sentence is predicted as potentially unfair if at least one of the SVMs predicts it as such. The second best approach is a single SVM exploiting BoW (unigrams and bigrams for words and part-of-speech tags);
    - As for CNNs and LSTMs, the slightly worse performance with respect to the other approaches could also be ascribed to the limited size of the training set.
- <ins>Categorization of potentially unfair clauses</ins>:
  - They employed eight SVM classifiers, each trained to discriminate between potentially unfair clauses of one category with respect to all the other categories.
  - The results show that discriminating amongst the different categories is a simpler task, since the F1 is larger than 74% for all tags, and is above 93% in four cases (jurisdiction, choice of law, limitation of liability, and contract by using).
  
### Conclusions

- This study was motivated by a long-term goal concerned with the pursuit of effective consumer protection by way of AI-based consumer-empowering tools.
- They are now investigating methods for exploiting contextual information, since the fairness of clauses might very well depend on the context.
- Another challenging line of research we are pursuing is the adaptation of the methodology used for CLAUDETTE in order to enable the automated analysis of privacy policies.

