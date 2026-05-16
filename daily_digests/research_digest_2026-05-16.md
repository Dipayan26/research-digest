# Research Digest — 2026-05-16

> **Coverage window:** arXiv submissions ~May 9–16 2026 (IDs 2605.01513 – 2605.15193); bioRxiv/HF Papers checked through May 15–16. Papers from today's arXiv new-submissions listing (posted afternoon UTC) are included where available.

---
TITLE: VibeProteinBench: An Evaluation Benchmark for Language-interfaced Vibe Protein Design
AUTHORS: Hyunjin Seo et al.
SOURCE: arXiv / HF Papers | 2605.10978 | [**Link**](https://arxiv.org/abs/2605.10978)
TOPIC TAG: Protein LM
TLDR: VibeProteinBench introduces a three-stage (recognition → engineering → generation) benchmark with expert-curated mechanistic rationales and multi-faceted in silico validation to evaluate LLMs on open-ended, natural-language-constrained protein design tasks.
WHY IT MATTERS: Existing protein design benchmarks either cover narrow tasks or use rigid structured input schemas; VibeProteinBench is the first to evaluate generalist protein design competence across an entire computational design workflow driven by flexible natural-language intents. Evaluation of a broad suite of general-purpose and domain-specialized LLMs reveals that no current model achieves strong performance across all three stages, establishing a clear open challenge for the field.
CODE: Not released

---

---
TITLE: RNA-FM: Flow-Matching Generative Model for Genome-wide RNA-Seq Prediction
AUTHORS: Yaxuan Song et al.
SOURCE: arXiv | 2605.11622 | [**Link**](https://arxiv.org/abs/2605.11622)
TOPIC TAG: Flow Matching / Genomics
TLDR: RNA-FM uses continuous-time conditional flow matching to predict genome-wide bulk RNA-seq profiles directly from histopathology whole-slide images, framing transcriptomic prediction as a probabilistic transport problem rather than deterministic regression.
WHY IT MATTERS: Deterministic WSI-to-transcriptome regression models capture only a point estimate and miss biological heterogeneity; by learning a velocity field that maps a simple prior to the target gene expression distribution conditioned on tissue morphology, RNA-FM captures the full distribution of plausible transcriptomic states. This creates a route to cost-effective virtual transcriptomics from routine clinical pathology slides, with direct implications for spatial omics and precision oncology.
CODE: Not released

---

---
TITLE: Deep Learning for Protein Complex Prediction and Design
AUTHORS: Ziwei Xie et al.
SOURCE: arXiv | 2605.11189 | [**Link**](https://arxiv.org/abs/2605.11189)
TOPIC TAG: Protein LM
TLDR: RedNet, a multiscale graph transformer integrating backbone geometry and side-chain information with a contrastive decoding algorithm, achieves fixed-backbone protein binder design optimized jointly for binding affinity and target specificity.
WHY IT MATTERS: Most binder design pipelines treat structural context and sequence design as separate steps; RedNet's multiscale graph representation directly encodes hierarchical structural context for sequence generation, improving specificity through a contrastive objective that explicitly penalizes off-target sequences. The work also advances multi-chain complex structure prediction by searching for interacting homologs from coevolutionary signals, bridging design and prediction in a single framework.
CODE: Not released

---

---
TITLE: BEAM: Binary Expert Activation Masking for Dynamic Routing in MoE
AUTHORS: Juntong Wu et al.
SOURCE: arXiv / HF Papers | 2605.14438 | [**Link**](https://arxiv.org/abs/2605.14438)
TOPIC TAG: MoE
TLDR: BEAM learns token-adaptive binary expert selection via trainable binary masks with straight-through estimation, reducing MoE-layer FLOPs by up to 85% while retaining >98% of model performance and achieving 2.5× faster decoding with 1.4× higher throughput.
WHY IT MATTERS: Standard fixed top-K routing wastes compute on trivial tokens; BEAM's dynamically learned sparsity is end-to-end differentiable and plug-and-play via a custom CUDA kernel integrated with vLLM, requiring no architectural redesign. This approach is directly applicable to large MoE biological language models (protein, DNA, RNA) that must be served under tight inference-cost budgets.
CODE: Not released

---

---
TITLE: Aligning Latent Geometry for Spherical Flow Matching in Image Generation
AUTHORS: Tuna Han Salih Meral et al.
SOURCE: arXiv / HF Papers | 2605.15193 | [**Link**](https://arxiv.org/abs/2605.15193)
TOPIC TAG: Flow Matching / Architecture
TLDR: By decomposing latent tokens into radial and angular components and replacing linear interpolation with spherical linear interpolation (SLERP), this method constrains flow paths to the data manifold's spherical shells throughout denoising, consistently improving FID on class-conditional ImageNet-256 without changing the diffusion architecture.
WHY IT MATTERS: Standard flow matching assumes linear paths in latent space, but both encoder outputs and prior samples concentrate on thin spherical shells, so linear chords leave the manifold and introduce unnecessary curvature in the velocity field — a problem equally present in protein structure and molecular latent spaces. The spherical projection framework is architecture-agnostic and could directly improve flow-matching generative models for protein backbone, RNA, or small-molecule generation.
CODE: Not released (project page: https://aligning-latent-geometry.github.io)

---

---
TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: Siddhant Dutta et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: SoftBlobGIN projects ESM-2 representations onto protein contact graphs and applies differentiable Gumbel-softmax substructure pooling to identify coarse functional modules, achieving 92.8% accuracy / 0.898 macro-F1 on enzyme classification while recovering biologically meaningful active-site residues via GNNExplainer.
WHY IT MATTERS: Protein language models encode structural and evolutionary signals implicitly in dense latent spaces that resist standard attribution methods; this plug-and-play framework provides auditable, structure-aware explanations without requiring protein structure as an explicit input. The ability to spatially localize catalytic residues and contact patterns from sequence-only embeddings has direct value for functional annotation and rational mutation design.
CODE: Not released

---

---
TITLE: GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
AUTHORS: Michael Lindsey et al.
SOURCE: arXiv | 2605.07608 | [**Link**](https://arxiv.org/abs/2605.07608)
TOPIC TAG: Genomics
TLDR: GoForth is a forward-trained RNA language model that handles structure, sequence-fixity, and protein-coding constraints as a unified compositional condition language, enabling fast high-quality candidate generation for mixed RNA design specifications without thermodynamic oracle calls during training.
WHY IT MATTERS: Prior RNA inverse folding models treat target structure as the sole design constraint; GoForth unifies fold targets, fixed-base requirements, and open-reading-frame constraints in a single generative framework trained on structure-masked sequence-condition pairs. The learned task embeddings also provide a model-free and robust measure of RNA designability, useful for filtering unfeasible design specifications before expensive wet-lab validation.
CODE: Not released

---

---
TITLE: Flow Matching for Count Data
AUTHORS: (arXiv 2605.07746 authors)
SOURCE: arXiv | 2605.07746 | [**Link**](https://arxiv.org/abs/2605.07746)
TOPIC TAG: Flow Matching / Genomics
TLDR: count-FM introduces a continuous-time flow matching framework native to discrete count data via a birth-death process with local unit jumps, enabling simulation-free training of conditional transition rates for high-dimensional count distributions such as single-cell RNA-seq.
WHY IT MATTERS: Single-cell RNA-seq data is inherently count-valued; treating each count as a categorical token explodes the state space while continuous approximations distort the data geometry, but count-FM solves this by operating in the natural count space. This provides a mathematically principled generative foundation for distribution transport between cell populations across batches, time points, or perturbation conditions — a core task in trajectory and perturbation modeling.
CODE: Not released

---

---
TITLE: Better Protein Function Prediction by Modeling Survivorship Bias
AUTHORS: (arXiv 2605.06879 authors)
SOURCE: arXiv | 2605.06879 | [**Link**](https://arxiv.org/abs/2605.06879)
TOPIC TAG: Protein LM / General ML
TLDR: Evo-PU integrates the nucleotide mutation model into a positive-unlabeled (PU) learning framework to distinguish non-functional protein sequences from those simply never observed, outperforming standard PU learning, one-class classification, and protein language models on viral fitness and SARS-CoV-2 variant emergence prediction.
WHY IT MATTERS: Sequence databases exhibit systematic survivorship bias because only functional, heritable sequences are observed — a fact ignored by methods that treat all unlabeled sequences as equally missing. By encoding the evolutionary likelihood that a sequence would have been sampled if functional, Evo-PU provides a principled mechanistic prior that significantly improves fitness prediction from single-organism uniform-coverage surveillance data.
CODE: Not released

---

---
TITLE: Long Context Pre-Training with Lighthouse Attention
AUTHORS: Bowen Peng, Subho Ghosh, Jeffrey Quesnelle
SOURCE: arXiv / HF Papers | 2605.06554 | [**Link**](https://arxiv.org/abs/2605.06554)
TOPIC TAG: Architecture
TLDR: Lighthouse Attention is a training-only symmetrical hierarchical attention algorithm that wraps standard SDPA with gradient-free adaptive compression/decompression, achieving faster pre-training with lower final loss; a short recovery phase at the end restores a full-attention model.
WHY IT MATTERS: Quadratic attention is a key bottleneck for training long-context genomic and protein language models on chromosomes or large protein databases; Lighthouse's "train fast, recover full attention" strategy decouples training efficiency from inference fidelity without any permanent architectural changes. The gradient-free selection avoids the complex and potentially unstable backward kernels that plague other learnable sparse attention variants.
CODE: [**Code**](https://github.com/ighoshsubho/lighthouse-attention)

---

---
TITLE: ProtDBench: A Unified Benchmark of Protein Binder Design and Evaluation
AUTHORS: Cong Liu et al.
SOURCE: arXiv | 2605.04118 | [**Link**](https://arxiv.org/abs/2605.04118)
TOPIC TAG: Protein LM
TLDR: ProtDBench standardizes protein binder design evaluation across ten diverse protein targets with fixed protocols and introduces throughput-aware metrics under a 24-hour compute budget, revealing substantial verifier-dependent bias in structural assessors such as AlphaFold2 and ESMFold.
WHY IT MATTERS: Inconsistent evaluation protocols — particularly the choice of structural verifier — have made comparison of protein binder design methods largely uninformative; ProtDBench's systematic analysis demonstrates that success-rate rankings shift dramatically depending on the verifier, a fundamental reproducibility problem across the field. Cluster-level success criteria additionally reward structural diversity among top hits, countering methods that simply generate many redundant decoys of the same high-scoring pose.
CODE: Not released

---

---
TITLE: ProMORNA: Protein-Conditioned Multi-Objective Reinforcement Learning for Full-Length mRNA Design
AUTHORS: (arXiv 2605.01513 authors)
SOURCE: arXiv | 2605.01513 | [**Link**](https://arxiv.org/abs/2605.01513)
TOPIC TAG: Genomics / General ML
TLDR: ProMORNA uses a BART encoder-decoder conditioned on the target protein sequence with Multi-Objective Group Relative Policy Optimization (MO-GRPO) to jointly design full-length mRNA (5′UTR + CDS + 3′UTR) optimized for translation efficiency, half-life, structural stability, and U-content.
WHY IT MATTERS: Prior mRNA optimization methods either tune coding sequences only or require a wild-type mRNA template; ProMORNA generates complete de novo transcripts from protein alone, trained on >6 million natural protein–mRNA pairs for broad generalization. MO-GRPO avoids instability from aggregating metrics with different scales and variances by normalizing relative advantages at the level of individual biological objectives, a principled solution to multi-objective RL for biology.
CODE: Not released

---

---
TITLE: FEST: Few-Shot Demonstration-Guided RLVR
AUTHORS: Kai Yan, Alexander G. Schwing, Yu-Xiong Wang
SOURCE: arXiv / HF Papers | 2605.15012 | [**Link**](https://arxiv.org/abs/2605.15012)
TOPIC TAG: General ML
TLDR: FEST uses just 128 randomly selected SFT demonstrations within a reinforcement learning with verifiable rewards (RLVR) framework, combining supervised signal, on-policy RL, and decaying SFT weights to match full-dataset baseline performance at 0.05% of the demonstration cost.
WHY IT MATTERS: In scientific domains — protein engineering, genomic variant interpretation — curated, reward-verified training examples are scarce and expensive to produce; FEST demonstrates that effective RL fine-tuning requires far fewer demonstrations than conventional SFT-then-RL pipelines assume. The decaying weight schedule prevents overfitting to the few-shot batch during multi-epoch training, a practical consideration for any guided RL pipeline applied to low-data biological tasks.
CODE: [**Code**](https://github.com/KaiYan289/FEST)

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. RNA-FM: Flow-Matching Generative Model for Genome-wide RNA-Seq Prediction
**Why it's the highlight:** RNA-FM reframes the WSI-to-transcriptome task as a continuous-time conditional transport problem, replacing deterministic regression with a generative model that learns the full distribution of genome-wide expression profiles conditioned on tissue morphology. This is methodologically novel — it is the first application of flow matching to genome-wide transcriptome prediction from pathology images — and practically impactful, since it could enable virtual transcriptomics at scale without expensive RNA sequencing. The approach's probabilistic nature directly addresses the biological reality that tissue heterogeneity produces a distribution of transcriptomic states, not a single vector.
**Code / weights:** Not released (arXiv: https://arxiv.org/abs/2605.11622)

---

### 2. VibeProteinBench: An Evaluation Benchmark for Language-interfaced Vibe Protein Design
**Why it's the highlight:** VibeProteinBench is the most comprehensive protein design benchmark to date in the language-interfaced paradigm, covering recognition, engineering, and generation in a single integrated evaluation driven by natural-language intents. Its expert-curated mechanistic rationales and multi-faceted in silico validation make it substantially more rigorous than prior benchmarks, and its key finding — that no current LLM generalizes across all three design stages — defines the state-of-the-field for language-model-driven protein design in 2026. The benchmark will likely serve as the standard evaluation framework for a new generation of protein design agents.
**Code / weights:** Not released (arXiv: https://arxiv.org/abs/2605.10978)

---

### 3. Flow Matching for Count Data (count-FM)
**Why it's the highlight:** count-FM is a foundational methodological contribution: a mathematically natural flow matching framework for discrete count data via a birth-death process that avoids both the state-space explosion of categorical treatment and the geometric distortion of continuous approximations. For computational biology, this directly addresses one of the most common data types — single-cell RNA-seq UMI counts, ChIP-seq read counts, protein abundance values — opening a rigorous generative modeling path for batch transport, perturbation modeling, and trajectory inference that was previously unavailable. The simulation-free training of conditional transition rates makes it scalable to high-dimensional genomic count data.
**Code / weights:** Not released (arXiv: https://arxiv.org/abs/2605.07746)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 13
- By topic: Protein LM: 5 | Flow Matching: 3 | Genomics: 3 | Architecture: 2 | MoE: 1 | General ML: 2 | Clinical: 0
- Sources: arXiv: 13 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 5 (cross-listed) | PWC: 0
- Papers with code released: 2 (Lighthouse Attention, FEST)
