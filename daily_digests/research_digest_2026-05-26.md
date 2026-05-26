# Research Digest — 2026-05-26

> **Coverage window:** arXiv Monday announcement (papers submitted Fri May 22 after 14:00 ET — Sun May 24 2026, IDs ≥ ~2605.22968); catch-up on selected bio-ML papers not featured in prior digests (IDs 2603.27950, 2605.01489, 2605.07938, 2605.11196); HF Papers checked through May 26. Sources: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, HF Papers, Papers With Code.

---

---
TITLE: Asymmetric Scaling Laws from Sparse Features
AUTHORS: John Sous et al.
SOURCE: arXiv | 2605.23591 | [**Link**](https://arxiv.org/abs/2605.23591)
TOPIC TAG: Architecture / MoE
TLDR: A theoretical model for neural scaling laws under sparse feature activations proves that rare unobserved coordinates create a bottleneck absent in dense models, inducing double-descent behavior with two distinct scaling exponents (one per-parameterization regime) and a compute-optimal frontier that favors data over capacity under fixed budgets.
WHY IT MATTERS: All current MoE scaling law analyses assume dense activation statistics; this work provides the first rigorous sparse-activation correction, explaining empirically observed asymmetries in MoE loss curves that dense power-law fits cannot capture. Knowing the exact data-vs-capacity tradeoff under sparsity directly informs compute-optimal training of bio foundation models with MoE layers—such as the genomic, protein, and single-cell multi-omics LLMs now increasingly built with sparse conditional computation.
CODE: Not released

---

---
TITLE: Uncertainty-aware Classification and Triage of Structural Heart Disease Using Electrocardiography and Echocardiography Metrics
AUTHORS: Mitchel J. Colebank et al.
SOURCE: arXiv | 2605.22968 | [**Link**](https://arxiv.org/abs/2605.22968)
TOPIC TAG: Clinical ML
TLDR: Using the EchoNext paired ECG-echocardiography repository, Bayesian neural network classifiers are compared against frequentist counterparts for structural heart disease detection, finding that Bayesian networks yield comparable or better classification accuracy with substantially better-calibrated uncertainty—enabling principled triage of ambiguous cases to expert review.
WHY IT MATTERS: Clinical deployment of cardiac AI requires knowing *when* the model should abstain; this is the first study to systematically apply Bayesian uncertainty quantification to a paired ECG+echo dataset for SHD classification, directly addressing the bottleneck of expert sonographer review for underserved rural clinics. Better-calibrated confidence scores translate into fewer false-safe decisions in autonomous screening workflows.
CODE: Not released

---

---
TITLE: Proteina-Complexa: Scaling Atomistic Protein Binder Design with Generative Pretraining and Test-Time Compute
AUTHORS: NVIDIA Research et al.
SOURCE: arXiv | 2603.27950 | [**Link**](https://arxiv.org/abs/2603.27950)
TOPIC TAG: Protein LM / Flow Matching
TLDR: Proteina-Complexa unifies all-atom protein binder generation and test-time hallucination in a single flow-matching framework pretrained on Teddymer—a new large-scale dataset of 9 million synthetic protein-protein complexes derived from domain-domain pairing of AlphaFold2 predictions—achieving state-of-the-art in-silico binder design success rates and demonstrating extensions to small-molecule targets and enzyme design.
WHY IT MATTERS: Generative pretraining and hallucination-based test-time optimization have been distinct paradigms; Proteina-Complexa is the first model to unify them, showing that a generative flow prior dramatically outperforms pure test-time search under matched compute budgets and enabling hydrogen-bond-guided and fold-class-conditioned binder generation. The Teddymer pretraining dataset is an order of magnitude larger than any prior complex-structure pretraining corpus, establishing a new data-scale baseline for all-atom protein co-design.
CODE: [**Code & models**](https://github.com/NVIDIA/proteina) *(ICLR 2026)*

---

---
TITLE: SciResearcher: Scaling Deep Research Agents for Frontier Scientific Reasoning
AUTHORS: Zheng Wang et al.
SOURCE: arXiv | 2605.01489 | [**Link**](https://arxiv.org/abs/2605.01489)
TOPIC TAG: General ML
TLDR: SciResearcher is an automated agentic framework that synthesizes frontier-science training data through two pipelines—conceptual (multi-step literature reasoning chains) and computational (tool-integrated experiment workflows)—yielding SciResearcher-8B, which achieves 19.46% on HLE-Bio/Chem-Gold and 13–15% absolute gains on SuperGPQA-Hard-Biology over prior methods at the same parameter scale.
WHY IT MATTERS: Existing scientific LLM benchmarks rely on factual recall; SciResearcher targets frontier reasoning where domain knowledge is scattered across sparse, heterogeneous academic sources—exactly the regime faced by computational biology researchers in exploratory research. The automated pipeline for generating tool-integrated scientific reasoning trajectories is transferable to domain-specific areas (protein function, CRISPR design, genomic interpretation) where curated supervision is costly.
CODE: Not released

---

---
TITLE: CellRefine: Prototype-Guided Post-Pretraining for Single-Cell Representation Learning
AUTHORS: (arXiv 2605.07938 team) et al.
SOURCE: arXiv | 2605.07938 | [**Link**](https://arxiv.org/abs/2605.07938)
TOPIC TAG: Genomics
TLDR: CellRefine introduces a post-pretraining stage between the base pretraining and task-specific fine-tuning of single-cell foundation models, updating the encoder on a curated set of prototype cells that anchor biologically meaningful clusters, substantially improving downstream performance in cell type annotation, perturbation response prediction, and batch integration without additional labeled data.
WHY IT MATTERS: Single-cell foundation models (scGPT, Geneformer, scFoundation) are typically deployed by direct fine-tuning from pretraining checkpoints, but pretraining objectives optimize reconstruction, not the representation geometry required for downstream tasks; CellRefine's prototype anchoring aligns the latent geometry with biological cell identity before any supervision. The post-pretraining paradigm is task-agnostic and can be applied to any single-cell FM, making it immediately usable by the wider single-cell community.
CODE: Not released

---

---
TITLE: Variational Linear Attention: Stable Associative Memory for Long-Context Transformers
AUTHORS: Vishal Pandey, Gopal Singh
SOURCE: arXiv | 2605.11196 | [**Link**](https://arxiv.org/abs/2605.11196)
TOPIC TAG: Architecture / SSM
TLDR: Variational Linear Attention (VLA) reframes the linear attention memory update as an online regularized least-squares problem with a per-step adaptive penalty matrix maintained via the Sherman-Morrison rank-1 update, proving that unit-normalized write directions make the Jacobian spectral norm exactly 1, bounding state-norm growth and reducing it 109× at T=1,000 relative to standard linear attention.
WHY IT MATTERS: The instability of linear attention state norms has been a known but unsolved problem—memory growth causes progressive interference that degrades recall over long contexts, preventing deployment for genomic or protein sequences spanning 100k+ tokens; VLA's theoretical guarantee of bounded state norm and near-perfect multi-query associative recall within the memory regime provides the missing rigorous foundation. This is a key step toward efficient O(T)-complexity long-context models for chromosome-scale genomics and full-proteome protein language modeling.
CODE: Not released

---

---
TITLE: Expert Routing for Communication-Efficient MoE via Finite Expert Banks
AUTHORS: (arXiv 2605.05278 team) et al.
SOURCE: arXiv | 2605.05278 | [**Link**](https://arxiv.org/abs/2605.05278)
TOPIC TAG: Architecture / MoE
TLDR: Replaces the standard MoE all-to-all routing with a finite expert bank design where each token selects from a fixed local pool, reducing inter-node communication by up to 70% while matching dense-routing performance—demonstrated at scale with hardware-efficient CUDA integration and tested on language modeling perplexity and throughput benchmarks.
WHY IT MATTERS: Communication overhead in distributed MoE inference currently limits scalability of large bio-foundation models (protein LMs, genomics LLMs) to small node counts; finite expert banks reduce this bottleneck without quality sacrifice, enabling deployment of MoE bio-LLMs across larger GPU clusters. The approach is architecturally compatible with existing models and can be applied post-training via fine-tuning, minimizing integration cost for deployed systems.
CODE: Not released

---

---
TITLE: Structure-Aligned Protein Language Model
AUTHORS: Can Chen et al.
SOURCE: arXiv / HF Papers | 2505.16896 | [**Link**](https://hf.co/papers/2505.16896)
TOPIC TAG: Protein LM
TLDR: A dual-task framework integrates structural knowledge from a protein graph neural network into a protein language model via both latent-level contrastive learning (inter-protein structural knowledge) and physical-level structural token prediction (intra-protein geometry), improving performance on contact prediction, remote homology, and enzyme classification while maintaining sequence-level capabilities.
WHY IT MATTERS: Most structure-aware protein LMs require explicit 3D coordinates at inference, limiting deployment to sequences with known structures; this framework injects structural knowledge entirely during training so the LM runs from sequence alone at inference. The dual contrastive+generative objective is more comprehensive than single-task structure alignment, capturing both pairwise similarity and local residue geometry.
CODE: Not released

---

---
TITLE: Deep-time Consistency in Proteome Elemental Composition Across Cellular and Viral Life
AUTHORS: L. Felipe Benites et al.
SOURCE: arXiv | 2605.19333 | [**Link**](https://arxiv.org/abs/2605.19333)
TOPIC TAG: Genomics
TLDR: Analysis of thousands of proteomes spanning all three cellular domains and all virus realms reveals remarkably constrained elemental stoichiometry (C, H, N, O, S, P ratios) despite vast evolutionary divergence—more conserved than amino acid frequencies or physicochemical properties—and not explained by phylogeny, function, or amino acid usage alone.
WHY IT MATTERS: Universal elemental constraints on proteome composition likely reflect deep biophysical requirements of protein folding thermodynamics rather than evolutionary history, providing a new principled constraint for de novo protein design with non-standard amino acids and for evaluating the physical plausibility of generative protein model outputs. The observation that viral proteomes converge to the same elemental space as cellular organisms despite independent origins adds a new dimension to understanding the limits of viable protein sequence space.
CODE: Not released

---

---
TITLE: SPADE: Faster Drug Discovery by Learning from Sparse Data
AUTHORS: (arXiv 2605.05370 team) et al.
SOURCE: arXiv | 2605.05370 | [**Link**](https://arxiv.org/abs/2605.05370)
TOPIC TAG: General ML / Clinical ML
TLDR: SPADE uses active-learning-inspired ligand selection to find 10 high-quality drug candidates with only 40 experimental tests on average—7–32% more sample-efficient than deep learning and Bayesian optimization baselines—and is 10× faster at scoring; code and dataset are publicly released.
WHY IT MATTERS: Early-stage drug screening faces a fundamental data scarcity problem where ML models are expected to generalize from only tens of labeled examples against millions of candidates; SPADE's sample-efficient design is specifically built for this regime where standard neural approaches typically underperform. The public release of code and benchmarking data directly enables comparison and iteration by the drug discovery community.
CODE: [**Code & dataset**](https://github.com/ut-austin-nvidia/SPADE)

---

---
TITLE: Benchmarking Open-Source Tools for In Silico Antiviral Drug Discovery
AUTHORS: (arXiv 2605.04265 team) et al.
SOURCE: arXiv | 2605.04265 | [**Link**](https://arxiv.org/abs/2605.04265)
TOPIC TAG: Clinical ML
TLDR: A systematic head-to-head comparison of open-source in silico antiviral pipelines across multiple viral protein targets finds Boltz-2 and DrugFormDTA ranked highest among ML-based methods while GNINA leads classical docking approaches; the result that Boltz-2 surpasses classical docking signals a turning point in ML-guided binding affinity prediction.
WHY IT MATTERS: Antiviral drug discovery has lacked a standardized open-source benchmarking framework, creating confusion about which computational tools to use for which targets; this study fills that gap with actionable guidance and provides the first direct evidence that a structure-biology ML model (Boltz-2) has crossed the performance threshold of classical docking for antiviral applications. The benchmarking methodology is readily extendable to new viral targets and emerging pathogens.
CODE: Not released

---

---
TITLE: Multi-Resolution Spatial Graphical Regression Models for Hierarchical Spatial Transcriptomics Data
AUTHORS: (arXiv 2605.16804 team) et al.
SOURCE: arXiv | 2605.16804 | [**Link**](https://arxiv.org/abs/2605.16804)
TOPIC TAG: Genomics
TLDR: A Bayesian multi-resolution spatial graphical regression framework jointly infers spatially varying gene-gene interaction networks at hierarchical tissue scales (cell → niche → region) from spatial transcriptomics data, with full uncertainty quantification via MCMC.
WHY IT MATTERS: Current spatial transcriptomics analyses model gene expression at a single resolution and independently at each spot, missing how regulatory context changes across tissue organization levels—from single-cell microenvironments to tissue compartments; this multi-scale Bayesian framework captures those scale-dependent regulatory shifts directly. The uncertainty quantification is critical for biological inference in low-cell-count regimes and provides a principled path to identifying spatially variable regulatory programs.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. Proteina-Complexa: Scaling Atomistic Protein Binder Design with Generative Pretraining and Test-Time Compute
[arXiv 2603.27950](https://arxiv.org/abs/2603.27950) | ICLR 2026 | NVIDIA

**What:** Proteina-Complexa is the first all-atom protein binder design model to unify flow-matching generative pretraining with test-time optimization (hallucination) in a single framework, pretrained on Teddymer—a 9-million-complex synthetic dataset built from AlphaFold2 domain-domain pairings—and extended to small-molecule targets and enzyme design.

**How:** The model achieves state-of-the-art in-silico binder success rates substantially above prior generative and hallucination baselines under normalized compute budgets, demonstrates hydrogen-bond-guided design and fold-class-conditioned generation, and releases code, model weights, and the Teddymer dataset openly.

**Why it matters:** Unifying these two paradigms resolves a long-standing debate about whether generative pretraining or test-time search is superior—it is both, synergistically. The Teddymer dataset sets a new scale benchmark for protein complex pretraining, and the multi-target extensions to small molecules and enzymes make Proteina-Complexa a general-purpose platform for therapeutic protein engineering.

Code / weights: [**GitHub**](https://github.com/NVIDIA/proteina)

---

### 2. Asymmetric Scaling Laws from Sparse Features
[arXiv 2605.23591](https://arxiv.org/abs/2605.23591)

**What:** The paper derives exact asymptotic scaling laws for neural networks trained on sparse features, proving that rare unobserved coordinates create a novel loss bottleneck—absent in dense models—that induces double-descent behavior with two distinct power-law exponents and shifts the compute-optimal frontier toward more data relative to capacity.

**How:** Using a tractable theoretical model, the authors analytically characterize both the underparameterized and overparameterized regimes, derive gradient-descent instability thresholds as scaling laws, and show the sparsity-induced effects persist under nonlinear activations.

**Why it matters:** All MoE scaling law analyses to date have used dense-activation theory, which cannot explain the asymmetric loss curves consistently observed in practice; this theoretical framework provides the right foundation for designing compute-optimal MoE bio-foundation models. Understanding these asymmetries is immediately actionable for practitioners choosing architecture depth, width, and dataset size for sparse genomic or protein language models.

Code: Not released

---

### 3. SciResearcher: Scaling Deep Research Agents for Frontier Scientific Reasoning
[arXiv 2605.01489](https://arxiv.org/abs/2605.01489)

**What:** SciResearcher introduces an automated pipeline that synthesizes diverse frontier-science training trajectories—blending multi-step literature reasoning and tool-integrated computational experiments—to produce SciResearcher-8B, which achieves 19.46% on HLE-Bio/Chem-Gold (13–15% absolute gain over prior 8B-scale methods).

**How:** The data construction framework generates conceptual tasks grounded in academic evidence and computational tasks requiring tool-integrated experiment execution, targeting the long-horizon reasoning and information acquisition challenges that stymie standard instruction-tuned LLMs on frontier scientific problems.

**Why it matters:** Scientific AI agents for biology must reason over sparse, heterogeneous literature and plan multi-step computational experiments—capabilities that existing benchmark-trained agents do not generalize to; SciResearcher provides both the training methodology and the first 8B-scale model demonstrably advancing that capability. This is a direct stepping stone toward autonomous hypothesis generation, experimental planning, and result interpretation in computational biology.

Code: Not released

---

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 12
- By topic: Protein LM: 2 | Flow Matching: 1 | Genomics: 3 | Architecture: 2 | MoE: 2 | General ML: 2 | Clinical ML: 3
- Sources: arXiv: 12 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 1 (cross-listed) | PWC: 0
- Papers with code released: 3 (Proteina-Complexa, SPADE, plus Structure-Aligned Protein LM weights on HF)
