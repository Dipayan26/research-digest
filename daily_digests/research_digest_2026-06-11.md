# Research Digest — 2026-06-11

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: Flexible Flows for Biological Sequence Design
AUTHORS: Yogesh Verma et al.
SOURCE: arXiv | 2606.10543 | [**Link**](https://arxiv.org/abs/2606.10543)
TOPIC TAG: Flow Matching
TLDR: Introduces a Discrete Flow Matching framework for biological sequence design that adds a structured, domain-informed source coupling, a latent edit-based rate parameterization for variable-length generation, and latent classifier-free guidance with Dirichlet-prior temperature scaling.
WHY IT MATTERS: Existing discrete flow matching methods for DNA/RNA/protein design rely on biologically uninformative source distributions and struggle with variable-length sequences and fine-grained controllability. By making the source coupling, length variation, and guidance all first-class, tunable components without changing the core training objective, this work offers a drop-in upgrade path for many existing biological sequence generators.
CODE: Not released
---

---
TITLE: VFUSE: Virulent Feature Understanding with Sparse autoEncoders
AUTHORS: [Authors from 2606.10080] et al.
SOURCE: arXiv | 2606.10080 | [**Link**](https://arxiv.org/abs/2606.10080)
TOPIC TAG: General ML
TLDR: Trains sparse autoencoders on the internal activations of diffusion-transformer protein models (RoseTTAFold3, RFdiffusion3) to surface interpretable, hazard-associated features and shows linear probes in the SAE latent space detect hazardous designs far better than probes on raw activations (up to 0.819 AUROC).
WHY IT MATTERS: As generative protein design models become more powerful, the ability to audit them for outputs relevant to biosecurity becomes critical, yet mechanistic interpretability has barely touched structure-generation diffusion models. Releasing SAE checkpoints and a catalog of hazard-associated features gives the field a concrete, reusable tool for safety screening of open-weight protein generators.
CODE: Not released
---

---
TITLE: Unified Energy for Invariant and Independent Decoding in Diffusion Language Models
AUTHORS: Yuchen Yan, Minkai Xu, Zaiquan Yang, Yatao Bian
SOURCE: arXiv | 2606.09159 | [**Link**](https://arxiv.org/abs/2606.09159)
TOPIC TAG: Text Diffusion
TLDR: Decomposes the quality gap between masked diffusion language models and autoregressive decoding into capacity, dependency, and invariance factors, and proposes an "invariant energy" objective with a sampling-based estimator to close the invariance gap under high parallel decoding.
WHY IT MATTERS: Discrete/masked diffusion LMs are the backbone of many protein, DNA, and RNA sequence generators (e.g., DPLM, EvoDiff-style models), and their main weakness versus autoregressive models emerges precisely at high parallel-decoding speeds. A principled fix to the invariance gap could directly improve sample quality and inference speed for biological sequence diffusion models built on the same masked-diffusion foundations.
CODE: Not released
---

---
TITLE: End-to-End Context Compression at Scale
AUTHORS: [Authors from 2606.09659] et al.
SOURCE: arXiv | 2606.09659 | [**Link**](https://arxiv.org/abs/2606.09659)
TOPIC TAG: Architecture
TLDR: Introduces Latent Context Language Models (LCLMs), encoder-decoder compressors continually pre-trained at scale (0.6B encoder / 4B decoder, 350B+ tokens) that map long token sequences into compact latent embeddings at 1:4–1:16 compression ratios, improving the Pareto frontier of quality, speed, and memory versus prior KV-cache compression methods.
WHY IT MATTERS: Long-context efficiency is a direct bottleneck for genomic and multi-omic foundation models that must process megabase-scale sequences or long multi-modal contexts (sequence + structure + function). A scaled, pretrained latent-compression recipe with strong Pareto trade-offs could be adapted to compress long genomic or multi-chain protein contexts for downstream LLM-style reasoning.
CODE: Not released
---

---
TITLE: OncoTraj: A Public Benchmark for Longitudinal Resistance Prediction in EGFR-Mutant Non-Small-Cell Lung Cancer on Osimertinib
AUTHORS: Abhijoy Sarkar, Aarchi Singh Thakur
SOURCE: arXiv | 2606.11144 | [**Link**](https://arxiv.org/abs/2606.11144)
TOPIC TAG: Clinical ML
TLDR: Releases a harmonized benchmark of 813 EGFR-mutant NSCLC patients on first-line osimertinib (combining MSK-CHORD, AACR GENIE BPC, and FLAURA molecular-resistance data) with three locked tasks — 12-month progression classification, time-to-progression regression, and resistance-mechanism classification — plus an open evaluation harness.
WHY IT MATTERS: Resistance to osimertinib under therapeutic pressure is a textbook case of predictable clonal evolution, but until now there was no public, standardized benchmark for training or comparing computational models on these longitudinal clinical-genomic trajectories. A locked, harmonized benchmark enables reproducible head-to-head comparisons of ML models for predicting resistance evolution in precision oncology.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Flexible Flows for Biological Sequence Design**
arXiv:2606.10543 | [Link](https://arxiv.org/abs/2606.10543)

This paper directly tackles three long-standing weaknesses of discrete flow matching for biological sequence design at once: uninformative source couplings, rigid fixed-length generation, and limited steerability. The structured coupling biases the noise distribution toward biologically plausible regions, the latent edit-based rate parameterization enables variable-length generation through edit operations conditioned on a shared latent, and latent classifier-free guidance with Dirichlet temperature scaling gives fine-grained control — all without altering the underlying training objective. As a general-purpose upgrade compatible with existing DFM pipelines, it could meaningfully improve protein, DNA, and RNA sequence generators across the board.
Code: Not released

**2. VFUSE: Virulent Feature Understanding with Sparse autoEncoders**
arXiv:2606.10080 | [Link](https://arxiv.org/abs/2606.10080)

VFUSE is one of the first applications of mechanistic interpretability — specifically sparse autoencoders — to diffusion-transformer protein design models like RoseTTAFold3 and RFdiffusion3. By finding that hazard-associated features are far more linearly separable in SAE latent space than in raw activations (up to 0.819 AUROC), and releasing checkpoints and a feature catalog, the work provides a practical safety-auditing toolkit for the growing ecosystem of open-weight protein generators.
Code: Not released

**3. Unified Energy for Invariant and Independent Decoding in Diffusion Language Models**
arXiv:2606.09159 | [Link](https://arxiv.org/abs/2606.09159)

This paper offers a clean theoretical decomposition of why masked diffusion language models lag autoregressive models — capacity, dependency, and invariance — and proposes an "invariant energy" correction with a tractable sampling-based estimator that specifically targets the invariance gap during highly parallel decoding. Because masked discrete diffusion underlies many protein and nucleic-acid sequence generators, a principled fix here has broad downstream applicability for faster, higher-quality biological sequence sampling.
Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 5
- By topic: Protein LM: 0 | Diffusion: 0 | Text Diffusion: 1 | Flow Matching: 1 | Genomics: 0 | Architecture: 1 | General ML: 1 | Clinical ML: 1
- Sources: arXiv: 5 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
