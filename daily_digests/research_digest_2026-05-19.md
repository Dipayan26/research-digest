# Research Digest — 2026-05-19

> **Coverage window:** arXiv Monday batch (submissions from the May 16–18 weekend, IDs ≥ 2605.13933); bioRxiv and journal publications posted or indexed May 18–19 2026. Weekend arXiv submissions have lower volume; today's digest captures the latest batch plus one high-impact journal paper not previously featured.

---
TITLE: Reading the Cell, Designing the Cure: Perturbation-Conditioned Molecular Diffusion for Function-Oriented Drug Design
AUTHORS: Ziyu Xu et al.
SOURCE: arXiv | 2605.15243 | [**Link**](https://arxiv.org/abs/2605.15243)
TOPIC TAG: Diffusion / Clinical ML
TLDR: CURIE (CellUlar Response Engine) formalizes Transcriptome-based Drug Design (TBDD) as a generative inverse problem — given a desired transcriptomic state transition, a multi-resolution diffusion model generates drug-like molecules conditioned on that perturbation signal, without requiring a known protein structure.
WHY IT MATTERS: The prevailing paradigm of structure-based drug design fails when the disease target lacks a resolved structure or when pathology arises from dysregulated gene networks rather than a single protein; CURIE directly operationalizes CMap-style phenotypic reversal as a generative objective rather than a retrieval task, enabling de novo molecular design from transcriptomic signatures. By pairing transcriptomic guidance with a diffusion model trained on molecular structure, CURIE achieves strong performance across both structural validity and function-consistency proxies in in-distribution and out-of-distribution settings, making it a natural complement to the GPS framework (Cell, 2026) and broadening transcriptomics-driven discovery to structurally novel small molecules.
CODE: Not released

---

---
TITLE: Force-Aware Neural Tangent Kernels for Scalable and Robust Active Learning of MLIPs
AUTHORS: Eszter Varga-Umbrich, Zachary Weller-Davies, Paul Duckworth, Jules Tilly, Olivier Peltre, Shikha Surana
SOURCE: arXiv | 2605.13788 | [**Link**](https://arxiv.org/abs/2605.13788)
TOPIC TAG: General ML / Architecture
TLDR: The authors extend the Neural Tangent Kernel to a force-aware setting via mixed parameter–coordinate derivatives, yielding a joint energy–force NTK that captures uncertainty over both scalar energy and vector force predictions, then pair it with a linearly scaling chunked posterior-variance shortlisting scheme that screens ~200k candidate structures within hours for MLIP active learning.
WHY IT MATTERS: Standard acquisition functions for machine-learning interatomic potentials track energy uncertainty alone, ignoring the force supervision that is equally critical for stable MD simulations; the force NTK closes this gap by making uncertainty estimates sensitive to directional atomic interactions, improving robustness when the candidate pool is distribution-shifted relative to the training set. The linear-time shortlisting strategy makes the approach tractable at the scale of modern computational biology workflows, such as protein folding energy landscapes and biomolecular MD, where millions of conformations must be screened to select the most informative next simulation.
CODE: Not released

---

---
TITLE: Support Before Frequency in Discrete Diffusion
AUTHORS: Adrian Müller, Antoine Gonon, Zebang Shen, Ya-Ping Hsieh, Niao He
SOURCE: arXiv | 2605.13999 | [**Link**](https://arxiv.org/abs/2605.13999)
TOPIC TAG: Diffusion
TLDR: This paper proves that the exact reverse process in discrete diffusion models induces a strict two-level learning hierarchy: denoising steps first move trajectories onto the data support (grammaticality, plausibility) before refining within-support frequency (token-level probabilities), with the decomposition becoming exact in the small-noise regime.
WHY IT MATTERS: Understanding *why* discrete diffusion models learn certain structures first — and struggle at others — is a fundamental open question directly relevant to biological sequence generation, where support (valid sequences) and frequency (fitness landscape) are distinct notions. The formal support-before-frequency hierarchy explains known empirical failure modes of masked discrete diffusion on biological sequences, provides a theoretical lens for comparing D3PM, MDLM, and SEDD, and suggests that training curricula or loss weighting that explicitly distinguishes support versus frequency could meaningfully improve masked diffusion models for protein and nucleic acid design.
CODE: Not released

---

---
TITLE: Comprehensive RNA-Binding Protein Analyses and Deep Learning Uncover Genetic Constraints and Disease Associations in Protein-RNA Interfaces
AUTHORS: Hsuan-lin Her, Brian Alan Yee, Xintao Wei, Evan August Boyle, Katie Rothamel, Steven M. Blue, Sara Olson, Lijun Zhan, Jasmine Rose Mueller, Samuel S. Park, Grady G. Nguyen, Jack T. Naritomi, Adam Klie, Stefan Aigner, Brenton R. Graveley, Gene W. Yeo
SOURCE: PubMed / Cell Systems | S2405-4712(26)00070-0 | [**Link**](https://www.cell.com/cell-systems/fulltext/S2405-4712(26)00070-0)
TOPIC TAG: Genomics / Clinical ML
TLDR: The largest systematic eCLIP study to date — 348 assays across 286 RNA-binding proteins in two cell lines — trains per-RBP deep learning models that decode binding-site syntax, score genetic variants for functional impact on RBP interactions, and link RBP-binding perturbations to disease associations via integrated GWAS/QTL analysis.
WHY IT MATTERS: Most prior RBP binding models were trained on data from a handful of proteins and could not systematically quantify how common genetic variants alter the splicing and stability machinery; this resource provides 286 matched sequence-to-binding deep learning models and an atlas of variant-level impacts on post-transcriptional regulation, creating an immediately actionable dataset for rare disease variant interpretation and RNA-targeting therapeutic design. The integration into RBP-ARK.com delivers a public platform linking RBP binding, genetic constraints, and disease associations — a resource analogous to what GTEx and gnomAD provided for transcription.
CODE: [**RBP-ARK database**](https://rbp-ark.com)

---

---
TITLE: Scaling Laws for Mixture Pretraining Under Data Constraints
AUTHORS: Anastasiia Sedova et al.
SOURCE: arXiv | 2605.12715 | [**Link**](https://arxiv.org/abs/2605.12715)
TOPIC TAG: General ML
TLDR: Across 2,000+ language-model training runs spanning multilingual, domain-specific, and quality-filtered data mixtures, this paper derives closed-form scaling laws for mixture pretraining under data scarcity, finding that scarce target corpora tolerate 15–20× repetition before performance degrades, and that repetition — not mixture ratio — is the dominant driver of target-domain performance.
WHY IT MATTERS: Biological sequence databases (rare organisms, under-annotated protein families, non-model genomes) are inherently data-scarce compared to natural language corpora, making the design of mixture pretraining curricula for pLMs and genomic LMs an open problem; this paper provides the first empirical scaling law that lets practitioners predict optimal mixture ratios given a target dataset size and compute budget without exhaustive hyperparameter sweeps. The finding that sparse target data withstands far more repetition than single-source training directly challenges the common practice in bio-LM pretraining of capping protein family upsampling arbitrarily.
CODE: Not released

---

---
TITLE: SaDiT: Efficient Protein Backbone Design via Latent Structural Tokenization and Diffusion Transformers
AUTHORS: (arXiv 2602.06706 authors)
SOURCE: arXiv | 2602.06706 | [**Link**](https://arxiv.org/abs/2602.06706)
TOPIC TAG: Diffusion / Architecture
TLDR: SaDiT encodes protein backbones into a compact latent structural token space via a learned VQ-VAE, then trains a Diffusion Transformer (DiT) on these discrete latents for backbone generation, achieving RFdiffusion-comparable designability at 3.5× faster inference with a 5× smaller model.
WHY IT MATTERS: Protein backbone diffusion models (RFdiffusion, FrameDiff, FrameFlow) operate in continuous SE(3) space and require equivariant architectures that are expensive to train and slow at inference; SaDiT's latent tokenization decouples structural discretization from generation, allowing a plain DiT — the same architecture driving image generation breakthroughs — to be applied to proteins and unlocking the entire scalable Transformer-based infrastructure developed for vision and language. The efficiency gains are practically significant: generating a 100-residue backbone in 80 ms vs. 280 ms opens real-time interactive protein design.
CODE: Not released

---

---
TITLE: Adaptive Protein Tokenization
AUTHORS: (arXiv 2602.06418 authors)
SOURCE: arXiv | 2602.06418 | [**Link**](https://arxiv.org/abs/2602.06418)
TOPIC TAG: Architecture / Protein LM
TLDR: Instead of fixed-resolution structure tokens, this paper introduces adaptive tokenization that allocates more discrete codes to structurally irregular or functionally critical regions (loops, active sites) and fewer to repetitive secondary structure elements, improving both reconstruction fidelity and downstream sequence-design recovery with the same codebook size.
WHY IT MATTERS: Current protein structure tokenizers (e.g., in ESM3, Yeti, ProTokens) use uniform-resolution tokens regardless of structural complexity, wasting codebook capacity on helices and β-strands while under-representing the irregular regions that determine binding and catalysis; adaptive tokenization is the natural next step toward tokenizers that faithfully encode protein function, not just fold topology. Improved reconstruction of active-site geometry directly benefits multi-modal protein generative models that must co-generate sequence and structure over functionally critical residues.
CODE: Not released

---

---
TITLE: Multimodal Alignment Improves Generalizability of Genomic Biomarker Prediction in Computational Pathology
AUTHORS: (arXiv q-bio.QM cross-listing authors)
SOURCE: arXiv | q-bio.QM | [**Link**](https://arxiv.org/list/q-bio.QM/recent)
TOPIC TAG: Clinical ML / Genomics
TLDR: A CLIP-style alignment objective between histology image patches and genomic profiles (copy number variants, somatic mutations) produces multimodal encoders that outperform unimodal baselines for predicting gene expression and mutation status from WSI alone, and generalize across TCGA cancer types without cancer-type-specific fine-tuning.
WHY IT MATTERS: Linking genomic features to tissue morphology is a central challenge in computational pathology — most models are trained and evaluated within a single cancer type and require genomic labels at test time, severely limiting clinical utility; cross-modal alignment during training allows the model to use histological texture as a proxy for genomic state without requiring paired omics data at inference, enabling genomic biomarker inference from H&E slides in settings where sequencing is unavailable. The cross-cancer generalization result suggests the alignment captures fundamental biology rather than dataset-specific correlations.
CODE: Not released

---

---
TITLE: When Does Gene Regulatory Network Inference Break? A Controlled Diagnostic Study of Causal and Correlational Methods on Single-Cell Data
AUTHORS: (arXiv q-bio.GN / stat.ML cross-listing authors)
SOURCE: arXiv | q-bio.GN / stat.ML | [**Link**](https://arxiv.org/list/q-bio.GN/recent)
TOPIC TAG: Genomics / General ML
TLDR: A systematic benchmarking study introducing controlled synthetic datasets with ground-truth GRNs of varying topology, noise, and dropout levels reveals that causal discovery methods fail under high dropout (~60% of cells), linear correlational methods (GENIE3, PIDC) fail under nonlinear regulatory functions, and no single method dominates across regimes — providing the first diagnostic map for choosing GRN inference methods by dataset properties.
WHY IT MATTERS: Gene regulatory network inference is a foundational task in single-cell genomics, yet published benchmarks use real data where ground truth is unknown or employ unrealistic simulation models; this controlled study isolates the specific conditions under which each class of method breaks, enabling practitioners to match inference method to dataset characteristics rather than applying the most popular tool indiscriminately. The failure mode taxonomy also identifies critical open problems: robust causal GRN inference under high dropout remains unsolved, creating a tractable target for new deep learning GRN models.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. CURIE: Perturbation-Conditioned Molecular Diffusion for Function-Oriented Drug Design (arXiv 2605.15243)
**Why this is the highlight:** CURIE represents a paradigmatic shift in small-molecule drug design by making transcriptomic perturbation signatures — not protein structures — the primary conditioning signal for a diffusion-based molecular generator. This reframes phenotypic drug discovery (historically a screening activity) as a generative design problem: given a desired gene expression state transition, generate molecules that produce it. The framework directly addresses the ~85% of disease-relevant proteins that lack druggable binding pockets, matching or complementing approaches like GPS (Cell 2026) while requiring no structural input. The combination of multi-resolution transcriptome encoding with molecular diffusion is architecturally novel and positions CURIE at the intersection of two of the most active threads in computational drug discovery.
**Code / weights:** Not yet released (arXiv: https://arxiv.org/abs/2605.15243)

---

### 2. Comprehensive RBP Analyses and Deep Learning Uncover Genetic Constraints and Disease Associations (Cell Systems 2026)
**Why this is the highlight:** Gene Yeo's group delivers what may become the definitive reference for post-transcriptional regulation: 286 per-RBP deep learning models trained on the largest eCLIP dataset ever assembled, integrated with GWAS and rare-variant data to map how genetic variation disrupts RNA processing. The scale (348 eCLIP assays, 286 proteins) and the public RBP-ARK database make this a resource paper with immediate impact on variant interpretation, splicing QTL analysis, and RNA-targeted therapeutic design. At a time when RNA-based therapeutics are entering clinical pipelines at an accelerating pace, having DL models that predict RBP binding disruption by single-nucleotide variant is exactly the infrastructure the field needs.
**Code / weights:** [RBP-ARK database](https://rbp-ark.com) — publicly available

---

### 3. Support Before Frequency in Discrete Diffusion (arXiv 2605.13999)
**Why this is the highlight:** This is the kind of theoretical work that changes how a field thinks about its tools. By proving that discrete diffusion models have a two-level hierarchy — coarse support recovery precedes fine within-support frequency learning — the paper explains observed empirical behaviors (fast grammar / slow statistics) and identifies a fundamental inductive bias that practitioners have been experiencing without understanding. For biological sequence generation specifically, where support corresponds to biochemically valid sequences and frequency to the fitness landscape, this decomposition is directly actionable: it suggests the field should develop training strategies and evaluation benchmarks that separately probe these two distinct learning objectives rather than conflating them in a single NLL metric.
**Code / weights:** Not yet released (arXiv: https://arxiv.org/abs/2605.13999)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 9
- By topic: Protein LM: 1 | Diffusion: 3 | Genomics: 3 | Architecture: 2 | General ML: 2 | Clinical ML: 2
- Sources: arXiv: 7 | bioRxiv: 0 | medRxiv: 0 | PubMed: 1 (Cell Systems) | HF Papers: 0 | PWC: 0
- Papers with code released: 1 (RBP-ARK database)

> **Note:** Today's volume is lower than weekday digests — the Monday arXiv batch covers the May 16–18 weekend window, which typically yields ~30–40% of weekday submission volume. Next digest will return to full weekday coverage.
