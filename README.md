[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)
![License](https://img.shields.io/github/license/antoiloui/awesome-legal-nlp)

# Legal Natural Language Processing

## 🗂 Datasets

#### <ins>Legal Judgement Prediction</ins> (LJP)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| FSCS (Niklaus et al., 2021) | [📄](https://arxiv.org/abs/2110.00806) [🤗](https://huggingface.co/datasets/swiss_judgment_prediction) [💻](https://github.com/JoelNiklaus/SwissJudgementPrediction) | Swiss court judgments | 🇩🇪 🇫🇷 🇮🇹 | 85K cases w/ 2 outcomes |
| ECtHR (Chalkidis et al., 2021) | [📄](https://arxiv.org/abs/2103.13084) [🤗](https://huggingface.co/datasets/ecthr_cases) | EU court judgments | 🇬🇧 | 11K cases w/ 11 outcomes |
| ECHR (Aletras et al., 2019) | [📄](https://arxiv.org/abs/1906.02059) [💾](https://archive.org/details/ECHR-ACL2019) | EU court judgments | 🇬🇧 | 11.5K cases w/ 11 outcomes |
| CAIL (Xiao et al., 2018) | [📄](https://arxiv.org/abs/1807.02478) [💻](https://github.com/china-ai-law-challenge/CAIL2018) | Chinese court judgements | 🇨🇳 | 2.6M cases w/ 6 outcomes |
| AnnoCaseLaw (2025) | [📄](https://arxiv.org/abs/2503.00128) [💻](https://github.com/anonymouspolar1/annocaselaw) | US Appeals Court negligence cases | 🇺🇸 | 471 annotated cases with expert labels |
| IndianBailJudgments-1200 (2025) | [📄](https://arxiv.org/abs/2507.02506) [🤗](https://huggingface.co/datasets/SnehaDeshmukh/IndianBailJudgments-1200) [💻](https://github.com/SnehaDeshmukh28/IndianBailJudgments-1200) | Indian court bail decisions | 🇮🇳 | 1.2K judgments with 20+ structured attributes |
| CaseSumm (2025) | [📄](https://arxiv.org/abs/2501.00097) [🤗](https://huggingface.co/datasets/ChicagoHAI/CaseSumm) | US Supreme Court opinions | 🇺🇸 | 25.6K opinions with official syllabuses |
| JUSTICE (2022) | [📄](https://arxiv.org/abs/2112.03414) [💻](https://github.com/Sanavesa/JUSTICE-Judgment-Prediction) | US Supreme Court cases | 🇺🇸 | Benchmark for judgment prediction |
| Cambridge Law Corpus (CLC) (2023) | [📄](https://arxiv.org/abs/2309.12269) | UK court cases | 🇬🇧 | 258K+ cases (16th century–present) |
| Super-SCOTUS (2025) | [📄](https://aclanthology.org/2023.nllp-1.20/) [💻](https://github.com/biaoyanf/Super-SCOTUS)| US Supreme Court decisions | 🇺🇸 | Decision direction and related tasks |

#### <ins>Legal Text Classification</ins> (LTC)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| GLC (Papaloukas et al., 2021) | [📄](https://arxiv.org/abs/2109.15298) [💻](https://github.com/christospi/glc-nllp-21) | Greek legislation | 🇬🇷  | 47.5K laws w/ 2.7K labels |
| CUAD (Hendrycks et al., 2021) | [📄](https://arxiv.org/abs/2103.06268) [🤗](https://huggingface.co/datasets/cuad) [💻](https://github.com/TheAtticusProject/cuad)| Contracts | 🇬🇧  | 510 contracts w/ 41 classes |
| MultiEURLEX (Chalkidis et al., 2021) | [📄](https://arxiv.org/abs/2109.00904) [🤗](https://huggingface.co/datasets/multi_eurlex) [💻](https://github.com/nlpaueb/multi-eurlex) | EU legislation | 🇬🇧 🇩🇪 🇫🇷 🇮🇹 🇪🇸 (18+) | 65K laws w/ 4.5K labels |
| LEDGAR (Tuggener et al., 2020) |  [📄](https://aclanthology.org/2020.lrec-1.155) [💾](https://drive.switch.ch/index.php/s/j9S0GRMAbGZKa1A) | Contracts | 🇬🇧 | 60.5K contracts w/ 12.6K labels |
| Contract Discovery (Borchmann et al., 2020) | [📄](https://arxiv.org/abs/1911.03911) [💻](https://github.com/applicaai/contract-discovery) | Contracts | 🇬🇧 | 2.6K clauses w/ 21 classes |
| EURLEX-57K (Chalkidis et al., 2019) | [📄](https://arxiv.org/abs/1906.02192) [💾](http://nlp.cs.aueb.gr/software_and_datasets/EURLEX57K/index.html) | EU legislation | 🇬🇧  | 57K laws w/ 4.3K labels |
| Unfair-ToS (Lippi et al., 2018) | [📄](https://arxiv.org/abs/1805.01217) [💾](http://155.185.228.137/claudette/ToS.zip) | Contracts | 🇬🇧 | 9.4K sentences w/ 9 classes |
| Contract Elements (Chalkidis et al., 2017) | [📄](https://dl.acm.org/doi/10.1145/3086512.3086515) [💾](http://nlp.cs.aueb.gr/software_and_datasets/CONTRACTS_ICAIL2017/index.html) | Contracts | 🇬🇧 | 2.4K contracts w/ 10 classes |
| OPP-115 (Wilson et al., 2016) | [📄](https://aclanthology.org/P16-1126) [💾](https://usableprivacy.org/data) | Privacy laws | 🇬🇧 | 115 policies w/ 23K labels |
| FairLex (2022) | [📄](https://aclanthology.org/2022.acl-long.301/) [🤗](https://huggingface.co/datasets/coastalcph/fairlex) [💻](https://github.com/coastalcph/fairlex) | Multi-jurisdictional legal texts | 🇬🇧🇩🇪🇫🇷🇮🇹🇨🇳 | Fairness-focused classification datasets |
| Legal Case Document Summarization (Kaggle) | [📄](https://www.kaggle.com/datasets/kageneko/legal-case-document-summarization) | Legal case summaries | Various | Large-scale dataset |
| Legal Citation Text Classification Dataset (Kaggle) | [📄](https://www.kaggle.com/datasets/amohankumar/legal-text-classification-dataset) | General legal documents | 🇬🇧 | 25K cases with catchphrases and citations |

#### <ins>Legal Information Retrieval</ins> (LIR)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| BSARD (Louis et al., 2022) | [📄](https://arxiv.org/abs/2108.11792) [🤗](https://huggingface.co/datasets/antoiloui/bsard) [💻](https://github.com/maastrichtlawtech/bsard) | Belgian legislation | 🇫🇷  | 1.1K questions w/ 22.6K candidate statutory articles |
| EU2UK (Chalkidis et al., 2021) | [📄](https://arxiv.org/abs/2101.10726) [💾](https://archive.org/details/eacl2021_regir_datasets) | EU & UK legislation |🇬🇧  | 2K query documents w/ 52.5K candidate documents |
| UK2EU (Chalkidis et al., 2021) | [📄](https://arxiv.org/abs/2101.10726) [💾](https://archive.org/details/eacl2021_regir_datasets) | EU & UK legislation |🇬🇧  | 2.1K query documents w/ 3.9K candidate documents |
| COLIEE-Case-Law-Retrieval (Rabelo et al., 2020) | [📄](https://sites.ualberta.ca/~rabelo/COLIEE2021/COLIEE_2020_summary.pdf) [💾](https://sites.ualberta.ca/~rabelo/COLIEE2020/) | Canadian precedents | 🇬🇧 |  650 query cases w/ 128K candidate cases |
| COLIEE-Statute-Law-Retrieval (Rabelo et al., 2020) | [📄](https://sites.ualberta.ca/~rabelo/COLIEE2021/COLIEE_2020_summary.pdf) [💾](https://sites.ualberta.ca/~rabelo/COLIEE2020/) | Japanese legislation | 🇬🇧 🇯🇵 |  808 questions w/ 768 candidate statutory articles |
| CAIL2019-SCM (Xiao et al., 2019) | [📄](https://arxiv.org/abs/1911.08962) [💻](https://github.com/china-ai-law-challenge/CAIL2019/tree/master/scm) | Chinese court judgements | 🇨🇳 | 8.9K triplets of cases |
| CLERC (2024) | [📄](https://arxiv.org/abs/2406.17186) [🤗](https://huggingface.co/datasets/jhu-clsp/CLERC) [💻](https://github.com/bohanhou14/CLERC) | Legal case retrieval | 🇬🇧 | Large corpus for retrieval and RAG |
| LEAD (2024) | [📄](https://arxiv.org/abs/2410.06581) [💻](https://github.com/thunlp/LEAD) | Legal case retrieval | Various | 100K+ pairs of similar legal cases |
| Legal IR Philippines (2024) | [📄](https://aclanthology.org/2024.paclic-1.35.pdf) | Philippine legal documents | 🇵🇭 | Datasets with synthetic queries |

#### <ins>Legal Question Answering</ins> (LQA)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| CaseHOLD (Zheng et al., 2021) | [📄](https://arxiv.org/abs/2104.08671) [💻](https://github.com/reglab/casehold) | US case holdings | 🇬🇧 | 53.1K multiple-choice questions |
| JEC-QA (Zhong et al., 2019) | [📄](https://arxiv.org/abs/1911.12011) [💾](https://jecqa.thunlp.org/) | Chinese law | 🇨🇳  | 26.3K multiple-choice questions |
| CJRC (Duan et al., 2019) | [📄](https://arxiv.org/abs/1912.09156) [💻](https://github.com/china-ai-law-challenge/CAIL2019) | Chinese court judgements | 🇨🇳 | 50K question-answers from 10K documents |
| PrivacyQA (Ravichander et al., 2019) | [📄](https://arxiv.org/abs/1911.00841) [💻](https://github.com/AbhilashaRavichander/PrivacyQA_EMNLP) | Privacy policies | 🇬🇧 | 1.7K question-answers from 35 documents |
| LLeQA (2024) | [📄](https://arxiv.org/abs/2309.17050) [🤗](https://huggingface.co/datasets/maastrichtlawtech/lleqa) [💻](https://github.com/maastrichtlawtech/lleqa) | French-Belgian statutes | 🇫🇷 | 1,868 expert-annotated long-form QA |
| IndicLegalQA (2025) | [📄](https://www.sciencedirect.com/science/article/pii/S2352340925003774) | Indian Supreme Court judgments | 🇮🇳 | 10K QA pairs from 1,256 judgments |
| GerLayQA (2024) | [📄](https://aclanthology.org/2024.eacl-long.122/) [💻](https://github.com/trusthlt/eacl24-german-legal-questions)| German civil law | 🇩🇪 | 21K laymen legal Qs with lawyer answers |
| LEGAL-UQA (2024) | [📄](https://arxiv.org/abs/2410.13013) | Legal questions | 🇵🇰 | 619 parallel Urdu–English QA pairs |

#### <ins>Legal Textual Entailment</ins> (LTE)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| COLIEE-Case-Law-Entailment (Rabelo et al., 2020) | [📄](https://sites.ualberta.ca/~rabelo/COLIEE2021/COLIEE_2020_summary.pdf) [💾](https://sites.ualberta.ca/~rabelo/COLIEE2020/) | Canadian precedents | 🇬🇧 |  425 cases w/ related case |
| COLIEE-Statute-Law-Entailment (Rabelo et al., 2020) | [📄](https://sites.ualberta.ca/~rabelo/COLIEE2021/COLIEE_2020_summary.pdf) [💾](https://sites.ualberta.ca/~rabelo/COLIEE2020/) | Japanese legislation | 🇬🇧 🇯🇵 |  808 questions w/ related statutory article |
| LAR-ECHR (2024) | [📄](https://arxiv.org/html/2410.13352v1) | European Court of Human Rights | 🇬🇧 | Legal argument reasoning task dataset |
| δ-Stance (2025) | [📄](https://aclanthology.org/2025.acl-long.1517.pdf) | US legal argumentation | 🇺🇸 | Large-scale stances and arguments |

#### <ins>Legal Text Summarization</ins> (LTS)

| Dataset | Links | Domain | Language | Size |
|---|---|---|---|---|
| UK-Abs (Shukla et al., 2022) | [📄](https://arxiv.org/abs/2210.07544) [💻](https://github.com/Law-AI/summarization/tree/aacl/dataset#uk-abs) [💾](https://zenodo.org/record/7152317#.Yz6mJ9JByC0) | UK court cases | 🇬🇧 | 793 pairs of (case, abastractive summary) from the UK Supreme Court |
| IN-Abs (Shukla et al., 2022) | [📄](https://arxiv.org/abs/2210.07544) [💻](hhttps://github.com/Law-AI/summarization/tree/aacl/dataset#in-abs) [💾](https://zenodo.org/record/7152317#.Yz6mJ9JByC0) | Indian court cases | 🇬🇧 | 7.1K pairs of (case, abastractive summary) from the Indian Supreme Court |
| IN-Ext (Shukla et al., 2022) | [📄](https://arxiv.org/abs/2210.07544) [💻](https://github.com/Law-AI/summarization/tree/aacl/dataset#in-ext) [💾](https://zenodo.org/record/7152317#.Yz6mJ9JByC0) | Indian court cases | 🇬🇧 | 50 pairs of (case, extractive summary) from the Indian Supreme Court |
| TOS;DR (Keymanesh et al., 2020) | [📄](https://ceur-ws.org/Vol-2645/paper3.pdf) [💻](https://github.com/senjed/Summarization-of-Privacy-Policies/commit/e6fabba8639593f45cde7d42639a5f354f5d9c3a) | Terms of service | 🇬🇧 | 1.6K pairs of (agreement text, summary) from data privacy policies |
| BillSum (Kornilova et al., 2019) | [📄](https://aclanthology.org/D19-5406/) [💻](https://github.com/FiscalNote/BillSum) [💾](https://drive.google.com/file/d/1SkwK-PfcHzznKUHy2S3jfdITR4D5MD5u/view) | US Congressional bills | 🇬🇧 | 22.2K pairs of (bill, summary) |
| TL;DRLegal (Manor et al., 2019) | [📄](https://aclanthology.org/W19-2201/) [💻](https://github.com/lauramanor/legal_summarization/blob/master/tldrlegal_v1.json) | Terms of service | 🇬🇧 | 84 pairs of (agreement text, summary) from software licenses |
| TOS;DR (Manor et al., 2019) | [📄](https://aclanthology.org/W19-2201/) [💻](https://github.com/lauramanor/legal_summarization/blob/master/tosdr_annotated_v1.json) | Terms of service | 🇬🇧 | 421 pairs of (agreement text, summary) from data privacy policies |
| BVA Cases (Zhong et al., 2019) | [📄](https://dl.acm.org/doi/10.1145/3322640.3326728) [💻](https://github.com/luimagroup/bva-summarization) | US court cases | 🇬🇧 | 92 pairs of (case, summary) from the US Board of Veterans' Appeal |
| LCR (Galgani et al., 2012) | [📄](https://aclanthology.org/W12-0515/) [💾](https://archive.ics.uci.edu/ml/datasets/Legal+Case+Reports) | Australian court cases | 🇬🇧 | 3.9K pairs of (case, catchphrases) |
| EurLexSummarization (2022) | [📄](https://aclanthology.org/2022.emnlp-main.519/) [🤗](https://huggingface.co/datasets/dennlinger/eur-lex-sum) [💻](https://github.com/achouhan93/eur-lex-sum) | EU legislation | 🌍 | Multilingual summarization across 24 languages |
| Multi-LexSum (2025) | [📄](https://arxiv.org/html/2503.04305v2) | Legal documents | 🇬🇧 | 40K+ documents with 9K+ expert summaries |
| CaseSumm (2025) | [📄](https://arxiv.org/abs/2501.00097) [🤗](https://huggingface.co/datasets/ChicagoHAI/CaseSumm) | US Supreme Court opinions | 🇬🇧 | 25.6K opinions with official syllabuses |

#### <ins>Legal Language Modeling</ins> (LLM)

| Dataset | Links | Language | Size |
|---|---|---|---|
| Pile of Law (Henderson et al., 2022) | [📄](https://arxiv.org/abs/2207.00220) [🤗](https://huggingface.co/datasets/pile-of-law/pile-of-law) [💻](https://github.com/Breakend/PileOfLaw) | 🇬🇧 | ~256GB of legal and administrative legal text |
| MultiLegalPile (2024) | [📄](https://aclanthology.org/2024.acl-long.805/) [🤗](https://huggingface.co/datasets/joelniklaus/Multi_Legal_Pile) | 🌍 | 689GB multilingual legal corpus from 17 jurisdictions |

#### <ins>Benchmarks</ins>

| Dataset | Task | Language | Tasks |
|---|---|---|---|
| FairLex (Chalkidis et al., 2022) | [📄](https://arxiv.org/abs/2203.07228) [🤗](https://huggingface.co/datasets/coastalcph/fairlex) [💻](https://github.com/coastalcph/fairlex) | 🇬🇧 🇩🇪 🇫🇷 🇮🇹 🇨🇳 | Clasification (x1), legal judgement prediction (x3) |
| LexGLUE (Chalkidis et al., 2022) | [📄](https://arxiv.org/abs/2110.00976) [🤗](https://huggingface.co/datasets/lex_glue) [💻](https://github.com/coastalcph/lex-glue) | 🇬🇧  | Classsification (x6), multiple-choice QA (x1) |

## 🔥 Models

| Model | Links | Language | Size |
|---|---|---|---|
| Legal-HeBERT (Chriqui et al., 2022) | [📄](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4147127) [🤗](https://huggingface.co/avichr/Legal-heBERT) [💻](https://github.com/avichaychriqui/Legal-HeBERT) | 🇮🇱 | 110M |
| PoL-BERT-Large (Henderson et al., 2022) | [📄](https://arxiv.org/abs/2207.00220) [🤗](https://huggingface.co/pile-of-law/legalbert-large-1.7M-1) [💻](https://github.com/Breakend/PileOfLaw) | 🇬🇧 | 336M |
| Italian-LEGAL-BERT (Licari and Comande, 2022) | [📄](https://ceur-ws.org/Vol-3256/km4law3.pdf) [🤗](https://huggingface.co/dlicari/Italian-Legal-BERT)| 🇮🇹 | 110M |
| JuriBERT (Douka et al., 2021) | [📄](https://arxiv.org/abs/2110.01485) [💾](http://master2-bigdata.polytechnique.fr/resources#juribert) | 🇫🇷  | {6M, 15M, 42M, 110M} |
| Custom-LEGAL-BERT (Zheng et al., 2021) | [📄](https://arxiv.org/abs/2104.08671) [🤗](https://huggingface.co/zlucia/custom-legalbert) [💻](https://github.com/reglab/casehold) | 🇬🇧  | 110M |
| LEGAL-BERT (Chalkidis et al., 2020) | [📄](https://arxiv.org/abs/2010.02559) [🤗](https://huggingface.co/nlpaueb/legal-bert-base-uncased) | 🇬🇧  | {35M, 110M} |
| LEGAL-GPT-{1,2} (Borchmann et al., 2020) | [📄](https://arxiv.org/abs/1911.03911) [💻](https://github.com/applicaai/contract-discovery) | 🇬🇧  | {117M, 1.5B} |
| MultiLegalPile Models (2024-2025) | [📄](https://reglab.stanford.edu/publications/multilegalpile/) [🤗](https://huggingface.co/collections/joelniklaus/multilegalpile-datasets-6535db705f5e918bdc17ecc7) | 🌍 | RoBERTa (multilingual + 24 monolingual), Longformer |
| Legal-BERT Fine-tuned (2024) | [📄](https://towardsai.net/p/artificial-intelligence/fine-tuning-legal-bert-llms-for-automated-legal-text-classification) | 🇬🇧 | Domain-adapted classification models |
| LegalCore Models (2025) | [📄](https://aclanthology.org/2025.findings-acl.1284.pdf) | 🌍 | Event coreference resolution for legal texts |
| Legal LLaMA (2025) | [📄](https://arxiv.org/abs/2305.15062) | 🇨🇳 | Chinese legal domain adaptations |
| FairLex Domain Models (2024-2025) | [🤗](https://huggingface.co/collections/coastalcph/legal-nlp-683ffd107b0dc24048c449ae) | 🌍 | Domain-specific BERT models for 4 jurisdictions |

## 📚  Books

- [`2017`] *Artificial Intelligence and Legal Analytics: New Tools for Law Practice in the Digital Age*, K. Ashley. [[link]](https://www.cambridge.org/core/books/artificial-intelligence-and-legal-analytics/E7D705EEF392501A1DB180645917E7E0)

- [`2024`] *Large Language Models and International Law*, Chicago Journal of International Law [[🌐]](https://cjil.uchicago.edu/print-archive/large-language-models-and-international-law)
- [`2024`] *Computational Legal Studies Comes of Age*, SSRN [[📄]](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4826144)

## 📄  Surveys

- [`2020-05`] *How Does NLP Benefit Legal System: A Summary of Legal Artificial Intelligence*, H. Zhong et al. [[pdf]](https://arxiv.org/pdf/2004.12158)
- [`2019-09`] *A Brief History of the Changing Roles of Case Prediction in AI and Law*, K. Ashley [[pdf]](https://journals.latrobe.edu.au/index.php/law-in-context/article/download/88/157)
- [`2018-12`] *Deep learning in law: early adaptation and legal word embeddings trained on large corpora*, I. Chalkidis et al. [[pdf]](https://link.springer.com/content/pdf/10.1007/s10506-018-9238-9.pdf)

- [`2024`] *Natural Language Processing for the Legal Domain: A Survey of Tasks, Datasets, Models and Challenges*, F. Ariai et al. [[📄]](https://arxiv.org/abs/2410.21306)
- [`2025`] *Computational Law: Datasets, Benchmarks, and Ontologies*, D. Küçük & F. Can [[📄]](https://arxiv.org/html/2503.04305v1)
- [`2025`] *A Comprehensive Survey on Legal Summarization*, arXiv [[📄]](https://arxiv.org/html/2501.17830v1)
- [`2024`] *Large Language Models in Law: A Survey*, J. Lai et al. [[📄]](https://www.sciencedirect.com/science/article/pii/S2666651024000172)
- [`2025`] *Large Language Models in Argument Mining: A Survey*, arXiv [[📄]](https://arxiv.org/html/2506.16383v3)
- [`2024`] *When Large Language Models Meet Law: Dual-Lens Survey*, arXiv [[📄]](https://arxiv.org/html/2507.07748v1)

## 🎙  Talks

- [`2019-06`] *Law as Data: The Promise and Challenges of Natural Language Processing for Legal Research*, A. Dyevre. [[slides]](https://drive.google.com/open?id=14zWlp2Hkm866MTup_oMZJa5T80fxsWtR)
- [`2019-04`] *Artificial Intelligence and Law – An Overview and History*, H. Surden. [[video]](https://www.youtube.com/watch?v=BG6YR0xGMRA)

## 🗓  Conferences & Workshops

- The Natural Legal Language Processing (NLLP) Workshop [[website]](https://nllpw.org/workshop/)
- The International Conference on Artificial Intelligence and Law (ICAIL) [[website]](https://dl.acm.org/doi/proceedings/10.1145/3322640#issue-downloads)
- The International Conference on Legal Knowledge and Information Systems (JURIX) [[website]](http://jurix.nl/)  
- The EXplainable AI in Law (XAILA) Workshop [[website]](https://www.geist.re/xaila:start)
- The International Workshop on Juris-informatics (JURISIN) [[website]](http://research.nii.ac.jp/~ksatoh/jurisin2020/)
- The Competition on Legal Information Extraction/Entailment (COLIEE) [[website]](https://sites.ualberta.ca/~rabelo/COLIEE2020/)
- The International Workshop on Legal Information Retrieval [[website]](https://tmr.liacs.nl/legalIR/)

### 2025 Conferences

- **NLLP 2025** - Natural Legal Language Processing Workshop (EMNLP 2025, Suzhou) [[🌐]](https://nllpw.org/workshop/)
- **RegNLP 2025** - Regulatory Natural Language Processing Workshop (COLING 2025) [[🌐]](https://aclweb.org/portal/content/call-papers-regnlp-2025-regulatory-natural-language-processing-workshop)
- **JURIX 2025** - 38th International Conference on Legal Knowledge and Information Systems (Turin, December 9-11, 2025) [[🌐]](https://jurix.nl/jurix-2025-call-for-papers/)
- **ICAIL 2025** - 20th International Conference on Artificial Intelligence and Law (Chicago, June 16-20, 2025) [[🌐]](https://iris-conferences.eu/mwail25)
- **MWAiL 2025** - Multilingual Workshop on AI & Law Research (Chicago, June 20, 2025) [[🌐]](https://iris-conferences.eu/mwail25)
- **LLMFinLegal 2025** - Workshop on Large Language Models for Finance and Legal (COLING 2025) [[🌐]](https://sites.google.com/nlg.csie.ntu.edu.tw/finnlp-fnp-llmfinlegal/home)
- **8th World Legal Tech and AI Summit** (Berlin, September 18-19, 2025) [[🌐]](https://www.luxatiainternational.com/product/8th-world-legal-tech-and-ai-summit)

### Industry & Professional Events

- **AI Legal Summit 2025** - Various industry conferences on AI in legal practice [[🌐]](https://future-bridge.eu/ai-legal-summit-2025-a-detailed-recap/)
- **Legal AI Conferences Online Platform** - Centralized platform for legal AI events [[🌐]](https://www.legalaiconferences.online)

<!---
Datasets to add:
- "FALQU: Finding Answers to Legal Questions"
- “MultiLegalSBD: A Multilingual Legal Sentence Boundary Detection Dataset”
- “ClassActionPrediction: A Challenging Benchmark for Legal Judgment Prediction of Class Action Cases in the US”
- "MultiLegalPile: A 689GB Multilingual Legal Corpus"
- "LeXFiles and LegalLAMA: Facilitating English Multinational Legal Language Model Development"
- "LEXTREME: A Multi-Lingual and Multi-Task Benchmark for the Legal Domain"
- "A Dataset for Evaluating Legal Question Answering on Private International Law"
- "EQUALS: A Real-world Dataset for Legal Questions Answering via Reading Chinese Laws"

Other cool resources to check:
- https://github.com/neelguha/legal-ml-datasets
- https://nllpw.org/resources/
- https://github.com/Liquid-Legal-Institute/Legal-Text-Analytics#datasets-and-data
-->

## 🧰  Tools & Evaluation

### Evaluation Tools

- Embedding Benchmarking Tools: MTEB, Hugging Face evaluate, LegalBench, COLIEE [[🌐]](https://milvus.io/ai-quick-reference/what-tools-can-benchmark-embeddings-for-legal-datasets)
- Legal Argument Mining Tools: RMU:ECHR corpus and mining models [[💻]](https://github.com/trusthlt/mining-legal-arguments)
- Multilingual Legal Processing: Evaluation pipelines for multilingual legal LLMs [[📄]](https://arxiv.org/html/2509.22472v1)

### Legal QA Applications

- LawQ (律问): Legal QA over 26k Chinese statutes in force — BM25 retrieval with citation-grounded LLM answers (web + WeChat Mini Program) [[💻]](https://github.com/thu-lawyer/lawq)

### Quality Assessment Frameworks

- LegalEval-Q: Quality evaluation for LLM-generated legal text [[📄]](https://arxiv.org/html/2505.24826v1)
- FairLex Evaluation: Bias and fairness assessment [[🌐]](https://huggingface.co/datasets/coastalcph/fairlex)

Last Updated: 2025-09-30
Research Coverage: 2024-01 to 2025-09
Sources: 180+ academic papers, datasets, and conference proceedings
