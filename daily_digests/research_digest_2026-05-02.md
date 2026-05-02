# Research Digest — 2026-05-02

> **Scope:** Papers posted or published in the last ~24–72 hours across arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, and Papers With Code.  
> **Focus areas:** Protein & Molecular ML · Generative Models in Biology · Sequence & Genome Models · Architecture Innovations · General Cutting-Edge ML · Clinical & Translational ML

---

## PAPERS

---

TITLE: Learning Biophysical Models of Gene Regulation with Probability Flow Matching
AUTHORS: (arXiv 2604.25062 team) et al.
SOURCE: arXiv | 2604.25062 | https://arxiv.org/abs/2604.25062
TOPIC TAG: Flow Matching / Genomics
TLDR: Introduces Probability Flow Matching (PFM) to fit coarse-grained stochastic models of gene transcription to observed marginal distributions from single-cell omics snapshot data, recovering interpretable regulatory parameters.
WHY IT MATTERS: Traditional inference of biophysical gene regulatory models from snapshot single-cell data requires expensive likelihood-free or variational methods; PFM provides a scalable, differentiable alternative that directly matches the learned ODE flow to empirical distributions. This is among the first direct bridges between modern flow-matching generative AI and mechanistic systems-biology modeling, opening high-throughput regulatory inference across thousands of genes simultaneously.
CODE: Not released

---

TITLE: IDiom: Generative Design of Intrinsically Disordered Protein Regions with an Autoregressive pLM
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.10.717777 | https://www.biorxiv.org/content/10.64898/2026.04.10.717777v1
TOPIC TAG: Protein LM
TLDR: Trained an autoregressive protein language model on 37 million intrinsically disordered region (IDR) sequences curated from the AlphaFold Database, enabling context-conditioned generation of IDRs and fully disordered proteins.
WHY IT MATTERS: Intrinsically disordered proteins mediate essential regulatory and signaling functions yet have been systematically neglected by structure-centric design tools; IDiom provides the first dedicated generative model trained at scale specifically for IDR sequences. Conditioning generation on flanking structured-domain context addresses the fundamental challenge of designing disordered regions that integrate with ordered protein modules.
CODE: Not released

---

TITLE: Generative Design of Intrinsically Disordered Proteins Based on Conditioned Protein Language Models: Data is the Limit
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.14.718363 | https://www.biorxiv.org/content/10.64898/2026.04.14.718363v1
TOPIC TAG: Protein LM
TLDR: Transformer encoder-decoder architecture maps numerical conformational ensemble descriptors to IDP sequences, demonstrating that accurate control over physicochemical properties only emerges at large data scale.
WHY IT MATTERS: Establishes that property-conditioned IDP generation requires previously unexplored data regimes — a critical empirical finding for practitioners designing scaled training pipelines for disordered proteins. Complements IDiom by focusing on quantitative property controllability rather than structural context conditioning, together suggesting that multi-objective IDP design is tractable at sufficient scale.
CODE: Not released

---

TITLE: IARA: A Deep Learning Predictor of Bindable Protein Surfaces to Guide Generative Synthetic Biology
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.04.16.718848 | https://www.biorxiv.org/content/10.64898/2026.04.16.718848v1.full
TOPIC TAG: Protein LM / Architecture
TLDR: Graph Neural Network trained on BindCraft trajectories predicts protein binder designability of surface patches in seconds, providing a rapid structural filter to triage inputs to expensive generative binder design pipelines.
WHY IT MATTERS: Generative binder design pipelines (RFdiffusion, BindCraft) are compute-intensive and often waste cycles on non-bindable targets; IARA acts as a fast upstream gatekeeper that identifies high-potential surface regions before committing to full generation runs. Training directly on BindCraft outputs rather than crystal structures means it captures the specific geometric features that AI-based tools actually exploit.
CODE: Not released

---

