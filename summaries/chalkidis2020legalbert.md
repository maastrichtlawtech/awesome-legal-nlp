##

+++++++++++++++++++++++++++++++  
<ins>Authors</ins>: I. Chalkidis et al.  
<ins>Date</ins>: 2020-10  
<ins>Tags</ins>: `bert`  
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

