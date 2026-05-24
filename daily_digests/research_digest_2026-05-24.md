# Research Digest — 2026-05-24

> Auto-generated daily digest covering ML × computational biology.
> Sources: arXiv (cs.LG · cs.AI · q-bio.BM · q-bio.QM · q-bio.GN · stat.ML · cs.NE) · bioRxiv · medRxiv · PubMed · HF Papers · Papers With Code

---

## Papers

---
TITLE: Towards A Generative Protein Evolution Machine with DPLM-Evo
AUTHORS: Xinyou Wang et al.
SOURCE: arXiv | 2605.00182 | [**Link**](https://arxiv.org/abs/2605.00182)
TOPIC TAG: Diffusion / Protein LM
TLDR: DPLM-Evo is an evolutionary discrete diffusion framework (ICML 2026 accepted) that explicitly models substitutions, insertions, and deletions via a biologically-informed contextualized noising kernel, achieving SOTA mutation effect prediction on ProteinGym in the single-sequence setting and enabling variable-length simulated protein evolution.
WHY IT MATTERS: Standard DPLMs use masking-based absorbing diffusion that contradicts the biological reality of protein evolution through accumulated edits (substitutions plus indels); DPLM-Evo addresses this by decoupling an upsampled-length latent alignment space from the variable-length observed sequence space, making indel-aware generation tractable. This is the first diffusion protein language model accepted at ICML that explicitly enables variable-length generation with biological grounding, opening the door to in silico directed evolution and ancestral sequence reconstruction.
CODE: [**Code**](https://github.com/bytedance/dplm)

---
TITLE: AgForce Enables Antigen-conditioned Generative Antibody Design
AUTHORS: Mansoor Ahmed et al.
SOURCE: arXiv | 2605.21610 | [**Link**](https://arxiv.org/abs/2605.21610)
TOPIC TAG: Protein LM
TLDR: AgForce introduces a GNN encoder-decoder with framework dropout, gated bottlenecks, and hyperbolic cross attention to enforce antigen conditioning in CDR sequence-structure co-design, achieving +8% amino acid recovery over the strongest baseline on CHIMERA-Bench while surpassing all baselines on interface quality metrics.
WHY IT MATTERS: A systematic audit of existing antigen-conditioned antibody design methods reveals three previously uncharacterized failure modes—antigen blindness (model ignores antigen input), vocabulary collapse (only 3–5 amino acids predicted per position), and positional marginal degeneracy (model converges to unconditional marginal distributions)—that collectively make standard cross-entropy-trained CDR design models provably unable to generate antigen-specific sequences. AgForce's hyperbolic cross attention routes design decisions through antigen features and breaks the antibody framework shortcut path, representing a fundamental architectural fix rather than a training-data solution.
CODE: Not released

---
TITLE: ProtSent: Protein Sentence Transformers
AUTHORS: Dan Ofer et al.
SOURCE: arXiv | 2605.06830 | [**Link**](https://arxiv.org/abs/2605.06830)
TOPIC TAG: Protein LM
TLDR: Contrastive fine-tuning framework training ESM-2 on five protein-pair datasets (Pfam families, structural hard negatives, AlphaFold DB pairs, StringDB PPI, deep mutational scanning) with MultipleNegativesRankingLoss, improving 15 of 23 downstream tasks including +105% remote homology detection, +17% variant effect prediction, and +19.9% Recall@1 on SCOPe-40 structural retrieval.
WHY IT MATTERS: Protein language models produce per-residue embeddings optimized for token prediction, not whole-protein similarity; ProtSent adapts Sentence-BERT ideas to biology, enabling semantic nearest-neighbor search over proteins without fine-tuning. The multi-dataset contrastive strategy ensures coverage of evolutionary, structural, functional, and interaction-level similarity simultaneously—unlike prior work that targeted single-level alignment.
CODE: Not released

---
TITLE: PPI-Net connects molecular protein interactions to functional processes in disease
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.07838 | [**Link**](https://arxiv.org/abs/2605.07838)
TOPIC TAG: Architecture / Clinical ML
TLDR: Hierarchical GNN integrating STRING PPI networks with a multi-layer Reactome pathway hierarchy via graph attention propagates gene expression profiles from protein-interaction nodes up through functional biological programs, achieving >90% balanced accuracy on cancer type classification across 10 TCGA cohorts.
WHY IT MATTERS: Most cancer multi-omics classifiers treat genes as independent features, ignoring how mutations propagate through protein interaction networks to dysregulate biological pathways; PPI-Net's two-level hierarchy provides both high accuracy and interpretable pathway-level explanations that align with known oncogenic signaling cascades. The STRING-to-Reactome design mirrors real biological signal flow, making the learned weights scientifically meaningful for identifying driver pathway disruptions across cancer types.
CODE: Not released

---
TITLE: ProtDBench: A Unified Benchmark of Protein Binder Design and Evaluation
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.04118 | [**Link**](https://arxiv.org/abs/2605.04118)
TOPIC TAG: General ML
TLDR: Standardized protein binder design benchmark revealing that evaluation verifier choice (which structure predictor is used to filter designs) drives reported success rates more than the generative method itself, and that throughput-aware success metrics under fixed 24-hour compute budgets substantially re-rank method performance across ten diverse protein targets.
WHY IT MATTERS: Success rates reported across protein binder design studies are largely incomparable due to non-standardized evaluation, especially the choice of structure prediction model used as a computational filter; ProtDBench quantifies this verifier-dependent bias for the first time using a large wet-lab annotated dataset. The cluster-level diversity metric and throughput-aware evaluation are essential additions for deployment-realistic assessment, since real drug discovery workflows must balance sequence diversity and compute cost alongside success rate.
CODE: Not released

---
TITLE: Training distribution determines the ceiling of drug-blind cancer sensitivity prediction
AUTHORS: Taekyung Heo
SOURCE: arXiv | 2605.20885 | [**Link**](https://arxiv.org/abs/2605.20885)
TOPIC TAG: Clinical ML
TLDR: The standard global Pearson r metric for cancer drug sensitivity prediction is dominated by between-drug potency differences captured by a trivial drug-mean predictor; switching to per-drug Pearson r (within-drug cell ranking) reveals no drug molecular encoding outperforms cell-only features across four independent datasets, with mechanism-of-action as a training-distribution constraint mattering more than drug representation.
WHY IT MATTERS: Drug sensitivity prediction has appeared to improve significantly over the past several years due to a metric artifact—not genuine progress in predicting cell-specific drug responses—and this paper provides the field's most rigorous re-evaluation of that claim. The finding that training distribution (grouping by MoA) is the decisive factor rather than drug featurization redirects research toward experimental design of training cohorts rather than ever-more-complex molecular encoders.
CODE: Not released

---
TITLE: Multimodal Alignment Improves Generalizability of Genomic Biomarker Prediction in Computational Pathology
AUTHORS: Ekaterina Redekop et al.
SOURCE: arXiv | 2603.00193 | [**Link**](https://arxiv.org/abs/2603.00193)
TOPIC TAG: Clinical ML
TLDR: MARBLE aligns histopathology WSI representations with LLM-derived textual and protein language model-derived genomic biomarker representations via contrastive pretraining on the MSK-IMPACT 40,000+ patient cohort, enabling few-shot and zero-shot transfer to novel, out-of-distribution biomarkers not seen during training.
WHY IT MATTERS: Standard computational pathology models require biomarker-specific supervised training from scarce labeled slides, preventing rapid deployment for new genomic assays; MARBLE's alignment pretraining makes the histology encoder biologically informed so it recognizes morphological correlates of novel biomarkers with minimal labeled examples. Validation on real-world panel versioning—where biomarker sets change over clinical deployment—is a significant step toward production-grade genomic pathology AI.
CODE: Not released

---
TITLE: Highly Accurate Estimation of the Fold Accuracy of Protein Structural Models
AUTHORS: [First Author] et al.
SOURCE: bioRxiv | 2026.04.15.718808 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.04.15.718808v2)
TOPIC TAG: Protein LM / General ML
TLDR: DeepUMQA-Global is a deep learning quality assessment framework for estimating global fold accuracy of protein structural models, providing a critical quality control layer for structure prediction pipelines used in drug discovery and structural biology.
WHY IT MATTERS: Despite dramatic progress in structure prediction, no single model is uniformly reliable across all protein families, and downstream drug discovery workflows need accurate confidence scores to triage predictions; current pLDDT-style per-residue scores do not directly translate to whole-model fold accuracy. DeepUMQA-Global fills this gap, enabling automatic selection and ranking of structure prediction outputs before expensive downstream analyses like docking or design.
CODE: Not released

---
TITLE: From Enhanced Sampling to Human-Readable Representations of Protein Dynamics
AUTHORS: Souvik Mondal et al.
SOURCE: arXiv | 2605.03394 | [**Link**](https://arxiv.org/abs/2605.03394)
TOPIC TAG: General ML
TLDR: Combines enhanced MD sampling along frequency-selective anharmonic mode collective variables with weighted dynamic cross-correlation matrices post-hoc to extract physically interpretable residue-residue correlated motion networks from biased protein trajectories.
WHY IT MATTERS: Enhanced sampling overcomes timescale limitations of conventional MD but typically produces high-dimensional outputs that resist physical interpretation; this approach bridges physics-based enhanced sampling and interpretable network representations of allosteric communication. The ability to read off correlated motion graphs directly from biased trajectories makes enhanced sampling outputs compatible with graph neural network analyses and allosteric drug discovery pipelines.
CODE: Not released

---
TITLE: Deep-time consistency in proteome elemental composition across cellular and viral life
AUTHORS: L. Felipe Benites et al.
SOURCE: arXiv | 2605.19333 | [**Link**](https://arxiv.org/abs/2605.19333)
TOPIC TAG: Genomics
TLDR: Analysis of thousands of proteomes spanning all cellular domains and viral realms reveals strikingly consistent elemental stoichiometry (C, H, N, O, S, P ratios) despite vast evolutionary divergence and orders-of-magnitude variation in proteome size—more constrained than amino acid frequencies or physicochemical properties—and not explained by evolutionary relatedness, function, or amino acid usage alone.
WHY IT MATTERS: The convergence of viral proteomes onto the same elemental composition space as cellular organisms despite lacking a shared ancestor implies deep biochemical physics—likely protein folding thermodynamics—constrains viable proteome composition independent of evolution. This universal elemental constraint has practical implications for designing synthetic proteins with non-standard amino acids, and for using proteome stoichiometry as a biosignature in astrobiology and origin-of-life research.
CODE: Not released

---
TITLE: Crossing the 12,000-atom Barrier with Heterogeneous Quantum-Classical Supercomputing: Quantum Chemistry of Protein-Ligand Complexes
AUTHORS: [First Author] et al.
SOURCE: arXiv | 2605.01138 | [**Link**](https://arxiv.org/abs/2605.01138)
TOPIC TAG: General ML
TLDR: Hybrid quantum-classical workflow combining quantum embedding with optimized subspace diagonalization on two 156-qubit IBM quantum processors (9,200 circuits, 1.3×10⁹ measurement outcomes) and distributed classical supercomputing (Fugaku, Miyabi-G) achieves quantum chemistry-level binding energy calculations for protein-ligand complexes of 11,608 and 12,635 atoms—a >40× increase in tractable system size.
WHY IT MATTERS: Ab initio wavefunction accuracy for protein-ligand binding has been limited to tens of atoms; crossing the 10,000-atom barrier with experimental quantum hardware demonstrates that hybrid quantum-classical approaches are approaching biological relevance for drug affinity prediction. As quantum hardware scales, this workflow provides a template for eventually replacing classical force-field approximations with first-principles quantum chemistry in structure-based drug discovery.
CODE: Not released

---

==============================================================
## HIGHLIGHTS OF THE DAY
==============================================================

### 1. DPLM-Evo: Towards A Generative Protein Evolution Machine
**[arXiv 2605.00182](https://arxiv.org/abs/2605.00182)** | *ICML 2026 Accepted*

DPLM-Evo extends the discrete diffusion protein language model framework to explicitly model protein evolution, introducing a contextualized evolutionary noising kernel that produces biologically informed, context-dependent mutation patterns and supports substitutions, insertions, and deletions—not just masking. The key architectural insight is decoupling a fixed-length latent alignment space from the variable-length observed sequence space, making indel-aware generation tractable with negligible computational overhead compared to fixed-length masking diffusion. This is arguably the most complete computational model of protein evolution to date: DPLM-Evo achieves SOTA on single-sequence ProteinGym mutation effect prediction, generates explicit edit trajectories for evolutionary reconstruction, and enables in silico directed evolution with adaptive scaffold growth—all within a single unified framework accepted at ICML 2026.
**Code:** [Released at bytedance/dplm](https://github.com/bytedance/dplm)

---

### 2. AgForce: Antigen-conditioned Generative Antibody Design
**[arXiv 2605.21610](https://arxiv.org/abs/2605.21610)**

AgForce begins with a systematic audit showing that current antigen-conditioned antibody design models—despite nominally conditioning on antigen structure—actually exhibit three fundamental failure modes that make antigen-specific generation provably impossible with standard training. It then proposes a concrete architectural remedy: a GNN encoder-decoder with framework dropout (removing the antibody shortcut), gated bottlenecks (forcing signal to flow through antigen), and hyperbolic cross attention (ensuring antigen features dominate CDR generation). Evaluated on CHIMERA-Bench, AgForce achieves +8% amino acid recovery over the best sequence baseline while improving all interface quality metrics, demonstrating that the failure modes identified are not just theoretical but practically addressable.
**Code:** Not yet released

---

### 3. ProtDBench: Unified Benchmark Exposes Evaluation Crisis in Protein Binder Design
**[arXiv 2605.04118](https://arxiv.org/abs/2605.04118)**

ProtDBench reveals a critical evaluation problem in the protein binder design field: the choice of structure prediction model used as a computational verifier dominates reported success rates more than the choice of generative design method, making cross-study comparisons essentially meaningless under current practice. Using a large wet-lab annotated dataset across ten protein targets, the benchmark quantifies verifier-dependent bias, introduces throughput-aware metrics (success rate within 24-hour compute budget), and adds cluster-level diversity criteria—three dimensions completely absent from existing reporting standards. This work is significant not just for binder design but as a case study in how premature standardization of evaluation pipelines can create misleading leaderboard dynamics across computational biology.
**Code:** Not yet released

---

==============================================================
## DAILY STATS
==============================================================
- **Total papers found today:** 11
- **By topic:** Protein LM: 5 | Diffusion: 1 | Genomics: 1 | Architecture: 1 | General ML: 3 | Clinical ML: 3
- **Sources:** arXiv: 9 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- **Papers with code released:** 1 (DPLM-Evo)