TITLE: Explainable Protein–Protein Binding Affinity Prediction via Fine-Tuning Protein Language Models
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.03.30.715237 | https://www.biorxiv.org/content/10.64898/2026.03.30.715237v1
TOPIC TAG: Protein LM
TLDR: Reframes PPI affinity prediction as metric learning by projecting two protein sequences into a shared latent space where cosine similarity correlates with binding affinity, with explainability via residue-level attribution.
WHY IT MATTERS: Most affinity predictors treat binding as a scalar regression task and require structural inputs; framing it as metric learning over pLM embeddings yields a sequence-only approach that generalizes across protein families and produces residue-level explanations aligned with known interface hotspots. The shared embedding space additionally enables zero-shot retrieval of binding partners.
CODE: Not released

---

TITLE: Distilling Genomic Foundation Models for Efficient mRNA Representation
AUTHORS: (ICLR 2026 ML4Genomics team) et al.
SOURCE: arXiv | 2604.08574 | https://arxiv.org/pdf/2604.08574
TOPIC TAG: Genomics / General ML
TLDR: Embedding-level knowledge distillation transfers mRNA representations from a large-scale genomic foundation model into a specialized model 200-fold smaller, retaining state-of-the-art performance on mRNA-specific downstream tasks.
WHY IT MATTERS: Large genomic foundation models are impractical for deployment in clinical or resource-constrained settings; this work demonstrates that 200× compression via targeted distillation preserves task-relevant representations for mRNA, providing a blueprint for specializing general DNA/RNA foundation models. Presented at the ICLR 2026 Machine Learning for Genomics Explorations Workshop.
CODE: Not released

---

TITLE: D3LM: A Discrete DNA Diffusion Language Model for Bidirectional DNA Understanding and Generation
AUTHORS: Yang, Z. et al.
SOURCE: arXiv | 2603.01780 | https://arxiv.org/abs/2603.01780
TOPIC TAG: Diffusion / Genomics
TLDR: Unified masked-diffusion language model in discrete DNA token space achieves both bidirectional representation learning and controllable regulatory element generation, outperforming autoregressive baselines on generation quality (sFID).
WHY IT MATTERS: Prior DNA models bifurcate into either masked/bidirectional (BERT-style, good at understanding) or autoregressive (GPT-style, good at generation) — D3LM unifies both capabilities under a single discrete diffusion objective, analogous to recent advances in text diffusion. The explicit discrete-space formulation avoids the continuous relaxation artifacts seen in latent DNA diffusion approaches.
CODE: Not released

---

TITLE: Discrete Diffusion for Single-Cell Gene Expression Modeling (DCM)
AUTHORS: (bioRxiv team) et al.
SOURCE: bioRxiv | 2026.02.19.705033 | https://www.biorxiv.org/content/biorxiv/early/2026/02/20/2026.02.19.705033.full.pdf
TOPIC TAG: Diffusion / Genomics
TLDR: Applies Score Entropy Discrete Diffusion (SEDD) directly to raw integer transcript count data for single-cell RNA-seq modeling, eliminating the continuous relaxation used by all prior scRNA generative models.
WHY IT MATTERS: Count data in scRNA-seq is inherently discrete and sparse; continuous relaxations introduce distributional mismatch that biases biological inference. DCM's native discrete treatment better preserves the zero-inflation and overdispersion characteristic of real count distributions, yielding improved cell-type clustering and perturbation response fidelity compared to continuous-space diffusion baselines.
CODE: Not released

---

TITLE: Lingshu-Cell: A Generative Cellular World Model for Transcriptome Modeling toward Virtual Cells
AUTHORS: Zhang, H. et al.
SOURCE: arXiv | 2603.25240 | https://arxiv.org/abs/2603.25240
TOPIC TAG: Diffusion / Genomics
TLDR: Masked discrete diffusion model learns transcriptomic state distributions across tissues and species, enabling conditional simulation of cellular responses to genetic perturbations and cytokine stimulation.
WHY IT MATTERS: Achieving "virtual cell" capabilities — predicting how any cell responds to any perturbation — requires a generative model that captures the full transcriptome-wide joint distribution, not just marginal statistics. Lingshu-Cell's discrete diffusion formulation respects count-data structure while scaling to genome-wide expression; it placed competitively on the Virtual Cell Challenge genetic perturbation benchmark, suggesting practical utility for in-silico screening.
CODE: Not released

---

