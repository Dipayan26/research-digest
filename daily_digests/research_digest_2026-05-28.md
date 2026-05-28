# Research Digest — 2026-05-28

> Auto-generated daily digest for a computational biology researcher specialising in ML for biological sequence and structure modelling.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, HF Papers, Papers With Code, Semantic Scholar.

---

---
TITLE: Co-folding model guided by structural proteomics
AUTHORS: Alon Shtrikman et al.
SOURCE: arXiv | 2605.26192 | [**Link**](https://arxiv.org/abs/2605.26192)
TOPIC TAG: Protein LM
TLDR: AIMS-Fold steers inference-time diffusion sampling for protein complex structure prediction using differentiable physical potentials derived from XL-MS spatial restraints and HDX-MS solvent-accessibility profiles, outperforming unguided Boltz-2 on antibody and PROTAC induced-proximity targets.
WHY IT MATTERS: Protein generative models excel at single-chain prediction but routinely fail to capture the correct conformational state of protein complexes—the critical bottleneck for antibody and PROTAC design. AIMS-Fold is the first framework to close the loop between a wet-lab structural proteomics experiment and inference-time diffusion guidance, creating a practical experimental-computational co-design pipeline that purely computational models cannot replicate.
CODE: Not released
---

---
TITLE: EvoStruct: Bridging Evolutionary and Structural Priors for Antibody CDR Design via Protein Language Model Adaptation
AUTHORS: (Shtrikman et al. first author not confirmed) et al.
SOURCE: arXiv | 2605.21485 | [**Link**](https://arxiv.org/abs/2605.21485)
TOPIC TAG: Protein LM
TLDR: EvoStruct connects a frozen protein language model to an E(3)-equivariant GNN via cross-attention, using progressive PLM unfreezing and R-Drop consistency regularisation to eliminate vocabulary collapse in antibody CDR design, improving sequence recovery by 16% and reducing perplexity by 43% over the best GNN baselines on Chimera-Bench.
WHY IT MATTERS: GNN-only CDR design methods converge to over-predict tyrosine and glycine, discarding functionally important residues—a failure that stems from learning amino-acid distributions de novo from limited structural data. EvoStruct is the first method to directly diagnose and resolve vocabulary collapse via a structured PLM-structure adapter, rather than treating it as an acceptable design artefact.
CODE: Not released
---

---
TITLE: Atom-level Protein Representation Learning Improves Protein Structure Prediction
AUTHORS: (First author unconfirmed) et al.
SOURCE: arXiv | 2605.22133 | [**Link**](https://arxiv.org/abs/2605.22133)
TOPIC TAG: Protein LM
TLDR: TriProRep pretrains protein representations by jointly recovering three aligned residue-level views—amino-acid identity, backbone geometry, and local full-atom geometry encoded via VQ-VAE tokenisers—corrupted with generator-level augmentations, and introduces RepSP to benchmark representations specifically in structure-predictive settings.
WHY IT MATTERS: Existing protein pretraining largely optimises for function-annotation tasks rather than structure-prediction conditioning; TriProRep is the first to target structure-predictive representation quality through three-way multi-view self-supervised learning at atomic resolution. The RepSP benchmark addresses a critical evaluation gap by measuring representation utility for downstream structure generation rather than classification.
CODE: Not released
---

---
TITLE: Protein Thoughts: Interpretable Reasoning with Tree of Thoughts and Embedding-Space Flow Matching for Protein-Protein Interaction Discovery
AUTHORS: Kingsley Yeon et al.
SOURCE: arXiv | 2605.21522 | [**Link**](https://arxiv.org/abs/2605.21522)
TOPIC TAG: Flow Matching
TLDR: Protein Thoughts decomposes PPI discovery into four auditable biological signals—sequence similarity, structural complementarity, interface balance, and chemical compatibility—explored via Tree of Thoughts with flow matching in embedding space, achieving a 76% improvement in mean best-binder rank (11.2 vs 47.7) on SHS148k and a Micro-F1 of 91.08 on binding prediction.
WHY IT MATTERS: Standard PPI prediction models are black boxes that produce opaque rankings, creating a barrier to adoption for biologists who need mechanistic justification. The modular architecture lets researchers trace exactly which biochemical signal drove a prediction, opening the door to hypothesis-driven experimental follow-up.
CODE: Not released
---

---
TITLE: Drifting Objectives for Refining Discrete Diffusion Language Models
AUTHORS: (First author unconfirmed) et al.
SOURCE: arXiv | 2605.19470 | [**Link**](https://arxiv.org/abs/2605.19470)
TOPIC TAG: Text Diffusion
TLDR: TokenDrift lifts categorical DDLM predictions to soft-token features in a frozen semantic space, applies anti-symmetric drifting objectives, and back-propagates stop-gradient feature targets to model logits—reducing Generation-PPL at 4 NFEs by 89% over matched continuation baselines for both masked and uniform-state diffusion backbones.
WHY IT MATTERS: Anti-symmetric drifting has been shown to improve continuous diffusion generation but was inapplicable to discrete tokens due to non-differentiability; TokenDrift solves this bottleneck via a soft-embedding interface. The 89% PPL reduction at just 4 denoising steps brings discrete diffusion into practical parity with autoregressive models for low-compute inference, with direct implications for biological sequence generation.
CODE: Not released
---

---
TITLE: Forward-Learned Discrete Diffusion: Learning how to noise to denoise faster
AUTHORS: Grigory Bartosh et al.
SOURCE: arXiv | 2605.18204 | [**Link**](https://arxiv.org/abs/2605.18204)
TOPIC TAG: Diffusion
TLDR: FLDD replaces the fixed Markovian forward schedule of discrete diffusion with a learnable non-Markovian noising process, allowing the factorised reverse model to match the learned forward distribution and enabling high-quality few-step generation.
WHY IT MATTERS: Standard discrete diffusion fixes a uniform or mask-based noising schedule that may not be optimal for the data domain, forcing long sampling chains to compensate; FLDD demonstrates that co-learning the noising process and the denoiser substantially reduces the number of function evaluations needed. This concept is directly applicable to biological sequences where optimal noise schedules likely differ across protein families, regulatory DNA, and RNA.
CODE: Not released
---

---
TITLE: Reading the Cell, Designing the Cure: Perturbation-Conditioned Molecular Diffusion for Function-Oriented Drug Design
AUTHORS: Ziyu Xu et al.
SOURCE: arXiv | 2605.15243 | [**Link**](https://arxiv.org/abs/2605.15243)
TOPIC TAG: Diffusion
TLDR: CURE formalises Transcriptome-based Drug Design (TBDD) as a generative inverse problem, employing a multi-resolution transcriptome-guided diffusion framework to generate drug candidates conditioned on desired gene-expression state transitions without requiring explicit target structure.
WHY IT MATTERS: Conventional structure-based drug design is inapplicable when targets are undruggable or disease phenotypes emerge from complex pathway dysregulation; CURE operationalises transcriptomic perturbation signatures as molecule-generation conditioning, enabling phenotypic drug discovery at generative scale. Bridging the chemistry-transcriptomics domain gap with multi-resolution conditioning is a principled advance over prior ligand-only or target-only methods.
CODE: Not released
---

---
TITLE: Support Before Frequency in Discrete Diffusion
AUTHORS: Adrian Müller et al.
SOURCE: arXiv | 2605.13999 | [**Link**](https://arxiv.org/abs/2605.13999)
TOPIC TAG: Diffusion
TLDR: Proves that the exact reverse process in uniform and masking discrete diffusion decomposes into a two-scale hierarchy—the leading term determines whether an edit moves toward the data support (grammatical validity), and the subleading term determines relative probability within that support (token frequency)—with formal bounds characterising this separation in the small-noise regime.
WHY IT MATTERS: This theoretical decomposition explains why discrete diffusion models struggle with rare amino acids and low-frequency regulatory motifs: the model must first learn support membership before it can learn fine-grained frequencies, a curriculum implicit in the diffusion process. The insight motivates explicit training interventions—such as curriculum masking or hierarchical objectives—that could substantially improve generation fidelity for rare biological tokens.
CODE: Not released
---

---
TITLE: ELF: Embedded Language Flows
AUTHORS: Keya Hu et al.
SOURCE: arXiv | 2605.10938 | [**Link**](https://arxiv.org/abs/2605.10938)
TOPIC TAG: Text Diffusion
TLDR: ELF is a continuous-time Flow Matching model for language that operates entirely in token embedding space until a shared-weight final projection to discrete tokens, achieving competitive perplexity with discrete diffusion baselines while enabling classifier-free guidance for controllable generation.
WHY IT MATTERS: Continuous diffusion language models have lagged behind discrete variants due to the embedding-to-token mismatch; ELF resolves this with a minimal architectural change that directly unlocks the rich toolkit of continuous-domain guidance developed for images and video. For biology, classifier-free guidance over continuous sequence embeddings enables scalable conditional generation of protein and nucleic-acid sequences conditioned on structural or functional targets.
CODE: [**Code**](https://github.com/lillian039/ELF)
---

---
TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: Siddhant Dutta et al.
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: SoftBlobGIN projects ESM-2 residue embeddings onto contact graphs and applies differentiable Gumbel-softmax substructure pooling via a lightweight GIN, recovering biologically meaningful active-site residues, spatially localised functional clusters, and catalytic contact patterns as post-hoc auditable structural explanations.
WHY IT MATTERS: Protein language models achieve state-of-the-art function prediction but encode structural and evolutionary signals in opaque dense latent spaces, limiting scientific trust and hypothesis generation. This plug-and-play interpretability framework requires no structural fine-tuning of the base PLM and produces structural explanations that align with known biochemical annotations, bridging the gap between sequence-level and structure-level reasoning.
CODE: Not released
---

---
TITLE: GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
AUTHORS: Michael Lindsey
SOURCE: arXiv | 2605.07608 | [**Link**](https://arxiv.org/abs/2605.07608)
TOPIC TAG: Genomics
TLDR: GoForth formulates RNA inverse design as a conditional generative problem with cleanly separated components—a sequence prior, a forward folding sampler, and a reward/constraint likelihood—enabling multi-constraint design (target secondary structure, fixed bases, coding restrictions) with full inverse folding as a special case.
WHY IT MATTERS: Existing RNA design methods entangle structure, sequence, and function constraints into monolithic models, precluding systematic compositional improvement; GoForth's modular separation means each component can be upgraded independently as better folding oracles or language models emerge. The explicit treatment of coding constraints for mRNA therapeutics fills a gap underserved by current RNA design tools.
CODE: [**Code**](https://github.com/quantumtative/GoForth)
---

---
TITLE: ProteinJEPA: Latent prediction complements protein language models
AUTHORS: Dan Ofer et al.
SOURCE: arXiv | 2605.07554 | [**Link**](https://arxiv.org/abs/2605.07554)
TOPIC TAG: Protein LM
TLDR: Masked-position MLM+JEPA—predicting latent targets only at masked positions while retaining the MLM cross-entropy objective—outperforms MLM-only continuation under matched wall-clock budget, winning 10–11 out of 16 downstream tasks (frozen linear probes + zero-shot fold retrieval) at ESM2-35M and ESM2-150M scale.
WHY IT MATTERS: JEPA-style objectives transformed vision pretraining (V-JEPA) but their role in protein language modelling had not been rigorously characterised; this work identifies that all-position latent prediction hurts but masked-position JEPA reliably helps. The result provides a practical plug-in recipe for upgrading existing ESM2-scale models without architectural changes or additional compute.
CODE: Not released
---

---
TITLE: EquiformerV3: Scaling Efficient, Expressive, and General SE(3)-Equivariant Graph Attention Transformers
AUTHORS: Yi-Lun Liao et al.
SOURCE: arXiv | 2604.09130 | [**Link**](https://arxiv.org/abs/2604.09130)
TOPIC TAG: Architecture
TLDR: EquiformerV3 improves SE(3)-equivariant GNNs through optimised implementation, improved layer normalisation, SwiGLU-S² activations, and smooth radius cutoffs, achieving state-of-the-art on OC20, OMat24, and Matbench Discovery for 3D atomic-scale property prediction.
WHY IT MATTERS: SE(3)-equivariant architectures underpin protein structure prediction, docking, and molecular property modelling; EquiformerV3 demonstrates that systematic architectural engineering—not just scale—yields meaningful improvements in accuracy and efficiency. The efficiency gains enable application to larger biomolecular complexes and tighter integration as the score network inside diffusion-based structure generators.
CODE: Not released
---

---
TITLE: Fair splits flip the leaderboard: CHANRG reveals limited generalization in RNA secondary-structure prediction
AUTHORS: Zhiyuan Chen et al.
SOURCE: arXiv | 2603.22330 | [**Link**](https://arxiv.org/abs/2603.22330)
TOPIC TAG: Genomics
TLDR: CHANRG introduces structure-aware deduplication and genome-aware split design for RNA secondary-structure benchmarking, showing that current foundation models lose robustness outside the training distribution despite achieving high held-out accuracy on leaky splits.
WHY IT MATTERS: The RNA structure prediction field has been systematically misled by train/test splits that leak structural information, making leaderboard gains appear larger than they are; CHANRG resets evaluation on genuinely fair data splits and reveals that higher held-out accuracy can correlate with worse OOD robustness—a critical warning for applied deployment. This parallels the data-leakage crises seen in protein fitness and genomics benchmarks.
CODE: Not released
---

---
TITLE: How Private Are DNA Embeddings? Inverting Foundation Model Representations of Genomic Sequences
AUTHORS: Sofiane Ouaari et al.
SOURCE: arXiv | 2603.06950 | [**Link**](https://arxiv.org/abs/2603.06950)
TOPIC TAG: Genomics
TLDR: Model inversion attacks on mean-pooled embeddings from DNABERT-2, Evo 2, and Nucleotide Transformer v2 demonstrate that original genomic sequences can be reconstructed with significant similarity, with vulnerability varying markedly by model architecture and tokenisation scheme.
WHY IT MATTERS: As DNA foundation model APIs and Embeddings-as-a-Service platforms proliferate, this work reveals that shared embeddings may not adequately de-identify sensitive personal genomic data—a privacy risk with direct legal and ethical implications. The systematic model-by-model vulnerability comparison provides a practical security audit framework for any organisation deploying genomic embedding services.
CODE: Not released
---

---
TITLE: D3LM: A Discrete DNA Diffusion Language Model for Bidirectional DNA Understanding and Generation
AUTHORS: (First author unconfirmed) et al.
SOURCE: arXiv | 2603.01780 | [**Link**](https://arxiv.org/abs/2603.01780)
TOPIC TAG: Genomics
TLDR: D3LM reformulates DNA language modelling as masked diffusion in discrete DNA space, enabling a single model to perform both bidirectional sequence understanding and de novo sequence generation, and provides the first systematic comparison of tokenisation schemes, masking schedules, and sampling strategies for genomic diffusion models.
WHY IT MATTERS: Prior DNA models split into bidirectional BERT-style encoders for understanding and causal decoders for generation, requiring separate models for different tasks; D3LM unifies both capabilities under masked diffusion. The systematic design-choice study fills a methodological gap and provides actionable guidance for future genomic diffusion model development.
CODE: Not released
---

---
TITLE: MMAI Gym for Science: Training Liquid Foundation Models for Drug Discovery
AUTHORS: Maksim Kuznetsov et al.
SOURCE: arXiv | 2603.03517 | [**Link**](https://arxiv.org/abs/2603.03517)
TOPIC TAG: Clinical ML
TLDR: A molecular Liquid Foundation Model trained on specialised molecular data formats and task-specific reasoning objectives outperforms larger general-purpose LLMs across drug discovery tasks—ADMET prediction, drug-target activity, retrosynthesis, and molecular optimisation—while maintaining computational efficiency.
WHY IT MATTERS: General LLMs with large parameter counts fail at molecular reasoning despite broad language capabilities; MMAI Gym demonstrates that domain-adapted training format and task-specific reasoning priors matter more than scale for drug discovery. The "Liquid" LFM framework, which adapts representational strategy to molecular data structure, generalises as a training paradigm beyond chemistry.
CODE: Not released
---

---
TITLE: Generative Chemistry Platform for Small Molecules Targeting RNA: A Case Study for Chemical Optimization
AUTHORS: Serna Bio Team et al.
SOURCE: bioRxiv | 2026.05.08.723908 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.08.723908v1)
TOPIC TAG: Clinical ML
TLDR: The Serna Bio GenAI platform—trained specifically on RNA-targeting rather than protein-targeting chemistry—outperforms state-of-the-art general chemical generators in multi-parameter optimisation and experimental validation for RNA-targeting small-molecule drug design.
WHY IT MATTERS: RNA is an emerging and largely undruggable target class, but nearly all chemical generative models are trained on protein-ligand data, embedding a systematic bias toward protein-compatible chemistry; domain-specific training on RNA-ligand pairs substantially improves design quality and experimental hit rates. The direct experimental validation against human expert-designed molecules sets a rigorous standard rarely met in generative chemistry papers.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. Co-folding model guided by structural proteomics (AIMS-Fold)
**arXiv:2605.26192** | [Link](https://arxiv.org/abs/2605.26192)

Protein complex structure prediction has been a stubborn failure mode for generative models: the same model that predicts single-chain structures with near-experimental accuracy collapses when asked to predict induced-proximity complex conformations critical for antibodies and PROTACs. AIMS-Fold from Protai Bio solves this by differentiating through physical potentials derived from two orthogonal structural proteomics readouts—XL-MS, which provides inter-residue distance restraints, and HDX-MS, which provides solvent accessibility profiles—and using these as guidance signals during diffusion sampling at inference time. The synergistic integration of these two data modalities at inference time (without retraining) outperforms purely computational models including Boltz-2 on the most challenging induced-proximity targets, making this immediately deployable alongside existing structural proteomics workflows. Code not yet released.

---

### 2. EvoStruct: Bridging Evolutionary and Structural Priors for Antibody CDR Design
**arXiv:2605.21485** | [Link](https://arxiv.org/abs/2605.21485)

Vocabulary collapse—where CDR design models converge to over-predicting tyrosine and glycine—is a well-known but unsolved failure of equivariant GNN approaches to antibody design, causing the generated sequences to lack functional diversity and biological plausibility. EvoStruct resolves this by bridging a frozen protein language model's evolutionary amino-acid statistics with 3D structural context from an E(3)-equivariant GNN via a cross-attention adapter, using progressive PLM unfreezing and R-Drop consistency regularisation to prevent catastrophic forgetting. The 16% sequence recovery improvement and 43% perplexity reduction on Chimera-Bench represent the largest gains reported on this benchmark and provide a clear recipe for retooling any existing PLM+structure pipeline to address vocabulary collapse. Code not yet released.

---

### 3. GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
**arXiv:2605.07608** | [Link](https://arxiv.org/abs/2605.07608)

RNA inverse design for therapeutic applications must simultaneously satisfy structural fold requirements, sequence motif constraints, and coding restrictions (for mRNA therapeutics)—constraints that current monolithic models conflate in a single architecture that breaks down when any constraint changes. GoForth disentangles these into three independently swappable components: a sequence prior, a forward folding sampler, and a reward/constraint likelihood, enabling full inverse folding as a special case and providing clean interfaces for upgrading individual components as better folding oracles emerge. The framework's support for coding constraints specifically addresses mRNA vaccine and therapeutic design workflows that are currently underserved by existing RNA generative tools, and the released code makes it immediately usable. Code: [**GitHub**](https://github.com/quantumtative/GoForth)

---

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 18
- By topic: Protein LM: 6 | Diffusion: 3 | Text Diffusion: 2 | Flow Matching: 1 | Genomics: 4 | Architecture: 1 | Clinical ML: 2
- Sources: arXiv: 17 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 2 (ELF, GoForth)
