# Research Digest — 2026-06-09

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: The Dark Regulome: Disentangling Predictability from Regulation in Genomic Foundation Models
AUTHORS: Chahat Baranwal et al.
SOURCE: arXiv | 2606.06834 | [**Link**](https://arxiv.org/abs/2606.06834)
TOPIC TAG: Genomics
TLDR: Introduces a residualization-and-permutation diagnostic across three genomic foundation models (Caduceus-Ph, HyenaDNA, Enformer) that separates predictability-driven from regulation-driven variance across 30,448 dark-genome elements at 92 glioma-relevant loci, identifying a sharp 10 kb proximal-regulatory horizon.
WHY IT MATTERS: A fundamental confound in in-silico mutagenesis (ISM) interpretation has remained unresolved—high foundation-model scores can reflect local sequence predictability rather than genuine regulatory activity. By decoupling these two sources of variance with a principled diagnostic, this work provides a necessary quality-control step before any ISM-based regulatory inference. The finding that the proximal-regulatory signal attenuates sharply at 10 kb directly constrains the scope of dark-regulome studies in cancer genomics.
CODE: Not released
---

---
TITLE: AlloGen: Conformation-Selective Binder Generation with Differential State Scoring
AUTHORS: [Researchers from CUHK and University of Pennsylvania] et al.
SOURCE: arXiv | 2606.05474 | [**Link**](https://arxiv.org/abs/2606.05474)
TOPIC TAG: Protein LM
TLDR: AlloGen decouples backbone generation from a fully differentiable, SE(3)-invariant interface graph transformer that scores conformational state selectivity, enabling conformation-specific binder design for allosteric targets such as kinases, nuclear receptors, and GPCRs.
WHY IT MATTERS: Conventional binder design maximizes affinity without regard to which conformational state is engaged; for allosteric targets this ambiguity nullifies functional specificity regardless of binding tightness. AlloGen's generator-agnostic scorer can integrate as a passive reranker or an active gradient guide into any backbone generator, making it immediately composable with existing pipelines such as RFdiffusion or Proteina.
CODE: Not released
---

---
TITLE: An Accurate Nucleic Acid–Small Molecule Docking Framework via Geometric Deep Learning with Large-Scale Pretraining (NucleoDock)
AUTHORS: [Authors from 2606.05198] et al.
SOURCE: arXiv | 2606.05198 | [**Link**](https://arxiv.org/abs/2606.05198)
TOPIC TAG: Clinical ML
TLDR: NucleoDock couples physics-guided pretraining on millions of synthetic docking complexes with fine-tuning on experimental co-crystal structures, achieving a 56% top-1 success rate at 2 Å RMSD on 125 nucleic acid–ligand complexes versus rDock's 29%, while generating 100 poses per complex in ~5 seconds.
WHY IT MATTERS: Nucleic acids are increasingly validated therapeutic targets (G-quadruplexes, riboswitches, viral RNAs) yet no deep learning docking tool has achieved protein-level accuracy for NA–small molecule complexes; NucleoDock is the first framework to bridge this gap meaningfully. The large-scale synthetic pretraining strategy directly addresses the critical data scarcity that has blocked prior attempts.
CODE: Not released
---

---
TITLE: GENEB: Why Genomic Models Are Hard to Compare
AUTHORS: Daria Ledneva, Mikhail Nuridinov, Denis Kuznetsov
SOURCE: arXiv | 2606.04525 | [**Link**](https://arxiv.org/abs/2606.04525)
TOPIC TAG: Genomics
TLDR: GENEB is a large-scale diagnostic benchmark evaluating frozen representations from 40 genomic foundation models across 100 tasks in 13 functional categories under a unified probing protocol, revealing that model rankings vary sharply across task categories and architectural/pretraining alignment outweighs parameter count.
WHY IT MATTERS: Fragmented benchmarks and incompatible evaluation protocols have made claims of superiority among genomic FMs largely unverifiable; GENEB provides the first principled, category-aware reference framework for model selection. The finding that scale gives only modest and inconsistent gains challenges a central assumption driving large genomic model investment.
CODE: Not released
---

---
TITLE: When Does Structure Help? The Information Bonus of AlphaFold2 Representations over Protein Language Models
AUTHORS: [Authors from 2606.04228] et al.
SOURCE: arXiv | 2606.04228 | [**Link**](https://arxiv.org/abs/2606.04228)
TOPIC TAG: Protein LM
TLDR: Introduces the "information bonus" (IB) metric—the linearly accessible advantage of frozen AF2 Evoformer embeddings over frozen ESM-2 embeddings under cross-validation—finding that ESM-2 dominates binding affinity and conformational flexibility tasks (IB < 0) but AF2 wins on allosteric-site residue classification.
WHY IT MATTERS: Practitioners routinely incur the compute cost of AlphaFold2 inference without evidence it benefits the downstream task; the IB metric provides an empirical answer across three representative protein-property tasks. The counter-intuitive result that ESM-2 outperforms AF2 on binding affinity prediction suggests that structural information can introduce noise for globally averaged representations.
CODE: Not released
---

---
TITLE: DeltaDiff: Training-Free, Physics-Guided Machine Learning for Predicting Mutant Protein Structures
AUTHORS: Yajie Cai, Yanbin Wang, Ming Chen
SOURCE: arXiv | 2606.04452 | [**Link**](https://arxiv.org/abs/2606.04452)
TOPIC TAG: Diffusion
TLDR: DeltaDiff is a training-free inference framework that injects mutation-aware physical guidance terms into a pre-trained backbone diffusion model at each reverse-diffusion step, enabling accurate prediction of mutant protein structures—including nonlocal conformational changes—without any retraining.
WHY IT MATTERS: ML models for mutant structure prediction have been bottlenecked by the high sequence similarity between wild-type and mutant, which limits informative training signal; physics-guided guidance at inference time bypasses this without modifying the model. The training-free nature allows instant application to any existing diffusion-based structure model.
CODE: Not released
---

---
TITLE: Enhancing Protein-Protein Interaction Prediction with Hierarchical Motif-based Multimodal Protein Embedding (MMM-PPI)
AUTHORS: Zaifei Yang, Samuel Ping-Man Choi, James Kwok
SOURCE: arXiv | 2606.02629 | [**Link**](https://arxiv.org/abs/2606.02629)
TOPIC TAG: Architecture
TLDR: MMM-PPI constructs PPI embeddings bottom-up across three scales—micro (residue-level sequence/structure/function), meso (multimodal motif encoder aggregating spatially-informed motif embeddings), and macro (protein encoder jointly modeling motif importance and inter-modal correlations)—to predict protein-protein interactions.
WHY IT MATTERS: Existing PPI predictors neglect the hierarchical organization of proteins and fail to integrate sequence, structure, and function modalities simultaneously; the explicit meso-scale motif representation captures structural units that critically regulate PPIs beyond residue-level signals. The bottom-up multimodal design is generalizable to other protein-level prediction tasks.
CODE: Not released
---

---
TITLE: ProtStructQA: A Denotation Threshold in Protein Structural Reasoning
AUTHORS: Aravind Mandiga, Guoming Li, Jin Lu, Ismailcem Budak Arpinar, Khaled Rasheed, Samuel E. Aggrey
SOURCE: arXiv | 2606.00451 | [**Link**](https://arxiv.org/abs/2606.00451)
TOPIC TAG: General ML
TLDR: ProtStructQA is an executable QA benchmark of 382.2K questions (330K active + 52.2K hard-negative robustness pool) generated from a typed DSL over AlphaFold-predicted structures spanning confidence, distances, PAE, solvent exposure, secondary structure, topology, and contacts across 10K proteins from four species.
WHY IT MATTERS: Existing protein LM evaluations measure perplexity or fold-level properties, but lack executable ground truth grounded in 3D coordinates; ProtStructQA closes this gap by providing an unambiguous denotation-level correctness criterion. The DSL-program provenance enables automatic difficulty stratification and robustness testing against hard negatives.
CODE: Not released
---

---
TITLE: CART: Context-Anchored Recurrent Transformer — A Parameter-Efficient Architecture with Learned Stability
AUTHORS: [Authors from 2606.01495] et al.
SOURCE: arXiv | 2606.01495 | [**Link**](https://arxiv.org/abs/2606.01495)
TOPIC TAG: Architecture
TLDR: CART introduces a hybrid recurrent-transformer architecture that anchors multi-head attention to dynamically learned context representations, achieving superior parameter efficiency and training stability over standard transformers on language modeling benchmarks.
WHY IT MATTERS: Recurrent architectures offer O(1) inference over long contexts but historically suffer from training instability; CART's context-anchoring mechanism addresses this fundamental challenge while remaining fully parallelizable during training. This architecture is directly applicable to ultra-long biological sequence modeling—genomic DNA, multi-chain protein complexes, and pangenome references.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. The Dark Regulome: Disentangling Predictability from Regulation in Genomic Foundation Models**
arXiv:2606.06834 | [Link](https://arxiv.org/abs/2606.06834)

This paper attacks a critical methodological confound that has quietly undermined the regulatory genomics literature: in-silico mutagenesis (ISM) scores from genomic foundation models (Caduceus-Ph, HyenaDNA, Enformer) conflate genuine regulatory signal with local sequence predictability. The authors introduce a residualization-and-permutation diagnostic that separates these two variance components across 30,448 dark-genome elements at 92 glioma-associated loci. The discovery of a sharp 10 kb proximal-regulatory horizon is a concrete, actionable finding that will reshape how practitioners design ISM experiments and interpret regulatory predictions in the dark genome.
Code: Not released

---

**2. NucleoDock: Nucleic Acid–Small Molecule Docking via Geometric Deep Learning with Large-Scale Pretraining**
arXiv:2606.05198 | [Link](https://arxiv.org/abs/2606.05198)

NucleoDock is the first deep learning docking framework to convincingly close the accuracy gap between protein-ligand and nucleic acid–ligand docking. By combining physics-guided synthetic pretraining on millions of NA-ligand complexes with fine-tuning on experimental structures, it achieves 56% top-1 success at 2 Å RMSD (vs. 29% for rDock) in ~5 seconds per complex. As riboswitches, G-quadruplexes, and viral RNA structures gain prominence as drug targets, NucleoDock provides a scalable computational tool that was critically absent from the drug-discovery toolkit.
Code: Not released

---

**3. AlloGen: Conformation-Selective Binder Generation with Differential State Scoring**
arXiv:2606.05474 | [Link](https://arxiv.org/abs/2606.05474)

AlloGen addresses the under-appreciated problem that most binder-design pipelines optimize affinity without specifying which conformational state of the target they engage—a critical limitation for allosteric targets like kinases and GPCRs where active/inactive state selectivity determines functional outcome. The SE(3)-invariant interface graph transformer scorer is fully differentiable and generator-agnostic, meaning it slots into any backbone generation framework as a reranker or gradient guide without retraining. This represents a conceptual advance that recasts binder design from a single-objective (affinity) to a multi-objective (affinity × state-selectivity) problem.
Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 9
- By topic: Protein LM: 2 | Diffusion: 1 | Genomics: 2 | Architecture: 2 | General ML: 1 | Clinical ML: 1
- Sources: arXiv: 9 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
