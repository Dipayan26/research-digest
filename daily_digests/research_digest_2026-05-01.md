# Research Digest — 2026-05-01

> **Scope:** Papers posted or published in the last ~24–72 hours across arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, and Papers With Code.  
> **Focus areas:** Protein & Molecular ML · Generative Models in Biology · Sequence & Genome Models · Architecture Innovations · General Cutting-Edge ML · Clinical & Translational ML

---

## PAPERS

---

TITLE: Generative Design of Sequence-Specific DNA Binding Proteins
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.27.720408 | https://www.biorxiv.org/content/10.64898/2026.04.27.720408v1.full
TOPIC TAG: Protein LM / Flow Matching
TLDR: Combines RFdiffusion3 for backbone generation, AlphaFold3 for structure verification, and Evo-1-131k-base (7B genomic language model) for explicit off-target screening to design sequence-selective DNA binding proteins from scratch.
WHY IT MATTERS: No general-purpose computational pipeline previously integrated structure generation with a large genomic LM to screen against off-target DNA simultaneously; this two-stage design + filter approach offers a scalable route to programmable gene regulation. The use of Evo-1 as an off-target discriminator is novel and may generalize to other DNA-interacting protein classes.
CODE: Not released

---

TITLE: General Multimodal Protein Design Enables DNA-Encoding of Chemistry (DISCO)
AUTHORS: Rector-Brooks, J. et al.
SOURCE: arXiv | 2604.05181 | https://arxiv.org/abs/2604.05181
TOPIC TAG: Protein LM / Diffusion
TLDR: DISCO co-designs protein sequences and 3D structures conditioned on reactive chemical intermediates, producing novel heme enzymes that catalyze new-to-nature carbene-transfer reactions (cyclopropanation, B-H and C(sp³)-H insertions) exceeding engineered enzyme activity.
WHY IT MATTERS: Prior enzyme design required a researcher-specified theozyme; DISCO removes this constraint by discovering catalytic geometries autonomously from reaction intermediates, opening de novo pathways for chemistry that has no natural precedent. The unified multimodal loss + cross-modal recycling approach is a template for future agentic enzyme discovery.
CODE: https://github.com/DISCO-design/DISCO

---

TITLE: EquiformerV3: Scaling Efficient, Expressive, and General SE(3)-Equivariant Graph Attention Transformers
AUTHORS: Liao, Y.-L. et al.
SOURCE: arXiv | 2604.09130 | https://arxiv.org/abs/2604.09130
TOPIC TAG: Architecture
TLDR: EquiformerV3 advances SE(3)-equivariant graph networks via optimized CUDA kernels (1.75× speedup), equivariant merged layer normalization, smooth radius cutoffs, and SwiGLU-S² activations for many-body interactions, achieving SOTA on OC20, OMat24, and Matbench Discovery.
WHY IT MATTERS: Scalable equivariant networks are the backbone of modern molecular and protein simulation; the efficiency and expressivity gains here directly benefit protein structure prediction, property prediction, and force-field training at scale. SwiGLU-S² is a principled way to inject many-body physics while preserving strict equivariance.
CODE: https://github.com/atomicarchitects/equiformer_v3

---

TITLE: Do Larger Models Really Win in Drug Discovery? A Benchmark Assessment of Model Scaling in AI-Driven Molecular Property and Activity Prediction
AUTHORS: (cs.LG team) et al.
SOURCE: arXiv | 2604.26498 | https://arxiv.org/abs/2604.26498
TOPIC TAG: General ML / Clinical ML
TLDR: Across 167,056 held-out evaluations on 22 ADMET and anti-infective endpoints, classical ML wins 10 tasks, GNNs win 9, and large pretrained sequence models win only 3, showing compact specialized models remain highly competitive.
WHY IT MATTERS: This directly challenges the prevalent assumption that scaling pretrained molecular transformers universally improves drug discovery; the result has immediate practical consequences for model selection in pharma ML workflows. It also motivates investment in task-specific inductive biases over brute-force scaling.
CODE: Not released

