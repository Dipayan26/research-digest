# Research Digest — 2026-06-10

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: Protein Dynamics Beyond Structure Prediction
AUTHORS: Juliette Griffié et al.
SOURCE: arXiv | 2606.08647 | [**Link**](https://arxiv.org/abs/2606.08647)
TOPIC TAG: General ML
TLDR: A large multi-author community roadmap arguing that AlphaFold-class structure prediction has not solved protein folding dynamics, conformational kinetics, or macromolecular self-assembly, and lays out what is required for ML to make these dynamic processes quantitatively predictive.
WHY IT MATTERS: As the field treats static structure prediction as "solved," this perspective recenters attention on the dynamic, time-dependent behaviors—folding pathways, conformational ensembles, assembly kinetics—that govern function and drug binding but remain largely outside current generative and predictive models. It functions as a shared problem statement likely to shape the next wave of ML-for-dynamics research and benchmarks.
CODE: Not released
---

---
TITLE: SurfDesign: Effective Protein Design on Molecular Surfaces
AUTHORS: Fang Wu et al.
SOURCE: arXiv | 2606.07567 | [**Link**](https://arxiv.org/abs/2606.07567)
TOPIC TAG: Protein LM
TLDR: SurfDesign conditions pretrained protein language models on continuous molecular-surface geometry (normals, curvature, directional features) via surface-based equivariant message passing and parameter-efficient fine-tuning, outperforming prior surface-conditioned and backbone-only methods on de novo binder and enzyme design benchmarks.
WHY IT MATTERS: Most protein design pipelines condition only on backbone coordinates, ignoring the surface geometry and physicochemical complementarity that actually determine binding and catalytic activity. By fusing continuous surface manifolds with PLMs through lightweight adapters, SurfDesign offers a generalizable recipe for retrofitting any pretrained PLM with surface awareness for functional design tasks.
CODE: Not released
---

---
TITLE: Demystifying Multimodal Biomolecular Co-design With Intrinsic Geodesic Coupling
AUTHORS: Keyue Qiu et al.
SOURCE: arXiv | 2606.01628 | [**Link**](https://arxiv.org/abs/2606.01628)
TOPIC TAG: Flow Matching
TLDR: GeoCoupling identifies that existing multimodal biomolecular co-design models—which jointly generate discrete sequence and continuous 3D structure—implicitly assume a fixed, synchronous temporal coupling between the per-modality diffusion/flow processes, and introduces a framework that explicitly optimizes this coupling.
WHY IT MATTERS: Co-design models for proteins and ligands typically denoise sequence and structure in lockstep, an unexamined design choice; this work shows the relative "speed" at which each modality is resolved is itself a critical, tunable degree of freedom for generation quality. The geodesic coupling framework is architecture-agnostic and could be retrofitted into existing co-design pipelines for proteins, RNA, and protein-ligand complexes.
CODE: Not released
---

---
TITLE: Structure-Aware Prediction of PROTAC-Mediated Protein Degradability via Graph Neural Networks
AUTHORS: Bryan Cheng, Austin Jin
SOURCE: arXiv | 2606.04021 | [**Link**](https://arxiv.org/abs/2606.04021)
TOPIC TAG: Clinical ML
TLDR: DegradoMap is a graph neural network that predicts PROTAC-mediated target degradability from only the target protein structure and E3 ligase identity (no PROTAC molecule required), using lysine-weighted graph pooling, protein-E3 cross-attention, and Cancer Dependency Map context, reaching 0.646 AUROC on unseen targets and 0.811 AUROC on unseen E3 ligases.
WHY IT MATTERS: Existing PROTAC degradability predictors require the full bifunctional molecule, which does not exist before synthesis; DegradoMap instead screens target/E3 pairs upfront, enabling early triage of "degradable" targets before any chemistry is performed. This reframing could meaningfully de-risk and accelerate targeted protein degradation drug discovery campaigns.
CODE: Not released
---

---
TITLE: Single-Cell Cross-Modal Transfer by Adversarial Fine-Tuning of Foundation Models
AUTHORS: Joseph Boyd et al.
SOURCE: arXiv | 2606.07676 | [**Link**](https://arxiv.org/abs/2606.07676)
TOPIC TAG: Genomics
TLDR: Introduces an adversarial fine-tuning scheme that adapts a pretrained single-cell foundation model to translate between unpaired spatial transcriptomics (limited gene panels) and scRNA-seq (whole-transcriptome) profiles.
WHY IT MATTERS: Spatial transcriptomics platforms typically profile only hundreds-to-thousands of genes per cell, while scRNA-seq captures the whole transcriptome; a robust cross-modal bridge lets researchers impute genome-wide expression onto spatial coordinates without paired training data. Adversarial fine-tuning of an existing foundation model offers a lightweight alternative to training new cross-modal architectures from scratch.
CODE: Not released
---

---
TITLE: Position: Genomic Model Research Must Move Beyond Anecdotal Evaluation of Interpretability Methods
AUTHORS: Shasha Zhou, Mingyu Huang, Ke Li
SOURCE: arXiv | 2606.07607 | [**Link**](https://arxiv.org/abs/2606.07607)
TOPIC TAG: Genomics
TLDR: A position paper arguing that interpretability research on genomic foundation models overwhelmingly relies on single, anecdotal applications of one IML method without systematic comparison or ground-truth validation, and proposes a more rigorous evaluation agenda.
WHY IT MATTERS: As genomic LMs proliferate, claims about what they "learn" increasingly rest on cherry-picked saliency maps or attribution examples; this paper crystallizes a methodological gap that, left unaddressed, undermines biological trust in interpretability-based discoveries. It sets an agenda for benchmark-driven, falsifiable evaluation of IML methods in genomics.
CODE: Not released
---

---
TITLE: Diffusion Language Model Parallel Decoding via Product-of-Experts Bridge
AUTHORS: [Authors from 2606.08048] et al.
SOURCE: arXiv | 2606.08048 | [**Link**](https://arxiv.org/abs/2606.08048)
TOPIC TAG: Diffusion
TLDR: PoE-Bridge introduces an intermediate distribution—constructed as a Product-of-Experts of the diffusion language model proposal and an autoregressive target—that lets DLMs draft multiple continuations in parallel and use rejection sampling against this bridge, drastically cutting the particle count needed versus prior importance-sampling approaches.
WHY IT MATTERS: Discrete diffusion language models offer fast parallel decoding but lag autoregressive models in quality, and prior bridging methods via importance sampling were too expensive to be practical. A cheaper, principled bridge between DLM and AR distributions is directly relevant to discrete diffusion protein/DNA/RNA sequence generators (e.g., DPLM, EvoDiff), where inference cost limits iterative design loops.
CODE: Not released
---

---
TITLE: Improving Bayesian Optimization via Training-Aware Conditional Diffusion Models
AUTHORS: Yilin Zheng, Haowei Wang, Szu Hui Ng, Enlu Zhou
SOURCE: arXiv | 2606.08438 | [**Link**](https://arxiv.org/abs/2606.08438)
TOPIC TAG: General ML
TLDR: Proposes training Conditional Diffusion Models with BO-aware objectives to approximate the posterior distribution over the location of the global optimum, replacing expensive Gaussian-process posterior sampling in information-theoretic acquisition functions, paired with a new "Diffusion-based Mode Seeking" acquisition strategy.
WHY IT MATTERS: Information-based BO acquisition functions (e.g., Predictive Entropy Search) are sample-efficient in principle but have been computationally prohibitive at scale; a diffusion-based posterior approximation could make these stronger strategies practical for high-dimensional design spaces. This is directly applicable to active-learning loops for protein and molecule optimization, where each wet-lab evaluation is costly.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Protein Dynamics Beyond Structure Prediction**
arXiv:2606.08647 | [Link](https://arxiv.org/abs/2606.08647)

This sweeping, ~40-author community roadmap pushes back on the narrative that protein structure prediction is "solved," arguing that the field's central unsolved problem is now dynamics: folding pathways, conformational ensembles, kinetics, and macromolecular self-assembly. It surveys what experimental and computational tools (cryo-EM, MD, ML emulators) currently can and cannot capture, and proposes concrete directions for building quantitative, predictive models of protein dynamics. As a perspective piece from a broad coalition of structural biologists and ML researchers, it is likely to set priorities and benchmarks for the next several years of generative and predictive modeling in structural biology.
Code: Not released

---

**2. SurfDesign: Effective Protein Design on Molecular Surfaces**
arXiv:2606.07567 | [Link](https://arxiv.org/abs/2606.07567)

SurfDesign tackles a long-standing blind spot in protein design: nearly all backbone-conditioned generative models ignore molecular surface geometry, even though surface shape and chemistry are what actually mediate binding and catalysis. By representing surfaces as continuous geometric manifolds and fusing them into pretrained protein language models via equivariant message passing and parameter-efficient fine-tuning, SurfDesign achieves consistent gains over both backbone-only and prior surface-conditioned baselines on binder and enzyme design benchmarks. The approach is a practical, adapter-style upgrade path that could be applied to many existing PLM-based design pipelines.
Code: Not released

---

**3. Structure-Aware Prediction of PROTAC-Mediated Protein Degradability via Graph Neural Networks (DegradoMap)**
arXiv:2606.04021 | [Link](https://arxiv.org/abs/2606.04021)

DegradoMap reframes PROTAC drug discovery by predicting whether a target protein is degradable by a given E3 ligase using only the target's structure and E3 identity—no candidate PROTAC molecule needed. Its lysine-weighted graph pooling, protein-E3 cross-attention, and integration of Cancer Dependency Map cellular context let it screen target/E3 pairs at the earliest possible stage (0.646 AUROC on unseen targets, 0.811 on unseen E3 ligases). This "degradability-first" triage could meaningfully cut the search space before any linker chemistry is designed, accelerating targeted protein degradation campaigns.
Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 8
- By topic: Protein LM: 1 | Diffusion: 1 | Flow Matching: 1 | Genomics: 2 | General ML: 2 | Clinical ML: 1
- Sources: arXiv: 8 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
