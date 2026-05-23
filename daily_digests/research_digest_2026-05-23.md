# Research Digest — 2026-05-23

> Auto-generated daily digest covering ML × computational biology.
> Sources: arXiv (cs.LG · cs.AI · q-bio.BM · q-bio.QM · q-bio.GN · stat.ML · cs.NE) · bioRxiv · medRxiv · PubMed · HF Papers · Papers With Code

---

## Papers

---
TITLE: Atom-level Protein Representation Learning Improves Protein Structure Prediction
AUTHORS: Taewon Kim et al.
SOURCE: arXiv | 2605.22133 | [**Link**](https://arxiv.org/abs/2605.22133)
TOPIC TAG: Protein LM
TLDR: TriProRep jointly pre-trains on three aligned residue-level views—amino-acid identity, backbone geometry, and local full-atom geometry—all discretely encoded via VQ-VAE tokenizers, learning to reconstruct corrupted cross-view tokens.
WHY IT MATTERS: Existing protein representation pre-training predominantly uses backbone-level geometry or sequence alone; capturing full-atom local geometry (side-chain environments) is essential for predicting binding pockets and thermodynamic stability. The authors introduce RepSP, a novel benchmark explicitly targeting structure-predictive settings, filling a gap left by function-focused evaluation suites like TAPE or ProteinGym.
CODE: Not released

---
TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: Siddhant Dutta et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: SoftBlobGIN projects ESM-2 residue embeddings onto protein contact graphs and applies differentiable Gumbel-softmax substructure pooling (SoftBlob layers) for structure-aware message passing, achieving 92.8% accuracy and 0.898 macro-F1 on enzyme classification.
WHY IT MATTERS: Despite strong downstream performance, protein language models remain structurally opaque—prior interpretability methods operated on attention maps over sequence rather than structural subgraphs. This plug-and-play framework generates auditable structural explanations, with GNNExplainer recovering biologically meaningful active-site residues and catalytic contact patterns that align with known enzyme mechanisms.
CODE: Not released

---
TITLE: ProteinJEPA: Latent prediction complements protein language models
AUTHORS: Dan Ofer et al.
SOURCE: arXiv | 2605.07554 | [**Link**](https://arxiv.org/abs/2605.07554)
TOPIC TAG: Protein LM
TLDR: Applying JEPA-style latent prediction exclusively at masked positions—while retaining the MLM cross-entropy—outperforms pure MLM continuation on 10 of 16 downstream tasks (including SCOPe-40 fold retrieval) at equal wall-clock budget on ESM-2 backbones.
WHY IT MATTERS: JEPA (Joint Embedding Predictive Architecture) has driven major advances in vision self-supervised learning but had not been systematically explored for protein sequence models; this work demonstrates that predicting in latent space rather than token space provides complementary signal to masked language modeling. Crucially, no structural data is required at training time, making the recipe broadly applicable to any protein LM.
CODE: Not released

---
TITLE: ToolMol: Evolutionary Agentic Framework for Multi-objective Drug Discovery
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.12784 | [**Link**](https://arxiv.org/abs/2605.12784)
TOPIC TAG: General ML
TLDR: ToolMol couples a multi-objective genetic algorithm with an LLM agent equipped with a comprehensive RDKit-backed toolbox, iteratively evolving ligand populations to achieve >10% stronger predicted binding affinity vs. existing de novo design baselines.
WHY IT MATTERS: Pure LLM-based molecular generation produces high rates of chemically invalid SMILES; grounding the agent in verified RDKit operations ensures syntactic and chemical validity with every edit. The evolutionary outer loop naturally handles multi-objective trade-offs (affinity, synthesizability, drug-likeness) in a way single-shot generative models cannot.
CODE: Not released

---
TITLE: SPADE: Faster Drug Discovery by Learning from Sparse Data
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.05370 | [**Link**](https://arxiv.org/abs/2605.05370)
TOPIC TAG: General ML
TLDR: SPADE's active-learning-inspired ligand selection finds 10 high-quality drug candidates with only 40 experimental tests on average—7–32% more sample-efficient than deep learning and Bayesian optimization competitors—and is 10× faster at scoring.
WHY IT MATTERS: Early-stage drug screening is expensive and produces only a ~5% pass rate; SPADE learns to navigate molecular space efficiently even when labeled data is extremely scarce, a regime where most ML models fail. The public code and dataset release enable immediate benchmarking and adoption by the broader computational drug discovery community.
CODE: [**Code**](https://github.com/ut-austin-nvidia/SPADE) (with dataset)

---
TITLE: Benchmarking open-source tools for in silico antiviral drug discovery
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.04265 | [**Link**](https://arxiv.org/abs/2605.04265)
TOPIC TAG: Clinical ML
TLDR: A systematic head-to-head comparison of open-source in silico antiviral pipelines finds Boltz-2 and DrugFormDTA ranked highest overall among ML-based methods, with GNINA best among classical docking approaches.
WHY IT MATTERS: The antiviral drug discovery community lacks a standardized open-source benchmarking framework, leading to inconsistent evaluation across tools; this work fills that gap and provides actionable guidance on which ML vs. docking approaches are most suitable for different target families. The result that Boltz-2 surpasses classical docking signals a turning point in ML-guided binding affinity prediction for antivirals.
CODE: Not released

---
TITLE: Multi-resolution Spatial Graphical Regression Models for Hierarchical Spatial Transcriptomics Data
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.16804 | [**Link**](https://arxiv.org/abs/2605.16804)
TOPIC TAG: Genomics
TLDR: A Bayesian multi-resolution spatial graphical regression framework jointly infers spatially varying gene-gene interaction networks at hierarchical tissue scales (cell → niche → region) from spatial transcriptomics data.
WHY IT MATTERS: Current spatial transcriptomics analyses model gene expression independently at a single resolution, ignoring the multi-scale tissue organization that shapes regulatory context; this work captures how gene network structure co-varies across hierarchical scales. The Bayesian formulation provides uncertainty quantification critical for biological inference in low-cell-count regimes.
CODE: Not released

---
TITLE: Accelerating inference in genomic and proteomic foundation models via speculative decoding
AUTHORS: Kimonas Provatas et al.
SOURCE: bioRxiv | 2026.01.13.699044 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.01.13.699044v1)
TOPIC TAG: General ML
TLDR: Speculative decoding adapted to DNAGPT, ProGen2, and ProtGPT2 achieves 20–40% average inference speedups (up to 100% in best cases) without any change to the target model's output distribution.
WHY IT MATTERS: Inference latency limits the practical use of large genomic/proteomic foundation models in high-throughput generation and screening workflows; speculative decoding is a training-free mechanism that has revolutionized NLP deployment but was previously untested in the bio-FM space. This establishes that the technique transfers cleanly to autoregressive genomic and protein sequence generation.
CODE: Not released

---
TITLE: CHIMERA-Bench: A Benchmark Dataset for Epitope-Specific Antibody Design
AUTHORS: Mansoor Ahmed et al.
SOURCE: HF Papers / arXiv | 2603.13431 | [**Link**](https://huggingface.co/papers/2603.13431)
TOPIC TAG: Protein LM
TLDR: CHIMERA-Bench introduces a standardized benchmark for epitope-conditioned CDR sequence-structure co-design with curated SAbDab data, biologically motivated generalization splits, and comprehensive metrics including epitope-specificity scores.
WHY IT MATTERS: Antibody design models are typically evaluated using random or sequence-similarity splits that dramatically inflate perceived performance relative to real-world generalization to novel epitopes. CHIMERA-Bench's biologically motivated splits (by epitope cluster and antigen family) provide the first honest evaluation of model generalization in the practical setting of designing antibodies for unseen targets.
CODE: Not released

---
TITLE: Protein Fold Classification at Scale: Benchmarking and Pretraining
AUTHORS: Dexiong Chen et al.
SOURCE: arXiv | [ICML 2026 Spotlight] | [**Link**](https://arxiv.org/list/cs.LG/recent)
TOPIC TAG: Protein LM
TLDR: A large-scale study of protein fold classification establishes rigorous benchmarking protocols and a new pretraining regime that achieves state-of-the-art performance, earning an ICML 2026 spotlight from the Borgwardt lab.
WHY IT MATTERS: Protein fold classification underpins evolutionary analysis, functional annotation, and structural drug design, but prior work used inconsistent evaluation setups making cross-method comparison unreliable. The spotlight recognition signals community consensus that this benchmark will serve as the community standard for fold classification going forward.
CODE: Not released

---
TITLE: Generalist biological artificial intelligence in modeling the language of life
AUTHORS: [First Author] et al.
SOURCE: Nature Biotechnology | DOI: 10.1038/s41587-026-03064-w | [**Link**](https://www.nature.com/articles/s41587-026-03064-w)
TOPIC TAG: Protein LM
TLDR: A comprehensive framework for Generalist Biological AI (GBAI) that simultaneously models DNA, RNA, proteins, and cellular phenotypes within a unified architecture, enabling cross-modal biological reasoning at scale.
WHY IT MATTERS: Siloed models for individual biological modalities miss cross-layer dependencies—e.g., how a DNA variant perturbs RNA splicing, which alters protein structure, which shifts cellular phenotype; GBAI architectures capture this full causal chain. Publication in Nature Biotechnology signals that integrating the full central dogma into a single learnable model is now tractable and scientifically credible.
CODE: Not released

---
TITLE: Diffusion Sequence Models for Enhanced Protein Representation and Generation
AUTHORS: Logan Hallee et al.
SOURCE: arXiv | 2506.08293 | [**Link**](https://arxiv.org/abs/2506.08293)
TOPIC TAG: Diffusion
TLDR: Diffusion Sequence Models (DSMs) apply masked forward diffusion over ESM-2/LLaDA-style architectures to simultaneously enable high-quality protein representation learning and generative protein design, outperforming classical protein LMs on the Bench-tested Binder Benchmark.
WHY IT MATTERS: Most protein generative models sacrifice representation quality for generation, or vice versa; the DSM framework unifies both via masked diffusion pre-training with a single objective. Results on the Bench-tested Binder Benchmark demonstrate practical utility for the high-value task of binder design, bridging the gap between pLM-based representation and sequence generation.
CODE: Not released

---
TITLE: Ankh3: Multi-Task Pretraining with Sequence Denoising and Completion Enhances Protein Representations
AUTHORS: Hazem Alsamkary et al.
SOURCE: HF Papers / arXiv | 2505.20052 | [**Link**](https://huggingface.co/papers/2505.20052)
TOPIC TAG: Protein LM
TLDR: Ankh3 combines masked language modeling with sequence denoising and completion objectives in a multi-task pretraining strategy, yielding improved downstream representations on secondary structure, fluorescence, fitness, and contact prediction.
WHY IT MATTERS: Single-objective pretraining (MLM alone) may under-exploit the rich signal available in protein sequences; multi-task denoising and completion objectives force the model to develop complementary skills—sequence completion captures local dependencies, while denoising builds robustness to evolutionary substitutions. This extends the Ankh family with a practical recipe applicable to any protein LM backbone.
CODE: Not released

---
TITLE: Functional In-Context Learning in Genomic Language Models with Nucleotide-Level Supervision and Genome Compression
AUTHORS: [First Author] et al.
SOURCE: bioRxiv | 2026.01.27.702015 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.01.27.702015.full.pdf)
TOPIC TAG: Genomics
TLDR: Genomic LMs fine-tuned with nucleotide-level supervision and a genome compression strategy develop functional in-context learning, adapting to new regulatory element prediction tasks from a handful of sequence-label exemplars in the prompt.
WHY IT MATTERS: In-context learning has transformed NLP but remained largely unexplored for genomic foundation models, which typically require task-specific fine-tuning; this work shows that the right training signals unlock ICL for DNA sequences. Nucleotide-level supervision ensures the model attends to base-pair resolution features relevant for regulatory elements, rather than coarse token-level representations from k-mer tokenizers.
CODE: Not released

---
TITLE: Fundamental limitations of genomic language models for realistic sequence generation
AUTHORS: [First Author] et al.
SOURCE: bioRxiv | 2026.01.17.700093 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.01.17.700093.full.pdf)
TOPIC TAG: Genomics
TLDR: A systematic analysis demonstrates that current genomic language models, despite strong discriminative benchmarks, fail to generate biologically realistic sequences—exhibiting distributional failures in GC content, repeat structure, and k-mer statistics.
WHY IT MATTERS: Genomic LMs are increasingly deployed for sequence design (promoters, enhancers, regulatory elements), but this study provides essential caution: discriminative accuracy does not imply generative realism. The identified failure modes (repeat bias, GC content drift) give actionable targets for future model architectures and training curricula for the genomics field.
CODE: Not released

---

==============================================================
## HIGHLIGHTS OF THE DAY
==============================================================

### 1. Atom-level Protein Representation Learning Improves Protein Structure Prediction (TriProRep)
**[arXiv 2605.22133](https://arxiv.org/abs/2605.22133)**

TriProRep is a structure-aware pretraining approach that jointly encodes three residue-level views of a protein—amino-acid identity, backbone geometry, and local full-atom geometry (side chains)—using VQ-VAE tokenizers to produce discrete representations, then recovers corrupted cross-view tokens during pretraining. The multi-view corruption-and-recovery objective forces the model to build representations that are simultaneously consistent with sequence, backbone shape, and full-atom chemical environment. This matters because side-chain geometry governs binding site complementarity, thermodynamic stability, and enzyme catalysis—properties that backbone-only models systematically mis-predict. The accompanying RepSP benchmark provides the first structure-prediction-centric evaluation suite, enabling rigorous comparison of representation methods specifically for structure-related downstream tasks.
**Code:** Not yet released

---

### 2. SPADE: Faster Drug Discovery by Learning from Sparse Data
**[arXiv 2605.05370](https://arxiv.org/abs/2605.05370)**

SPADE reframes drug discovery as an adaptive sampling problem, using an active-learning-inspired ligand selection strategy that iteratively queries only the most informative candidates given previously observed binding data. It identifies 10 high-quality ligands in only 40 experimental tests on average—a 7–32% improvement in sample efficiency over deep learning and Bayesian optimization baselines—and runs 10× faster at scoring than its nearest competitor. The work is broadly significant because fewer than 5% of candidates pass even early-stage drug discovery filters, and the ability to converge rapidly from sparse experimental data could dramatically reduce screening costs, especially for novel targets with limited assay data. Code and dataset are publicly released for immediate adoption.
**Code:** [Released](https://github.com/ut-austin-nvidia/SPADE)

---

### 3. ProteinJEPA: Latent prediction complements protein language models
**[arXiv 2605.07554](https://arxiv.org/abs/2605.07554)**

ProteinJEPA adapts the JEPA (Joint Embedding Predictive Architecture) paradigm—where models predict in latent representation space rather than token space—to protein sequence pre-training, finding that masked-position latent prediction combined with standard MLM cross-entropy wins 10 of 16 tasks vs. MLM-only continuation at equal computational budget on ESM-2 backbones. The key insight is that predicting a richer latent target (rather than a raw amino acid token) provides a more informative learning signal by forcing the model to capture abstract structural and evolutionary relationships at masked positions. This is significant because JEPA has dominated vision self-supervised learning but its application to discrete biological sequences was previously unexplored; this work establishes a new pretraining recipe applicable to any masked protein LM without requiring any structural data.
**Code:** Not yet released

---

==============================================================
## DAILY STATS
==============================================================
- **Total papers found today:** 15
- **By topic:** Protein LM: 7 | Diffusion: 1 | Genomics: 3 | Architecture: 0 | General ML: 3 | Clinical ML: 1
- **Sources:** arXiv: 9 | bioRxiv: 3 | medRxiv: 0 | PubMed: 0 | HF Papers: 2 | PWC: 0 | Nature Biotechnology: 1
- **Papers with code released:** 1 (SPADE)
