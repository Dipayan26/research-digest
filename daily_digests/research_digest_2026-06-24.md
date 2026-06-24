# Research Digest — 2026-06-24

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct fetches to arxiv.org/export.arxiv.org, biorxiv.org, and medrxiv.org/pubmed.ncbi.nlm.nih.gov again returned HTTP 403 in this environment, so discovery relied on WebSearch (five parallel sweeps across source/topic clusters) plus the Hugging Face MCP connector (partially available — `paper_search` worked, `hf_hub_query` connection was dropped). PubMed and medRxiv contributed no items today: no candidate could be confirmed with a verifiable last-24-48h date, so none are reported rather than risk an unverified date. As in prior days, arXiv/bioRxiv indexing for items posted in the last 24h is lagging, so this sweep draws on a ~2-week window (June 10-23) and was cross-checked line-by-line against the full prior digest history (373 titles / IDs through 2026-06-22) to exclude duplicates — several strong-looking candidates (ProHiFlo, m6A-FORM, AgentPLM, SurfDesign, AlloGen, Viral Proteins Reveal Geometry of PLMs, CisTransCell, RicciBind, "Language Modeling Materializes a World Model of Protein Biology," FLOWR, Origin-1, Single-Cell Cross-Modal Transfer) turned out to already be covered or too stale and were dropped. One candidate (arXiv:2606.09675, "The Challenge of Cell Segmentation in Spatially Resolved Transcriptomics") was excluded as a perspective piece with no new method/result. "Arch4Health" (computer-hardware architecture for health data infra) and a classical molecular-dynamics simulation paper were excluded as out of ML-for-bio scope.

---

---
TITLE: A High-Level Programming Language for Generative Biology with Proto
AUTHORS: Aditi T. Merchant et al.
SOURCE: bioRxiv | 10.64898/2026.06.22.733870 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.22.733870v1)
TOPIC TAG: General ML
TLDR: Proto is a domain-specific programming language that composes generative primitives into multi-objective design campaigns across DNA, RNA, proteins, and ligands, with synthetic intron and promoter-repressor pairs experimentally validated in human cells.
WHY IT MATTERS: Generative biology tooling today is mostly single-modality and single-objective; Proto's composable abstractions let predictive ML models be wired natively into cross-scale design campaigns instead of bespoke one-off pipelines. Closing the loop with wet-lab validation in human cells (not just in silico scoring) is a meaningfully higher bar than most generative-design infrastructure papers clear.
CODE: Not released
---

---
TITLE: SAbDab2: The Structural Antibody Database in the Age of Machine Learning
AUTHORS: Capel, Vavourakis, et al.
SOURCE: bioRxiv | 10.64898/2026.06.16.732554 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.16.732554v1)
TOPIC TAG: Protein LM
TLDR: Re-engineers SAbDab into an ML-ready antibody structure resource — 21,237 curated structures with versioned, leakage-aware train/test splits and unique IDs that map identical variable domains across PDB entries.
WHY IT MATTERS: Antibody design benchmarks have long suffered from date-based train/test leakage and inconsistent sequence-redundancy handling, making cross-paper comparisons unreliable; SAbDab2 is the first public resource to handle this explicitly and refresh on a fixed cadence. As a shared benchmark substrate, it directly affects how every antibody pLM/inverse-folding paper built on top of it should be evaluated going forward.
CODE: Dataset released on Zenodo (exact link not confirmed)
---

---
TITLE: Dissecting and Directing Pathology Foundation Models (PICASSO)
AUTHORS: Kim, Kaczmarzyk, et al.
SOURCE: bioRxiv | 10.64898/2026.06.12.731496 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.12.731496v1)
TOPIC TAG: Clinical ML
TLDR: PICASSO trains sparse autoencoders on pathology foundation model embeddings across 120M tissue patches and 32 cancer types to decompose them into human-interpretable histomorphological concepts that can be directly intervened on.
WHY IT MATTERS: Pathology foundation models are widely deployed but remain black boxes, which is a real barrier to clinical adoption; PICASSO gives pathologists a concept-level interface to inspect and steer model decisions rather than trusting opaque embeddings. The scale (120M patches, 32 cancer types) makes the resulting concept atlas a reusable interpretability layer for other models built on the same foundation backbones.
CODE: Not released
---

