# Research Digest — 2026-06-18

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct arXiv/bioRxiv listing pages and the arXiv API returned HTTP 403 in this environment, so today's sweep relied entirely on web search. Search-engine indexing of arXiv/bioRxiv/PubMed/HF Papers continues to lag the live feed by roughly 1–5 days (confirmed again today: targeted searches for arXiv IDs in the 2606.17xxx–2606.18xxx range, which are already populated by non-bio papers, surfaced essentially no computational-biology results yet). All candidates below were cross-checked against the full prior digest history (through 2026-06-17) and excluded if already covered — notably AlloGen (2606.05474, covered 06-09 and 06-13) and GLACIER (2606.11382, covered 06-15). Today's set is therefore smaller than usual and draws on the most recent verifiable, not-yet-covered postings: two arXiv architecture papers from June 15 (IDs just past yesterday's cutoff), one arXiv ADME paper from June 9 that had not surfaced in prior sweeps, and four bioRxiv preprints posted 2026-06-16.

---

---
TITLE: Long-Context Modeling via GSS-Transformer Hybrid Architecture with Learnable Mixing
AUTHORS: Kuzey Torlak, Hüseyin Arda Arslan, Anıl Dervişoğlu, Beyza Nur Deniz, Onur Boyar
SOURCE: arXiv | 2606.16093 | [**Link**](https://arxiv.org/abs/2606.16093)
TOPIC TAG: SSM
TLDR: Proposes a Parallel Hybrid Architecture that runs Gated State Spaces (global context), Grouped Query Attention (selective retrieval), and FFNs as independent parallel branches fused by a learnable mixing mechanism, instead of forcing SSMs to approximate attention or serializing the two paradigms.
WHY IT MATTERS: Long-context genomic and protein-sequence modeling needs exactly this tradeoff — SSMs give linear-time global context while attention gives precise local retrieval — and most hybrids today serialize or interleave the two rather than letting each specialize in parallel. A learnable-mixing parallel hybrid is a directly transferable backbone design for whole-chromosome or long-read genomic foundation models.
CODE: Not released
---

---
TITLE: Taylor-Calibrate: Principled Initialization for Hybrid Linear Attention Distillation
AUTHORS: Zhongzhu Zhou, Qingyang Wu, Junxiong Wang, Mayank Mishra, Shuaiwen Leon Song, Ben Athiwaratkun, Chenfeng Xu
SOURCE: arXiv | 2606.16429 | [**Link**](https://arxiv.org/abs/2606.16429)
TOPIC TAG: Architecture
TLDR: Introduces a lightweight initialization scheme for hybrid Gated DeltaNet students distilled from pretrained Transformer teachers, using Taylor-guided teacher attention statistics to set the value projection, memory timescale, write gates, and output gate so the student starts in a good dynamical regime.
WHY IT MATTERS: Converting a pretrained Transformer to an efficient linear-attention/SSM hybrid (rather than pretraining from scratch) is the practical path to making large bio-sequence LMs cheaper to serve, but naive weight-copying leaves the recurrent dynamics badly initialized and burns huge amounts of distillation compute to repair. A principled initialization that removes this cold-start tax is directly reusable for compressing existing protein/genomic foundation models into long-context-efficient variants.
CODE: Not released
---

---
TITLE: Probabilistic Contrastive Pretraining for Multi-task ADME Property Prediction
AUTHORS: Yifan Xue, Srimukh Prasad Veccham, Saee Paliwal, Tyler Shimko, Micha Livne (NVIDIA)
SOURCE: arXiv | 2606.11508 | [**Link**](https://arxiv.org/abs/2606.11508)
TOPIC TAG: General ML
TLDR: Augments a KERMT-style molecular graph-transformer pretraining framework with a contrastive mutual-information objective (cMIM) plus domain-specific chemistry self-supervision, improving multi-task ADME prediction by 7.6–9.9% over the KERMT baseline across Biogen, ExpansionRX, and ChEMBL-MT benchmarks.
WHY IT MATTERS: ADME/property prediction pipelines increasingly rely on pretrained molecular encoders, and this shows that adding a probabilistic contrastive objective on top of existing graph-transformer pretraining yields a sizeable, consistent improvement across three independent industry-scale benchmarks rather than a single dataset. It's a drop-in pretraining upgrade for anyone already running KERMT-style ADMET pipelines.
CODE: Not released
---

---
TITLE: ConformFlow: Scalable Normalizing Flow for Protein Conformational Ensemble Generation
AUTHORS: Y. Liu, G. Lin, M. Chen
SOURCE: bioRxiv | 2026.06.16.732304 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.16.732304)
TOPIC TAG: Flow Matching
TLDR: Presents a normalizing-flow architecture for generating protein conformational ensembles that targets the scalability limitations of prior Boltzmann-generator-style flows, aiming to sample the underlying energy landscape rather than a single static fold.
WHY IT MATTERS: Conformational ensemble generation (vs. single-structure prediction) is a fast-growing subfield this month alone (joining ExEnDiff, BBFlow, AlphaFlow-style approaches), reflecting a field-wide shift toward modeling protein dynamics as central to function and allostery rather than a downstream afterthought to structure prediction. Normalizing flows offer exact likelihoods unlike diffusion/flow-matching alternatives, which matters for downstream free-energy estimation.
CODE: Not released
---

---
TITLE: scIsoAgent: Autonomous Isoform-Resolved Characterization and Sequence-Informed Interpretation of Long-Read Single-Cell Transcriptomes
AUTHORS: C. Zhao, M. Liu, X. Li, D. Li, Y. Xu, Z. Wang
SOURCE: bioRxiv | 2026.06.12.731829 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.12.731829)
TOPIC TAG: Genomics
TLDR: Builds an autonomous (agentic) pipeline that characterizes isoforms from long-read single-cell RNA-seq data and grounds the interpretation of detected isoforms in sequence-level context, rather than treating isoform calling and biological interpretation as separate manual steps.
WHY IT MATTERS: Long-read single-cell isoform analysis currently requires stitching together multiple specialized tools (ScIsoX, SCOTCH, Isosceles) followed by manual biological interpretation; an agentic wrapper that closes the loop from raw isoform calls to sequence-informed interpretation could substantially speed up splicing/isoform studies at single-cell resolution. It's part of a broader trend (alongside AgentPLM, Pepti-Agent) of wrapping bioinformatics pipelines in LLM agents rather than building new end-to-end models.
CODE: Not released
---

---
TITLE: A Transformer-Derived Transcriptomic Score Associates with Ex-Vivo Drug Response in AML
AUTHORS: J. Barman, S. Adhikari, C. Heckman, M. Vaha-Koskela
SOURCE: bioRxiv | 2026.06.12.731810 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.12.731810)
TOPIC TAG: Clinical ML
TLDR: Derives a transformer-based transcriptomic score from AML patient gene-expression data and shows it associates with ex-vivo measured drug sensitivity, positioning the score as a candidate biomarker for treatment selection.
WHY IT MATTERS: Most transcriptomic AML classifiers are built on classical ML or simple deconvolution; a transformer-derived score that correlates with real ex-vivo drug-response phenotypes (not just retrospective outcome labels) gives a more direct functional readout for precision treatment selection in a notoriously heterogeneous cancer. This adds to the growing evidence base for transformer-based expression scores as clinically actionable biomarkers rather than purely predictive curiosities.
CODE: Not released
---

---
TITLE: Infectious Disease Forecasting via Physics-Informed Machine Learning
AUTHORS: J. C. Hart, H. Smith, C. McMahan, L. Rennert
SOURCE: bioRxiv | 2026.06.12.731957 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.12.731957)
TOPIC TAG: Clinical ML
TLDR: Embeds a compartmental epidemiological model directly into the training loss of a physics-informed neural network for infectious disease forecasting, with a covariate sub-network capturing time-varying transmission drivers like mobility and cumulative vaccination.
WHY IT MATTERS: Pure data-driven forecasters overfit on short, noisy outbreak time series, while pure mechanistic compartmental models can't flexibly absorb covariates; embedding the mechanistic model as a loss-function constraint is a general recipe for getting both data efficiency and epidemiological plausibility. The covariate sub-network design is a practical template for incorporating real-world drivers (mobility, vaccination) into PINN-based forecasting more broadly.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Long-Context Modeling via GSS-Transformer Hybrid Architecture with Learnable Mixing** (arXiv:2606.16093)
Rather than forcing state-space models to mimic attention or stacking the two sequentially, this paper runs Gated State Spaces, Grouped Query Attention, and FFNs as fully parallel branches combined through a learnable mixing mechanism — letting SSMs handle global context and attention handle precise retrieval, each playing to its strength. This "specialize, don't compromise" design directly addresses the core tension that limits long-context genomic and protein-sequence foundation models today: SSMs are cheap but recall-limited, attention recalls precisely but is quadratic. Any group building whole-chromosome-scale or long-read genomic LMs should be tracking this architecture pattern closely.
Code/weights: Not released.

