##

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: I. Chalkidis et al.  
<ins>Date</ins>: 2020-10  
<ins>Tags</ins>: `bert`, `text classification`, `sequence tagging`    
+++++++++++++++++++++++++++++++  


### Intro

- Being pre-trained on generic corpora, BERT has been reported to under-perform in specialised domains, such as biomedical or scientific text. Consequently, recent work studied the effect of further pre-training BERT on domain-specific texts (BioBERT, SciBERT, ClinicalBERT, NetBERT).
- One shortcoming is that all previous work does not investigate the effect of varying the number of pre-training steps.
- More importantly, when fine-tuning for the downstream task, all previous work blindly adopts the hyper-parameter selection guidelines of Devlin et al. (2019) without further investigation.
- Finally, no previous work considers the effectiveness and efficiency of smaller models (e.g., fewer layers) in specialised domains. The full capacity of larger and computationally more expensive models may be unnecessary in specialised domains, where syntax may be more standardized, the range of topics discussed may be narrower, terms may have fewer senses etc.


### Contributions

- In this paper, they explore several approaches for applying BERT models to downstream legal tasks, evaluating on multiple datasets.
- They propose a systematic investigation of the available strategies when applying BERT in specialised domains, which are:
  1. Use BERT out of the box;
  2. Further pre-train (FP) BERT on domain-specific corpora;
  3. Pre-train BERT from scratch (SC) on domain specific corpora with a new vocabulary of sub-word units.


### Key findings

1. Further pre-training (FP) or pre-training BERT from scratch (SC) on domain specific corpora, performs better than using BERT out of the box for domain-specific tasks (both strategies are mostly comparable in three legal datasets).
2. Exploring a broader hyper-parameter range, compared to the guidelines of Devlin et al. (2019), can lead to substantially better performance.
3. Smaller BERT-based models can be competitive to larger, computationally heavier ones in specialised domains.


***

### 1. Pre-training

- Training corpora: **12 GB** of diverse English legal text from several fields (e.g., legislation, court cases, contracts) scraped from publicly available resources.
- Legal-BERT-FP (further pre-training): While Devlin et al. (2019) suggested additional steps up to 100k, they also pre-train models up to **500k** to examine the effect of prolonged in-domain pre-training when fine-tuning on downstream tasks.
- Legal-BERT-SC (scratch): they use a newly created **vocabulary** of equal size to BERT’s vocabulary. They also experiment with **LEGAL-BERT-SMALL**, a substantially smaller model, with 6 layers, 512 hidden units, and 8 attention heads (35M parameters, 32% the size of BERT-BASE).

### 2. Experiments

- They evaluate their models on **text classification** and **sequence tagging** using 3 datasets:
  - EURLEX57K: a large-scale multi-label text classification dataset of EU laws.
  - ECHR-CASES: contains cases from the European Court of Human Rights and can be used for binary and multi-label text classification.
  - CONTRACTS-NER: dataset for named entity recognition on US contracts consisting of three subsets (namely, *contract header, dispute resolution*, and *lease details*).
- As a rule of thumb to fine-tune BERT for downstream tasks, Devlin et al. (2019) suggested a minimal **hyperparameter tuning strategy** relying on a gridsearch on the following ranges: learning rate {2e-5; 3e-5; 4e-5; 5e-5}, number of training epochs {3,4}, batch size {16, 32} and fixed dropout rate of 0.1. These not well justified suggestions are blindly followed in the literature. Interestingly, in preliminary experiments, they found that some models still underfit after 4 epochs, the maximum suggested, thus they use early stopping based on validation loss, without a fixed maximum number of training epochs. They also consider an additional lower learning rate (1e-5) to avoid overshooting local minima, and an additional higher drop-out rate (0.2) to improve regularization. They noticed that their enriched grid-search (tuned) has a substantial impact in most of the end-tasks compared to the default hyper-parameter strategy.
