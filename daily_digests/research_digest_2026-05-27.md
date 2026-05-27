# Research Digest — 2026-05-27

> Auto-generated daily digest covering ML × computational biology.
> Sources: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.GN, q-bio.QM, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, HF Papers, Semantic Scholar, Papers With Code.

---

## Papers

---

TITLE: Moirain: Multimodal Alignment and Preference Optimization for Zero-Shot Conditional RNA Generation
AUTHORS: (Authors from arXiv:2605.23961) et al.
SOURCE: arXiv | 2605.23961 | [**Link**](https://arxiv.org/abs/2605.23961)
TOPIC TAG: Diffusion / General ML
TLDR: Built Moirain, a suite of models (Base, Multi, DPO) that conditions RNA sequence generation on protein structural and sequential features via multimodal SFT + DPO alignment, achieving superior binding affinity and biological plausibility over baselines in zero-shot settings.
WHY IT MATTERS: Most RNA generation methods are unconditional; tying RNA synthesis directly to a protein target via preference optimization is a step toward true inverse-design of RNA aptamers and therapeutics. The DPO refinement with synthetic interaction data avoids collapsing the natural RNA distribution while improving functional fitness — a clean alignment recipe applicable beyond RNA.
CODE: Not released

---

TITLE: AgForce Enables Antigen-conditioned Generative Antibody Design
AUTHORS: (Authors from arXiv:2605.21610) et al.
SOURCE: arXiv | 2605.21610 | [**Link**](https://arxiv.org/abs/2605.21610)
TOPIC TAG: Protein LM
TLDR: Proposed AgForce, an encoder-decoder architecture with a GNN encoder and specialized co-design decoder that solves antigen-conditioned CDR sequence-structure co-design by diagnosing and fixing vocabulary collapse caused by standard cross-entropy training.
WHY IT MATTERS: Prior CDR design models were shown to ignore the antigen input entirely, converging to positional marginal distributions — a fundamental failure mode in antigen-specific antibody design. AgForce directly addresses this by diagnosing the collapse mechanism, making it one of the first methods to reliably generate antigen-specific CDR sequences.
CODE: Not released

---

TITLE: Protein Thoughts: Interpretable Reasoning with Tree of Thoughts and Embedding-Space Flow Matching for Protein-Protein Interaction Discovery
AUTHORS: Kingsley Yeon, Xuefeng Liu, Promit Ghosal et al.
SOURCE: arXiv | 2605.21522 | [**Link**](https://arxiv.org/abs/2605.21522)
TOPIC TAG: Flow Matching / Protein LM
TLDR: Reformulated PPI discovery as an interpretable Tree-of-Thoughts search over four biological signals (sequence similarity, structural complementarity, interface balance, chemical compatibility), using hypothesis-conditioned embedding-space flow matching to transport candidate proteins toward the binder manifold.
WHY IT MATTERS: Standard PPI predictors are black boxes; decomposing binding evidence into explicit, biologically grounded hypotheses improves interpretability without sacrificing accuracy. The use of embedding-space flow matching for soft candidate refinement — rather than expensive structure-based docking — is a novel and efficient paradigm for hypothesis-driven interaction screening.
CODE: Not released

---

TITLE: StateXDiff: Cell State-Contextualized Multimodal Diffusion for Single-Cell Perturbation Prediction
AUTHORS: Peiting Shi, Ningfeng Que, Xianzhe Huang, Xiaofei Wang, Jianzhong Jeff Xi et al.
SOURCE: arXiv | 2605.16104 | [**Link**](https://arxiv.org/abs/2605.16104)
TOPIC TAG: Diffusion / Genomics
TLDR: Developed StateXDiff, which first learns a disentangled multimodal cellular state representation integrating transcriptomics with inferred protein features, then uses a conditional diffusion model to generate perturbation-specific transcriptomic changes at single-cell resolution under OOD conditions.
WHY IT MATTERS: Predicting drug perturbation responses at single-cell resolution for unseen drugs is a major challenge; the two-stage disentanglement + diffusion approach explicitly models heterogeneous cell states, preventing spurious correlations that plague simpler RNA-only methods. This extends the CPA/GEARS paradigm toward multi-modal, diffusion-based perturbation modeling.
CODE: Not released

---

TITLE: Yeti: A Compact Protein Structure Tokenizer for Reconstruction and Multi-Modal Generation
AUTHORS: (Authors from arXiv:2605.09981) et al.
SOURCE: arXiv | 2605.09981 | [**Link**](https://arxiv.org/abs/2605.09981)
TOPIC TAG: Flow Matching / Protein LM / Architecture
TLDR: Introduced Yeti, a protein structure tokenizer trained end-to-end with a flow matching reconstruction objective and lookup-free quantization, achieving best codebook utilization and token diversity with 10× fewer parameters than ESM3, while enabling comparable unconditional sequence-structure co-generation.
WHY IT MATTERS: Structure tokenization is a critical bottleneck for multimodal protein language models — existing tokenizers either lose fine-grained geometric information or are oversized. Yeti's flow-matching-based training provides continuous geometric supervision during tokenizer learning, yielding a compact, information-dense discrete vocabulary ideal for downstream generative modeling.
CODE: Not released

---

TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: (Authors from arXiv:2605.10985) et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: Proposed a framework that projects ESM-2 residue representations onto protein contact graphs and applies SoftBlobGIN — a Graph Isomorphism Network with differentiable substructure pooling — to perform structure-aware message passing and learn functional substructures for downstream prediction.
WHY IT MATTERS: Despite impressive performance, protein language models are largely uninterpretable structurally; this work bridges the gap by grounding latent representations in graph-theoretic structural motifs through a differentiable partitioning step. The result is a new mechanistic handle on why pLM representations correlate with function.
CODE: Not released

---

TITLE: Learning the Interaction Prior for Protein-Protein Interaction Prediction: A Model-Agnostic Approach (L3-PPI)
AUTHORS: Ziqi Gao, Chenyi Zi, Zijing Liu, Ziqiao Meng, Yu Li, Jia Li et al.
SOURCE: arXiv | 2605.09964 | [**Link**](https://arxiv.org/abs/2605.09964)
TOPIC TAG: Protein LM / General ML
TLDR: Designed L3-PPI, a biologically informed PPI classifier motivated by the L3 rule (multiple length-3 graph paths indicate interaction), using L3-path-regularized graph prompt learning that generates a virtual prompt graph with controlled L3 paths atop any protein representation.
WHY IT MATTERS: Existing PPI methods focus entirely on representation quality while using naive aggregation (concatenation/dot product) in the classifier head — ignoring known biological priors. Showing that standard datasets strongly support the L3 rule and encoding it as an inductive bias is a principled, model-agnostic improvement applicable to any backbone PLM.
CODE: Not released

---

TITLE: Deep Learning for Protein Complex Prediction and Design
AUTHORS: Ziwei Xie et al.
SOURCE: arXiv | 2605.11189 | [**Link**](https://arxiv.org/abs/2605.11189)
TOPIC TAG: Protein LM / Architecture
TLDR: Comprehensive survey covering deep learning architectures for protein complex structure prediction and sequence design, cataloguing domain-specific architectural choices, search algorithms for sequence space navigation, and evaluation benchmarks for multi-chain complexes.
WHY IT MATTERS: Complex prediction has outpaced synthesis of knowledge; this survey provides a unified view of how hierarchical and co-evolutionary information flows through modern models (AlphaFold-Multimer, RoseTTAFold-All-Atom, etc.), useful for researchers entering the multi-chain modeling space. The analysis of design-specific challenges (interface designability, symmetry) is particularly timely.
CODE: Not released

---

TITLE: When Molecular Similarity Works: Property Cliffs Reveal Hidden Errors in Molecular Property Prediction
AUTHORS: (Authors from arXiv:2605.17265) et al.
SOURCE: arXiv | 2605.17265 | [**Link**](https://arxiv.org/abs/2605.17265)
TOPIC TAG: Clinical ML / General ML
TLDR: Systematically demonstrated that state-of-the-art molecular property prediction models fail specifically at property cliffs — pairs of structurally similar molecules with sharply different target properties — identifying these as underexplored failure modes for drug discovery.
WHY IT MATTERS: High accuracy on benchmarks masks localized catastrophic failures near activity cliffs, which are precisely the cases most relevant to lead optimization in drug discovery. Characterizing when and why similarity-based generalization breaks down provides a new diagnostic lens for evaluating ML models deployed in medicinal chemistry.
CODE: Not released

---

TITLE: ReCoG: Relational and Compact Context Graph Learning for Few-Shot Molecular Property Prediction
AUTHORS: (Authors from arXiv:2605.13024) et al.
SOURCE: arXiv | 2605.13024 | [**Link**](https://arxiv.org/abs/2605.13024)
TOPIC TAG: Clinical ML / General ML
TLDR: Proposed ReCoG, a few-shot molecular property prediction framework that constructs relational context graphs over support molecules to extract compact task-relevant representations, outperforming prior FSMPP methods on standard benchmarks under extreme label scarcity.
WHY IT MATTERS: Labeled molecular data is expensive; few-shot methods that generalize across assays are crucial for practical drug discovery. The relational graph induction step explicitly models inter-support-set structure (scaffold similarity, pharmacophore overlap) rather than treating each molecule independently, leading to better task-level representations.
CODE: Not released

---

TITLE: Structured-Sparse Attention for Entity Tracking with Subquadratic Sequence Complexity
AUTHORS: (Authors from arXiv:2605.22476) et al.
SOURCE: arXiv | 2605.22476 | [**Link**](https://arxiv.org/abs/2605.22476)
TOPIC TAG: Architecture
TLDR: Introduced a structured-sparse attention operator for entity tracking tasks where task-specific attention compresses deep Transformer stacks, achieving O(n^{4/3}d) subquadratic complexity while maintaining accuracy on long-sequence entity state modeling.
WHY IT MATTERS: Long genomic and proteomic sequences demand sub-quadratic transformers; the entity-tracking framing maps naturally to tracking regulatory elements or protein domains along a sequence. The theoretical complexity bound with empirical validation provides a clean foundation for extending the architecture to biological long-context tasks.
CODE: Not released

---

TITLE: Advancing Regulatory Variant Effect Prediction with AlphaGenome
AUTHORS: Žiga Avsec, Natasha Latysheva, Jun Cheng et al. (DeepMind)
SOURCE: PubMed / Nature | DOI: 10.1038/s41586-026 | [**Link**](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12851941/)
TOPIC TAG: Genomics
TLDR: AlphaGenome takes 1 Mb of DNA sequence as input and simultaneously predicts thousands of functional genomic tracks (gene expression, chromatin accessibility, histone marks, splice usage, TF binding, chromatin contacts) at single-base-pair resolution, matching or exceeding the best specialized models in 25/26 variant effect prediction evaluations.
WHY IT MATTERS: Previous models faced a hard resolution-vs-context tradeoff (SpliceAI: high-res, short context; Enformer: long context, low-res); AlphaGenome resolves this dichotomy in a single unified model, enabling simultaneous modeling of fine-grained splicing and long-range enhancer-promoter interactions. This will likely become the reference model for non-coding variant interpretation in the same way AlphaFold2 transformed structure prediction.
CODE: [**Code/Weights**](https://github.com/google-deepmind/alphagenome)

---

TITLE: scooby: Modeling Multimodal Genomic Profiles from DNA Sequence at Single-Cell Resolution
AUTHORS: (Authors from Nature Methods 2025) et al.
SOURCE: PubMed / Nature Methods | [**Link**](https://www.nature.com/articles/s41592-025-02854-5)
TOPIC TAG: Genomics / Architecture
TLDR: Adapted the bulk multi-omics predictor Borzoi with a cell-specific decoder and fine-tuned sequence embeddings ("scooby") to simultaneously predict scRNA-seq coverage and scATAC-seq insertion profiles along the genome at single-cell resolution, correctly identifying lineage-specific regulators and cell-type-specific variant effects.
WHY IT MATTERS: Single-cell genomics lacks sequence-to-function models that preserve cellular heterogeneity; scooby bridges this gap by conditioning Borzoi's sequence tower on single-cell embedding coordinates, enabling genotype-to-phenotype inference at cell-level granularity. The cell-conditioned decoder design is directly extensible to other cell-type-specific prediction tasks.
CODE: [**Code**](https://github.com/gagneurlab/scooby)

---

TITLE: Variational Linear Attention: Stable Associative Memory for Long-Context Transformers
AUTHORS: (Authors from arXiv:2605.11196) et al.
SOURCE: arXiv | 2605.11196 | [**Link**](https://arxiv.org/abs/2605.11196)
TOPIC TAG: Architecture
TLDR: Proposed Variational Linear Attention (VLA), a sub-quadratic attention mechanism that models the memory state as a variational distribution to achieve stable associative recall over long contexts, eliminating the memory state explosion issues of existing linear attention variants.
WHY IT MATTERS: Linear attention and SSMs have struggled with stable long-range retention in genomic and proteomic sequence modeling; VLA's probabilistic memory state offers a principled Bayesian alternative that avoids catastrophic forgetting while remaining linear-time. This addresses one of the key practical failure modes of deploying sub-quadratic models on kilobase-to-megabase biological sequences.
CODE: Not released

---

==============================================================
## HIGHLIGHTS OF THE DAY
==============================================================

### 1. AlphaGenome — Unified DNA Sequence Model for Regulatory Variant Effect Prediction
**Why this is the highlight:** AlphaGenome from DeepMind is a landmark unified model that resolves the longstanding resolution-vs-context tradeoff in genomics: it accepts 1 Mb of DNA and predicts thousands of functional tracks (RNA-seq, ATAC-seq, histone marks, splice sites, chromatin contacts) simultaneously at single-base-pair resolution. Trained on human and mouse genomes, it matches or surpasses the best specialist models in 25 of 26 variant effect benchmarks, including rare variant effects on splicing and long-range enhancer regulation. This positions AlphaGenome as the computational genomics equivalent of AlphaFold2 — a foundation model that will likely anchor non-coding variant interpretation workflows for the foreseeable future.
**Code/Weights:** [GitHub](https://github.com/google-deepmind/alphagenome)

---

### 2. Moirain — DPO-Aligned Multimodal RNA Generation Conditioned on Protein Targets
**Why this is the highlight:** Moirain introduces the first multimodal alignment pipeline for conditional RNA design, framing RNA aptamer/therapeutic generation as a RLHF/DPO-style preference optimization problem conditioned on protein structure and sequence. The Moirain-DPO model uses synthetic protein-RNA interaction data to fine-tune a pretrained generative model via Direct Preference Optimization, producing novel, diverse, and biologically plausible RNA molecules with higher binding affinity without collapsing the natural sequence distribution. This is the first demonstration that DPO-style alignment — dominant in LLM post-training — can be cleanly applied to generate functional biological molecules, opening a new design paradigm for RNA therapeutics.
**Code/Weights:** Not released

---

### 3. AgForce — Diagnosing and Fixing Vocabulary Collapse in Antigen-Conditioned Antibody Design
**Why this is the highlight:** AgForce identifies a critical failure mode in generative antibody design — vocabulary collapse, where models trained with standard cross-entropy converge to positional marginals and effectively ignore the antigen input entirely. By diagnosing this collapse mechanism and designing an encoder-decoder architecture with a GNN antigen encoder and specialized co-design decoder with appropriate training objectives, AgForce becomes one of the first methods to reliably generate antigen-specific CDR sequences. This has immediate implications for epitope-targeted antibody discovery, where existing computational tools were unknowingly producing antigen-agnostic sequences.
**Code/Weights:** Not released

---

==============================================================
## DAILY STATS
==============================================================
- **Total papers found today:** 14
- **By topic:** Protein LM: 5 | Diffusion: 3 | Flow Matching: 2 | Genomics: 3 | Architecture: 3 | General ML: 3 | Clinical ML: 2
- **Sources:** arXiv: 12 | PubMed/Nature: 2 | bioRxiv: 0 | medRxiv: 0 | HF Papers: 0 | PWC: 0
- **Papers with code released:** 2 (AlphaGenome, scooby)

---

*Generated by Claude research-digest agent on 2026-05-27*