---
TITLE: Retrieval-Augmented Multimodal Learning for Enzyme-Substrate Interaction Prediction Under Low-Homology Shift (RAMMESI)
AUTHORS: Chen Liu, Bingxin Zhou, Xinyuan Wang, Ming Li, Guisheng Fan, Liang Hong
SOURCE: arXiv | 2606.22823 | [**Link**](https://arxiv.org/abs/2606.22823)
TOPIC TAG: General ML
TLDR: RAMMESI learns cross-modal enzyme-substrate representations and retrieves neighboring enzymes at inference time to predict catalytic activity for test enzymes with low sequence identity to training data.
WHY IT MATTERS: Biocatalyst discovery routinely needs predictions on enzymes far from any training homolog, exactly where standard similarity-based models fail; retrieval-augmented inference is a comparatively underused fix for this distribution-shift problem in enzyme engineering. Imbalance-aware training on top of the retrieval mechanism targets the sparse-positive-label regime that plagues most enzyme-substrate datasets.
CODE: [**Code**](https://github.com/code4luck/RAMMESI.git)
---

---
TITLE: Contextualizing Biological Language Models across Modalities via Logit-Space Contrastive Alignment (LOGICA)
AUTHORS: Yanjun Shao et al.
SOURCE: arXiv | 2606.18703 | [**Link**](https://arxiv.org/abs/2606.18703)
TOPIC TAG: Protein LM
TLDR: LOGICA performs contrastive learning directly in a biological LM's output-logit space to inject task-specific context conditioning without retraining the backbone, improving over SOTA on protein-ligand binding, TCR-peptide activity, and drug-resistance prediction.
WHY IT MATTERS: Most context-conditioning methods for biological LMs require architecture changes or fine-tuning that breaks the pretrained likelihood interface; operating in logit space preserves that interface while still letting the model react to new context. The reported token-level interpretability is a useful side effect for diagnosing what context signal is actually being used.
CODE: Not released
---

---
TITLE: EasyNano: Rapid Epitope-Targeted Nanobody CDR Design via Differentiable Distogram Optimization with ESMFold2
AUTHORS: Yue Hu et al.
SOURCE: arXiv | 2606.12772 | [**Link**](https://arxiv.org/abs/2606.12772)
TOPIC TAG: Protein LM
TLDR: EasyNano designs nanobody CDRs against a user-specified epitope by differentiably optimizing ESMFold2-predicted distograms, running in 10-20 minutes on a personal workstation versus days for stochastic sampling baselines.
WHY IT MATTERS: Unlike inverse-folding pipelines that redesign a sequence for a fixed backbone, EasyNano targets a specific epitope directly, which is the practically relevant constraint in therapeutic nanobody campaigns. The speed gain (minutes vs. days) lowers the barrier for iterative, in-the-loop nanobody design on commodity hardware.
CODE: Not released
---

---
TITLE: MOLAR: Learning Multimodal Molecular Representations from Noisy Labels
AUTHORS: Yingxu Wang et al.
SOURCE: arXiv | 2606.18390 | [**Link**](https://arxiv.org/abs/2606.18390)
TOPIC TAG: General ML
TLDR: MOLAR fuses graph and text views of a molecule while explicitly separating a latent clean-property variable from the observed (possibly mislabeled) assay label, with posterior diagnostics for label reliability.
WHY IT MATTERS: Most multimodal molecular representation methods implicitly assume clean supervision, but real assay data is full of measurement and annotation noise; MOLAR's probabilistic noise model is a more honest fit to actual drug-discovery datasets. The per-label reliability diagnostic is directly useful for dataset curation, not just model training.
CODE: Not released
---

---
TITLE: Benchmarking AI Agents for Addressing Scientific Challenges Across Scales (SciAgentArena)
AUTHORS: Tianyu Liu et al.
SOURCE: arXiv | 2606.12736 | [**Link**](https://arxiv.org/abs/2606.12736)
TOPIC TAG: General ML
TLDR: SciAgentArena is an interactive benchmark of ~200 tasks across five scientific domains showing current AI agents handle well-specified workflows but fail at molecular representation handling and output formatting in drug-discovery tasks.
WHY IT MATTERS: As agentic pipelines get proposed for everything from genomics to chemistry, there has been little rigorous, task-diverse evaluation of where they actually break; this benchmark pinpoints cheminformatics/molecular-handling as a concrete capability gap rather than a vague "agents aren't reliable yet" claim. It gives agent developers a reusable target for closing exactly that gap.
CODE: [**Code**](https://sciagentarena.github.io/)
---

---
TITLE: Trustworthy Agentic Genomics through Versioned Skill Libraries
AUTHORS: Corpas et al.
SOURCE: bioRxiv | 10.64898/2026.06.11.731523 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.11.731523v1)
TOPIC TAG: Clinical ML
TLDR: Moves correctness out of stochastic LLM generations into versioned, deterministic code "skills," tested on pharmacogenomic variant-to-drug mappings across 9 LLMs and 110 clinical cases with model-invariant, auditable outputs.
WHY IT MATTERS: Clinical genomics agents can't tolerate LLM hallucination, and this paper shows a practical way around it: constrain the agent to call versioned, auditable code rather than trusting free-form generation for the parts that must be correct. Achieving identical outputs across 9 different backbone LLMs is a strong demonstration that correctness can be decoupled from model choice.
CODE: Not released
---

---
TITLE: BioBrain: A Multi-Agent Framework for Natural Language Driven Quantitative Microscopy Data Analysis
AUTHORS: Tsolakidis, Breuer, et al.
SOURCE: bioRxiv | 10.64898/2026.06.17.732700 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.17.732700v1)
TOPIC TAG: Clinical ML
TLDR: A multi-agent system translates natural-language analysis goals into executable, reproducible quantitative microscopy pipelines, orchestrating the full image-analysis workflow autonomously.
WHY IT MATTERS: Quantitative microscopy analysis currently gatekeeps on bespoke scripting expertise; letting biologists specify the analysis goal in English and get a reproducible pipeline out lowers that barrier substantially. It's a concrete instance of the broader trend of agentic systems taking over glue-code workflows in experimental biology.
CODE: Not released
---

---
TITLE: biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes
AUTHORS: Ariyaratne, Somaratna, et al.
SOURCE: bioRxiv | 10.64898/2026.06.10.731380 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1)
TOPIC TAG: Clinical ML
TLDR: An autonomous agent orchestrates phylogenetic reconstruction, Bayesian phylodynamics, and selection analysis end-to-end on 1,000 dengue virus genomes from 16 Asian countries, finding 1,869 candidate immune-escape sites in under 24 hours.
WHY IT MATTERS: Genomic epidemiology pipelines are multi-step and error-prone under manual execution; full agentic orchestration compresses what is normally weeks of expert effort into a single reproducible session, which matters directly for outbreak-response timelines. The candidate immune-escape site list is also a concrete, actionable output rather than just a methods demonstration.
CODE: Not released
---

---
TITLE: Benchmarking Cell Type Annotation in Spatial Transcriptomics: Resolving Cellular Hierarchies, Biological Fidelity, and Dynamic Cell States
AUTHORS: Yuling Zhu et al.
SOURCE: bioRxiv | 10.64898/2026.06.16.732716 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.16.732716v1)
TOPIC TAG: Genomics
TLDR: A systematic benchmark of ML/DL cell-type annotation methods for spatial transcriptomics, evaluated specifically on hierarchical cell-type structure and dynamic-state assignment rather than flat classification accuracy alone.
WHY IT MATTERS: Cell-type annotation is the bottleneck step before almost any downstream spatial-omics analysis, and most existing benchmarks ignore hierarchy and dynamic states; this fills that evaluation gap with a systematic comparison. The results give a concrete basis for choosing an annotation method rather than defaulting to whatever ships with a given platform.
CODE: Not released
---

---
TITLE: Benchmarking Gene Expression Reconstruction from Single-Cell Latent Representations
AUTHORS: Xiaotong Fu et al.
SOURCE: bioRxiv | 10.64898/2026.06.15.731445 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.15.731445v1)
TOPIC TAG: Genomics
TLDR: Systematically benchmarks single-cell foundation models on how faithfully their latent codes can reconstruct gene expression, finding reconstruction fidelity is an overlooked but critical evaluation axis.
WHY IT MATTERS: Single-cell foundation models are increasingly used purely as compressors into a latent space for downstream tasks, but few papers check whether that compression actually preserves biological signal; this benchmark makes that check standard. It's directly useful for anyone choosing a single-cell foundation model backbone for a new downstream application.
CODE: Not released
---

---
TITLE: Complex-Valued Representations of Time-Series Gene Expression Profiles for Network Analysis
AUTHORS: Sun, Cao, et al.
SOURCE: bioRxiv | 10.64898/2026.06.16.732574 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.16.732574v1)
TOPIC TAG: Genomics
TLDR: Encodes temporal gene-expression trajectories as complex-valued vectors — amplitude for expression level, phase for direction of change — inspired by quantum-information geometry, to improve gene-gene network similarity estimation.
WHY IT MATTERS: Time-series expression analysis usually discards temporal ordering or needs bespoke dynamical models; representing both magnitude and direction of change in a single complex-valued embedding is an elegant way to keep that structure inside a standard network-analysis pipeline. The approach is method-agnostic and could be dropped into any existing gene-network workflow that currently only uses static expression snapshots.
CODE: Not released
---

---
TITLE: Few-Shot Classification of C. elegans Developmental Stages via Explainable Hierarchical Hyperbolic Graph Embeddings
AUTHORS: Nazish Khalid et al.
SOURCE: bioRxiv | 10.64898/2026.06.21.733631 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733631v1)
TOPIC TAG: General ML
TLDR: Uses a graph neural network with hyperbolic (rather than Euclidean) embeddings to capture the hierarchical structure of C. elegans developmental stages, enabling few-shot classification with interpretable feature attribution.
WHY IT MATTERS: Developmental hierarchies are tree-like by nature, which hyperbolic geometry represents far more efficiently than Euclidean space — a useful, broadly transferable design choice for any biological classification task with an inherent hierarchy and scarce labels. The explainability component (feature attribution over the graph) addresses a common complaint about geometric deep learning being a black box.
CODE: Not released
---