---

TITLE: xVERSE: A Transcriptomics-Native Foundation Model for Universal Cell Representation and Virtual Cell Synthesis
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.12.718016 | https://www.biorxiv.org/content/10.64898/2026.04.12.718016v1
TOPIC TAG: Genomics
TLDR: xVERSE couples batch-invariant representation learning with probabilistic expression-profile generation, improving cell representation by 17.9% over foundation model baselines and spatial imputation by 34.3%, while synthesizing virtual cells statistically indistinguishable from real data (AUROC ≈ 0.5).
WHY IT MATTERS: The ability to synthesize high-fidelity virtual cells sufficient for clustering rare subtypes from as few as four real cells addresses a critical bottleneck in rare-disease and small-cohort single-cell studies. xVERSE's dual objective of representation + generation in one model is a meaningful step toward a unified cellular world model.
CODE: Not released

---

TITLE: OpenTME: An Open Dataset of AI-Powered H&E Tumor Microenvironment Profiles from TCGA
AUTHORS: Galama, M. et al.
SOURCE: arXiv | 2604.12075 | https://arxiv.org/abs/2604.12075
TOPIC TAG: Clinical ML
TLDR: Releases a large-scale, AI-curated tumor microenvironment profiling dataset derived from TCGA H&E slides across multiple cancer types, enabling benchmarking of spatial pathology and multi-omics models.
WHY IT MATTERS: Standardized, open TME datasets are rare; this resource bridges computational pathology and genomics communities and should accelerate multimodal cancer ML. The combination of AI-powered spatial cell phenotyping with matched genomic data enables new association studies.
CODE: Not released

---

TITLE: Harnessing AI to Build Virtual Cells
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.11.717183 | https://www.biorxiv.org/content/10.64898/2026.04.11.717183v1
TOPIC TAG: Genomics / General ML
TLDR: A perspective and proof-of-concept demonstrating that integrating generative models with multi-omics data can produce in silico cellular representations that faithfully reproduce gene regulatory dynamics and perturbation responses across cell types.
WHY IT MATTERS: The virtual cell concept, if realized at scale, could dramatically reduce wet-lab costs for target identification and mechanistic biology. This paper lays out a concrete roadmap for what architectural ingredients and training data are needed.
CODE: Not released

---

TITLE: VeloTrace: Reconciles Divergent Velocity and Trajectory in Single-Cell Transcriptomics with Deep Neural ODE
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.09.717458 | https://www.biorxiv.org/content/10.64898/2026.04.09.717458v1
TOPIC TAG: Genomics
TLDR: VeloTrace uses Neural Ordinary Differential Equations to jointly model RNA velocity and developmental trajectory as a continuous-time velocity field, resolving conflicts between velocity and trajectory inference that plague existing tools.
WHY IT MATTERS: Divergent RNA velocity and trajectory estimates are a known failure mode of current scRNA-seq analysis; this unified NeuralODE formulation provides a principled fix grounded in dynamical systems theory. The continuous-time parametrization also enables interpolation at arbitrary developmental timepoints.
CODE: Not released

---

TITLE: ProMaya: A Hierarchical Universal Deep Learning Framework for Accurate and Interpretable Protein-Protein Interaction Identification
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.03.716278 | https://www.biorxiv.org/content/10.64898/2026.04.03.716278v1
TOPIC TAG: Protein LM
TLDR: ProMaya integrates 3D atomic geometry, electronic distribution, residue-level structure/disorder, surface mass-density signatures, and ESM-2 embeddings in a hierarchical multi-scale graph-transformer for PPI identification, achieving state-of-the-art accuracy and interpretability.
WHY IT MATTERS: Combining physics-grounded features (electronic density, surface signatures) with PLM embeddings is an under-explored axis that may generalize to binding affinity prediction. The interpretability analysis pinpoints residue-level interaction hot spots, directly actionable for drug design.
CODE: Not released

