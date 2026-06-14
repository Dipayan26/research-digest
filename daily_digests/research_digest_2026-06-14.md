# Research Digest — 2026-06-14

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: MiniMax Sparse Attention
AUTHORS: Xunhao Lai et al.
SOURCE: arXiv | 2606.13392 | [**Link**](https://arxiv.org/abs/2606.13392)
TOPIC TAG: Architecture
TLDR: Introduces MiniMax Sparse Attention (MSA), a blockwise sparse-attention mechanism built on Grouped Query Attention with a lightweight Index Branch that selects top-k KV blocks per GQA group, cutting per-token attention compute by 28.4x at 1M-token context on a 109B-parameter multimodal model.
WHY IT MATTERS: Sub-quadratic attention at million-token scale is directly relevant to long-context genomic and multi-omics foundation models, which routinely need to process whole chromosomes or large MSAs. The co-designed inference kernel (14.2x prefill / 7.6x decode speedup on H800) and public release in a production model give a concrete, deployable recipe other long-context bio-LMs could adopt.
CODE: Inference kernel reportedly released alongside the MiniMax-M3 model (link not verified)
---

---
TITLE: Flexible Kernels for Protein Property Prediction
AUTHORS: Martin Jankowiak et al.
SOURCE: arXiv | 2606.11057 | [**Link**](https://arxiv.org/abs/2606.11057)
TOPIC TAG: Protein LM
TLDR: Proposes a class of Gaussian-process sequence kernels that combine evolutionary substitution matrices with local-linearity assumptions, giving data-efficient models of protein fitness/binding/thermostability landscapes that often beat protein-language-model embedding baselines on sparse experimental data.
WHY IT MATTERS: Most recent protein property-prediction work leans on ever-larger pLM embeddings, but this shows a lightweight kernel method can match or exceed them in the low-data regime typical of real assay-design campaigns. The structure-aware, multi-task variants offer a cheap drop-in for active-learning loops in directed evolution and binder optimization.
CODE: Not released
---

---
TITLE: Contemporary AI lacks the imagination to diverge or negate in science
AUTHORS: Honglin Bao et al.
SOURCE: arXiv | 2606.08251 | [**Link**](https://arxiv.org/abs/2606.08251)
TOPIC TAG: General ML
TLDR: A large-scale study invited authors of 121,640 recent biology/medicine/chemistry/social-science preprints to rate LLM-generated follow-up hypotheses (6,749 scientists, 25,139 ratings) and finds non-reasoning LLMs collapse into a narrow "hivemind" of similar ideas while no model class spontaneously proposes null hypotheses.
WHY IT MATTERS: As LLM-based "co-scientist" pipelines are increasingly proposed for hypothesis generation in computational biology, this is one of the largest empirical audits of their actual creativity, run against working scientists' own judgments rather than synthetic benchmarks. It highlights a concrete blind spot — failure to generate disconfirming/null hypotheses — that any agentic discovery system for biology should be tested against.
CODE: Not released
---

---
TITLE: Density Field State Space Models: 1-Bit Distillation, Efficient Inference, and Knowledge Organization in Mamba-2
AUTHORS: Chirag Shinde
SOURCE: arXiv | 2606.10932 | [**Link**](https://arxiv.org/abs/2606.10932)
TOPIC TAG: Architecture
TLDR: Presents DF-SSM, a method that distills a Mamba-2 1.3B model into a 1-bit scaffold plus INT8 low-rank correction, yielding a 278MB model (9.7x smaller) that runs 21.4x faster on GPU while staying within 2-4 points of a from-scratch 1.58-bit baseline, using only 32M tokens and 6 GPU-hours.
WHY IT MATTERS: State-space models are increasingly used as long-context backbones for genomic and single-cell sequence models (e.g., HybriDNA-style hybrids); a cheap post-hoc 1-bit distillation recipe makes deploying such models on edge or CPU hardware far more practical. The released GPU/CPU inference kernels lower the barrier for groups without large compute budgets to adopt Mamba-based bio-LMs.
CODE: [**Code**](https://github.com/cs-cmyk/df-ssm)
---

---
TITLE: Seeing Below the Limit of Detection: A Censored-Poisson Bayesian Latent-Growth Change-Point Detector (the Span Detector) for Serial ctDNA in HR+/HER2- Metastatic Breast Cancer
AUTHORS: Aarchi Singh Thakur, Abhijoy Sarkar
SOURCE: arXiv | 2606.11876 | [**Link**](https://arxiv.org/abs/2606.11876)
TOPIC TAG: Clinical ML
TLDR: Introduces "Span", a censored-Poisson Bayesian latent-growth change-point detector that treats below-limit-of-detection ctDNA readings as left-censored observations and raises a calibrated competing-risks alarm for emerging drug-resistant subclones in serial ctDNA monitoring of metastatic breast cancer.
WHY IT MATTERS: Most ctDNA monitoring pipelines discard or crudely threshold sub-LoD measurements, throwing away the earliest signal of resistance; explicitly modeling the censoring process could meaningfully shorten the lead time before imaging-confirmed progression. The Bayesian formulation gives calibrated false-alarm control, a property essential for any clinical deployment of ML-based liquid-biopsy monitoring.
CODE: Not released
---

---
TITLE: Small LLMs for Biomedical Claim Verification: Cost-Effective Fine-Tuning, Structural Dataset Shortcuts, and Cross-Domain Generalization
AUTHORS: Gaurav Kumar
SOURCE: arXiv | 2606.12854 | [**Link**](https://arxiv.org/abs/2606.12854)
TOPIC TAG: Clinical ML
TLDR: Fine-tunes small LLMs (Phi-3-mini, Qwen2.5-3B, Mistral-7B) via QLoRA on SciFact/HealthVer for biomedical claim verification, finding Mistral-7B QLoRA beats GPT-4o and GPT-5 by up to 12% F1 at a fraction of the cost using only ~1,000 training examples, while also exposing a previously unreported structural shortcut artifact in SciFact.
WHY IT MATTERS: Reliable, cheap claim verification is a core component for literature-grounded research agents (e.g., checking generated hypotheses against the literature). The discovery of a dataset-level shortcut in a widely-used benchmark is a useful caution for anyone evaluating LLM-based fact-checking tools on biomedical text.
CODE: Not released
---

---
TITLE: Discovering Functionally Selective Brain Regions with a Deep Topographic Multimodal Model
AUTHORS: Badr AlKhamissi et al.
SOURCE: arXiv | 2606.09770 | [**Link**](https://arxiv.org/abs/2606.09770)
TOPIC TAG: General ML
TLDR: Introduces Topo-Omni, built by fine-tuning Qwen2.5-Omni-3B with a spatial-smoothness objective and self-distillation loss so that visual, auditory, and language/cognitive processing share one contiguous "cortical sheet," producing multimodal topographic maps consistent with human neuroimaging.
WHY IT MATTERS: This is a rare case of an architectural inductive bias (cortex-like spatial smoothness) imposed on a pretrained multimodal foundation model after the fact, rather than designed in from scratch — a pattern that could be reused to impose other biologically-motivated structure (e.g., modularity, sparsity) on existing bio foundation models. It also offers a new computational lens for comparing model representations to brain organization.
CODE: Not released
---

---
TITLE: Compress-Distill: Reasoning Trace Compression for Efficient Knowledge Distillation
AUTHORS: Maxime Griot, Paul Steven Scotti, Tanishq Mathew Abraham
SOURCE: arXiv | 2606.05988 | [**Link**](https://arxiv.org/abs/2606.05988)
TOPIC TAG: General ML
TLDR: Studies post-hoc compression of long chain-of-thought traces (from Qwen3.5-397B-A17B and gpt-oss-120B teachers, ~283k traces each) before distillation, showing compressed traces cut training tokens to 12-30% and speed up training 2-7.6x, though raw traces still give the best downstream accuracy.
WHY IT MATTERS: As reasoning-augmented LLMs are increasingly distilled into smaller models for deployment in scientific-assistant tools, this quantifies the accuracy/efficiency trade-off of trace compression — directly relevant to building affordable reasoning models for tasks like protein-design agents or literature triage.
CODE: Not released
---

---
TITLE: A likelihood-based framework for simultaneously learning both noise and growth dynamics using biologically-informed neural networks
AUTHORS: Rebecca M. Crossley, Ruth E. Baker
SOURCE: arXiv | 2606.13475 | [**Link**](https://arxiv.org/abs/2606.13475)
TOPIC TAG: General ML
TLDR: Extends Biologically-Informed Neural Networks (BINNs) with a learnable, heteroscedastic noise model, enabling joint discovery of both the underlying growth-law dynamics and the structure of biological measurement noise from sparse population-growth data.
WHY IT MATTERS: Most neural-ODE/mechanistic-discovery approaches in computational biology assume homoscedastic Gaussian noise, which can bias the recovered dynamics; explicitly modeling noise structure could improve mechanistic models fit to noisy single-cell, tumor-growth, or population-dynamics time series. The likelihood-based framework is general and could be combined with other mechanistic neural-network discovery pipelines.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**MiniMax Sparse Attention**
- MSA's top-k block-sparse retrieval on top of GQA cuts attention compute by 28.4x at 1M-token context while matching dense GQA quality, validated on a 109B-parameter production multimodal model. It achieves 14.2x prefill and 7.6x decode speedups with a co-designed kernel on H800 GPUs. Long-context efficiency at this scale is a direct enabler for bio-LMs that need to process whole chromosomes, long MSAs, or multi-omics records in a single context window.
- Code: kernel released alongside the MiniMax-M3 model release.

**Flexible Kernels for Protein Property Prediction**
- The paper builds Gaussian-process kernels that fuse evolutionary substitution-matrix priors with local-linearity assumptions to model protein fitness landscapes from sparse data. These kernels frequently outperform protein-language-model embedding baselines and extend naturally to structure-aware, multi-task settings. For labs running iterative directed-evolution or binder-optimization campaigns with limited assay data, this offers a cheap, interpretable alternative to fine-tuning large pLMs.
- Code: Not released.

**Contemporary AI lacks the imagination to diverge or negate in science**
- In the largest study of its kind, 6,749 working scientists rated LLM-generated hypotheses derived from 121,640 of their own recent preprints across biology, medicine, and chemistry. Non-reasoning LLMs cluster into a narrow set of similar ideas, while even reasoning models never spontaneously propose null hypotheses — a mode of scientific thinking humans use routinely. This is essential context for anyone building or evaluating LLM "co-scientist" agents for hypothesis generation in computational biology.
- Code: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 9
- By topic: Protein LM: 1 | Diffusion: 0 | Genomics: 0 | Architecture: 2 | General ML: 4 | Clinical ML: 2
- Sources: arXiv: 9 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 1