---
TITLE: scGTN: Deep Siamese Graph Transformer Network for Single-Cell RNA Sequencing Clustering
AUTHORS: Jinke Wu et al.
SOURCE: arXiv | 2606.18672 | [**Link**](https://arxiv.org/abs/2606.18672)
TOPIC TAG: Genomics
TLDR: A Siamese graph transformer architecture for scRNA-seq clustering explicitly designed around the sparsity and noise structure of single-cell count data rather than treating it as generic tabular input.
WHY IT MATTERS: Generic clustering architectures borrowed from other domains tend to underperform on scRNA-seq because they don't account for its extreme sparsity and dropout noise; building the inductive bias in from the start (graph structure + Siamese contrastive objective) is a more principled fix than post-hoc normalization tricks. It's a direct architectural alternative to the GNN- and attention-based scRNA-seq clustering methods currently in wide use.
CODE: Not released
---

---
TITLE: Surveying the Adaptive Landscapes of 10,000 Antibodies
AUTHORS: Daniel P. G. H. Wong et al.
SOURCE: arXiv | 2606.21351 | [**Link**](https://arxiv.org/abs/2606.21351)
TOPIC TAG: Protein LM
TLDR: Applies a parameter-free population-genetics framework across more than 10,000 public antibody clonotypes to identify mutations under positive selection during affinity maturation, at a scale far beyond prior single-lineage studies.
WHY IT MATTERS: Generative antibody design models are typically trained and validated on small curated datasets; a population-scale empirical map of which mutations are actually favored during real affinity maturation is exactly the kind of ground truth those models are missing. It also gives the field design heuristics for affinity maturation that don't depend on any particular structural or language model's priors.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. A High-Level Programming Language for Generative Biology with Proto**
Proto turns generative biological design into a composable programming problem: researchers write design campaigns that span DNA, RNA, protein, and ligand modalities using shared abstractions, with predictive ML models wired in as native primitives rather than glued on afterward. It validated this in practice by experimentally testing synthetic introns and promoter-repressor pairs in human cells, not just scoring designs in silico. This is the kind of infrastructure shift — going from one-off model pipelines to a reusable design language — that could change how every other generative-biology paper in this space gets built going forward.
Code: Not released.

**2. SAbDab2: The Structural Antibody Database in the Age of Machine Learning**
SAbDab2 rebuilds the field's most widely used antibody structure database specifically to fix the train/test leakage and redundancy problems that have quietly undermined antibody ML benchmarking for years, adding versioned splits and identity-aware deduplication on a fixed release cadence. Because nearly every antibody design or affinity-prediction paper in this space ultimately benchmarks against SAbDab-derived data, a more rigorous version directly raises the evidentiary bar for the whole subfield. It's an unglamorous but unusually high-leverage contribution — better data discipline rather than another model.
Code: Dataset released on Zenodo (exact link not confirmed).

**3. Dissecting and Directing Pathology Foundation Models (PICASSO)**
PICASSO trains sparse autoencoders on pathology foundation model embeddings at a scale (120M tissue patches, 32 cancer types) large enough to extract a genuinely comprehensive atlas of human-interpretable histomorphological concepts, then shows those concepts can be directly intervened on. This addresses one of the most concrete blockers to clinical adoption of pathology AI — that pathologists currently can't inspect or correct what the model is actually keying on. A reusable, large-scale interpretability layer like this is valuable well beyond this specific model, for any clinical workflow built on the same foundation backbones.
Code: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 17
- By topic: Protein LM: 4 | Diffusion: 0 | Genomics: 4 | Architecture: 0 | General ML: 5 | Clinical: 4 (note: tags overlap loosely, e.g. agentic-genomics items span Genomics/Clinical ML)
- Sources: arXiv: 7 | bioRxiv: 10 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 3
