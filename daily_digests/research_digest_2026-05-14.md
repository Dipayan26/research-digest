# Research Digest — 2026-05-14

> **Scope:** Papers posted or published in the last ~24–48 hours across arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, and Papers With Code.  
> **Focus areas:** Protein & Molecular ML · Generative Models in Biology · Sequence & Genome Models · Architecture Innovations · General Cutting-Edge ML · Clinical & Translational ML

---

## PAPERS

---

TITLE: TD3B: Transition-Directed Discrete Diffusion for Allosteric Binder Generation
AUTHORS: Cao, H. et al.
SOURCE: arXiv | 2605.09810 | [**Link**](https://arxiv.org/abs/2605.09810)
TOPIC TAG: Diffusion
TLDR: TD3B is a sequence-based discrete diffusion framework that designs allosteric binders (e.g., for GPCRs) with explicit agonist-vs-antagonist directional control, achieved via a transition-state objective that biases generation toward specified receptor state transitions rather than static conformation binding.
WHY IT MATTERS: Virtually all structure-based generative methods target static binding pockets, making it impossible to encode functional directionality—the key distinction between an agonist and antagonist for clinically critical targets like GPCRs. TD3B is the first generative model to formalize allosteric functional directionality as a training objective, opening a route to therapeutics that predictably bias receptor signaling downstream of binding.
CODE: Not released

---

TITLE: RNA-FM: Flow-Matching Generative Model for Genome-wide RNA-Seq Prediction
AUTHORS: (arXiv 2605.11622 team) et al.
SOURCE: arXiv | 2605.11622 | [**Link**](https://arxiv.org/abs/2605.11622)
TOPIC TAG: Flow Matching / Genomics
TLDR: RNA-FM formulates genome-wide bulk RNA-seq prediction from histopathology whole-slide images as a continuous-time conditional transport problem, learning a velocity field that maps a Gaussian prior to the target gene expression distribution conditioned on image morphology.
WHY IT MATTERS: Obtaining genome-wide transcriptomics requires sequencing; histology slides are orders of magnitude cheaper and more widely available. RNA-FM's continuous flow matching formulation properly handles the high-dimensional, continuous nature of bulk RNA-seq data and avoids the mode-collapse issues of prior GAN-based spatially-resolved expression predictors. This could democratize transcriptomics-level molecular profiling from standard pathology workflows.
CODE: Not released

---

TITLE: Conditional Generation of Antibody Sequences with Classifier-Guided Germline-Absorbing Discrete Diffusion
AUTHORS: (arXiv 2605.06720 team) et al.
SOURCE: arXiv | 2605.06720 | [**Link**](https://arxiv.org/abs/2605.06720)
TOPIC TAG: Diffusion
TLDR: Introduces a germline-absorbing noise process for discrete diffusion over antibody sequences—using the nearest germline sequence as the absorbing state rather than a mask token—combined with classifier guidance to condition generation on antigen specificity and developability.
WHY IT MATTERS: Standard mask-absorbing diffusion ignores the evolutionary structure of antibody sequence space, discarding the biological prior that antibodies evolve from a germline root; the germline-absorbing formulation injects this bias directly into the forward process, yielding generated sequences with improved naturalness and expression. Classifier guidance for joint antigen specificity + developability control in a single diffusion model is a step change from two-stage design pipelines.
CODE: Not released

---

TITLE: A-CODE: Fully Atomic Protein Co-Design with Unified Multimodal Diffusion
AUTHORS: (arXiv 2605.03360 team) et al.
SOURCE: arXiv | 2605.03360 | [**Link**](https://arxiv.org/abs/2605.03360)
TOPIC TAG: Diffusion / Protein LM
TLDR: A-CODE jointly diffuses all-atom protein backbone coordinates and sequence identities in a single unified multimodal diffusion model, enabling simultaneous sequence-structure co-design without any auto-regressive decoding step.
WHY IT MATTERS: Existing protein design pipelines decouple structure generation from sequence design, introducing accumulating errors and consistency gaps between the two stages. Unifying them in a single atomic-resolution diffusion model captures the tight coupling between sidechain packing and backbone geometry that governs protein stability and function, representing a significant architectural advance over modular pipelines.
CODE: Not released

---

TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: (arXiv 2605.10985 team) et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: Projects ESM-2 residue embeddings onto protein contact graphs and applies SoftBlobGIN—a Graph Isomorphism Network with differentiable Gumbel-softmax substructure pooling—achieving 92.8% accuracy and 0.898 macro-F1 on enzyme classification while producing interpretable structural subgraph explanations.
WHY IT MATTERS: Protein language model representations achieve strong benchmark numbers but remain opaque black boxes; this work is one of the first to extract structurally meaningful, differentiable explanations directly from pLM embeddings without requiring auxiliary structure prediction. The Gumbel-softmax partitioning is a general plug-and-play method applicable to any graph-structured molecular data, including RNA contact maps and small-molecule interaction graphs.
CODE: Not released

---

TITLE: Deep Learning for Protein Complex Prediction and Design
AUTHORS: Xie, Z. et al.
SOURCE: arXiv | 2605.11189 | [**Link**](https://arxiv.org/abs/2605.11189)
TOPIC TAG: Protein LM
TLDR: Comprehensive thesis presenting domain-specific hierarchical architectures for protein complex structure prediction and novel search algorithms for navigating the vast sequence space of multi-chain protein complexes, with experimental validation on several design tasks.
WHY IT MATTERS: Protein complexes dominate biology but are dramatically underrepresented in prediction benchmarks and generative models compared to single chains; this work systematically addresses the hierarchical geometry of interface modeling and shows that architectural choices tuned to multi-chain topology yield substantial improvements over single-chain models applied naively to complexes. The accompanying search algorithms provide a blueprint for scalable sequence space exploration in complex design.
CODE: Not released

---

TITLE: Learning the Interaction Prior for Protein-Protein Interaction Prediction: A Model-Agnostic Approach
AUTHORS: (arXiv 2605.09964 team) et al.
SOURCE: arXiv | 2605.09964 | [**Link**](https://arxiv.org/abs/2605.09964)
TOPIC TAG: Protein LM
TLDR: Proposes a model-agnostic framework that explicitly learns a prior over protein-protein interaction patterns from large unlabelled protein databases and plugs it into any downstream PPI classifier, improving cross-dataset generalization without retraining the base model.
WHY IT MATTERS: PPI predictors trained on curated interaction databases suffer from severe distribution shift when applied to proteins from understudied organisms or novel interaction types; the interaction prior captures statistical regularities of binding interfaces at scale, functioning as a regularizer that makes classifiers more robust without requiring labelled interaction data from the target distribution. The model-agnostic design makes this immediately applicable to existing production PPI systems.
CODE: Not released

---

TITLE: VibeProteinBench: An Evaluation Benchmark for Language-Interfaced Vibe Protein Design
AUTHORS: (arXiv 2605.10978 team) et al.
SOURCE: arXiv | 2605.10978 | [**Link**](https://arxiv.org/abs/2605.10978)
TOPIC TAG: General ML / Protein LM
TLDR: Introduces a three-stage benchmark—intent parsing, constraint satisfaction, and structural validity—that evaluates language-model-driven protein design systems end-to-end from open-ended natural-language design intents to physically plausible protein outputs.
WHY IT MATTERS: As LLM-orchestrated protein design agents proliferate, the field lacks standardized evaluation that tests the full pipeline from free-text user intent to structured outputs; VibeProteinBench fills this gap by mirroring the actual computational protein design workflow and exposing failure modes invisible to individual component benchmarks. The benchmark should become a standard for evaluating agentic protein design systems as they become increasingly user-facing.
CODE: Not released

---

TITLE: Better Protein Function Prediction by Modeling Survivorship Bias
AUTHORS: (arXiv 2605.06879 team) et al.
SOURCE: arXiv | 2605.06879 | [**Link**](https://arxiv.org/abs/2605.06879)
TOPIC TAG: Protein LM
TLDR: Frames biases in curated protein function databases as a positive-unlabeled (PU) learning problem, using a scientific model of mutational survivorship to generate reliable negative examples and substantially reduce false-negative contamination in training data.
WHY IT MATTERS: Most protein function benchmark datasets contain large numbers of unlabelled sequences that in fact possess the function of interest but were never experimentally characterized—a form of survivorship bias that degrades model calibration. Explicitly modeling this bias through PU learning is more principled than label smoothing or threshold tuning and yields better-calibrated predictors that matter most in active learning loops for experimental protein engineering.
CODE: Not released

---

TITLE: PPI-Net: Connecting Molecular Protein Interactions to Functional Processes in Disease
AUTHORS: (arXiv 2605.07838 team) et al.
SOURCE: arXiv | 2605.07838 | [**Link**](https://arxiv.org/abs/2605.07838)
TOPIC TAG: Protein LM / Clinical ML
TLDR: A hierarchical GNN that integrates protein-protein interaction networks with pathway-level representations, applied to RNA-seq data from ten cancer types, achieving over 90% balanced accuracy for cancer-type classification across multiple cohorts.
WHY IT MATTERS: Mapping from molecular protein interactions to pathway-level disease phenotypes requires a model that explicitly respects the multi-scale biological hierarchy—PPI-Net does this by learning joint embeddings at both the interaction and pathway level in a unified architecture. Robust >90% accuracy across ten cancer types suggests that the hierarchical PPI representation captures conserved oncogenic pathway dysregulation patterns more efficiently than flat expression-based models.
CODE: Not released

---

TITLE: GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
AUTHORS: (arXiv 2605.07608 team) et al.
SOURCE: arXiv | 2605.07608 | [**Link**](https://arxiv.org/abs/2605.07608)
TOPIC TAG: Genomics
TLDR: Trains a language model on (target-structure, sequence) pairs derived by masking observed RNA folds, enabling joint satisfaction of secondary structure, sequence motif, and protein-coding constraints—a multi-constraint RNA design setting not addressed by prior inverse-folding methods.
WHY IT MATTERS: Therapeutic RNA design (mRNA therapeutics, riboswitches, aptamers) requires sequences that simultaneously adopt a desired structure, encode a protein, and avoid immunogenic motifs—constraints that were previously optimized in separate disconnected steps. GoForth is the first language model explicitly trained to satisfy all three constraint types jointly, providing a natural generative framework for end-to-end therapeutic RNA molecule design.
CODE: Not released

---

TITLE: Flow Matching for Count Data
AUTHORS: (arXiv 2605.07746 team) et al.
SOURCE: arXiv | 2605.07746 | [**Link**](https://arxiv.org/abs/2605.07746)
TOPIC TAG: Flow Matching / Genomics
TLDR: Count-FM defines a continuous-time flow matching framework native to count-valued spaces using a birth-death process with local unit jumps, learning conditional transition rates simulation-free, enabling transport between arbitrary count-distributed source and target populations in high dimensions.
WHY IT MATTERS: Single-cell RNA-seq data are fundamentally count-valued, yet existing continuous flow matching frameworks require pre-processing (log-normalization, PCA) that destroys count statistics critical for differential expression and batch correction; Count-FM operates directly in count space, preserving those statistics without artificial smoothing. The birth-death formulation admits rigorous theoretical analysis and may generalize to other discrete biological data types such as copy-number variation and chromatin accessibility counts.
CODE: Not released

---

TITLE: FlashMol: High-Quality Molecule Generation in as Few as Four Steps
AUTHORS: (arXiv 2605.07020 team) et al.
SOURCE: arXiv | 2605.07020 | [**Link**](https://arxiv.org/abs/2605.07020)
TOPIC TAG: Diffusion / Molecular ML
TLDR: FlashMol achieves up to 250× acceleration in diffusion-based 3D molecule generation speed while maintaining high molecular quality on QM9 and GEOM-DRUG benchmarks, using a distilled few-step sampler trained without auxiliary networks.
WHY IT MATTERS: Molecular generation via diffusion requires hundreds of denoising steps, making it impractical for high-throughput virtual screening campaigns where millions of candidates must be evaluated; 250× speedup at maintained quality brings diffusion-generated molecules within reach of real-time drug discovery workflows. The distillation approach is architecture-agnostic and could accelerate other biological generative models such as protein backbone diffusion.
CODE: Not released

---

TITLE: Decomposing the Generalization Gap in PROTAC Activity Prediction: Variance Attribution and the Inter-Laboratory Ceiling
AUTHORS: (arXiv 2605.11764 team) et al.
SOURCE: arXiv | 2605.11764 | [**Link**](https://arxiv.org/abs/2605.11764)
TOPIC TAG: Clinical ML / General ML
TLDR: Decomposes the generalization gap of ML models predicting PROTAC-mediated target degradation into variance attributable to model architecture, molecular descriptor choice, and irreducible inter-laboratory assay variability—revealing that assay noise sets a practical ceiling on achievable generalization.
WHY IT MATTERS: Targeted protein degraders (PROTACs) are a rapidly growing drug modality but their activity depends on complex ternary complex formation that standard ML models fail to predict cross-assay; quantifying the inter-laboratory ceiling is essential for setting realistic expectations and guiding data collection strategy. The variance decomposition framework is broadly applicable to any drug discovery ML task where assay reproducibility limits generalization.
CODE: Not released

---

TITLE: When Are Experts Misrouted? Counterfactual Routing Analysis in Mixture-of-Experts Language Models
AUTHORS: (arXiv 2605.07260 team) et al.
SOURCE: arXiv | 2605.07260 | [**Link**](https://arxiv.org/abs/2605.07260)
TOPIC TAG: MoE / Architecture
TLDR: Uses counterfactual interventions to evaluate whether the routes selected by a trained top-k router in MoE LLMs are actually the best-performing ones, finding that systematic misrouting is prevalent at medium model scales and correlates with specific input domain categories including biological and scientific text.
WHY IT MATTERS: MoE architectures are increasingly used as backbone LLMs for biological sequence and scientific reasoning tasks, but routing quality has not been directly measured; evidence of domain-correlated misrouting has immediate practical implications for MoE pre-training of specialized bio-LLMs. The counterfactual analysis methodology provides a diagnostic tool for auditing routing quality in any MoE system before deployment.
CODE: Not released

---

TITLE: Emo: Pretraining Mixture of Experts for Emergent Modularity
AUTHORS: (arXiv 2605.06663 team) et al.
SOURCE: arXiv | 2605.06663 | [**Link**](https://arxiv.org/abs/2605.06663)
TOPIC TAG: MoE / Architecture
TLDR: Enforces expert specialization during MoE pretraining by routing tokens to experts based on predefined semantic domains (math, code, biology, etc.), showing that deploying only domain-relevant expert subsets largely preserves performance at inference while enabling modular fine-tuning.
WHY IT MATTERS: Biology-specific LLMs are typically dense models or MoEs with learned (emergent) routing that lacks interpretable domain structure; Emo's approach of explicitly seeding domain-expert assignment during pretraining produces modular models where the biology-relevant expert subset can be fine-tuned without disturbing other domains. This is a key step toward efficient continual learning of new biological knowledge in large foundation models.
CODE: Not released

---

TITLE: Federation of Experts: Communication Efficient Distributed Inference for Large Language Models
AUTHORS: (arXiv 2605.06206 team) et al.
SOURCE: arXiv | 2605.06206 | [**Link**](https://arxiv.org/abs/2605.06206)
TOPIC TAG: MoE / Architecture
TLDR: Restructures the MoE transformer block into geographically co-located expert clusters (Federation of Experts), reducing all-to-all cross-node communication by routing tokens within clusters first, cutting distributed inference latency by up to 40% on standard benchmarks without accuracy loss.
WHY IT MATTERS: Deploying MoE-based biology foundation models (protein language models, genomics LLMs) at inference scale requires expert parallelism across many nodes, and communication overhead currently dominates runtime; the Federation of Experts architecture is directly applicable to these bio-LLM deployment scenarios. A 40% latency reduction translates directly to faster hypothesis generation in high-throughput protein design or genomics screens.
CODE: Not released

---

TITLE: ProtDBench: A Unified Benchmark of Protein Binder Design and Evaluation
AUTHORS: (arXiv 2605.04118 team) et al.
SOURCE: arXiv | 2605.04118 | [**Link**](https://arxiv.org/abs/2605.04118)
TOPIC TAG: General ML / Protein LM
TLDR: ProtDBench is a standardized, throughput-aware evaluation framework for protein binder design that defines unified tasks, protocols, and success criteria, and uses a large wet-lab annotated dataset to reveal substantial verifier-dependent bias across commonly used structure prediction-based evaluation models.
WHY IT MATTERS: The protein binder design community has proliferated methods evaluated under inconsistent protocols with structure prediction models as proxies for experimental success—a circularity that has masked genuine progress; ProtDBench's wet-lab ground truth reveals that verifier choice alone changes apparent state-of-the-art rankings. Standardized evaluation will enable more reproducible progress and better prioritization of computational resources in binder design campaigns.
CODE: Not released

---

TITLE: AgenticPosesRanker: An Agentic AI Framework for Physically Grounded Ranking of Protein-Ligand Docking Poses
AUTHORS: (arXiv 2605.03707 team) et al.
SOURCE: arXiv | 2605.03707 | [**Link**](https://arxiv.org/abs/2605.03707)
TOPIC TAG: General ML / Molecular ML
TLDR: Combines six deterministic, physics-based analysis tools with GPT-5 chain-of-thought reasoning in an agentic loop to evaluate and rank protein-ligand docking poses, outperforming standalone scoring functions on pose re-ranking benchmarks by exploiting structured reasoning over physical descriptors.
WHY IT MATTERS: Neural scoring functions for docking are black boxes that frequently fail on unusual chemotypes or allosteric sites; grounding LLM reasoning in deterministic physics tools preserves interpretability and generalizability while the LLM provides flexible integration of heterogeneous evidence. The agentic architecture is a template for extending LLM reasoning to any multi-physics computational biology evaluation task.
CODE: Not released

---

TITLE: D3LM: A Discrete DNA Diffusion Language Model for Bidirectional DNA Understanding and Generation
AUTHORS: Yang, Z. et al.
SOURCE: arXiv / HF Papers | 2603.01780 | [**Link**](https://arxiv.org/abs/2603.01780)
TOPIC TAG: Diffusion / Genomics
TLDR: D3LM unifies bidirectional DNA representation learning and sequence generation in a single masked-diffusion model trained in discrete DNA token space, outperforming autoregressive models on regulatory element generation benchmarks including promoter and enhancer design.
WHY IT MATTERS: DNA language models have bifurcated into masked models (BERT-style, good at classification) and autoregressive models (GPT-style, good at generation)—D3LM collapses the distinction by exploiting discrete diffusion's inherent bidirectionality to achieve strong performance on both paradigms simultaneously. Outperforming autoregressive models on regulatory element generation is especially relevant because regulatory sequences have complex non-local dependencies that autoregressive left-to-right decoding handles poorly.
CODE: [**Code**](https://github.com/yangyz1230/D3LM)

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### #1 — TD3B: Transition-Directed Discrete Diffusion for Allosteric Binder Generation
**arXiv 2605.09810**

TD3B addresses one of the most clinically consequential limitations of structure-based generative design: the inability to encode functional directionality. For GPCR targets—the largest class of approved drug targets—therapeutic outcome depends not just on whether a molecule binds but on whether it acts as an agonist, partial agonist, or antagonist. TD3B introduces a transition-state objective within a discrete diffusion framework that biases generated sequences toward producing a defined receptor state transition, encoding agonism vs. antagonism as a generation-time condition rather than a post-hoc filter. This is the first generative model architecture explicitly formalized around allosteric functional directionality, establishing a new design paradigm relevant to kinases, ion channels, and any protein whose function is controlled by conformational state transitions.

Code: Not released

---

### #2 — RNA-FM: Flow-Matching Generative Model for Genome-wide RNA-Seq Prediction
**arXiv 2605.11622**

RNA-FM reframes the computational pathology problem of predicting transcriptomics from histology as a continuous-time conditional transport problem using flow matching. Rather than training a regressor to output a single expression vector, RNA-FM learns a velocity field that maps a simple Gaussian prior to the full conditional distribution of genome-wide RNA-seq counts given a whole-slide image, enabling both point estimates and uncertainty quantification over transcriptomic profiles. The flow matching formulation is particularly well-suited to this problem because RNA-seq data lives in a high-dimensional continuous space with strong global covariance structure—properties that flow matching handles more robustly than both GANs and denoising diffusion, which struggle with mode coverage or computational cost at this dimensionality.

Code: Not released

---

### #3 — Conditional Generation of Antibody Sequences with Classifier-Guided Germline-Absorbing Discrete Diffusion
**arXiv 2605.06720**

This paper rethinks the absorbing state for discrete diffusion over antibody sequences: instead of absorbing to a mask token, it absorbs to the nearest germline sequence in V(D)J recombination space, injecting the evolutionary structure of antibody diversity directly into the forward process. This biological prior steers the learned reverse process toward antibody-like sequences, dramatically reducing the burden on the model to re-learn germline proximity from data. Combined with classifier guidance that jointly optimizes for antigen specificity and developability properties (expression, stability, low polyspecificity), the method produces antibody candidates that are simultaneously more natural and more property-constrained than prior discrete diffusion approaches—a critical advance for therapeutic antibody discovery workflows.

Code: Not released

---

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 20
- By topic: Protein LM: 6 | Diffusion: 5 | Flow Matching: 2 | Genomics: 2 | Architecture/MoE: 3 | General ML: 3 | Clinical ML: 2
- Sources: arXiv: 19 | HF Papers: 1 (D3LM cross-listed) | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | PWC: 0
- Papers with code released: 1 (D3LM)
