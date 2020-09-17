## Inducing Predictive Models for Decision Support in Administrative Adjudication

tags: `legal prediction`

### Intro

Administrative adjudications are the most common form of legal decisions in many countries, so improving the efficiency, accuracy, and consistency of administrative processes could significantly benefit a large number of citizens. 


### Contributions

- They explore the hypothesis that predictive models induced from previous administrative decisions can improve subsequent decision-making processes. This paper describes three data sets for exploring this hypothesis:
  - motion-rulings;
  - Board of Veterans Appeals (BVA) decisions;
  - World Intellectual Property Organization (WIPO) domain name dispute decisions.
  
- They use three different approaches for prediction in these domains were tested:
  - maximum entropy over token n-grams;
  - SVM over token n-grams;
  - Hierarchical Attention Network (HAN) applied to the full text.
  
- Results: each approach was capable of predicting outcomes, with the simpler WIPO cases appearing to be much more predictable than BVA or motion-ruling cases.
 
- They also explore several approaches to using predictive models to identify salient phrases in the predictive texts (i.e., motion or contentions and factual background), and propose a design for displaying this information to decision makers.


### Take away

[...]
