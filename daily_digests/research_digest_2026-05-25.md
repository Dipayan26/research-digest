# Research Digest — 2026-05-25

**Focus:** Computational Biology × Machine Learning | Daily Briefing for Sequence & Structure Modeling Researchers

---

---
TITLE: EvoStruct: Bridging Evolutionary and Structural Priors for Antibody CDR Design via Protein Language Model Adaptation
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.21485 | [**Link**](https://arxiv.org/abs/2605.21485)
TOPIC TAG: Protein LM
TLDR: EvoStruct adapts a frozen protein language model with an E(3)-equivariant GNN cross-attention adapter to jointly leverage evolutionary sequence priors and 3D structural context for antibody CDR design, improving amino acid recovery by 16% and reducing perplexity by 43% over GNN-only baselines.
WHY IT MATTERS: Most antibody design methods are either structure-based or sequence-based; EvoStruct's adapter-based fusion is parameter-efficient and avoids full model retraining, enabling both modalities to be leveraged simultaneously. The method recovers 2.3× greater amino acid diversity with the highest binding-pair correlation to ground truth, making it directly applicable to therapeutic antibody development pipelines.
CODE: Not released
---

---
TITLE: VibeProteinBench: An Evaluation Benchmark for Language-interfaced Vibe Protein Design
AUTHORS: Hyunjin Seo et al.
SOURCE: arXiv / HF Papers | 2605.10978 | [**Link**](https://hf.co/papers/2605.10978)
TOPIC TAG: Protein LM
TLDR: VibeProteinBench introduces 76 expert-curated tasks spanning protein recognition, engineering, and de novo generation under natural-language constraints to benchmark LLM generalist capabilities in protein design, with mechanistic rationales and in silico validation.
WHY IT MATTERS: As LLMs are increasingly deployed for autonomous protein design, no standardized evaluation framework existed for language-interfaced, multi-task design; VibeProteinBench fills this gap across antibodies, enzymes, binders, and scaffolds. It benchmarks both open and closed-source models, revealing significant gaps between LLM capabilities and expert-level design performance.
CODE: Not released
---

---
TITLE: GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.07608 | [**Link**](https://arxiv.org/abs/2605.07608)
TOPIC TAG: Genomics
TLDR: GoForth is an RNA inverse sequence design language model that simultaneously conditions on secondary structure, nucleotide composition, and codon-level coding targets, enabling design of mRNAs with controlled codon usage for synthetic biology and RNA therapeutics.
WHY IT MATTERS: Prior RNA design methods address structure or coding constraints independently, failing to satisfy all constraints simultaneously at scale; GoForth's joint conditioning via language modeling scales to full-length mRNAs where combinatorial methods fail. Codon-optimized mRNA design under structural constraints is a critical bottleneck in the multi-billion-dollar RNA therapeutics pipeline.
CODE: Not released
---

---
TITLE: ProteinJEPA: Latent Prediction Complements Protein Language Models
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.07554 | [**Link**](https://arxiv.org/abs/2605.07554)
TOPIC TAG: Protein LM
TLDR: ProteinJEPA introduces a Joint Embedding Predictive Architecture (JEPA) objective for protein LMs—predicting latent structural targets at masked positions while retaining MLM cross-entropy—finding that the combined objective improves downstream task performance over MLM-only pretraining.
WHY IT MATTERS: JEPA-style self-supervised learning has driven breakthroughs in vision (I-JEPA, V-JEPA) but is underexplored for biological sequences; this work demonstrates that predicting latent structure-aware representations captures structural inductive biases inaccessible to token-level MLM. It opens a new pretraining paradigm that bridges sequence and structure learning without requiring explicit structural supervision.
CODE: Not released
---

---
TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: The paper projects ESM-2 residue representations onto protein contact graphs and applies SoftBlobGIN—a Graph Isomorphism Network with differentiable pooling—to reveal how pLM embeddings encode local 3D structural neighborhoods, providing mechanistic interpretability for protein LM representations.
WHY IT MATTERS: Despite widespread use of pLMs in biology, it remains poorly understood which structural features their embeddings encode; differentiable graph partitioning provides a principled framework for pLM interpretability beyond attention map visualization. This work informs better pLM architecture design and reveals structure-sequence encoding principles learned implicitly during sequence-only pretraining.
CODE: Not released
---

---
TITLE: Benchmarking and Behavioral Characterization of LLM Agents for Protein Design
AUTHORS: (Unknown) et al.
SOURCE: bioRxiv | 2026.05.06.723381 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.06.723381v1)
TOPIC TAG: Protein LM
TLDR: BioDesignBench introduces 76 expert-curated protein design tasks across antibodies, enzymes, fluorescent proteins, binders, and scaffolds to systematically benchmark and characterize the behavioral profiles of LLM-based autonomous protein design agents.
WHY IT MATTERS: Autonomous LLM agents for protein design are proliferating, but systematic benchmarking of capabilities and failure modes has been absent; BioDesignBench enables direct comparison across agent architectures and identifies key behavioral gaps between current LLMs and expert-level protein engineering. The benchmark covers the full design pipeline from natural-language specification to in silico validation.
CODE: Not released
---

---
TITLE: CHIMERA-Bench: A Benchmark Dataset for Epitope-Specific Antibody Design
AUTHORS: Mansoor Ahmed et al.
SOURCE: arXiv / HF Papers | 2603.13431 | [**Link**](https://hf.co/papers/2603.13431)
TOPIC TAG: Protein LM
TLDR: CHIMERA-Bench standardizes evaluation of epitope-conditioned CDR sequence-structure co-design through a curated SAbDab dataset, a unified task formulation, and comprehensive metrics across biologically motivated generalization splits that test epitope specificity.
WHY IT MATTERS: Antibody design benchmarks have lacked standardization and epitope-specificity focus, making it impossible to fairly compare methods; CHIMERA-Bench's biologically motivated splits reveal generalization failures of current models when tested on novel epitopes, directly informing therapeutic antibody development. It provides a shared evaluation substrate that the community has been missing.
CODE: Not released
---

---
TITLE: Flow Matching for Count Data
AUTHORS: Ganchao Wei, John Pearson
SOURCE: arXiv | 2605.07746 | [**Link**](https://arxiv.org/abs/2605.07746)
TOPIC TAG: Flow Matching
TLDR: count-FM introduces a flow-matching framework for discrete count data based on a continuous-time birth-death process with local unit jumps, enabling simulation-free training for generative modeling of scRNA-seq UMI count data.
WHY IT MATTERS: Standard flow matching assumes continuous data; scRNA-seq UMI counts are fundamentally non-negative integers, requiring new theoretical foundations that count-FM provides through principled extension of flow matching via birth-death processes. This enables high-quality generative modeling of transcriptomic data for perturbation simulation and synthetic data augmentation in single-cell biology.
CODE: Not released
---

---
TITLE: Sampling from Flow Language Models via Marginal-Conditioned Bridges
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.13681 | [**Link**](https://arxiv.org/abs/2605.13681)
TOPIC TAG: Flow Matching
TLDR: Flow Language Models adapt continuous flow matching to one-hot encoded discrete token sequences using marginal-conditioned bridge processes, providing principled discrete sequence generation without hand-crafted noise schedules.
WHY IT MATTERS: Applying flow matching to discrete biological sequences (DNA, protein, RNA) requires bridging the continuous-discrete gap, which prior methods handle heuristically; marginal-conditioned bridges provide a theoretically grounded unification of flow matching with discrete diffusion, potentially superseding MDLM and SEDD-style models. This framework is directly applicable as a masked LM alternative for protein and nucleic acid sequence generation.
CODE: Not released
---

---
TITLE: Drift Flow Matching
AUTHORS: Chenrui Ma
SOURCE: arXiv | 2605.17244 | [**Link**](https://arxiv.org/abs/2605.17244)
TOPIC TAG: Flow Matching
TLDR: Drift Flow Matching (DFM) unifies SDE-based drifting generative models with flow-based iterative generation in a single framework, preserving ODE inference efficiency while enabling multi-step stochastic refinement for improved sample quality and diversity.
WHY IT MATTERS: The gap between diffusion (stochastic) and flow matching (deterministic) generative models has been theoretically understood but not architecturally exploited; DFM enables adaptive trade-offs between stochasticity and determinism at inference time, improving sample diversity on high-dimensional problems like protein backbone generation. This is a foundational advance applicable to all structure-based generative models in biology.
CODE: Not released
---

---
TITLE: Multi-Scale Generative Modeling with Heat Dissipation Flow Matching
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.19371 | [**Link**](https://arxiv.org/abs/2605.19371)
TOPIC TAG: Flow Matching
TLDR: Heat Dissipation Flow Matching (HDFM) introduces a continuous blurring process into the flow matching trajectory to inject multi-scale structural priors into the generative model, improving sample diversity and quality on structured data modalities.
WHY IT MATTERS: Biological sequences and structures exhibit intrinsic hierarchical organization across scales (secondary structure → domain → full chain), yet standard flow matching uses scale-free Gaussian interpolation; HDFM's multi-scale noise injection could naturally encode these priors in generative models for proteins, RNA, and genomes. This technique is broadly applicable wherever hierarchical structure is biologically meaningful.
CODE: Not released
---

---
TITLE: ToolMol: Evolutionary Agentic Framework for Multi-objective Drug Discovery
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.12784 | [**Link**](https://arxiv.org/abs/2605.12784)
TOPIC TAG: General ML
TLDR: ToolMol combines a multi-objective genetic algorithm with an LLM agentic operator to iteratively evolve drug-like ligands, achieving >10% stronger predicted binding affinity than state-of-the-art baselines on three protein targets while maintaining drug-likeness and synthesizability.
WHY IT MATTERS: Multi-objective drug optimization (potency + synthesizability + drug-likeness) has historically required separate, non-integrated optimization loops; ToolMol's evolutionary-agentic design shows LLMs can serve as biology-aware molecular mutation and crossover operators in a closed design loop. The target-agnostic framework is directly applicable to lead optimization in drug discovery and is competitive with specialized molecular generative models.
CODE: Not released
---

---
TITLE: Hierarchical Contrastive Learning for Multi-Domain Protein-Ligand Binding
AUTHORS: (Unknown) et al.
SOURCE: arXiv | 2605.19902 | [**Link**](https://arxiv.org/abs/2605.19902)
TOPIC TAG: General ML
TLDR: A hierarchical contrastive learning framework improves protein-ligand binding affinity prediction by aligning representations across multiple structural and biochemical domains, improving cross-protein-family generalization on affinity prediction benchmarks.
WHY IT MATTERS: Protein-ligand affinity prediction suffers from severe domain shift when models trained on crystallographic data are applied to novel protein families; hierarchical contrastive alignment provides richer representations that transfer better across binding sites. This is directly relevant to early-stage drug discovery and virtual screening for underexplored protein targets.
CODE: Not released
---

---
TITLE: EDMolGPT: From Holo Pockets to Electron Density — GPT-style Drug Design with Density
AUTHORS: Jiahao Chen et al.
SOURCE: arXiv / HF Papers | 2605.08767 | [**Link**](https://hf.co/papers/2605.08767)
TOPIC TAG: General ML
TLDR: EDMolGPT is a decoder-only autoregressive framework that generates 3D drug molecules conditioned on low-resolution electron density point clouds of protein binding pockets, producing structurally accurate conformations directly from experimental electron density without relying on atom-resolution pocket models.
WHY IT MATTERS: Conventional structure-based drug design relies on atom-resolution models that may introduce errors from structure determination pipelines; using electron density as input bypasses these artifacts and enables molecular design directly from cryo-EM or X-ray data. The GPT-style autoregressive generation is efficient and scalable, introducing a fundamentally new input representation for structure-based generative models.
CODE: Not released
---

---
TITLE: A Multimodal Neural Network Model for Early Recurrence Prediction in Lung Adenocarcinoma
AUTHORS: (Unknown) et al.
SOURCE: bioRxiv | 2026.05.14.725244 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.14.725244v1)
TOPIC TAG: Clinical ML
TLDR: PLASMA integrates clinical data, mRNA expression profiles, and somatic mutation data via a multimodal deep learning architecture to predict early recurrence in lung adenocarcinoma, achieving AUROC 85.0% on TCGA and 76.5% on an independent external validation cohort.
WHY IT MATTERS: Early recurrence prediction in lung adenocarcinoma is clinically critical for adjuvant therapy decisions; PLASMA demonstrates that multi-omics integration substantially outperforms single-modality models and generalizes across independent datasets, suggesting direct clinical utility. The multi-omics fusion architecture is a generalizable template for recurrence prediction across other solid tumor types.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. EvoStruct: Bridging Evolutionary and Structural Priors for Antibody CDR Design via Protein Language Model Adaptation
[arXiv 2605.21485](https://arxiv.org/abs/2605.21485)

**What:** EvoStruct attaches an E(3)-equivariant GNN cross-attention adapter to a frozen protein LM, enabling simultaneous use of evolutionary sequence priors and 3D structural context for antibody CDR design without retraining the base model.

**How:** The method achieves 16% improvement in amino acid recovery and 43% reduction in perplexity over the best GNN-only baselines, while recovering 2.3× greater amino acid diversity and the highest binding-pair correlation with ground truth across multiple antibody CDR design benchmarks.

**Why it matters:** Bridging evolutionary and structural information in a single, parameter-efficient adapter is a broadly applicable technique for pLM fine-tuning—applicable far beyond antibody design to any protein engineering task where both homology and structure are informative. This represents a practical and immediately deployable advance for therapeutic antibody development pipelines.

Code/Model: Not released

---

### 2. VibeProteinBench: An Evaluation Benchmark for Language-interfaced Vibe Protein Design
[arXiv / HF Papers 2605.10978](https://hf.co/papers/2605.10978)

**What:** VibeProteinBench provides 76 expert-curated protein design tasks with natural-language constraints spanning recognition, engineering, and de novo generation of antibodies, enzymes, binders, and scaffolds, with expert-curated mechanistic rationales enabling rigorous evaluation of LLM protein designers.

**How:** The benchmark systematically evaluates both open and closed-source LLMs in a unified pipeline, revealing large performance gaps between current models and expert-level biological reasoning—particularly on functional engineering and de novo generation tasks.

**Why it matters:** Language-interfaced protein design ("vibe protein design") is emerging as a dominant paradigm, but rigorous evaluation has been absent; VibeProteinBench will serve as the standard benchmark for this rapidly growing sub-field, analogous to GPQA/MMLU for biological reasoning. Its release will drive progress toward LLMs that truly understand protein biochemistry and accelerate the design-build-test cycle.

Code/Model: Not released

---

### 3. GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
[arXiv 2605.07608](https://arxiv.org/abs/2605.07608)

**What:** GoForth is the first RNA language model for inverse sequence design that simultaneously conditions on secondary structure, nucleotide composition, and codon-level coding targets, directly applicable to mRNA vaccine engineering and synthetic gene circuits.

**How:** The language modeling approach scales to full-length mRNA sequences where combinatorial constraint-satisfaction methods fail, generating diverse, valid RNA sequences satisfying all three constraint types simultaneously—a capability not demonstrated by prior RNA design tools.

**Why it matters:** mRNA therapeutics require sequences that fold correctly, are codon-optimized for the host, and meet composition constraints—GoForth is the first model to solve all three simultaneously, making it directly applicable to a multi-billion-dollar RNA therapeutics pipeline including mRNA vaccines, protein replacement therapy, and synthetic biology. It positions RNA design as a major frontier for biological language models.

Code/Model: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 15
- By topic: Protein LM: 6 | Flow Matching: 4 | Genomics: 1 | General ML: 3 | Clinical ML: 1
- Sources: arXiv: 13 | bioRxiv: 2 | HF Papers: 2 (cross-listed with arXiv) | medRxiv: 0 | PubMed: 0 | PWC: 0
- Papers with code released: 0
