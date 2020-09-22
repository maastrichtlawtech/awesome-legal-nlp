## Inducing Predictive Models for Decision Support in Administrative Adjudication

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: K. Branting et al.  
<ins>Date</ins>: 2017   
<ins>Tags</ins>: `legal prediction`, `attention network`  
+++++++++++++++++++++++++++++++

### Intro

Administrative adjudications are the most common form of legal decisions in many countries, so improving the efficiency, accuracy, and consistency of administrative processes could significantly benefit a large number of citizens. 


### Contributions

- They explore the hypothesis that predictive models induced from previous administrative decisions can improve subsequent decision-making processes.
  - Step 1:  show the feasibility of creating models that predict the outcomes of routine administrative cases. 
  - Step 2: demonstrate how such predictive models can be used to improve decision processes. 
  
- Their focus is on assisting individual decision makers by using predictive models to:
  - (1) identify the aspects of the instant case that are most relevant to its outcome;
  - (2) determine the prior cases that share the most relevant similarities to the instant case.

- Three data sets used:
  - motion-rulings;
  - Board of Veterans Appeals (BVA) decisions;
  - World Intellectual Property Organization (WIPO) domain name dispute decisions.
  
- They use three different approaches for prediction in these domains were tested:
  - maximum entropy over token n-grams;
  - SVM over token n-grams;
  - Hierarchical Attention Network (HAN) applied to the full text.
  
- Results: each approach was capable of predicting outcomes, with the simpler WIPO cases appearing to be much more predictable than BVA or motion-ruling cases. But since this approach does not perform argumentation mining and has no explicit model of the applicable legal issues and rules, there is a limit to the predictive accuracy that this approach can achieve except in highly routine and predictable domains.

- They emphasize that one of the challenges of decision making is sifting through irrelevant portions of the case record to locate the most important facts. They distinguish two uses of predictive text:
  - **Highlighting the parts of a document most relevant outcome** so that the decision maker can quickly identify the facts determinative of the outcome (e.g., granting or denying a motion, or accepting or rejecting a claim for benefits);
  - **Highlighting the parts of one document most relevant to assessing the similarity or difference between the cases**.

- In practice, identification of the most predictive text is a special case of feature selection. Hence, they explore several approaches to using predictive models to identify salient phrases in the predictive texts (i.e., motion or contentions and factual background):
  - Mutual information;
  - Neural network attention weights;
  - Linear model weights (maximum entropy and SVM with linear kernels).

- Finally, they propose a design for displaying this information to decision makers (e.g., allows a user to view the most relevant cases in multiple ways).


### Conclusions

- This paper studies the ability to predict outcomes from previous administrative decisions using three different approaches: maximum entropy over token n-grams; SVM over token n-grams; and a hierarchical attention network applied to the full text. 
- The evaluation did not establish the superiority of one approach over another, but rather indicates that the outcome of routine decisions is predictable using multiple alternative models from the text of the motion or contentions and factual background alone and that predictive accuracy varies depending on the domain and the nature of the predictive texts.
- They propose use of feature weights or network attention weights from these predictive models to identify salient phrases in motions or contentions and case facts.
- They have developed an interface design for presenting this information to improve decision making.
- The ultimate objective of this work is to improve the efficiency, accuracy, and consistency of administrative decision making, the form of adjudication that has the greatest impact on most citizens, by integrating automated decision models into the human decision process.
