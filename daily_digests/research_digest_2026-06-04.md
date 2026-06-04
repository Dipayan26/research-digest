# Research Digest — 2026-06-04

*Computational Biology × Machine Learning | Daily Paper Digest*

---

---
TITLE: Demystifying Multimodal Biomolecular Co-design With Intrinsic Geodesic Coupling
AUTHORS: Keyue Qiu et al.
SOURCE: arXiv | 2606.01628 | [**Link**](https://arxiv.org/abs/2606.01628)
TOPIC TAG: Flow Matching
TLDR: GeoCoupling introduces a framework that learns optimal temporal couplings between modalities (sequence and structure) during joint biomolecular generation by following geodesic paths in transport-cost space rather than naive diagonal synchronization.
WHY IT MATTERS: Existing co-design models enforce fixed synchronous coupling between modalities, introducing high-variance supervision and inconsistent intermediate states; GeoCoupling makes the coupling itself a learnable degree of freedom. By framing the optimal coupling trajectory as a geodesic over a cost manifold, the framework consistently improves modality consistency and co-design quality on structure-based drug design and protein co-design benchmarks.
CODE: Not released
---

---
TITLE: Probe Before You Edit: Probing-Guided Molecular Optimization for LLM Agents in Structure-Based Drug Design
AUTHORS: Zaifei Yang et al.
SOURCE: arXiv | 2606.00555 | [**Link**](https://arxiv.org/abs/2606.00555)
TOPIC TAG: Clinical ML
TLDR: PROBE is a probing-guided framework that queries how a target pocket responds to controlled analog edits before selecting an optimization direction, enabling LLM agents to jointly improve binding affinity and drug-likeness rather than trading one off against the other.
WHY IT MATTERS: Single-step molecular editing by LLM agents rarely achieves simultaneous gains on both binding affinity and druggability—a failure mode that PROBE quantifies with two new diagnostic metrics. By mimicking the iterative probe-then-edit workflow of medicinal chemists, PROBE outperforms existing LLM-agent pipelines on structure-based drug design benchmarks, representing a more principled integration of chemical intuition into generative drug discovery.
CODE: Not released
---

---
TITLE: Enhancing Protein-Protein Interaction Prediction with Hierarchical Motif-based Multimodal Protein Embedding
AUTHORS: Zaifei Yang et al.
SOURCE: arXiv | 2606.02629 | [**Link**](https://arxiv.org/abs/2606.02629)
TOPIC TAG: Protein LM
TLDR: MMM-PPI constructs protein embeddings in a bottom-up, three-scale fashion—micro (residue sequence, structure, function), meso (spatially-informed motif), and macro (full protein)—outperforming state-of-the-art PPI prediction models, especially under challenging data splits.
WHY IT MATTERS: Prior PPI models overlook the meso-scale motif organization that critically regulates protein-protein interactions, and fail to fuse all three modalities coherently. MMM-PPI addresses both limitations simultaneously, showing marked gains under cross-species and limited-data evaluation conditions that mimic real-world experimental settings.
CODE: Not released
---

---
TITLE: TadA-Bench: A Million-Variant Benchmark for Future-Round Discovery Toward Agentic Protein Engineering
AUTHORS: Jin Gao et al.
SOURCE: arXiv | 2606.02624 | [**Link**](https://arxiv.org/abs/2606.02624)
TOPIC TAG: General ML
TLDR: TadA-Bench provides a million-variant wet-lab replay benchmark from 31 rounds of TadA base-editor directed evolution, where the task is to rank variants appearing only in future rounds given earlier experimental data—exposing a critical gap between interpolation and extrapolation for protein fitness models.
WHY IT MATTERS: Standard random-split evaluations grossly overestimate model performance; TadA-Bench's future-round task exposes that even strong models struggle with temporal generalization. By providing aligned DNA, RNA, and protein views with a Seq2Graph label-unification pipeline, it sets a rigorous standard for agentic protein engineering systems that must plan forward experiments.
CODE: Not released
---

---
TITLE: On the Recoverability of Causal Relations from Bulk Gene Expression Data
AUTHORS: Gongxu Luo et al.
SOURCE: arXiv | 2606.00568 | [**Link**](https://arxiv.org/abs/2606.00568)
TOPIC TAG: Genomics
TLDR: The authors formally derive necessary and sufficient conditions for recovering causal gene-regulatory relations from bulk RNA-seq, showing that causal recoverability holds only under linear aggregations (sum/mean) coupled with affine structural equations—a result with broad implications for GRN inference.
WHY IT MATTERS: A large body of computational GRN inference methods assumes causal identifiability from bulk data without theoretical justification; this work proves that cell-level aggregation is a lossy, non-invertible step that can break causal recovery in general. The derivation provides both positive guarantees (when bulk inference works) and negative examples (when it provably fails), guiding future method design for gene regulatory network learning.
CODE: Not released
---

---
TITLE: VibeProteinBench: An Evaluation Benchmark for Language-interfaced Vibe Protein Design
AUTHORS: Hyunjin Seo et al.
SOURCE: arXiv | 2605.10978 | [**Link**](https://arxiv.org/abs/2605.10978)
TOPIC TAG: General ML
TLDR: VibeProteinBench is a language-interfaced benchmark probing generalist protein design capabilities across three complementary stages—recognition, engineering, and generation—via open-ended natural-language constraints, revealing significant capability gaps in current protein LLMs.
WHY IT MATTERS: Existing protein design benchmarks either restrict evaluation to a single task type or require structured inputs, preventing holistic assessment of language-driven models. VibeProteinBench unifies the full design workflow and uses expert-curated mechanistic rationales for in silico validation, providing the first standardized framework for comparing protein design models under flexible natural-language intent.
CODE: Not released
---

---
TITLE: ProtDBench: A Unified Benchmark of Protein Binder Design and Evaluation
AUTHORS: Cong Liu et al.
SOURCE: arXiv | 2605.04118 | [**Link**](https://arxiv.org/abs/2605.04118)
TOPIC TAG: Protein LM
TLDR: ProtDBench introduces throughput-aware metrics and standardized evaluation protocols across 10 diverse protein targets, revealing that verifier choice introduces substantial bias and that existing binder design methods diverge significantly under fair comparison.
WHY IT MATTERS: In silico protein binder design metrics are not standardized, making cross-study comparison unreliable; ProtDBench demonstrates that filtering rules, success definitions, and model-as-verifier choices can shift apparent success rates dramatically. The 24-hour budget-normalized metric and wet-lab annotated dataset enable reproducible, practically meaningful comparison of generative binder design approaches.
CODE: Not released
---

---
TITLE: MIMIC: A Generative Multimodal Foundation Model for Biomolecules
AUTHORS: Miles Cranmer et al. (PolymathicAI)
SOURCE: arXiv | 2604.24506 | [**Link**](https://arxiv.org/abs/2604.24506)
TOPIC TAG: Architecture
TLDR: MIMIC is a split-track encoder-decoder foundation model trained on LORE—a new dataset linking nucleic acid, protein, evolutionary, structural, regulatory, and semantic modalities—achieving state-of-the-art splicing prediction and matching or exceeding best-available models on 6/7 tasks of mRNABench.
WHY IT MATTERS: Most biological foundation models are unimodal or at best bimodal, missing the coupled constraints across the central dogma that determine biological function. MIMIC's partially observed conditioning enables generation or reconstruction of any missing modality given any observed subset, providing the first truly integrative generative model spanning genome, transcriptome, and proteome simultaneously.
CODE: [**Code**](https://github.com/PolymathicAI/MIMIC)
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. MIMIC: A Generative Multimodal Foundation Model for Biomolecules (arXiv:2604.24506)**
MIMIC is the first foundation model to span nucleic acids, proteins, structural, evolutionary, regulatory, and semantic modalities within a single unified architecture. Trained on the newly curated LORE dataset, it uses a split-track encoder-decoder that conditions on any observed subset of modalities and reconstructs or generates missing ones—including isoform-aware splicing prediction and performance matching or exceeding the best available public models on 6/7 tasks of mRNABench. This represents a paradigm shift from modality-specific models toward a truly integrative biological foundation model, with released code enabling immediate community adoption.
Code/weights: [**Code**](https://github.com/PolymathicAI/MIMIC)

**2. GeoCoupling — Demystifying Multimodal Biomolecular Co-design With Intrinsic Geodesic Coupling (arXiv:2606.01628)**
GeoCoupling addresses a previously overlooked degree of freedom in joint sequence-structure generative modeling: the temporal coupling between modalities during flow matching or diffusion. Rather than synchronizing modalities on a fixed diagonal schedule, GeoCoupling learns geodesic coupling trajectories in transport-cost space, resulting in more coherent and consistent intermediate states during co-design. Applied to protein-ligand co-design and protein sequence-structure generation, it outperforms parallel-marginal baselines, offering a principled theoretical and practical advance for any multimodal generative task in computational biology.
Code: Not released

**3. TadA-Bench: A Million-Variant Benchmark for Future-Round Discovery Toward Agentic Protein Engineering (arXiv:2606.02624)**
TadA-Bench derives from 31 rounds of real directed-evolution experiments on the TadA adenine base editor, providing over one million labeled variants with aligned DNA, RNA, and protein views. Its defining innovation is framing evaluation as future-round ranking: models must identify high-fitness variants appearing only in later experimental rounds given only earlier data, exposing a dramatic gap between interpolation ability and genuine forward-planning capability. This benchmark is positioned to become a key standard as the field moves toward autonomous, lab-in-the-loop agentic protein engineering.
Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 8
- By topic: Protein LM: 2 | Flow Matching: 1 | Genomics: 1 | Architecture: 1 | General ML: 3 | Clinical ML: 1
- Sources: arXiv: 8 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 1 | PWC: 0
- Papers with code released: 1 (MIMIC)
