# Research Digest — 2026-05-17

> **Coverage window:** arXiv submissions through May 17 2026 (catch-up on IDs 2605.02745 – 2605.13932 not covered in the May 16 digest, plus the May 16–17 new-submissions window); PubMed/Cell checked for high-impact publications posted in the last 24 h. Weekend submissions have lower volume; today's digest emphasises depth over breadth.

---
TITLE: A-CODE: Fully Atomic Protein Co-Design with Unified Multimodal Diffusion
AUTHORS: Cheng Shi et al.
SOURCE: arXiv | 2605.03360 | [**Link**](https://arxiv.org/abs/2605.03360)
TOPIC TAG: Diffusion / Protein LM
TLDR: A-CODE is the first fully atomic one-stage protein co-design model, simultaneously denoising discrete atom types (mask diffusion) and continuous atom coordinates (Gaussian diffusion) in a unified multimodal diffusion process — residue identities are inferred solely from atom-level predictions rather than from a separate sequence decoder.
WHY IT MATTERS: All dominant binder design pipelines are two-stage: first design backbone, then decode sequence; A-CODE collapses this into a single denoising pass over atoms, enabling finer residue-level cross-modal coupling that yields state-of-the-art unconditional protein generation and a tenfold improvement in success rate on hard binder design tasks versus the best existing one-stage method. Critically, A-CODE's atomic formulation naturally extends to non-canonical amino acid (ncAA) modeling for the first time, opening a route to therapeutic peptide and chemically modified protein design.
CODE: Not released

---

---
TITLE: Yeti: A Compact Protein Structure Tokenizer for Reconstruction and Multi-modal Generation
AUTHORS: Nabin Giri, Steven Farrell, Kristofer E. Bouchard
SOURCE: arXiv | 2605.09981 | [**Link**](https://arxiv.org/abs/2605.09981)
TOPIC TAG: Architecture / Protein LM
TLDR: Yeti is a lightweight VQ-VAE-style protein structure tokenizer that achieves the best codebook utilization and token diversity among comparable methods with 10× fewer parameters than ESM3, and a compact multimodal model trained from scratch on Yeti tokens jointly with amino acid sequences produces designable protein sequence–structure pairs on par with models 10× larger.
WHY IT MATTERS: Discretizing protein structure into tokens is the bottleneck for scaling multimodal protein models — an expressive but inefficient codebook wastes model capacity and harms generation diversity. Yeti's efficiency unlocks training of sequence–structure co-generation models at modest compute budgets, and its benchmark reveals that models in the literature overestimate codebook utilization because they ignore token collapse, a reproducibility issue for the whole tokenizer subfield.
CODE: Not released

---

---
TITLE: OmicsLM: A Multimodal Large Language Model for Multi-Sample Omics Reasoning
AUTHORS: (arXiv 2605.06728 authors)
SOURCE: arXiv | 2605.06728 | [**Link**](https://arxiv.org/abs/2605.06728)
TOPIC TAG: Architecture / Genomics
TLDR: OmicsLM aligns continuous transcriptomic embeddings with a large language model via explicit gene tokenization, trained on >5.5 million instruction-following examples spanning 70+ task types, enabling natural-language queries over multiple interleaved RNA-seq profiles in a single context window.
WHY IT MATTERS: Prior omics foundation models operate on fixed task schemas and cannot reason linguistically over expression data; OmicsLM is the first model that jointly handles quantitative omics signals, gene symbol mentions, and free-text biological knowledge in one prompt, outperforming both omics-specialized models and general LLMs on language-guided tasks. The authors also release GEO-OmicsQA, a large-scale QA dataset grounded in real transcriptomic profiles from GEO, providing the first contamination-controlled benchmark for evaluating LLM reasoning over expression data.
CODE: Not released

---

---
TITLE: ProtSent: Protein Sentence Transformers
AUTHORS: Dan Ofer, Oriel Perets, Michal Linial, Nadav Rappoport
SOURCE: arXiv | 2605.06830 | [**Link**](https://arxiv.org/abs/2605.06830)
TOPIC TAG: Protein LM
TLDR: ProtSent applies contrastive fine-tuning with MultipleNegativesRankingLoss over five protein-pair datasets (Pfam families, structural hard negatives, AlphaFold DB pairs, STRING PPIs, DMS data) to convert PLMs into general-purpose embedding models, improving 15/23 downstream tasks for ESM-2 150M with gains of +105% on remote homology and +19.9% Recall@1 on structural retrieval.
WHY IT MATTERS: Standard PLMs are pretrained with per-residue masked language modeling, so their mean-pooled sequence embeddings are not aligned to functional or structural similarity — a mismatch that limits retrieval and few-shot classification. ProtSent's multi-source contrastive curriculum systematically closes this gap by exposing the model to pairs defined by family, structure, interaction, and fitness simultaneously, providing a drop-in embedding improvement for any downstream task that consumes fixed-length protein representations.
CODE: Not released

---

---
TITLE: FlashMol: High-Quality Molecule Generation in as Few as Four Steps
AUTHORS: (arXiv 2605.07020 authors)
SOURCE: arXiv | 2605.07020 | [**Link**](https://arxiv.org/abs/2605.07020)
TOPIC TAG: Diffusion
TLDR: FlashMol adapts distribution matching distillation (DMD) — a reverse-KL minimization objective — to distill a 1000-step 3D molecular conformation diffusion teacher into a 4-step student, achieving up to 250× inference speedup while matching or exceeding teacher quality on QM9 and GEOM-DRUG benchmarks.
WHY IT MATTERS: Classical diffusion-based 3D molecule generation requires hundreds of score evaluations per sample, making large-scale virtual screening computationally prohibitive; FlashMol is the first demonstration that distribution matching distillation transfers effectively to the molecular domain, retaining both structural validity and sample stability that prior few-step methods (12–50 steps) sacrifice. At 250× speedup, FlashMol makes diffusion-quality 3D conformer generation competitive with rule-based tools for high-throughput screening pipelines.
CODE: Not released

---

---
TITLE: ToolMol: Evolutionary Agentic Framework for Multi-objective Drug Discovery
AUTHORS: (arXiv 2605.12784 authors)
SOURCE: arXiv | 2605.12784 | [**Link**](https://arxiv.org/abs/2605.12784)
TOPIC TAG: General ML
TLDR: ToolMol combines a multi-objective genetic algorithm with an agentic LLM operator that proposes, critiques, and applies structure-editing mutations to evolve ligand populations toward Pareto-efficient trade-offs across binding affinity, drug-likeness, and synthesizability simultaneously.
WHY IT MATTERS: Existing generative drug discovery models either optimize one property at a time or require differentiable surrogates that struggle with non-convex multi-objective landscapes; ToolMol's evolutionary loop treats the LLM as a chemistry-aware mutation operator that reasons about structure–activity relationships in natural language, achieving >10% stronger predicted binding affinity than state-of-the-art baselines while maintaining synthesizability. The agent-in-the-loop design enables seamless incorporation of any oracle — including wet-lab assay results — making the framework adaptable to active learning campaigns.
CODE: Not released

---

---
TITLE: PPI-Net: Connecting Molecular Protein Interactions to Functional Processes in Disease
AUTHORS: (arXiv 2605.07838 authors)
SOURCE: arXiv | 2605.07838 | [**Link**](https://arxiv.org/abs/2605.07838)
TOPIC TAG: Protein LM / Clinical ML
TLDR: PPI-Net is a hierarchical graph attention network that embeds patient-specific molecular profiles within a STRING protein–protein interaction network and propagates representations through a multi-layer Reactome pathway hierarchy, linking individual protein perturbations to pathway-level disease phenotypes in a single end-to-end model.
WHY IT MATTERS: Most disease ML models treat omics features as independent or learn flat gene–phenotype associations, losing the network-level context that determines downstream biological consequences; PPI-Net's dual-hierarchy design explicitly encodes both physical protein interactions and functional pathway membership, enabling mechanistic interpretability by attributing predictions to individual pathway subtrees. The biological hierarchy acts as a strong structural prior that improves generalization across tissue types and disease contexts relative to flat graph models.
CODE: Not released

---

---
TITLE: SPADE: Faster Drug Discovery by Learning from Sparse Data
AUTHORS: Rahul Nandakumar, Ben Fauber, Deepayan Chakrabarti
SOURCE: arXiv | 2605.05370 | [**Link**](https://arxiv.org/abs/2605.05370)
TOPIC TAG: General ML / Clinical ML
TLDR: SPADE replaces global affinity regression with a targeted classification objective and injects robustness via an expected-loss regularizer over distributions centered at each positive ligand, finding 10 high-quality ligands in ~40 assay tests — 7–32% more sample-efficient than deep learning and Bayesian optimization baselines — while running 3–4 orders of magnitude faster.
WHY IT MATTERS: Early-stage drug campaigns typically have fewer than a dozen confirmed actives; SPADE's positive-unlabeled formulation with a local distributional regularizer is specifically designed for this extreme data sparsity regime, rather than assuming the large labeled sets that deep learning models implicitly require. The drastic speed advantage (milliseconds vs. seconds per candidate) makes SPADE practical for real-time active experimental design during high-throughput screening cycles.
CODE: Not released

---

---
TITLE: Rethinking Molecular OOD Generalization via Target-Aware Source Selection
AUTHORS: (arXiv 2605.13932 authors)
SOURCE: arXiv | 2605.13932 | [**Link**](https://arxiv.org/abs/2605.13932)
TOPIC TAG: General ML
TLDR: Rather than assuming all training scaffolds are equally informative under distribution shift, this work proposes target-aware source selection — identifying training molecules most structurally and chemically proximal to a target scaffold family — showing that selective training sets substantially improve out-of-distribution molecular property prediction in AI-driven drug discovery.
WHY IT MATTERS: AI drug discovery models routinely fail in real campaigns because they are evaluated in-distribution while deployed on novel chemotypes; existing domain adaptation approaches require labeled target-domain data. Target-aware source selection is data-free at test time and provides a principled recipe for constructing training corpora that generalize, addressing a fundamental bottleneck in deploying ML models to realistic lead-optimization scenarios.
CODE: Not released

---

---
TITLE: Deep-Learning-Based De Novo Discovery and Design of Therapeutics That Reverse Disease-Associated Transcriptional Phenotypes
AUTHORS: (Cell 2026 authors)
SOURCE: PubMed / Cell | 10.1016/j.cell.2026.02.016 | [**Link**](https://www.cell.com/cell/fulltext/S0092-8674(26)00223-0)
TOPIC TAG: Clinical ML / Genomics
TLDR: GPS (Gene expression Profile predictor on chemical Structures) is a deep learning platform that predicts compound-induced transcriptional perturbation signatures directly from chemical structures, then uses tree-search optimization to design de novo molecules that reverse disease-specific gene expression programs — validated in hepatocellular carcinoma (two novel series with in vivo efficacy) and idiopathic pulmonary fibrosis (one novel anti-fibrotic compound).
WHY IT MATTERS: Classical transcriptomics-guided drug discovery (CMap/LINCS) requires measured perturbation profiles and can only repurpose existing compounds; GPS generalizes phenotypic reversal to structurally novel molecules by learning structure-to-transcriptome mappings end-to-end, enabling de novo design rather than screening. In vivo validation across two distinct disease contexts — one oncological and one fibrotic — with single-cell transcriptomic multi-cell-type reversal demonstrates that GPS-designed molecules translate beyond in silico benchmarks to preclinical relevance.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. A-CODE: Fully Atomic Protein Co-Design with Unified Multimodal Diffusion
**Why this is the highlight:** A-CODE is the first one-stage protein co-design model to operate at full atomic resolution, eliminating the artificial two-stage pipeline (backbone → sequence) that dominates protein design. By jointly denoising atom types and coordinates in a unified diffusion process, A-CODE achieves tenfold improvement in success rate on hard binder tasks and, for the first time, extends generative protein design to non-canonical amino acids — a prerequisite for designing therapeutically relevant stapled peptides, bicyclics, and chemically modified biologics. This is a genuine paradigm shift in how the community frames protein co-design.
**Code / weights:** Not yet released (arXiv: https://arxiv.org/abs/2605.03360)

---

### 2. GPS: De Novo Therapeutic Design via Transcriptional Phenotype Reversal (Cell 2026)
**Why this is the highlight:** GPS closes the loop between transcriptomics and de novo drug design by learning to predict genome-wide perturbation signatures from chemical structure, then using tree-search optimization to construct novel molecules that maximally reverse disease gene programs. The approach leaps beyond CMap-style repurposing by designing entirely new chemical matter — and validates it in vivo in hepatocellular carcinoma and idiopathic pulmonary fibrosis. Publishing in Cell with preclinical validation across two diseases marks this as one of the most complete demonstrations of end-to-end AI-driven drug discovery to date.
**Code / weights:** Not released (DOI: https://doi.org/10.1016/j.cell.2026.02.016)

---

### 3. OmicsLM: Multimodal LLM for Multi-Sample Omics Reasoning
**Why this is the highlight:** OmicsLM represents a new paradigm for computational biology infrastructure: instead of training task-specific omics models, it aligns continuous transcriptomic embeddings with an LLM, enabling natural-language reasoning over gene expression data across multiple samples in a single context. Trained on 5.5M instruction-following examples spanning 70+ task types and benchmarked on the new GEO-OmicsQA dataset, OmicsLM outperforms both omics specialists and general LLMs on language-guided biological reasoning. This is the clearest demonstration yet that the generalist LLM paradigm can absorb quantitative molecular biology data without sacrificing the precision of specialized tools.
**Code / weights:** Not released (arXiv: https://arxiv.org/abs/2605.06728)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 10
- By topic: Protein LM: 3 | Diffusion: 2 | Genomics: 2 | Architecture: 2 | General ML: 3 | Clinical ML: 3
- Sources: arXiv: 9 | bioRxiv: 0 | medRxiv: 0 | PubMed: 1 (Cell) | HF Papers: 0 | PWC: 0
- Papers with code released: 0
