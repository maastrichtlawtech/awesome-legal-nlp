## A Brief History of the Changing Roles of Case Prediction in AI and Law

Tags: `history`

### Intro

Predicting case outcomes has long played a role in research on Artificial Intelligence and Law.

## Contributions

- This article provides a short history of AI and Law research on predicting case outcomes. 

- It then focuses on recent developments in legal text analytics, which employs natural language processing (NLP), machine learning and other computational techniques automatically to extract meanings (or semantics) from archives of legal case decisions, contracts, or statutes.

## Key points

### Modeling legal expertise

- Building computational models that reason with legal rules, argue with legal cases and precedents, predict legal outcomes, and explain those predictions required addressing the following core questions:
  1. **What legal domain to model?**: determine which areas of the law and problems of interest are to be modeled and what is the use case to which the model will be applied. Due to the difficulties of representing legal knowledge, models generally cover relatively narrow domains.
  2. **How to represent the legal knowledge?**: Knowledge representation techniques may take many forms (i.e., formal representations of legal rules, representations of generalized case facts, stereotypical fact patterns that strengthen or weaken a side’s claim, or representations of legal document texts
as term vectors).
  3. **Which inference methods to implement?**: whether to employ generic methods (such as logical inference with rules) or statistical inference based on frequencies. One must also consider how to explain the inferences (e.g., statistical inferences may make accurate predictions but not be able to explain those predictions in terms that legal professionals would recognize). Evaluation is a further consideration: it includes how to evaluate both the predictions and the explanations.
  4.**Wow to acquire the legal knowledge?**: determine how to acquire information with which to populate the knowledge representations for the domain and use case. What technical and domain expertise is needed to create and fill domain representations?


### Brief history of AI & Law

- Predicting case outcomes all began using a nearest neighbor algorithm or inducing rules via decision trees from substantive features of legal cases and outcomes.
- Today, machine learning text analytic programs using neural networks are predicting outcomes from case texts and automatically identifying predictive features without recourse to traditional legal knowledge representation.