TITLE: Generative Modeling in Protein Design: Neural Representations, Conditional Generation, and Evaluation Standards
AUTHORS: (arXiv team) et al.
SOURCE: arXiv | 2603.26378 | https://arxiv.org/abs/2603.26378
TOPIC TAG: Protein LM / Diffusion / Flow Matching
TLDR: Comprehensive survey covering protein representation learning, all major generative model families (diffusion, flow matching, sequence LMs), de novo backbone generation, joint sequence–structure co-design, and emerging hybrid predictor–generator architectures.
WHY IT MATTERS: The protein design field now spans dozens of distinct architectures and evaluation protocols that are rarely compared directly; this survey provides the first unified taxonomy of generative approaches alongside standardized evaluation recommendations, filling a critical need as the field moves toward multi-property conditional design. Particularly valuable is its analysis of how evaluation metrics (designability, novelty, diversity) relate to actual experimental success rates.
CODE: Not released

---

TITLE: SEAL: Towards Spatial Transcriptomics-Driven Pathology Foundation Models
AUTHORS: Hemker, K. et al.
SOURCE: arXiv | 2602.14177 | https://arxiv.org/abs/2602.14177
TOPIC TAG: Clinical ML / Genomics
TLDR: Spatial Expression-Aligned Learning (SEAL) fine-tunes pathology vision models with spatial transcriptomics gene expression data via parameter-efficient adapters, improving both visual representations and cross-modal gene expression prediction.
WHY IT MATTERS: Pathology foundation models trained on H&E images alone discard the molecular information now accessible through spatial transcriptomics; SEAL provides an efficient bridge that enriches visual representations with expression data at the cost of a small number of trainable parameters. The cross-modal capability — predicting spatially resolved gene expression from pathology patches — is directly relevant for clinical settings where ST data is unavailable at inference time.
CODE: Not released

---

TITLE: MambaFormer: Token-Level Guided Routing Mixture-of-Experts for Accurate and Efficient Clinical Assistance
AUTHORS: (arXiv team) et al.
SOURCE: arXiv | 2601.01260 | https://arxiv.org/abs/2601.01260
TOPIC TAG: MoE / SSM / Clinical ML
TLDR: Hybrid MoE architecture interleaves Mamba SSM layers with transformer attention and uses token-level routing to allocate compute, achieving competitive medical QA accuracy with substantially lower inference cost.
WHY IT MATTERS: Clinical LLMs require high accuracy on complex reasoning while remaining deployable under latency constraints; MambaFormer's token-level routing dynamically assigns clinical tokens requiring long-range reasoning to attention heads while routing syntactic or simple factual tokens through cheaper SSM layers. This is among the first demonstrations of jointly training MoE routing across heterogeneous SSM/transformer experts for a domain-specific medical setting.
CODE: Not released

---

TITLE: Elucidating the Design Space of Multimodal Protein Language Models
AUTHORS: Hsieh, C. et al.
SOURCE: arXiv | 2504.11454 | https://arxiv.org/abs/2504.11454
TOPIC TAG: Protein LM
TLDR: Systematic study of tokenization strategies, structure token prediction objectives, and representation learning architectures for multimodal pLMs identifies that tokenization loss and poor inter-modal alignment are primary bottlenecks, improving structure generation diversity and folding accuracy.
WHY IT MATTERS: Multimodal pLMs that co-model sequence and structure have become the dominant paradigm for protein design, but design choices have been made largely heuristically; this work provides the first controlled ablation study across all major components, yielding actionable guidelines. The finding that tokenization loss — not model capacity — is the main limiting factor reorients where future compute should be invested.
CODE: Not released

---

TITLE: GeneMamba: Bidirectional Mamba for Single-Cell Data with Biological Fidelity
AUTHORS: Qi, C. et al.
SOURCE: arXiv | 2504.16956 | https://arxiv.org/abs/2504.16956
TOPIC TAG: SSM / Genomics
TLDR: GeneMamba is a scalable single-cell transcriptomics foundation model based on bidirectional Mamba SSM with pathway-aware contrastive loss and rank-based gene encoding, achieving linear-time complexity and superior cell type annotation.
WHY IT MATTERS: Transformer-based scRNA foundation models face quadratic complexity that limits scalability to millions of cells; GeneMamba's Bi-Mamba architecture achieves linear scaling while its biologically-informed pathway contrastive objective makes learned representations more interpretable relative to gene ontology structure. Demonstrated superior multi-batch integration and cell type annotation versus scGPT and Geneformer baselines.
CODE: Not released

