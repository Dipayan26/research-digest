# Research Digest — 2026-06-13

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: EpiBench: Verifiable Evaluation of AI Agents on Epigenomics Analysis
AUTHORS: Harihara Muralidharan, Reema Baskar, Soo Hee Lee, Tim Proctor, Kenny Workman
SOURCE: arXiv | 2606.13602 | [**Link**](https://arxiv.org/abs/2606.13602)
TOPIC TAG: Genomics
TLDR: Introduces a verifiable benchmark of 106 deterministic tasks spanning CUT&Tag/CUT&RUN, ATAC-seq, ChIP-seq, and DNA methylation workflows, finding frontier AI agents pass only ~22-34% of tasks depending on assay type.
WHY IT MATTERS: As agentic LLM pipelines are increasingly proposed for automating wet-lab and bioinformatics analysis, this benchmark exposes a major reliability gap between current frontier models and the rigor needed for real epigenomics workflows. It provides a concrete, deterministic yardstick for measuring progress on agentic bioinformatics — an area with almost no prior standardized evaluation.
CODE: Not released
---

---
TITLE: Is It You or Your Environment? A Bayesian Inference Framework for Genomically-Anchored Personalized Physiological Interpretation
AUTHORS: Aruna Dey, Suraj Biswas
SOURCE: arXiv | 2606.13556 | [**Link**](https://arxiv.org/abs/2606.13556)
TOPIC TAG: Clinical ML
TLDR: Proposes using an individual's GWAS-derived genomic effect sizes as a fixed Bayesian prior to disentangle constitutional (genetic) variation from environmentally-driven physiological changes, addressing the cold-start problem in personalized health AI.
WHY IT MATTERS: Most personalized-medicine models need months of longitudinal behavioral data before they can give useful individualized interpretations; anchoring on genomic priors enables meaningful personalization from day one. This is a lightweight, broadly applicable pattern for combining static GWAS knowledge with dynamic wearable/EHR data streams.
CODE: Not released
---

---
TITLE: A Structural Causal Framework for Interventions on Evolutionary Accumulation Models
AUTHORS: Ramon Diaz-Uriarte, Íñigo Ríos-Arroyo, Iain G. Johnston
SOURCE: arXiv | 2606.12597 | [**Link**](https://arxiv.org/abs/2606.12597)
TOPIC TAG: Clinical ML
TLDR: Formalizes Pearl's do-operator for evolutionary accumulation models (OT, OncoBN, CBN, H-ESBCN, MHN, HyperHMM, HyperTraPS), enabling these cancer-progression models to make causal predictions about intervening on mutation-accumulation order.
WHY IT MATTERS: Cancer progression models have historically been used only for descriptive/predictive purposes; adding a rigorous causal-intervention layer turns them into tools for reasoning about "what if we blocked mutation X" — directly relevant to identifying and prioritizing therapeutic targets. The framework is general enough to apply across the whole family of widely-used accumulation models rather than being model-specific.
CODE: Not released
---

---
TITLE: OCOO-T: A Simple and Scalable Virtual Cell Model for Transcriptional Perturbation Response Prediction
AUTHORS: Infinite Evolution Technology (INFevo) and XtalPi researchers
SOURCE: arXiv | 2606.12838 | [**Link**](https://arxiv.org/abs/2606.12838)
TOPIC TAG: Flow Matching
TLDR: Presents a minimalist flow-matching Transformer that predicts transcriptional perturbation responses directly on continuous gene-expression profiles via continuous-time denoising, without auxiliary VAEs or gene-interaction-graph priors.
WHY IT MATTERS: Virtual cell models for perturbation prediction have trended toward increasingly complex architectures with hand-engineered priors; this work shows a vanilla-Transformer flow-matching formulation can be competitive while being far simpler and more scalable. A simpler recipe lowers the barrier for labs to build their own perturbation-response virtual cell models.
CODE: Not released
---

---
TITLE: Viral Proteins Reveal Geometry of Protein Language Models
AUTHORS: Arthur Bigot, Harmon Bhasin, Core Francisco Park, Eugene Shakhnovich, Dianzhuo Wang
SOURCE: arXiv | 2606.12609 | [**Link**](https://arxiv.org/abs/2606.12609)
TOPIC TAG: Protein LM
TLDR: Using viral proteins as a probe, finds that ESM-family protein language model embeddings contain a dominant "nativeness axis" — aligned with masked-reconstruction perplexity — that orders cellular proteins, viral proteins, and random sequences, while viral-specific signal remains linearly separable.
WHY IT MATTERS: Protein LMs are known to underperform on viral sequences, but the geometric origin of this gap was unclear; this work gives a mechanistic, embedding-geometry explanation. Identifying a linearly separable "viral" direction suggests practical fixes (e.g., debiasing or auxiliary heads) for improving pLM performance on viral and other underrepresented sequence families.
CODE: Not released
---

---
TITLE: Language Modeling Materializes a World Model of Protein Biology
AUTHORS: [Authors from bioRxiv 2026.06.03.729735]
SOURCE: bioRxiv | 10.64898/2026.06.03.729735 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.03.729735v1)
TOPIC TAG: Protein LM
TLDR: Shows that the internal representations of a protein language model encode a structured "world model" of protein biology, used to generate a map covering 6.8 billion sequences and 1.1 billion predicted structures aligned with empirical biological organization.
WHY IT MATTERS: Moving beyond per-protein predictions, this work argues pLM internals implicitly capture global organizing principles of protein space (families, functions, structural neighborhoods) at unprecedented scale. Such a "world map" could become a navigation/search substrate for protein design and functional annotation across the full sequence universe.
CODE: Not released
---

---
TITLE: AlloGen: Conformation-Selective Binder Generation with Differential State Scoring
AUTHORS: Hanqun Cao, Pranam Chatterjee, et al.
SOURCE: HF Papers | arXiv:2606.05474 | [**Link**](https://hf.co/papers/2606.05474)
TOPIC TAG: Protein LM
TLDR: Introduces a modular binder-design framework that decouples backbone generation from a learned SE(3)-invariant "differential state scorer," enabling generation of binders selective for one conformational state (e.g., active vs. inactive kinase/GPCR), validated in wet-lab experiments on calmodulin.
WHY IT MATTERS: Most generative binder-design pipelines ignore that target proteins are conformationally dynamic and design against a single static structure; AlloGen's scorer-based approach is generator-agnostic and can be bolted onto existing diffusion/flow backbone generators. Conformation-selective binders are directly relevant to allosteric drug discovery, where state-selectivity is often the entire therapeutic value proposition.
CODE: Not released
---

---
TITLE: SurfDesign: Effective Protein Design on Molecular Surfaces
AUTHORS: [Authors from HF Papers 2606.07567]
SOURCE: HF Papers | arXiv:2606.07567 | [**Link**](https://hf.co/papers/2606.07567)
TOPIC TAG: Architecture
TLDR: Proposes a surface-conditioned protein design framework that models molecular surfaces as continuous geometric manifolds and integrates them with pretrained protein language models via surface-based equivariant message passing, improving de novo binder and enzyme design benchmarks.
WHY IT MATTERS: Surface geometry is often the most functionally relevant aspect of a protein for binding and catalysis, yet most sequence-/backbone-centric design pipelines treat it only implicitly. Combining equivariant surface representations with pLM priors offers a general add-on module that could improve any backbone-conditioned design pipeline for binders or enzymes.
CODE: Not released
---

---
TITLE: Single-Cell Cross-Modal Transfer by Adversarial Fine-Tuning of Foundation Models
AUTHORS: Joseph Boyd et al.
SOURCE: arXiv | 2606.07676 | [**Link**](https://arxiv.org/abs/2606.07676)
TOPIC TAG: Genomics
TLDR: Adversarially fine-tunes a single-cell foundation model to translate between unpaired spatial transcriptomics and scRNA-seq data, outperforming dedicated multi-omics translation methods.
WHY IT MATTERS: Spatial transcriptomics and scRNA-seq capture complementary information but are rarely available for the same cells/samples; effective cross-modal transfer lets researchers leverage large scRNA-seq atlases to enrich sparser spatial datasets. Repurposing a general single-cell foundation model via adversarial fine-tuning (rather than building bespoke translation architectures) is a reusable recipe for other unpaired multi-omics translation tasks.
CODE: Not released
---

---
TITLE: Using Protein Language Models for Pangenome Construction
AUTHORS: [Authors from bioRxiv 2026.06.04.730042]
SOURCE: bioRxiv | 10.64898/2026.06.04.730042 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.04.730042v1)
TOPIC TAG: Genomics
TLDR: Uses protein language model embeddings — which capture functional/semantic similarity beyond sequence identity — to construct and organize pangenomes, grouping gene families by functional relatedness rather than raw sequence similarity alone.
WHY IT MATTERS: Traditional pangenome construction relies heavily on sequence-identity clustering, which can split or merge gene families incorrectly when sequence divergence outpaces functional divergence (or vice versa). Embedding-based pangenome construction could yield more biologically meaningful gene family definitions across large collections of microbial or eukaryotic genomes.
CODE: Not released
---

---
TITLE: scFAIR Consortium: A Decentralized Hub for Single-Cell RNA-Seq Data Standardization and Unification
AUTHORS: [scFAIR Consortium authors]
SOURCE: bioRxiv | 10.64898/2026.06.05.730084 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.05.730084v1)
TOPIC TAG: Genomics
TLDR: Describes a decentralized infrastructure and consortium for standardizing and unifying scRNA-seq datasets across labs to support training and benchmarking of single-cell foundation models.
WHY IT MATTERS: Single-cell foundation models are bottlenecked as much by inconsistent metadata/formats across datasets as by model architecture; a decentralized, community-governed standardization hub could substantially raise the floor for training-data quality across the field. This kind of infrastructure effort, while not a model itself, underpins the next generation of scRNA-seq foundation models.
CODE: Not released
---

---
TITLE: Cross-Chirality Generalization by Axial Vectors for Hetero-Chiral Protein-Peptide Interaction Design
AUTHORS: Ziyi Yang, Zitong Tian, Yinjun Jia, Tianyi Zhang, Jiqing Zheng, Hao Wang, Yubu Su, Juncai He, et al.
SOURCE: HF Papers | arXiv:2605.29980-series | [**Link**](https://hf.co/papers/2602.20176)
TOPIC TAG: Diffusion
TLDR: Injects axial-vector features into an E(3)-equivariant latent diffusion model to generalize across chirality, enabling the first wet-lab-validated generative design of de novo D-peptide binders (L-target / D-binder).
WHY IT MATTERS: D-peptides are attractive therapeutics due to their protease resistance, but the lack of training data (almost all known structures are L-chirality) has made generative design for D-peptides essentially impossible until now. The axial-vector trick for cross-chirality generalization is a general equivariance technique that could extend to other mirrored-symmetry problems in structural biology.
CODE: [**Code**](https://github.com/YZY010418/PepMirror)
---

---
TITLE: Genetically Aligned Patient Representations Improve Hematological Diagnosis (GenBloom)
AUTHORS: Muhammed Furkan Dasdelen, Fatih Ozlugedik, Ilaria Looser, Rao Muhammad Umer, Christian Pohlkamp, Carsten Marr
SOURCE: HF Papers | arXiv:2605.29980 | [**Link**](https://hf.co/papers/2605.29980)
TOPIC TAG: Clinical ML
TLDR: Pretrains on single white-blood-cell histology images aligned with karyotype and somatic mutation data via supervised contrastive "genetic alignment," outperforming slide-only pathology foundation models on AML diagnosis.
WHY IT MATTERS: Most pathology foundation models learn purely from images and miss the molecular drivers that define many hematological malignancies; explicitly aligning cell morphology with genetic data at pretraining time bakes in clinically critical information that pure vision models would otherwise need huge labeled datasets to learn. This multimodal alignment recipe (image + genotype) is broadly applicable to other cancers where morphology and genetics are jointly diagnostic.
CODE: [**Code**](https://github.com/marrlab/GenBloom)
---

---
TITLE: Can I Buy Your KV Cache?
AUTHORS: [Authors from arXiv 2606.13361]
SOURCE: arXiv | 2606.13361 | [**Link**](https://arxiv.org/abs/2606.13361)
TOPIC TAG: General ML
TLDR: Analyzes the economics of KV cache reuse vs. recomputation across inference providers, finding that KV cache is "nearly incompressible" so shipping it (egress cost) often exceeds the prefill compute it would save, motivating provider-side KV cache hosting.
WHY IT MATTERS: As bio-LLMs and agentic genomics/protein pipelines scale to very long contexts (full genomes, large MSAs, multi-chain complexes), KV cache costs become a dominant factor in deployment economics. This analysis is directly relevant to anyone designing infrastructure for serving long-context biological foundation models cost-effectively.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. EpiBench: Verifiable Evaluation of AI Agents on Epigenomics Analysis**
arXiv:2606.13602 | [Link](https://arxiv.org/abs/2606.13602)

EpiBench introduces 106 deterministic, verifiable tasks covering CUT&Tag/CUT&RUN, ATAC-seq, ChIP-seq, and DNA methylation analysis pipelines, and evaluates frontier AI agents against them. Models pass only 22-34% of tasks depending on assay type, revealing that "agentic bioinformatics" is far less reliable than headline LLM benchmarks suggest. As labs increasingly consider delegating routine epigenomics analysis to AI agents, this is the first rigorous yardstick for whether that's actually safe to do.
Code: Not released

**2. AlloGen: Conformation-Selective Binder Generation with Differential State Scoring**
arXiv:2606.05474 | [Link](https://hf.co/papers/2606.05474)

AlloGen decouples binder backbone generation from a learned SE(3)-invariant scorer that distinguishes target conformational states, letting any generative backbone model be steered toward binders selective for, e.g., the active vs. inactive state of a kinase or GPCR. The approach was wet-lab validated on calmodulin, giving real experimental grounding to a generator-agnostic design strategy. State-selective binders are central to allosteric drug discovery, a therapeutic modality that static-structure design pipelines have largely been unable to address.
Code: Not released

**3. Cross-Chirality Generalization by Axial Vectors for Hetero-Chiral Protein-Peptide Interaction Design**
HF Papers | [Link](https://hf.co/papers/2602.20176)

This work injects axial-vector geometric features into an E(3)-equivariant latent diffusion model, enabling it to generalize from the all-L-chirality training data to design D-peptide binders against L-chirality targets — and validates designs in the wet lab. D-peptides are highly attractive as protease-resistant therapeutics but were essentially inaccessible to generative design due to the near-total absence of D-chirality structural data. The axial-vector equivariance trick is a template for other mirrored-symmetry generalization problems across structural biology.
Code: [GitHub](https://github.com/YZY010418/PepMirror)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 14
- By topic: Protein LM: 3 | Diffusion: 1 | Text Diffusion: 0 | Flow Matching: 1 | Genomics: 4 | Architecture: 1 | MoE: 0 | General ML: 1 | Clinical ML: 3
- Sources: arXiv: 6 | bioRxiv: 3 | medRxiv: 0 | PubMed: 0 | HF Papers: 5 | PWC: 0
- Papers with code released: 2