**2. Taylor-Calibrate: Principled Initialization for Hybrid Linear Attention Distillation** (arXiv:2606.16429)
Taylor-Calibrate solves a quietly important practical problem: converting an existing pretrained Transformer into an efficient linear-attention hybrid by distillation works far better if the new recurrent dynamics (decay, write-gate, output-gate) are initialized from Taylor-guided teacher attention statistics instead of naive weight-copying, removing a costly "cold start" that otherwise burns enormous distillation budgets. This is a systems-level efficiency unlock — it makes converting today's large pretrained bio-sequence LMs into long-context-efficient deployable models meaningfully cheaper, rather than requiring a from-scratch pretraining run.
Code/weights: Not released.

**3. Probabilistic Contrastive Pretraining for Multi-task ADME Property Prediction** (arXiv:2606.11508)
NVIDIA's team shows that adding a contrastive mutual-information objective (cMIM) plus chemistry-specific self-supervision on top of an existing KERMT-style graph-transformer pretraining pipeline delivers a consistent 7.6–9.9% improvement across three independent, industry-scale ADME benchmarks (Biogen, ExpansionRX, ChEMBL-MT). Consistent gains across multiple real pharma-scale benchmarks (rather than one academic dataset) make this an unusually credible, drop-in pretraining upgrade for anyone already running ADMET screening pipelines built on graph-transformer molecular encoders.
Code/weights: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 7
- By topic: Protein LM: 0 | Diffusion: 0 | Flow Matching: 1 | Genomics: 1 | Architecture: 1 | SSM: 1 | General ML: 1 | Clinical ML: 3
- Sources: arXiv: 3 | bioRxiv: 4 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
