# A Brief History of the Changing Roles of Case Prediction in AI and Law

Tags: `history`, `legal prediction`

## Intro

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
  4. **How to acquire the legal knowledge?**: determine how to acquire information with which to populate the knowledge representations for the domain and use case. What technical and domain expertise is needed to create and fill domain representations?


### Brief history of AI & Law

- **1970s**: nearest neighbor algorithm (k-NN).
- **1980s**: rule induction and decision trees.
- **2014**: [Katz *et al.*](katz2014predicting.md) have developed and evaluated the first supervised machine learning program to predict if a US Supreme Court Justice or the whole will affirm or reverse a lower court’s judgment. It employs an extremely randomized forest of decision trees to evaluate a case, input as a set of feature values, and to predict its outcome, based on all previous decisions for that Justice, the Court, and all previous cases. Starting in 1816 and carrying through the conclusion of the October 2014 term, their model correctly predicts 70.2% of the Court's decisions.
- **2016**: Aletras *et al.* used unsupervised machine learning (spectral clustering on an n-gram similarity matrix) to identify features such as topics. Their goal was to predict violations of particular articles of the European Convention on Human Rights (ECHR) from the texts of cases tried by the European Court of Human Rights (ECtHR). The researchers applied a linear support vector machine model and evaluated the trained model (using 10-fold stratified cross validation). Their model achieved an accuracy of 79% accuracy at the case outcome level.
- **2017**: Branting *et al.* have employed Hierarchical Attention Networks (HANs) to induce models from previous case decision texts that can predict case outcomes. The attention model assigns higher weights to the text portions that have greater influence on the model’s outcome prediction. The HAN approach was used to predict outcomes from the full texts of cases in a corpus of decisions of the Board of Veterans Appeals (BVA) and of WIPO domain name disputes.
- **2017**: Falakmasir *et al.* employed a word-embedding text representation technique, Doc2Vec, to capture contextual semantic information in trade secret cases from CourtListener , trained a machine learning model for each factor, and predicted the factors that apply in each case document. In an evaluation applying the model to 30% of the documents as a hold-out test set, the result was an F1 measure of .69/.65 (micro/macro).
- **2019**: [Branting *et al.*](branting2019explainable.md) present the SCALE approach as a semi-supervised machine learning method for achieving explainable legal prediction. SCALE employs a small set of annotated data and maps it onto a larger set of candidate documents. It applies word-embedding representations and clustering algorithms that can identify semantically similar descriptive text segments across the case texts. The technique could be used to predict outcomes based on the relevant resulting clusters and explain the predictions in terms of cluster-related concepts. Alternatively, it could be applied as a pre-processing technique to make detailed annotation more efficient.
- **2019**: Medvedeva *et al.* made predictions directly from the texts represented only as feature vectors. The researchers assembled a database of ECtHR cases for nine ECHR articles, applied a support vector machine model, and achieved an average accuracy of 0.74 on a held-out test.
- **2019**: Zhong *et al.* automatically summarized legal cases. The researchers employed a template for generating summaries comprising one sentence each stating: the source of the appeal, the issue on appeal, the military service history, and the conclusion. Each of these were identified with regular expressions (i.e., regex rules). A random forest decision tree classifier, trained on an annotated training set, identified reasoning and evidential support sentences from the set of most predictive sentences.
