# Research Digest — 2026-05-22

> **Coverage window:** arXiv Friday batch (papers submitted Thu May 21 – Fri May 22 2026, announced May 22, IDs ≥ ~2605.19376); catch-up on selected bio-ML papers with IDs 2605.04118–2605.18643 and February 2026 IDs 2602.02093, 2602.09067 not featured in prior digests; bioRxiv postings checked through May 22. Sources: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, HF Papers, Papers With Code.

---

---
TITLE: FlowLM: Few-Step Language Modeling via Diffusion-to-Flow Adaptation
AUTHORS: (arXiv 2605.20199 authors)
SOURCE: arXiv | 2605.20199 | [**Link**](https://arxiv.org/abs/2605.20199)
TOPIC TAG: Text Diffusion / Flow Matching
TLDR: FlowLM adapts pre-trained discrete diffusion language models into flow matching models via lightweight fine-tuning, enabling high-quality sequence generation in just a few sampling steps rather than hundreds.
WHY IT MATTERS: Discrete diffusion language models have shown strong performance on biological sequence design (protein, DNA, RNA) but are impractically slow due to their many denoising steps; FlowLM's diffusion-to-flow adaptation retrofits existing trained diffusion models at a fraction of retraining cost, bringing inference latency to near-autoregressive levels. For wet-lab deployment pipelines that require rapid in-silico screening, this is a decisive practical advance — any discrete diffusion pLM (DPLM, MDLM, LLaDA variants) can be converted to a few-step generator without sacrificing generation quality.
CODE: Not released

---

---
TITLE: GRAM: Generative Recursive Reasoning Models
AUTHORS: Junyeob Baek, Mingyu Jo, Minsu Kim, Mengye Ren, Yoshua Bengio, Sungjin Ahn
SOURCE: arXiv | 2605.19376 | [**Link**](https://arxiv.org/abs/2605.19376)
TOPIC TAG: General ML
TLDR: GRAM turns iterative latent-state refinement into probabilistic multi-trajectory computation by modeling reasoning as a stochastic latent path, enabling multiple solution hypotheses and inference-time scaling through both recursive depth and parallel trajectory sampling.
WHY IT MATTERS: Biological sequence and structure problems routinely require multi-hypothesis reasoning under uncertainty — multiple plausible protein conformations, multiple gene regulation scenarios, multiple variant-effect interpretations — which deterministic recursive models collapse to a single prediction; GRAM's amortised variational inference over stochastic latent trajectories natively supports this multi-hypothesis regime. The latent-variable generative formulation also supports unconditional generation, making GRAM a candidate architecture for unified biological foundation models that reason about and generate sequences simultaneously.
CODE: [**Project page**](https://ahn-ml.github.io/gram-website)

---

---
TITLE: Post-Trained MoE Can Skip Half Experts via Self-Distillation
AUTHORS: (arXiv 2605.18643 authors)
SOURCE: arXiv | 2605.18643 | [**Link**](https://arxiv.org/abs/2605.18643)
TOPIC TAG: Architecture / MoE
TLDR: A self-distillation method applied post-training allows Mixture-of-Experts language models to prune approximately 50% of their expert parameters while retaining near-full performance by distilling retained experts to absorb the knowledge of pruned ones.
WHY IT MATTERS: MoE architectures are increasingly adopted for large biological foundation models (genomic LMs, protein LMs, multi-omics models) where total parameter counts must be large to capture evolutionary diversity but deployment costs are prohibitive; halving expert count at inference time without retraining directly enables these models to run on single-node or even edge-compute setups. Unlike weight merging approaches, the self-distillation mechanism preserves specialised expert knowledge in the retained parameters, which is critical for bio LMs where expert routing corresponds to sequence family or structural class signals.
CODE: Not released

---

---
TITLE: LPDP: Inference-Time Reward Control for Variable-Length DNA Generation with Edit Flows
AUTHORS: (arXiv 2605.11368 authors)
SOURCE: arXiv | 2605.11368 | [**Link**](https://arxiv.org/abs/2605.11368)
TOPIC TAG: Genomics / General ML
TLDR: LPDP (Local Perturbation Discrete Programming) is a training-free inference-time guidance operator that steers variable-length DNA generation toward desired reward signals by framing edit operations — insertions, deletions, and substitutions — as a local discrete programming problem within an edit-flow framework.
WHY IT MATTERS: DNA regulatory and coding sequence design requires variable-length outputs that existing fixed-length diffusion and language models cannot natively handle; by working directly with biologically natural edit operations (indels, SNPs), LPDP aligns the generative process with the mutational mechanisms that evolution and CRISPR editing actually use. The training-free design means LPDP can be grafted onto any pre-trained DNA language model or generative model without re-optimisation, enabling reward-guided promoter engineering, codon optimisation, and guide RNA design from existing foundation models.
CODE: Not released

---

---
TITLE: Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning
AUTHORS: Siddhant Dutta, Edward Tan Beng Wai, Soumick Sarker, Pasan Gunawardane, Jagath C. Rajapakse
SOURCE: arXiv | 2605.10985 | [**Link**](https://arxiv.org/abs/2605.10985)
TOPIC TAG: Protein LM
TLDR: Projects ESM-2 residue embeddings onto protein contact graphs and applies a lightweight GIN with differentiable Gumbel-softmax substructure pooling, achieving 92.8% accuracy and 0.898 macro-F1 on enzyme EC-number classification while mapping pLM features to structural and evolutionary motifs.
WHY IT MATTERS: Protein language models encode rich structural and evolutionary signals in dense, opaque latent spaces that resist conventional attention-weight attribution; this framework provides a principled differentiable method to partition pLM representations into biologically meaningful structural subgraphs, offering mechanistic interpretability beyond saliency maps. By grounding pLM feature analysis in the contact-graph topology rather than sequence positions alone, the method is applicable to understanding which structural motifs drive enzyme catalysis, binding site prediction, and mutational effect models.
CODE: Not released

---

---
TITLE: Learning the Interaction Prior for Protein–Protein Interaction Prediction: A Model-Agnostic Approach (L3-PPI)
AUTHORS: (arXiv 2605.09964 authors)
SOURCE: arXiv | 2605.09964 | [**Link**](https://arxiv.org/abs/2605.09964)
TOPIC TAG: Protein LM
TLDR: L3-PPI constructs virtual L3-path prompt graphs — encoding shared interaction-partner topology — as structural priors for any backbone protein encoder, reformulating the PPI binary classification task as a graph-level classification problem to capture network-level interaction context.
WHY IT MATTERS: Standard PPI prediction models treat each protein pair in isolation, missing the evolutionary co-selection pressure that manifests as shared interaction neighborhoods in PPI networks; the L3-path prior explicitly encodes the information that interacting protein pairs tend to share common interaction partners. As a model-agnostic drop-in, L3-PPI improves PPI prediction performance across multiple backbone pLMs without architectural modifications, with direct impact on drug target identification and disease pathway mapping.
CODE: Not released

---

---
TITLE: PPI-Net: Connecting Molecular Protein Interactions to Functional Processes in Disease
AUTHORS: (arXiv 2605.07838 authors)
SOURCE: arXiv | 2605.07838 | [**Link**](https://arxiv.org/abs/2605.07838)
TOPIC TAG: Clinical ML / Protein LM
TLDR: PPI-Net is a hierarchical GNN that integrates molecular PPI networks with pathway-level representations, learning a multi-scale graph hierarchy from individual protein interactions to functional disease processes for improved disease phenotype prediction.
WHY IT MATTERS: Disease prediction from molecular interaction data requires connecting micro-scale protein binding events to meso-scale pathway dysregulation to macro-scale phenotypic outcomes — a multi-scale modeling problem that flat GNNs address poorly; PPI-Net's hierarchical architecture explicitly models each scale, yielding interpretable intermediate representations that expose which pathways mediate individual PPI contributions to disease. This is particularly valuable for rare diseases and cancer subtypes where pathway-level context disambiguates phenotypically similar but mechanistically distinct presentations.
CODE: Not released

---

---
TITLE: Flow Matching for Count Data (count-FM)
AUTHORS: (arXiv 2605.07746 authors)
SOURCE: arXiv | 2605.07746 | [**Link**](https://arxiv.org/abs/2605.07746)
TOPIC TAG: Flow Matching / Genomics
TLDR: count-FM defines a principled flow matching framework for integer-valued count data by constructing continuous-time birth-death process trajectories with local unit jumps, providing a mathematically native generative model for scRNA-seq count matrices.
WHY IT MATTERS: Single-cell RNA-seq data is fundamentally discrete and non-negative (UMI counts), yet all existing continuous diffusion and flow matching models require an artificial real-valued transformation (log-normalisation, Gaussian assumptions) that distorts the count distribution and worsens downstream tasks such as imputation, augmentation, and perturbation modeling; count-FM operates directly in the integer count domain, preserving the statistical properties of sparse count data including dropout zeros. By deriving flow matching transport in the birth-death process formalism, count-FM provides both a rigorous theoretical foundation and a practical generative model for cell atlas synthesis, in silico perturbation, and trajectory inference.
CODE: Not released

---

---
TITLE: Conditional Generation of Antibody Sequences with Classifier-Guided Germline-Absorbing Discrete Diffusion
AUTHORS: (arXiv 2605.06720 authors)
SOURCE: arXiv | 2605.06720 | [**Link**](https://arxiv.org/abs/2605.06720)
TOPIC TAG: Diffusion / Protein LM
TLDR: Replaces the standard uniform-mask absorbing state in discrete diffusion with biologically meaningful germline sequences, combined with classifier guidance, to generate antibody sequences with controllable binding properties while accurately modeling somatic hypermutation variability.
WHY IT MATTERS: Standard discrete diffusion models absorb toward uninformative [MASK] tokens, discarding the evolutionary information encoded in germline templates that constrain the B-cell somatic hypermutation landscape; using germline as the absorbing state grounds the generative prior in immunological biology, making the denoising trajectory mirror the actual antibody maturation process. Classifier guidance on top of this biologically grounded prior enables simultaneous control of binding affinity, germline identity, and developability during generation — a combination directly relevant to the therapeutic antibody design pipeline.
CODE: Not released

---

---
TITLE: GoForth: Language Models for RNA Design under Structure, Sequence, and Coding Constraints
AUTHORS: (arXiv 2605.07608 authors)
SOURCE: arXiv | 2605.07608 | [**Link**](https://arxiv.org/abs/2605.07608)
TOPIC TAG: Genomics
TLDR: GoForth is an autoregressive language model for RNA sequence design that integrates hard satisfaction of secondary structure, sequence motif, and coding/non-coding constraints directly into the decoding process via constrained beam search and neural constraint scoring.
WHY IT MATTERS: RNA design for therapeutic applications (mRNA, siRNA, aptamers) simultaneously requires thermodynamic stability (target secondary structure), codon optimality (for protein-coding RNA), and sequence motif avoidance (immunogenicity, off-target binding) — constraint types from completely different biological layers that unconstrained generative models cannot jointly satisfy; GoForth's unified constraint-aware decoding resolves these competing objectives in a single pass. The framework's modular constraint interface allows domain-specific constraints (ribosome binding site grammar, IRES elements, poly-A signal avoidance) to be incorporated without retraining, making it broadly applicable across RNA therapeutic modalities.
CODE: Not released

---

---
TITLE: ProtDBench: A Unified Benchmark of Protein Binder Design and Evaluation
AUTHORS: (arXiv 2605.04118 authors)
SOURCE: arXiv | 2605.04118 | [**Link**](https://arxiv.org/abs/2605.04118)
TOPIC TAG: General ML / Protein LM
TLDR: ProtDBench establishes a standardised, reproducible evaluation pipeline for protein binder design that enforces realistic evaluation settings — consistent target sets, train/test splits, in silico validation metrics aligned to experimental success criteria — enabling fair systematic comparison of binder design methods.
WHY IT MATTERS: The absence of standardised benchmarks has led to inflated and incomparable claims across protein binder design methods, as each paper selects its own targets, evaluation protocols, and baselines; ProtDBench fixes these variables, enabling the community to determine which architectural advances genuinely generalise to held-out protein targets. As binder design becomes a critical bottleneck in therapeutic antibody and non-antibody biologics pipelines, this infrastructure paper directly addresses the reproducibility crisis that slows clinical translation.
CODE: Not released

---

---
TITLE: AntigenLM: Structure-Aware DNA Language Modeling for Influenza (ICLR 2026)
AUTHORS: (arXiv 2602.09067 authors)
SOURCE: arXiv | 2602.09067 | [**Link**](https://arxiv.org/abs/2602.09067)
TOPIC TAG: Genomics
TLDR: AntigenLM is a generative DNA language model pretrained on whole influenza genome segments with structure-aware objectives that capture RNA secondary structure and codon usage jointly, enabling few-shot adaptation for antigen sequence prediction and vaccine-candidate generation.
WHY IT MATTERS: Existing genomic language models are almost exclusively pretrained on human reference genomes; AntigenLM focuses on viral genome architecture where functional RNA secondary structure and codon usage jointly constrain evolutionary sequence variation — a regime that human-genome-trained models mishandle. The structure-aware pretraining confers genuine few-shot cross-strain generalisation for antigen design, directly accelerating the influenza vaccine design cycle from strain emergence to computational candidate generation.
CODE: Not released

---

---
TITLE: Cell-JEPA: Latent Representation Learning for Single-Cell Transcriptomics
AUTHORS: (arXiv 2602.02093 authors)
SOURCE: arXiv | 2602.02093 | [**Link**](https://arxiv.org/abs/2602.02093)
TOPIC TAG: Genomics
TLDR: Cell-JEPA applies the Joint-Embedding Predictive Architecture to scRNA-seq by training a context encoder to predict the representations of masked gene blocks in latent space rather than reconstructing raw expression counts, yielding richer cell-state embeddings for downstream clustering, annotation, and perturbation modeling.
WHY IT MATTERS: Masked-autoencoder-style pretraining for scRNA-seq forces models to reconstruct highly sparse and noisy raw UMI counts, squandering model capacity on noise reconstruction rather than learning semantic cell-state structure; Cell-JEPA's latent-prediction objective sidesteps raw count reconstruction entirely, learning representations that directly capture biologically meaningful variation. Adapting JEPA — which showed superior representation quality over MAE for images and video — to transcriptomics offers a principled path toward scRNA-seq foundation models that generalise better to rare cell types and unseen perturbation conditions.
CODE: Not released

---

---
TITLE: Machine Learning Cross-Platform Proteomic Imputation Enables Protein Quality Scoring and Replication of Epidemiological Associations
AUTHORS: (bioRxiv 2026.05.05.723059 authors)
SOURCE: bioRxiv | 2026.05.05.723059 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.05.723059v1)
TOPIC TAG: Clinical ML
TLDR: ML models trained on 5,325 participants with paired SomaScan/Olink measurements harmonise the two dominant proteomics platforms, enabling cross-platform protein imputation and validating epidemiological disease associations in UK Biobank (n=41,405) and the Cardiovascular Health Study.
WHY IT MATTERS: SomaScan and Olink each measure partially overlapping sets of thousands of proteins with distinct antibody-based measurement principles, creating fragmented large-scale proteomic cohorts where the same disease associations cannot be replicated across platforms; ML-based harmonisation expands each cohort's effective protein panel and provides a confidence score for each imputed measurement. Replication in UK Biobank at n=41,405 scale demonstrates clinical-grade utility, directly enabling meta-analyses that pool SomaScan and Olink cohorts for biomarker discovery in cardiovascular disease, cancer, and neurodegeneration.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. Conditional Generation of Antibody Sequences with Classifier-Guided Germline-Absorbing Discrete Diffusion
*arXiv 2605.06720*

This paper makes a conceptually elegant biological correction to discrete diffusion models for immunology: instead of absorbing toward uninformative [MASK] tokens, the model absorbs toward germline sequences — the actual evolutionary prior for antibody diversity. This makes the denoising trajectory a computational analogue of B-cell somatic hypermutation, giving the generative model genuine immunological grounding that improves both biological realism and property-conditional controllability. Paired with classifier guidance for binding affinity and developability, the framework addresses the exact failure modes of current therapeutic antibody design tools: germline bias in unconditioned generation and inability to flexibly guide toward multi-property therapeutic profiles.
Code / weights: Not yet released (arXiv: https://arxiv.org/abs/2605.06720)

---

### 2. LPDP: Inference-Time Reward Control for Variable-Length DNA Generation with Edit Flows
*arXiv 2605.11368*

LPDP is the first training-free method for reward-guided variable-length DNA sequence generation, closing a major gap in generative genomics: existing guided diffusion methods assume fixed-length outputs and cannot handle the biologically essential operations of insertion and deletion. By framing edit operations as a local discrete programming problem within an edit-flow generative model, LPDP makes reward guidance (e.g., maximise transcription factor binding affinity, minimise off-target CRISPR activity, optimise codon usage) directly applicable to variable-length regulatory and coding sequences without any retraining. This is directly deployable on top of existing DNA foundation models such as Nucleotide Transformer and HyenaDNA.
Code / weights: Not yet released (arXiv: https://arxiv.org/abs/2605.11368)

---

### 3. Flow Matching for Count Data (count-FM)
*arXiv 2605.07746*

count-FM solves a fundamental mismatch that has plagued generative modeling of single-cell RNA-seq data: all continuous diffusion and flow matching models require transforming integer UMI counts to a real-valued domain, introducing distributional artifacts that hurt imputation, augmentation, and trajectory inference. By constructing flow matching transport as a continuous-time birth-death process with unit-jump transitions native to the count domain, count-FM provides the first theoretically principled generative model that respects the integer, non-negative, overdispersed nature of scRNA-seq data. This is a foundational methodological contribution for single-cell genomics that will enable higher-fidelity cell atlas synthesis, in silico perturbation models, and generative approaches to trajectory analysis.
Code / weights: Not yet released (arXiv: https://arxiv.org/abs/2605.07746)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 15
- By topic: Protein LM: 4 | Diffusion: 1 | Flow Matching: 3 | Genomics: 6 | Architecture: 1 | MoE: 1 | General ML: 3 | Clinical ML: 2
- Sources: arXiv: 14 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0

> **Note on coverage:** Today's primary batch (IDs ≥ 2605.19376) includes FlowLM and GRAM as today's freshest arrivals. The bulk of today's digest draws on catch-up papers from IDs 2605.04118–2605.18643 (mid-May biology-specific submissions that escaped the prior digests' crosslisting filters) plus two ICLR-2026-accepted papers from February 2026 (AntigenLM, Cell-JEPA) that were not captured in earlier runs.
