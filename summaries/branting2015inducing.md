## Inducing Predictive Models for Decision Support in Administrative Adjudication

tags: `legal prediction`

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
  
- Results: each approach was capable of predicting outcomes, with the simpler WIPO cases appearing to be much more predictable than BVA or motion-ruling cases.
 
- They also explore several approaches to using predictive models to identify salient phrases in the predictive texts (i.e., motion or contentions and factual background), and propose a design for displaying this information to decision makers.


### Conclusions

- The results of the prediction experiments indicate that routine adjudications and orders are predictable to some extent from models trained from text representing the facts of the case.

- But since this approach does not perform argumentation mining and has no explicit model of the applicable legal issues and rules, there is a limit to the predictive accuracy that this approach can achieve except in highly routine and predictable domains.

- They emphasize that one of the challenges of decision making is sifting through irrelevant portions of the case record to locate the most important facts. Hence, they distinguish two uses of predictive text:
  - <span style="background-color: #FFFF00">Highlighting the parts of a document most relevant outcome</span> so that the decision maker can quickly identify the facts determinative of the outcome (e.g., granting or denying a motion, or accepting or rejecting a claim for benefits);
  - 
