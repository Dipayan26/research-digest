# Research Digest — 2026-06-15

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Note: Direct access to arXiv/bioRxiv/HF listing pages and the Hugging Face MCP server was unavailable for this run (network egress blocked / connection lost), so coverage today relies on web-search discovery and is narrower than usual. Papers already covered in the 2026-06-13/14 digests were excluded.

---

---
TITLE: ProHiFlo: Hierarchical Flow Matching with Functional Guidance for De Novo Protein Generation
AUTHORS: Chuanzhen Wang et al.
SOURCE: arXiv | 2606.11243 | [**Link**](https://arxiv.org/abs/2606.11243)
TOPIC TAG: Flow Matching
TLDR: Introduces ProHiFlo, a hierarchical SE(3)-equivariant flow-matching framework that generates protein backbones coarse-to-fine (backbone geometry first, all-atom coordinates second) and steers generation with pretrained property predictors at inference time, reaching state-of-the-art unconditional and functional design results with 4x fewer sampling steps.
WHY IT MATTERS: Most flow-matching protein generators operate at a single resolution and need retraining to add new design objectives; ProHiFlo's coarse-to-fine multi-scale generation plus retraining-free functional guidance directly targets the compute cost and inflexibility that limit large-scale binder/enzyme design campaigns. Reported 58.9% success on enzyme active-site scaffolding suggests a meaningful jump for motif-conditioned design tasks.
CODE: Not released
---

---
TITLE: Mean Flow Distillation: Robust and Stable Distillation for Flow Matching Models
AUTHORS: An Zhao et al.
SOURCE: arXiv | 2606.11155 | [**Link**](https://arxiv.org/abs/2606.11155)
TOPIC TAG: Flow Matching
TLDR: Proposes Mean Flow Distillation (MFD), a distillation framework for flow-matching generative models that exploits the geometric structure of flow trajectories to act as a temporal low-pass filter, suppressing the high-frequency noise that destabilizes prior variational score-distillation approaches and enabling stable few-step sampling.
WHY IT MATTERS: Flow matching is now a dominant paradigm for protein backbone, RNA, and molecule generation, but multi-step ODE sampling is a major inference bottleneck for high-throughput design/screening loops. A more stable, general-purpose distillation recipe (accepted as an ICML 2026 poster, code released) is directly transferable to speeding up SE(3) flow-matching protein and ligand generators.
CODE: [**Code**](https://github.com/happyw1nd/MFD)
---

---
TITLE: GLACIER: A Multimodal Student-Teacher Foundation Model for Molecular Property Prediction
AUTHORS: Emily Nguyen et al.
SOURCE: arXiv | 2606.11382 | [**Link**](https://arxiv.org/abs/2606.11382)
TOPIC TAG: General ML
TLDR: GLACIER pretrains separate graph, SMILES-transformer, and physicochemical-descriptor encoders on 100k drug-like molecules, fuses them with a novel Finsler-geometry-aware module, and distills knowledge from larger teacher models (MiniMol, MolFormer) into one lightweight multimodal model via contrastive learning.
WHY IT MATTERS: Large unimodal molecular foundation models are increasingly expensive to train and serve; GLACIER shows a compact multimodal student can match or beat much larger teachers on property-prediction benchmarks, which is directly relevant to scaling ADMET/binding-affinity screening pipelines on modest compute. The Finsler-space fusion mechanism is also a novel general recipe for combining heterogeneous molecular modalities.
CODE: [**Code**](https://github.com/eemokey/glacier)
---

---
TITLE: ReasonAlloc: Hierarchical Decoding-Time KV Cache Budget Allocation for Reasoning Models
AUTHORS: Wenhao Liu et al.
SOURCE: arXiv | 2606.11164 | [**Link**](https://arxiv.org/abs/2606.11164)
TOPIC TAG: Architecture
TLDR: Proposes a training-free, two-level KV-cache compression scheme for long chain-of-thought reasoning models — an offline layer-wise "Reasoning Wave" preallocation plus an online head-wise reallocation to information-rich heads — that beats uniform-budget eviction baselines on long-CoT inference.
WHY IT MATTERS: As reasoning-augmented agentic pipelines for hypothesis generation and experimental-design planning in biology adopt long chain-of-thought decoding, KV-cache growth becomes a hard memory bottleneck; a training-free, architecture-aware allocation scheme is a drop-in efficiency gain for any such deployed reasoning LLM, including bio-domain copilots.
CODE: Not released
---

---
TITLE: Routing-Aware Expert Calibration for Machine Unlearning in Mixture-of-Experts Language Models
AUTHORS: Jingyi Xie et al.
SOURCE: arXiv | 2606.10338 | [**Link**](https://arxiv.org/abs/2606.10338)
TOPIC TAG: MoE
TLDR: Identifies that forget-data in MoE LLMs disproportionately activates a small subset of "forget-critical" experts that retain data barely touches, then proposes TRACE, which detects these experts from offline activation statistics and reweights retain-loss regularization per expert during unlearning.
WHY IT MATTERS: As MoE backbones become common for large bio/chem foundation models trained on proprietary or sensitive datasets (patient records, proprietary compound libraries), targeted unlearning without degrading general capability is an emerging compliance requirement; this is one of the first works to address unlearning specifically for sparse expert routing rather than dense models.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================
- TITLE: ProHiFlo: Hierarchical Flow Matching with Functional Guidance for De Novo Protein Generation
  Why this is the highlight: ProHiFlo tackles two persistent pain points in generative protein design at once — the cost of all-atom diffusion/flow sampling and the need to retrain models for every new design objective. Its coarse-to-fine SE(3)-equivariant architecture generates backbone topology first and refines atomic detail second, while plug-in pretrained predictors steer generation toward functional goals (e.g., enzyme active-site scaffolding) at inference time only. A reported 58.9% success rate on enzyme active-site scaffolding with 4x fewer sampling steps would be a notable practical gain for binder/enzyme design pipelines.
  Code/weights: Not released.

- TITLE: Mean Flow Distillation: Robust and Stable Distillation for Flow Matching Models
  Why this is the highlight: Flow matching underlies most state-of-the-art protein backbone, RNA and small-molecule generators, but iterative ODE sampling remains a throughput bottleneck for large design campaigns. MFD reframes distillation around the intrinsic geometry of flow trajectories, acting as a temporal low-pass filter that stabilizes training compared to prior score-distillation approaches — an ICML 2026 poster with code already released. Any group running high-throughput generative screening with flow-matching models could plug this in for faster few-step sampling.
  Code/weights: https://github.com/happyw1nd/MFD

- TITLE: GLACIER: A Multimodal Student-Teacher Foundation Model for Molecular Property Prediction
  Why this is the highlight: GLACIER demonstrates that a compact, multimodal (graph + SMILES + descriptor) student model distilled from larger teachers (MiniMol, MolFormer) via a novel Finsler-geometry fusion can match or exceed much larger unimodal molecular foundation models on property prediction. This is a practical recipe for cheaper, faster ADMET and binding-affinity screening at scale, and the code is already public.
  Code/weights: https://github.com/eemokey/glacier

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 5
- By topic: Protein LM: 0 | Diffusion/Flow Matching: 2 | Genomics: 0 | Architecture: 2 (incl. MoE: 1) | General ML: 1 | Clinical: 0
- Sources: arXiv: 5 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 2