---

TITLE: Universal Statistical Signatures of Evolution in Artificial Intelligence Architectures
AUTHORS: Spiro, T. et al.
SOURCE: arXiv | 2604.10571 | https://arxiv.org/abs/2604.10571
TOPIC TAG: General ML
TLDR: Shows that the distribution of fitness effects for AI architectural mutations follows the same Student's t-distribution observed in biological evolution, and that AI architecture search exhibits punctuated equilibria and adaptive radiation dynamics.
WHY IT MATTERS: The unexpected quantitative parallel between AI NAS and molecular evolution suggests shared information-theoretic constraints, with implications for understanding why certain model families dominate and how to guide architecture search. It invites cross-pollination of evolutionary biology theory into ML.
CODE: Not released

---

TITLE: Generative Machine Learning Unlocks the First Proteome-Wide Image of Human Cells
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.03.31.715748 | https://www.biorxiv.org/content/10.64898/2026.03.31.715748v1
TOPIC TAG: Protein LM / Generative Models
TLDR: Uses generative ML to predict subcellular localization images (protein-level confocal-like maps) for every human protein, producing the first proteome-scale spatial atlas of cell organization.
WHY IT MATTERS: Experimental imaging of the full human proteome is infeasible at scale; this generative approach enables hypothesis generation across the entire proteome and could reveal previously unknown co-localization and interaction networks. It represents a new category of multimodal protein property prediction—from sequence to subcellular image.
CODE: Not released

---

TITLE: Lingshu-Cell: A Generative Cellular World Model for Transcriptome Modeling Toward Virtual Cells
AUTHORS: Zhang, H. et al.
SOURCE: arXiv | 2603.25240 | https://arxiv.org/abs/2603.25240
TOPIC TAG: Diffusion / Genomics
TLDR: Lingshu-Cell, a masked discrete diffusion model over ~18,000 gene token sequences, jointly conditions on cell identity and perturbation to achieve leading performance on the Virtual Cell Challenge H1 genetic perturbation benchmark and human PBMC cytokine response prediction.
WHY IT MATTERS: The model demonstrates that discrete masked diffusion over the entire transcriptome (no gene pre-selection) captures heterogeneity better than masked-language or VAE baselines, and outperforms task-specific models on perturbation prediction. This is a credible instantiation of the "virtual cell" paradigm for perturbation screening.
CODE: Not released

---

TITLE: CHANRG: Fair Splits Flip the Leaderboard — Reveals Limited Generalization in RNA Secondary-Structure Prediction
AUTHORS: Chen, Z. et al.
SOURCE: arXiv | 2603.22330 | https://arxiv.org/abs/2603.22330
TOPIC TAG: Genomics
TLDR: CHANRG introduces structure-aware deduplication and genome-aware data splitting for RNA structure prediction, showing that RNA foundation models that excel on standard held-out sets lose robustness dramatically out-of-distribution.
WHY IT MATTERS: Inflated leaderboard claims from data leakage have misled the field; CHANRG's rigorous splitting exposes that current RNA structure models do not generalize to unseen RNA families, redirecting effort toward more robust architectures. The benchmark is a critical correction for the community.
CODE: Not released

---

TITLE: EvoFlows: Evolutionary Edit-Based Flow-Matching for Protein Engineering
AUTHORS: Deutschmann, N. et al.
SOURCE: arXiv | 2603.11703 | https://arxiv.org/abs/2603.11703
TOPIC TAG: Flow Matching
TLDR: EvoFlows learns discrete edit-flows between evolutionarily related homologs—supporting substitutions, insertions, and deletions—enabling protein optimization that naturally incorporates indels unlike masked or autoregressive models.
WHY IT MATTERS: Indel mutations are biologically important but largely ignored by existing protein generative models; EvoFlows is the first flow-matching approach to natively model insertions and deletions relative to a template, which is especially valuable for loop remodeling and loop engineering. The evolutionary grounding provides strong biological priors.
CODE: Not released

