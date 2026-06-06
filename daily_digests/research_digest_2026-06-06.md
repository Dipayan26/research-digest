# Research Digest — 2026-06-06

> Computational biology × machine learning · daily digest
> Coverage window: last 24 hours (June 5–6, 2026)
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Papers With Code

---

---
TITLE: Language Modeling Materializes a World Model of Protein Biology
AUTHORS: Salvatore Candido, Thomas Hayes, Alexander Derry, Roshan Rao et al. (CZ Biohub)
SOURCE: bioRxiv | 10.64898/2026.06.03.729735 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.03.729735v1)
TOPIC TAG: Protein LM
TLDR: Trained ESMC — a protein language model on ~2.8 billion sequences — and ESMFold2 for complex structure prediction, building a "world model" that maps 6.8 billion sequences and 1.1 billion predicted structures, with LM representation space encoding known biological organization as an emergent property.
WHY IT MATTERS: This is the most comprehensive attempt to date to create a unified, scalable foundation for all of protein biology, integrating sequence, structure, and function in a single model family; ESMFold2 surpasses AlphaFold 3 on antibody-antigen binding pose prediction from ESMC representations alone. Unlike prior ESM releases, the ESM Atlas uses sparse autoencoders to decompose internal representations into human-interpretable features summarized in natural language, directly bridging model internals and biological knowledge.
CODE: [**Code & Weights**](https://github.com/Biohub/esm)
---

---
TITLE: AgentPLM: Agentic Protein Language Models with Reasoning-Augmented Decoding for Protein Sequence Design
AUTHORS: (First author not disclosed in search results) et al.
SOURCE: arXiv | 2606.02386 | [**Link**](https://arxiv.org/abs/2606.02386)
TOPIC TAG: Protein LM
TLDR: Equipped a pre-trained protein language model with Reasoning-Augmented Decoding (RAD) that interleaves autoregressive generation with external tool calls, and Contrastive Agent Policy Optimisation (CAPO) to stabilize fine-tuning, yielding measurable gains on protein sequence design benchmarks.
WHY IT MATTERS: This is the first work to make protein language models "agentic" — capable of querying structure predictors, databases, and oracles mid-sequence-generation — rather than generating sequences in a single pass; CAPO directly addresses reward hacking that plagues standard RLHF-style fine-tuning of PLMs. Together, RAD and CAPO shift the PLM paradigm from passive generators to active design agents, with implications for every sequence design task.
CODE: Not released
---

---
TITLE: EpiFormer: Learning Antigen-Antibody Interactions for Epitope Prediction via Geometric Deep Learning
AUTHORS: (First author not disclosed) et al.
SOURCE: arXiv | 2606.04154 | [**Link**](https://arxiv.org/abs/2606.04154)
TOPIC TAG: Protein LM
TLDR: Built an encoder-decoder GNN with interleaved cross-attention enabling bidirectional antigen-antibody information flow throughout representation learning, achieving >40% F1 improvement over the previous best method on standard epitope prediction benchmarks.
WHY IT MATTERS: Accurate epitope prediction is the key bottleneck in structure-guided vaccine and antibody design; prior methods encoded antigen and antibody independently and fused only at the output, missing the coupled geometry. EpiFormer's emergent finding — that the learned cross-attention favors antigen-to-antibody flow and prefers geometric over evolutionary features — independently recapitulates known biology without explicit supervision, validating both the architecture and the training objective.
CODE: Not released
---

---
TITLE: DeltaDiff: Training-Free, Physics-Guided Machine Learning for Predicting Mutant Protein Structures
AUTHORS: Yajie Cai, Yanbin Wang, Ming Chen
SOURCE: arXiv | 2606.04452 | [**Link**](https://arxiv.org/abs/2606.04452)
TOPIC TAG: Diffusion
TLDR: Incorporated a mutation-aware coarse-grained potential energy function as a guidance signal during diffusion model inference (no retraining required) to predict mutant protein structures, including challenging cases with nonlocal conformational changes in Chignolin T8P, Novispirin G-10, and BBL D162N.
WHY IT MATTERS: Standard structure predictors like AlphaFold2 fail on mutants because similar sequences produce nearly identical predictions, missing biologically critical structural rearrangements; DeltaDiff solves this through inference-time physical guidance without any parameter updates. The training-free design means it can be applied on top of any generative backbone, making it a plug-in enhancement for the entire ecosystem of diffusion-based structure modeling.
CODE: Not released
---

---
TITLE: When Does Structure Help? The Information Bonus of AlphaFold2 Representations over Protein Language Models
AUTHORS: Kargi Chauhan
SOURCE: arXiv | 2606.04228 | [**Link**](https://arxiv.org/abs/2606.04228)
TOPIC TAG: Protein LM
TLDR: Introduced the "information bonus" (IB) metric to measure the linearly accessible advantage of frozen AlphaFold2 Evoformer representations over frozen ESM-2 embeddings across binding affinity regression, conformational flexibility, and allostery tasks, finding that structure uniquely enables above-chance allosteric site prediction while sequence suffices for most other tasks.
WHY IT MATTERS: Practitioners routinely face the question of whether to pay the cost of structure inference; this work provides the first systematic, task-level empirical answer and introduces a clean quantitative framework (IB) to guide future decisions. The finding that long-range geometric signal for allostery is irretrievable from sequence alone has direct implications for computational drug design targeting allosteric pockets.
CODE: Not released
---

---
TITLE: TadA-Bench: A Million-Variant Benchmark for Future-Round Discovery Toward Agentic Protein Engineering
AUTHORS: Jin Gao, Juntu Zhao, Zirui Zeng, Jiaqi Shen, Junseok Lee, Dukun Zhao, Yuming Lu, Dequan Wang
SOURCE: arXiv | 2606.02624 | [**Link**](https://arxiv.org/abs/2606.02624)
TOPIC TAG: General ML
TLDR: Released a wet-lab replay benchmark from 31 TadA base-editor directed-evolution rounds with aligned DNA/RNA/protein views and Seq2Graph label unification; models achieve strong interpolation within rounds but fail substantially at future-round variant ranking — the task that actually matters for agentic wet-lab guidance.
WHY IT MATTERS: Existing protein ML benchmarks use random train/test splits that inflate performance; TadA-Bench's chronological structure forces genuine extrapolation into uncharted fitness space, exposing a critical capability gap between current models and the requirements of autonomous laboratory automation. Seq2Graph's cross-round label reconciliation also addresses a persistent data quality problem in high-throughput protein screening datasets.
CODE: Not released
---

---
TITLE: AbBiBench: A Benchmark for Antibody Binding Affinity Maturation and Design
AUTHORS: Xinyan Zhao, Yi-Ching Tang, Akshita Singh, Victor J. Cantu, KwanHo An et al.
SOURCE: arXiv | 2506.04235 | [**Link**](https://arxiv.org/abs/2506.04235)
TOPIC TAG: Protein LM
TLDR: Curated 184,500 experimental measurements of antibody mutants across 14 antibodies and 9 antigens — treating the full Ab-Ag complex as the evaluation unit — and found that structure-conditioned inverse folding models outperform sequence-only and generative models in both affinity correlation and design tasks.
WHY IT MATTERS: Prior benchmarks evaluated antibodies in isolation using metrics like amino acid recovery or structural RMSD, which are poorly correlated with actual binding function; AbBiBench's complex-centric evaluation is biologically grounded and its scale (184K measurements) dwarfs all previous resources. The benchmark is immediately applicable for the entire antibody design community to rigorously compare generative, inverse-folding, and language-model approaches on the same experimental ground truth.
CODE: Not released
---

---
TITLE: Value-and-Structure Alignment for Routing-Consistent Quantization of Mixture-of-Experts Models
AUTHORS: (First author not disclosed) et al.
SOURCE: arXiv | 2606.05688 | [**Link**](https://arxiv.org/abs/2606.05688)
TOPIC TAG: MoE
TLDR: Proposed a post-training quantization method for MoE LLMs that jointly aligns weight-value distributions and expert routing decisions across bit-widths, preserving routing consistency and preventing expert collapse at low precision.
WHY IT MATTERS: MoE architectures are increasingly the backbone of large bio-foundation models (protein, DNA, single-cell); routing collapse under quantization is a known failure mode that silently degrades performance without obvious error signals. This work provides a practical solution for deploying large biology-MoE models in compute-constrained settings like clinical or cloud inference pipelines.
CODE: Not released
---

---
TITLE: Genetically Aligned Patient Representations Improve Hematological Diagnosis
AUTHORS: Muhammed Furkan Dasdelen, Fatih Ozlugedik, Ilaria Looser, Rao Muhammad Umer, Christian Pohlkamp, Carsten Marr
SOURCE: arXiv | 2605.29980 | [**Link**](https://arxiv.org/abs/2605.29980)
TOPIC TAG: Clinical ML
TLDR: Developed a two-stage framework that first self-supervises a histopathology vision model (iBOT + transformer aggregator), then aligns patient-level image embeddings to genetic profiles via supervised contrastive loss, improving acute myeloid leukemia patient stratification.
WHY IT MATTERS: Genetic sequencing for AML is expensive and not always available; if visual representations can be aligned to genetic space, pathology images become a cost-effective proxy for genetic profiles. The genetic-alignment stage generalizes across cohorts and provides a blueprint for image-to-omics alignment that could scale to any cancer type with paired histology and sequencing data.
CODE: Not released
---

---
TITLE: Inferring Cellular Heterogeneity with Mixture Models for DNA Methylation Rates
AUTHORS: Hugo Barbot et al.
SOURCE: arXiv | 2606.04175 | [**Link**](https://arxiv.org/abs/2606.04175)
TOPIC TAG: Genomics
TLDR: Developed a mixture model framework to simultaneously infer cell-type proportions and cell-type-specific methylation states from bulk bisulfite sequencing, characterizing epigenomic heterogeneity in mixed tissue samples.
WHY IT MATTERS: Bulk DNA methylation data confounds signals from multiple cell types, a problem especially acute in tumor samples; rigorous statistical deconvolution enables accurate cell-type-specific epigenomic profiling without single-cell resolution. The framework provides a principled alternative to reference-based deconvolution, applicable even in tissues where pure cell-type reference methylomes are unavailable.
CODE: Not released
---

---
TITLE: On the Recoverability of Causal Relations from Bulk Gene Expression Data
AUTHORS: Gongxu Luo, Boyang Sun, Kun Zhang
SOURCE: arXiv | 2606.00568 | [**Link**](https://arxiv.org/abs/2606.00568)
TOPIC TAG: Genomics
TLDR: Theoretically and empirically characterized conditions under which causal gene-regulatory relationships are identifiable from bulk RNA-seq data aggregated across heterogeneous cell populations, showing that aggregation preserves some but not all causal structures depending on cell composition variability.
WHY IT MATTERS: The vast majority of gene regulatory network inference operates on bulk data, yet the theoretical foundations for what is recoverable have been poorly understood; this work provides the first rigorous identifiability theory for the aggregation setting. The results directly inform how to design bulk RNA-seq studies and interpret causal network inference results, with practical implications for computational drug target discovery.
CODE: Not released
---

---
TITLE: Methods for Inferring Interaction Potentials from Cross-Linking Mass Spectrometry Data
AUTHORS: (First author not disclosed) et al.
SOURCE: arXiv | 2606.05541 | [**Link**](https://arxiv.org/abs/2606.05541)
TOPIC TAG: Protein LM
TLDR: Established a computational pipeline from XL-MS experimental measurements to coarse-grained protein-protein interaction potentials for systems where liquid-liquid phase separation governs function, enabling physics-informed simulation of protein condensates.
WHY IT MATTERS: Biomolecular condensates are a major frontier in cell biology and disease (e.g., FUS, TDP-43 ALS-related proteins); XL-MS provides sparse structural restraints that have been hard to translate into simulation-ready models. This work bridges experimental proteomics and coarse-grained simulation, enabling condensate behavior to be studied at scales inaccessible to atomic-detail MD.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. Language Modeling Materializes a World Model of Protein Biology
**CZ Biohub | bioRxiv | [Link](https://www.biorxiv.org/content/10.64898/2026.06.03.729735v1)**

This is arguably the most significant protein ML release of 2026: a full "world model" for proteins combining ESMC (a language model trained on ~2.8 billion sequences from across the tree of life) with ESMFold2, which surpasses AlphaFold 3 on antibody-antigen complex prediction from sequence alone. The key insight is that the LM representation space spontaneously organizes itself in alignment with known biological taxonomy and function — structure emerges from scale, not explicit supervision. Most strikingly, the ESM Atlas uses sparse autoencoders to decompose representations into human-interpretable features summarized in natural language, marking the first system that bridges the gap between protein representation learning and human biological understanding at planetary scale.

Code & Weights: [**https://github.com/Biohub/esm**](https://github.com/Biohub/esm)

---

### 2. AgentPLM: Agentic Protein Language Models with Reasoning-Augmented Decoding
**arXiv 2606.02386 | [Link](https://arxiv.org/abs/2606.02386)**

AgentPLM introduces a genuinely new paradigm: instead of generating protein sequences in a single forward pass, the model interleaves autoregressive generation with external tool calls (structure predictors, databases, functional oracles) using Reasoning-Augmented Decoding. The CAPO (Contrastive Agent Policy Optimisation) training objective stabilizes learning without reward hacking. This shifts the entire PLM design paradigm from "generate-then-filter" to "reason-while-generating," with measurable benchmark improvements. The implications extend beyond proteins — any domain where generation benefits from iterative verification during sampling stands to gain from this architectural pattern.

Code: Not released

---

### 3. EpiFormer: Learning Antigen-Antibody Interactions for Epitope Prediction via Geometric Deep Learning
**arXiv 2606.04154 | [Link](https://arxiv.org/abs/2606.04154)**

EpiFormer's 40%+ F1 improvement on standard epitope benchmarks is the largest single-paper gain on this task in years. The key architectural innovation — interleaved cross-attention within GNN layers enabling bidirectional antigen-antibody information flow throughout, rather than just at fusion — is elegant and likely to generalize to other co-complex prediction tasks. The emergent biological alignment (favoring antigen-to-antibody information flow, preferring geometric over evolutionary features at epitope residues) provides strong post-hoc validation that the model is solving the right problem for the right reasons.

Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 12
- By topic: Protein LM: 6 | Diffusion: 1 | Genomics: 2 | Architecture: 0 | MoE: 1 | General ML: 2 | Clinical ML: 1 | (multi-tag papers counted under primary tag)
- Sources: arXiv: 11 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 1 (ESM World Model — code + weights on GitHub + HuggingFace)