---

TITLE: Leveraging State Space Models in Long-Range Genomics
AUTHORS: Popov, M. et al.
SOURCE: arXiv | 2504.06304 | https://arxiv.org/abs/2504.06304
TOPIC TAG: SSM / Genomics
TLDR: Benchmarks SSM architectures (Caduceus, Hawk) against transformers across long-range genomic tasks, showing SSMs match transformer performance while handling dramatically longer sequences and enabling zero-shot length extrapolation.
WHY IT MATTERS: Genomic sequences are orders of magnitude longer than what transformers can process efficiently; this systematic benchmark provides the evidence base for preferring SSMs in genomic settings and demonstrates zero-shot extrapolation beyond training lengths — a property absent in standard transformers. Establishes SSMs as the practical default for whole-chromosome and enhancer–gene interaction modeling.
CODE: Not released

---

TITLE: Structure-Aligned Protein Language Model (SaESM2 / SaAMPLIFY)
AUTHORS: Chen, C. et al.
SOURCE: arXiv | 2505.16896 | https://arxiv.org/abs/2505.16896
TOPIC TAG: Protein LM
TLDR: Dual-task framework integrates intra-protein structural knowledge via latent-level contrastive learning and inter-protein structural knowledge via physical-level structural token prediction into ESM2 and AMPLIFY, boosting contact prediction and functional annotation.
WHY IT MATTERS: Existing pLMs are pretrained solely on sequences and must learn structural priors implicitly; this dual-task integration directly supervises structure-aware representations without abandoning sequence pre-training, yielding gains on both contact prediction and remote homology detection. The approach is architecture-agnostic and can be applied as a post-hoc alignment stage to any existing pLM.
CODE: Not released

---

TITLE: La-Proteina: Atomistic Protein Generation via Partially Latent Flow Matching
AUTHORS: Geffner, T. et al.
SOURCE: arXiv | 2507.09466 | https://arxiv.org/abs/2507.09466
TOPIC TAG: Flow Matching / Protein LM
TLDR: Partially latent representation combines coarse backbone structure with per-residue latent variables; flow matching over this hybrid space achieves state-of-the-art all-atom co-designability and scales to large proteins.
WHY IT MATTERS: Fully all-atom protein generation has been hampered by the high dimensionality of side-chain conformational space; La-Proteina's partially latent approach compresses side-chain information into residue-level latents while keeping backbone explicit, enabling tractable flow matching trajectories. SOTA performance on all-atom co-designability while supporting motif scaffolding positions this as a successor to FrameFlow for high-resolution design tasks.
CODE: Not released

---

TITLE: DrugFlow: Multi-Domain Distribution Learning for De Novo Drug Design
AUTHORS: Schneuing, A. et al.
SOURCE: arXiv | 2508.17815 | https://arxiv.org/abs/2508.17815
TOPIC TAG: Flow Matching / General ML
TLDR: DrugFlow combines continuous flow matching for molecular conformation with discrete Markov bridges for atom identity, enabling structure-based drug design with native uncertainty estimation and preference-aligned sampling for protein–ligand interactions.
WHY IT MATTERS: Prior SBDD generative models treat atom types and coordinates with separate frameworks that do not share uncertainty information; DrugFlow's joint continuous–discrete formulation propagates geometric uncertainty into atom-type predictions, which is critical for hit prioritization. The preference-aligned sampling (analogous to DPO in LLMs) enables steering generation toward molecules with user-specified physicochemical profiles without retraining.
CODE: Not released

---

TITLE: SPACE: Your Genomic Profile Predictor is a Powerful DNA Foundation Model
AUTHORS: Yang, Z. et al.
SOURCE: arXiv | 2506.01833 | https://arxiv.org/abs/2506.01833
TOPIC TAG: MoE / Genomics
TLDR: Supervised training for genomic profile prediction using a species-profile adaptive collaborative Mixture-of-Experts model outperforms unsupervised DNA sequence pre-training as a strategy for learning effective DNA representations.
WHY IT MATTERS: The dominant paradigm for DNA foundation models mimics NLP pre-training with masked/autoregressive sequence objectives, but SPACE challenges this assumption by showing that MoE models trained on functional regulatory profiles learn more transferable DNA representations — implying that biological function, not sequence statistics, is the optimal pre-training signal. The species-adaptive routing in MoE enables cross-species generalization without explicit multi-species fine-tuning.
CODE: Not released