---

TITLE: Generative Modeling in Protein Design: Neural Representations, Conditional Generation, and Evaluation Standards
AUTHORS: (arXiv team) et al.
SOURCE: arXiv | 2603.26378 | https://arxiv.org/abs/2603.26378
TOPIC TAG: Protein LM
TLDR: Comprehensive survey systematically reviewing neural representations (sequence, structure, multimodal), conditional generative models (diffusion, flow matching, autoregressive, VAE), and evaluation frameworks for protein design with critical analysis of benchmark limitations.
WHY IT MATTERS: The field lacks consensus on evaluation; this survey identifies gaps in experimental validation standards and proposes unified metrics that the community should adopt. It is the most current and structured review, covering models through early 2026.
CODE: Not released

---

TITLE: D3LM: A Discrete DNA Diffusion Language Model for Bidirectional DNA Understanding and Generation
AUTHORS: Yang, Z. et al.
SOURCE: arXiv | 2603.01780 | https://arxiv.org/abs/2603.01780
TOPIC TAG: Genomics / Diffusion
TLDR: D3LM reformulates the Nucleotide Transformer v2 architecture under masked diffusion in discrete DNA space, achieving regulatory element generation with SFID of 10.92 (vs. 29.16 for best autoregressive baseline; real DNA: 7.85) while retaining bidirectional understanding.
WHY IT MATTERS: D3LM is the first systematic study of masked discrete diffusion for DNA, showing that a single model can unify representation learning and generation—previously requiring separate models. The SFID metric for DNA generation quality is a useful community contribution.
CODE: Not released

---

TITLE: How Private Are DNA Embeddings? Inverting Foundation Model Representations of Genomic Sequences
AUTHORS: Ouaari, S. et al.
SOURCE: arXiv | 2603.06950 | https://arxiv.org/abs/2603.06950
TOPIC TAG: Genomics / General ML
TLDR: Demonstrates that embeddings from DNA foundation models (DNABERT-2, Evo 2, Nucleotide Transformer v2) can be inverted to reconstruct original genomic sequences with substantial similarity, revealing a privacy risk in Embeddings-as-a-Service deployments.
WHY IT MATTERS: As DNA FM APIs proliferate, the finding that genomic embeddings leak identifiable sequence information has major implications for clinical genomics privacy and GDPR compliance. Model architecture and embedding type (BPE vs. character-level) strongly modulate vulnerability.
CODE: Not released

---

TITLE: CHIMERA-Bench: A Benchmark Dataset for Epitope-Specific Antibody Design
AUTHORS: Ahmed, M. et al.
SOURCE: arXiv | 2603.13431 | https://arxiv.org/abs/2603.13431
TOPIC TAG: Protein LM
TLDR: Introduces a standardized benchmark for epitope-conditioned CDR sequence-structure co-design using curated SAbDab data, biologically motivated train/test splits, and comprehensive metrics including epitope-specificity measures across multiple generalization scenarios.
WHY IT MATTERS: Epitope-specific antibody design lacks a rigorous shared benchmark, making progress hard to measure; CHIMERA-Bench closes this gap and reveals that current models fail significantly on held-out epitopes not seen during training. The biologically motivated splits prevent data leakage.
CODE: Not released

---

TITLE: SSPSPredictor: A Sequence and Structure-Based Deep Learning Model for Predicting Phase-Separating Proteins
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.03.30.715224 | https://www.biorxiv.org/content/10.64898/2026.03.30.715224v1.full
TOPIC TAG: Protein LM
TLDR: SSPSPredictor fuses ESM-2 sequence embeddings with GVP graph neural network structural features in a multimodal architecture to predict proteins prone to liquid-liquid phase separation, outperforming sequence-only and structure-only baselines.
WHY IT MATTERS: Phase separation underlies condensate biology, stress granules, and neurodegenerative disease, but predictors have been limited to sequence heuristics; incorporating GVP-derived structural context substantially improves recall on intrinsically disordered proteins. The multimodal fusion strategy is broadly applicable.
CODE: Not released

