# Research Digest — 2026-06-16

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Papers already covered in the 2026-06-15 digest (arXiv IDs up to 2606.11382 and those explicitly listed) are excluded. Today's focus is on newly announced papers with IDs ≥ 2606.11574, plus select bioRxiv papers from June 2026 not yet covered.

---

---
TITLE: Viral Proteins Reveal Geometry of Protein Language Models
AUTHORS: Arthur Bigot et al.
SOURCE: arXiv | 2606.12609 | [**Link**](https://arxiv.org/abs/2606.12609)
TOPIC TAG: Protein LM
TLDR: Probing ESM model families with viral proteins as underrepresented-sequence surrogates, the authors identify a dominant "nativeness axis" in pLM embedding space — aligned with masked-reconstruction perplexity — that orders representations from cellular proteins through viral proteins to shuffled sequences, while viral-specific signal remains linearly separable from nativeness alone.
WHY IT MATTERS: Exposes a fundamental geometry of protein language model representations: training-distribution bias imprints a single dominant axis that governs how novel or underrepresented sequences are embedded. Viral proteins offer a practical probe to audit pLM generalization without needing fully unseen folds, with direct implications for deploying ESM-style models on non-standard biology (viral proteomes, synthetic sequences).
CODE: Not released
---

---
TITLE: Range-Aware Bayesian Optimization for Discovering Diverse Designs within Target Property Windows
AUTHORS: Shengli Jiang et al.
SOURCE: arXiv | 2606.11574 | [**Link**](https://arxiv.org/abs/2606.11574)
TOPIC TAG: General ML
TLDR: Introduces range-aware Bayesian optimization (RaBO), an acquisition function that directly scores posterior probability that a candidate falls within a user-specified target property window, enabling simultaneous discovery of multiple structurally diverse solutions satisfying the specification.
WHY IT MATTERS: Most BO frameworks optimize a scalar objective, yet practical molecular/protein design often targets a range (e.g., melting temperature 65–75°C, IC50 1–10 nM), where multiple chemically distinct solutions are desirable for robustness and cost reasons. RaBO fills this gap with a principled acquisition strategy applicable to any latent-space generative model.
CODE: Not released
---

---
TITLE: In-Context Learning for Latent Space Bayesian Optimization
AUTHORS: Tuan A. Vu et al.
SOURCE: arXiv | 2606.09664 | [**Link**](https://arxiv.org/abs/2606.09664)
TOPIC TAG: General ML
TLDR: Adapts tabular foundation model surrogates (TabPFN/TabICL) to latent-space Bayesian optimization of structured objects such as molecules and proteins by augmenting pretraining with synthetic optimization tasks defined on a molecular VAE latent space, resolving the distribution mismatch that degrades off-the-shelf in-context surrogates.
WHY IT MATTERS: Latent-space BO is the standard tool for data-efficient protein/drug optimization in wet-lab experimental design campaigns, but surrogate models trained on standard regression tasks transfer poorly to latent manifolds. This work provides a practical recipe to leverage large pretrained tabular regressors in BO loops without costly retraining on domain data.
CODE: Not released
---

---
TITLE: Flexible Kernels for Protein Property Prediction
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.11057 | [**Link**](https://arxiv.org/abs/2606.11057)
TOPIC TAG: Protein LM
TLDR: Proposes sequence kernels that exploit evolutionary substitution matrices (BLOSUM, PAM) as a basis for Gaussian process models of protein property landscapes, achieving data-efficient fitness prediction with principled uncertainty quantification across benchmark binding-affinity and thermostability tasks.
WHY IT MATTERS: Large neural protein models require thousands of labelled variants to fine-tune effectively, yet most directed evolution campaigns generate only tens to hundreds of assay measurements per round. Kernel-based GPs with evolutionary substitution kernels provide uncertainty-calibrated surrogate models for low-n regimes, directly improving active learning loops in enzyme and antibody engineering.
CODE: Not released
---

---
TITLE: When Does Structure Help? The Information Bonus of AlphaFold2 Representations over Protein Language Models
AUTHORS: Kargi Chauhan et al.
SOURCE: arXiv | 2606.04228 | [**Link**](https://arxiv.org/abs/2606.04228)
TOPIC TAG: Protein LM
TLDR: Introduces the "information bonus" (IB) metric — the linear-regression advantage of frozen AF2 Evoformer embeddings over frozen ESM-2 embeddings under protein-level cross-validation — and finds IB is sharply task-dependent: high for conformational flexibility and allosteric-site annotation, near zero for many binding-affinity regression benchmarks.
WHY IT MATTERS: Running AlphaFold2 inference to generate structure-aware representations incurs substantial compute cost; this work provides the first quantitative, task-level framework to decide whether that cost is justified. The IB metric is a practical screening tool for lab groups deciding between sequence-only and structure-conditioned pipelines for any given downstream task.
CODE: Not released
---

---
TITLE: DeltaDiff: Training-Free, Physics-Guided Machine Learning for Predicting Mutant Protein Structures
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.04452 | [**Link**](https://arxiv.org/abs/2606.04452)
TOPIC TAG: Diffusion
TLDR: DeltaDiff incorporates mutation-aware physical guidance (energy gradients from a molecular mechanics force field) into the inference loop of a pretrained diffusion structure model without any retraining, significantly improving mutant-structure prediction on three benchmark systems (Chignolin T8P, Novispirin G-10, BBL D162N) involving non-local conformational changes.
WHY IT MATTERS: Determining mutant structures is critical for understanding how mutations alter biochemical mechanisms, yet current deep learning structure predictors struggle when mutations cause non-local rearrangements far from the mutated residue — exactly the regime most interesting for stability engineering and disease-variant analysis. Physics-guided inference without retraining makes this an immediately deployable upgrade to any diffusion-based folding pipeline.
CODE: Not released
---

---
TITLE: NucleoDock: An Accurate Nucleic Acid–Small Molecule Docking Framework via Geometric Deep Learning with Large-Scale Pretraining
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.05198 | [**Link**](https://arxiv.org/abs/2606.05198)
TOPIC TAG: Clinical ML
TLDR: NucleoDock combines physics-guided pretraining on millions of synthetic nucleic acid–ligand docking poses with fine-tuning on curated experimental co-crystal structures, integrating sequence- and structure-informed nucleotide representations to achieve 56% top-1 success at 2 Å RMSD on an external benchmark of 125 NA–ligand complexes (vs. 29% for rDock), generating 100 poses in ~5 seconds per complex.
WHY IT MATTERS: Drug discovery tooling for nucleic acid targets (RNA riboswitches, G-quadruplexes, splice junctions) lags far behind protein-directed pipelines due to scarcity of training data and lack of specialized models. NucleoDock directly addresses this gap and, with improved early enrichment on the ROBIN virtual screening benchmark, provides a practical path toward RNA-targeted drug campaigns.
CODE: Not released
---

---
TITLE: Using Protein Language Models for Pangenome Construction
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: bioRxiv | 2026.06.04.730042 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.04.730042v1)
TOPIC TAG: Protein LM
TLDR: Leverages pLM embeddings (functional and evolutionary similarity) in place of sequence-identity thresholds for orthogroup inference in pangenome construction, outperforming the SCARAP baseline on both randomly sampled OrthoDB and CAFA5 datasets on all functional coherence and consistency metrics, with GPU-accelerated dynamic batching and ONNX export enabling near-linear scaling to millions of proteins.
WHY IT MATTERS: Pangenome construction — clustering millions of proteins from diverse organisms into orthogroups — underpins comparative genomics and functional annotation pipelines across all of biology. Replacing rigid sequence-identity cutoffs with semantic pLM distances allows grouping of functionally related but sequence-divergent proteins, directly improving the accuracy of downstream GWAS, gene-family evolution, and annotation transfer analyses.
CODE: Not released
---

---
TITLE: The Dark Regulome: Disentangling Predictability from Regulation in Genomic Foundation Models
AUTHORS: Chahat Baranwal et al.
SOURCE: arXiv | 2606.06834 | [**Link**](https://arxiv.org/abs/2606.06834)
TOPIC TAG: Genomics
TLDR: Introduces a residualization-and-permutation diagnostic that separates predictability-driven from regulation-driven variance when using in-silico mutagenesis with genomic foundation models (Caduceus-Ph, HyenaDNA, Enformer), revealing that likelihood-based regulatory scores are confounded with local sequence predictability across 30,448 dark-genome elements at 92 glioma-relevant loci.
WHY IT MATTERS: In-silico mutagenesis with genomic FMs is widely used for variant effect prediction on non-coding DNA, but a systematic confound — model-assessed likelihood and sequence predictability co-vary — inflates apparent regulatory signal in low-complexity regions. This diagnostic is a necessary sanity check before deploying FM-based regulatory scores for clinical variant interpretation or eQTL fine-mapping.
CODE: Not released
---

---
TITLE: ViroBench: Benchmarking Nucleotide Foundation Models on Viral Genomics Tasks
AUTHORS: Dongxin Ye et al.
SOURCE: HF Papers | 2605.25388 | [**Link**](https://hf.co/papers/2605.25388)
TOPIC TAG: Genomics
TLDR: ViroBench is the first comprehensive benchmark for nucleotide foundation models (NFMs) in viral settings, evaluating 66 models across 18 scenarios and 4 task types spanning biological understanding and biosecurity risk; key findings are that NFMs degrade under phylogenetic/temporal shift, generation tasks decouple statistical likelihood from functional validity, and taxonomic diversity in pretraining data outweighs parameter scale (a diverse lightweight model gains 67.5% over its baseline).
WHY IT MATTERS: Prior NFM evaluations primarily cover human/model-organism genomics; ViroBench exposes that current models extrapolate poorly to viral diversity and can generate sequences with low biological validity despite high likelihood — an unaddressed latent biosecurity risk. The 66-model evaluation and reproducible framework provide a clear benchmark for future viral FM development.
CODE: [**Code**](https://github.com/QIANJINYDX/ViroBench)
---

---
TITLE: CHIMERA-Bench: A Benchmark Dataset for Epitope-Specific Antibody Design
AUTHORS: Mansoor Ahmed et al.
SOURCE: HF Papers | 2603.13431 | [**Link**](https://hf.co/papers/2603.13431)
TOPIC TAG: Protein LM
TLDR: Introduces a unified benchmark for epitope-conditioned antibody CDR sequence-structure co-design, standardizing evaluation with curated SAbDab-derived datasets, biologically motivated generalization splits (epitope, antigen, and temporal), and a multi-metric suite covering epitope specificity, binding geometry, and diversity across leading generative paradigms.
WHY IT MATTERS: The antibody design field lacks a shared evaluation standard — different papers use incompatible datasets, splits, and metrics, making progress hard to measure. CHIMERA-Bench provides the scaffolding for rigorous head-to-head comparison of de novo generators, diffusion models, and LM-based approaches under realistic deployment conditions including OOD generalization.
CODE: Not released
---

---
TITLE: Geometric Coherence of Single-Cell CRISPR Perturbations Reveals Regulatory Architecture and Predicts Cellular Stress
AUTHORS: Prashant C. Raju et al.
SOURCE: HF Papers | 2604.16642 | [**Link**](https://hf.co/papers/2604.16642)
TOPIC TAG: Genomics
TLDR: Analyses the geometric coherence of transcriptional responses to CRISPR perturbations in single-cell data to infer gene regulatory architecture and predict cellular stress, finding that geometric structure in perturbation response space encodes regulatory hierarchy and generalizes to hold-out perturbations.
WHY IT MATTERS: Mapping gene regulatory networks from CRISPR perturbation screens is a central goal of functional genomics, but most methods rely on pairwise correlations or causal graph inference from noisy data. Using the geometric structure of the full perturbation manifold provides a more holistic view of regulatory architecture and opens a route to predicting unseen perturbation phenotypes.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Viral Proteins Reveal Geometry of Protein Language Models** (arXiv 2606.12609)
The paper reveals that protein language model embedding spaces are dominated by a single "nativeness axis" — a gradient from well-modeled cellular proteins through viral proteins to shuffled sequences — that aligns with masked-reconstruction perplexity. Despite this compression, viral-specific signal remains linearly separable. This finding exposes a previously uncharacterized geometric structure in pLM representations arising from training-distribution bias. For practitioners, it provides both a diagnostic (perplexity as nativeness proxy) and an assay (viral proteins as bias probes), directly informing how pLMs should and should not be deployed on underrepresented sequence spaces such as designed proteins, viral therapeutics, or synthetic biology applications.
Code/weights: Not released.

**2. NucleoDock: An Accurate Nucleic Acid–Small Molecule Docking Framework** (arXiv 2606.05198)
NucleoDock addresses a critical gap: while dozens of high-accuracy protein–ligand docking models exist, no deep learning tool has been validated for nucleic acid targets at scale. By combining physics-guided pretraining on synthetic poses with geometric deep learning fine-tuned on co-crystal structures, NucleoDock achieves 56% top-1 success at 2 Å RMSD versus 29% for the best classical tool, in ~5 seconds per complex. RNA-targeting therapeutics (riboswitches, splicing modulators, aptamers) are a rapidly growing drug class, and NucleoDock provides the computational infrastructure currently missing for high-throughput RNA-targeted virtual screening.
Code/weights: Not released.

**3. When Does Structure Help? The Information Bonus of AlphaFold2 Representations over Protein Language Models** (arXiv 2606.04228)
This paper introduces the "information bonus" (IB) metric and provides the first task-level quantification of when expensive AF2 structure inference is worth the compute over ESM-2 sequence embeddings. The finding that IB is near zero for many binding-affinity benchmarks but high for conformational flexibility tasks is directly actionable: groups running routine property prediction can in many cases skip structural inference without performance loss, while groups doing flexibility or allostery analysis should retain it. The framework generalizes to any pair of representation models and any downstream task.
Code/weights: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 12
- By topic: Protein LM: 5 | Diffusion: 1 | Genomics: 3 | Architecture: 0 | General ML: 2 | Clinical ML: 1
- Sources: arXiv: 9 | bioRxiv: 1 | HF Papers: 2 | medRxiv: 0 | PubMed: 0 | PWC: 0
- Papers with code released: 1 (ViroBench)
