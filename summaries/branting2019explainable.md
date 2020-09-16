## Semi-Supervised Methods for Explainable Legal Prediction

Tags: `Legal Reasoning`, `Computational Models of Argument`

### Intro
 - Effective decision-support systems could potentially improve access to justice for significant numbers of citizens by improving transparency, compensating for lack of affordable human legal assistance, and speeding case decisions. A useful form of decision support is **explainable legal decision prediction**. For example, benefits applicants could make better-informed decisions if they knew (1) the likelihood of success of an application and (2) the strengths or weaknesses of their application (i.e., the reasons for the predicted likelihood). Similarly, adjudicators and decision processes could be more productive and consistent if the strengths or weaknesses of each application could be automatically identified and presented along with the application itself.
 - There is a trade-off in explainable outcome prediction systems between *explanation quality* and *development effort*. At one ex- treme, purely machine-learning-based systems require relatively little development effort but typically have little or no explanatory capability. At the other extreme, systems in which case facts have been represented in manually engineered features and legal rules are represented in executable logic may be capable of generating explanations with considerable fidelity to human explanations but require prohibitively high levels of development effort for applica- tion at scale.
 - A key requirement for explainable decision predictions systems is therefore optimizing the trade-off between explanation quality and development effort, that is, identifying approaches that can produce useful and comprehensible predictions but for which the en- gineering effort is low enough to permit development, verification, and maintenance at scale. A particularly important requirement for large-scale adoption is the ability to accept free text rather than manually-engineered features as input.


### Contributions
This paper describes two approaches to *explainable outcome prediction* that that operate on textual inputs and obviate both annotation of an entire decision corpus and manual processing of new cases.
   - **NFE** (No Feature Engineering): uses an *Attention Network* for prediction and attention weights to highlight salient case text. It was shown to be capable of predicting decisions, but attention-weight-based text highlighting did not demonstrably improve human decision speed or accuracy.
   - **SCALE** (Semi-supervised Case Annotation for Legal Explanations): the justification structure of a representative set of cases is annotated, and tags for factual and legal findings are propagated to sentences in unannotated cases that share a high degree of simi- larity to the annotated sentences in a semantic embedding space. This approach exploits the structural and semantic regularities in case corpora to identify fact patterns with predictable relationships to case decisions.


### Take away