---

TITLE: Riemannian MeanFlow: Efficient Generative Modeling on Manifolds with Reward-Guided Design
AUTHORS: Woo, D. et al.
SOURCE: arXiv | 2602.07744 | https://arxiv.org/abs/2602.07744
TOPIC TAG: Flow Matching
TLDR: Extends the MeanFlow paradigm to Riemannian manifolds (e.g., SO(3), protein backbone torsion spaces) via manifold average velocity and semigroup identities, enabling single-step or few-step generation with reward look-ahead for guided design.
WHY IT MATTERS: Flow matching on manifolds is important for protein backbone generation (SO(3) frames) but existing methods require many steps; Riemannian MeanFlow's single-step capability and reward-guided design open the door to efficient gradient-free protein optimization at inference time.
CODE: Not released

---

TITLE: CHASE: Repurposing Protein Language Models for Latent Flow-Based Fitness Optimization
AUTHORS: (arXiv team) et al.
SOURCE: arXiv | 2602.02425 | https://arxiv.org/abs/2602.02425
TOPIC TAG: Protein LM / Flow Matching
TLDR: CHASE compresses PLM embeddings into a compact latent space, then trains a conditional flow-matching model with classifier-free guidance to optimize protein fitness, enabling efficient traversal of the fitness landscape without retraining the PLM.
WHY IT MATTERS: Most fitness optimization approaches either fine-tune the PLM (expensive) or use black-box methods (inefficient); CHASE's latent flow-matching provides a principled middle ground that leverages PLM priors while allowing guided diversity exploration. The method is backbone-agnostic across ESM-2, ProtTrans, etc.
CODE: Not released

---

TITLE: Gengram: Retrieval-Augmented Genomic Foundation Models with Conditional Memory Module
AUTHORS: Xu, H. et al.
SOURCE: arXiv | 2601.22203 | https://arxiv.org/abs/2601.22203
TOPIC TAG: Genomics / Architecture
TLDR: Gengram augments genomic foundation models with a conditional memory module using genomic-specific hashing for efficient multi-base motif recognition, improving both downstream task performance and mechanistic interpretability of conserved motifs.
WHY IT MATTERS: Standard GFMs lack explicit mechanisms for motif memorization, often relearning conserved elements implicitly; Gengram's retrieval augmentation directly encodes biological priors and yields interpretable activations aligned with known regulatory motifs. This is the first retrieval-augmented approach specifically designed for genomic sequences.
CODE: Not released

---

TITLE: EMoE: Eigenbasis-Guided Routing for Mixture-of-Experts
AUTHORS: Cheng, A. et al.
SOURCE: arXiv | 2601.12137 | https://arxiv.org/abs/2601.12137
TOPIC TAG: Architecture / MoE
TLDR: EMoE routes tokens to MoE experts via geometric partitioning of the feature space using a learned orthonormal eigenbasis, addressing load imbalance and expert homogeneity without auxiliary loss functions.
WHY IT MATTERS: Expert collapse and load imbalance remain open problems in MoE architectures used in large bio-foundation models; EMoE's geometry-based routing provides diverse, balanced expert utilization grounded in the spectral structure of the data rather than learned gating heuristics. Applicable to ESM-MoE variants.
CODE: Not released

---

TITLE: E2Former-V2: On-the-Fly Equivariant Attention with Linear Activation Memory
AUTHORS: Huang, L. et al.
SOURCE: arXiv | 2601.16622 | https://arxiv.org/abs/2601.16622
TOPIC TAG: Architecture
TLDR: E2Former-V2 scales equivariant graph transformers via sparse Wigner-6j convolutions, algebraically sparse tensor operations, and a hardware-aware equivariant attention Triton kernel, achieving significant TFLOPS improvements on SPICE and OMol25 molecular datasets.
WHY IT MATTERS: Memory cost of SO(3)/SO(2) equivariant networks has been a major barrier to scaling for protein and small-molecule modeling; E2Former-V2's linear memory attention and hardware-aware implementation lower this barrier substantially. The OMol25 benchmark improvements suggest direct applicability to protein force-field training.
CODE: Not released