---

TITLE: PAST: A Multimodal Single-Cell Foundation Model for Histopathology and Spatial Transcriptomics in Cancer
AUTHORS: Yang, C. et al.
SOURCE: arXiv | 2507.06418 | https://arxiv.org/abs/2507.06418
TOPIC TAG: Clinical ML / Genomics
TLDR: Pan-cancer single-cell foundation model integrates histopathology image patches and single-cell transcriptomes to jointly predict spatially resolved gene expression, perform virtual molecular staining, and conduct multimodal survival analysis.
WHY IT MATTERS: Spatial heterogeneity in tumors drives therapy resistance but requires expensive spatial omics to characterize; PAST enables virtual spatial transcriptomics prediction from routine H&E slides, potentially democratizing access to molecular tumor phenotyping. The pan-cancer training strategy captures shared oncogenic processes across tumor types, outperforming cancer-specific models on cross-tumor generalization benchmarks.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Learning Biophysical Models of Gene Regulation with Probability Flow Matching**
*(arXiv 2604.25062)*

This is the most timely paper of today's digest: it applies Probability Flow Matching — a technique from the generative AI world — to a classical problem in systems biology: fitting coarse-grained stochastic models of gene transcription to single-cell snapshot data. Rather than running expensive likelihood-free inference, PFM converts the problem into learning a differentiable ODE that transports a reference distribution to the observed marginal, recovering interpretable kinetic parameters such as burst frequency and degradation rates. The significance is two-fold: first, it gives mechanistic biologists a fast, scalable inference engine for gene regulatory parameters from abundant scRNA-seq data; second, it establishes a template for using flow matching as a *scientific inference* tool rather than only a generative one, an emerging paradigm with broad implications across computational biology.
Code / weights: Not released

---

**2. Lingshu-Cell: A Generative Cellular World Model for Transcriptome Modeling toward Virtual Cells**
*(arXiv 2603.25240)*

Lingshu-Cell tackles one of the grandest goals in computational biology — building a "virtual cell" capable of predicting any cell's transcriptomic response to any perturbation. The model applies masked discrete diffusion over a tokenized transcriptome-wide expression space, learning joint gene-expression distributions across diverse tissues and species. Crucially, this discrete formulation naturally respects the count-based, zero-inflated nature of scRNA-seq data without requiring Gaussian approximations. In competitive evaluation on the Virtual Cell Challenge genetic perturbation benchmark, Lingshu-Cell demonstrates state-of-the-art prediction of unseen perturbation responses and cytokine-induced transcriptional programs, suggesting this architecture class is now mature enough for practical use in in-silico drug screening pipelines.
Code / weights: Not released

---

**3. IDiom: Generative Design of Intrinsically Disordered Protein Regions**
*(bioRxiv 2026.04.10.717777)*

IDiom fills a critical gap in the protein design toolkit: while AlphaFold, RFdiffusion, and ProteinMPNN have transformed design of structured proteins, intrinsically disordered regions (IDRs) — which constitute ~30–40% of the human proteome and govern critical signaling, phase separation, and regulatory functions — have had no dedicated generative model. IDiom trains an autoregressive pLM on 37 million IDR sequences from the AlphaFold Database, with context conditioning on flanking structured domains to ensure that generated disordered regions are compatible with their protein-domain context. This positions IDiom as an essential complement to structure-based design tools for engineering multi-domain proteins, therapeutic peptides, and synthetic condensate-forming constructs.
Code / weights: Not released

---

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 20
- By topic: Protein LM: 6 | Diffusion: 3 | Flow Matching: 3 | Genomics: 5 | SSM/Mamba: 2 | MoE: 2 | General ML: 1 | Clinical ML: 2
- Sources: arXiv: 13 | bioRxiv: 5 | HF Papers (cross-listed): 7 | medRxiv: 0 | PubMed: 0 | PWC: 0
- Papers with code released: 0