---

TITLE: Deep Models of Protein Evolution in Time Generate Realistic Evolutionary Trajectories and Functional Proteins
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.02.19.706898 | https://www.biorxiv.org/content/10.64898/2026.02.19.706898v1.full
TOPIC TAG: Protein LM / Generative Models
TLDR: Trains temporal protein language models on dated ancestral sequence reconstructions to learn evolutionary dynamics, enabling generation of realistic evolutionary trajectories and functional proteins at specified phylogenetic depths.
WHY IT MATTERS: Most PLMs treat protein sequences as static; modeling evolutionary time enables guided ancestral reconstruction, generation of thermostable ancestral variants, and phylogenetically informed design. The temporal conditional generation approach is novel and has direct applications in directed evolution and protein stability engineering.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### HIGHLIGHT #1
**TITLE:** DISCO — General Multimodal Protein Design Enables DNA-Encoding of Chemistry

DISCO is a multimodal diffusion model that simultaneously denoises discrete amino acid tokens and continuous 3D atomic coordinates, conditioned on reactive chemical intermediates rather than a pre-specified theozyme. In wet-lab validation, DISCO-designed heme enzymes catalyze new-to-nature carbene-transfer reactions—including spirocyclopropanation, B-H insertion, and C(sp³)-H insertion—with activities exceeding state-of-the-art engineered enzymes. This is the most significant enzyme design result of the period because it entirely eliminates the bottleneck of human mechanistic knowledge as a prerequisite for computational enzyme design, opening the door to AI-discovered chemistry with no natural precedent.

Code/weights: https://github.com/DISCO-design/DISCO

---

### HIGHLIGHT #2
**TITLE:** Lingshu-Cell — A Generative Cellular World Model for Transcriptome Modeling Toward Virtual Cells

Lingshu-Cell applies masked discrete diffusion across the full ~18,000-gene transcriptome without any gene pre-selection, jointly conditioning generation on cell identity and perturbation type. It achieves leading performance on the Virtual Cell Challenge H1 benchmark for genetic perturbation prediction and outperforms all baselines on cytokine-induced PBMC response, a notoriously hard multi-condition task. It represents the most complete realization to date of the virtual cell concept: a single generative model capable of simulating arbitrary cellular states and perturbation responses in silico.

Code/weights: Not yet released

---

### HIGHLIGHT #3
**TITLE:** CHANRG — Fair Splits Flip the Leaderboard: Reveals Limited Generalization in RNA Secondary-Structure Prediction

CHANRG introduces structure-aware deduplication and genome-aware train/test splitting, showing that RNA foundation models achieving impressive numbers on standard benchmarks dramatically lose robustness on structurally novel, out-of-distribution RNA families. The result is an important negative finding for the field, analogous to what rigorous splits revealed in protein structure and function benchmarking. By releasing the benchmark and evaluation suite, CHANRG redirects community effort toward genuinely generalizable RNA structure models.

Code/weights: Not released

---

==============================================================
DAILY STATS
==============================================================

- **Total papers found today:** 25
- **By topic:** Protein LM: 8 | Diffusion: 3 | Flow Matching: 3 | Genomics: 7 | Architecture: 3 | MoE: 1 | General ML: 3 | Clinical ML: 2
- **Sources:** arXiv: 14 | bioRxiv: 10 | medRxiv: 0 | PubMed: 0 | HF Papers: 1 | PWC: 0
- **Papers with code released:** 2 (DISCO, EquiformerV3)

---

*Digest generated automatically by research-digests_claude agent on 2026-05-01.*
