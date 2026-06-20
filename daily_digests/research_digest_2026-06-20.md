# Research Digest — 2026-06-20

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct WebFetch access to arxiv.org, biorxiv.org, medrxiv.org, pubmed.ncbi.nlm.nih.gov, huggingface.co/papers, paperswithcode.com, and the NCBI/arXiv/Europe PMC APIs all returned HTTP 403 again in this environment, so today's sweep relied entirely on WebSearch. Web-search indexing of new arXiv/bioRxiv submissions consistently lagged real posting dates by roughly 5-10 days, so no item could be confirmed as posted strictly within the last 24h; PubMed, medRxiv, Hugging Face Papers, and Papers With Code surfaced nothing both on-topic and unconfirmed-as-already-covered. Every candidate below was cross-checked against the full prior digest history (through 2026-06-19) and any duplicate (e.g. TCRDiff, MoE-Bind, Bioinf-Farma, the cryo-EM reconstruction paper, the TF-binding paper, ProtAff, AgentPLM, SurfDesign, RicciBind — all already covered on 2026-06-17/06-19) was excluded. The 9 items below are the newest verified, not-yet-covered papers found, spanning arXiv submissions June 16-18 and bioRxiv preprints June 9-18.

---

---
TITLE: BioHarness: Substrate-Aware Evidence Assembly for Biomedical Question Answering across Literature, Knowledge Bases, and Biological Atlases
AUTHORS: Not specified in accessible abstract
SOURCE: arXiv | 2606.19396 | [**Link**](https://arxiv.org/abs/2606.19396)
TOPIC TAG: General ML
TLDR: BioHarness is an LLM agent harness that stages biomedical question answering by combining literature retrieval, curated knowledge-base lookups, and atlas-derived structured measurements under a single question-conditioned reranker with "grounded cascade control" that decides when evidence is sufficient.
WHY IT MATTERS: Most biomedical QA systems either retrieve from one substrate (text-only RAG) or hard-code a single pipeline; explicitly modeling literature, KBs, and atlases as distinct evidence substrates with a controller deciding when to stop searching is a reusable pattern for any scientific QA system spanning heterogeneous data types. The cascade-control mechanism is directly relevant to reducing hallucinated or premature answers in agentic biomedical literature tools.
CODE: Not released
---

---
TITLE: Measurement noise limits the advantage of nonlinear models over linear models in biomedical prediction
AUTHORS: Marc-André Schulz, Kerstin Ritter
SOURCE: arXiv | 2606.18420 | [**Link**](https://arxiv.org/abs/2606.18420)
TOPIC TAG: General ML
TLDR: Shows analytically and empirically that additive measurement noise attenuates a degree-k nonlinear interaction by the k-th power of feature reliability, so at typical biomedical measurement reliabilities the theoretical advantage of flexible/nonlinear models over linear ones can largely vanish.
WHY IT MATTERS: This directly challenges the default assumption that deep/nonlinear models should outperform linear baselines on biomedical prediction tasks, and shows the gap can't be closed by collecting more samples — only by reducing measurement noise itself. It's a useful sanity check for any group benchmarking deep learning against linear baselines on noisy omics, imaging, or EHR-derived features.
CODE: Not released
---

---
TITLE: HiST: A Hierarchical Sparse Transformer for Cross-Modal Spatial Transcriptomics Modeling
AUTHORS: Not specified in accessible abstract
SOURCE: arXiv | 2606.14251 | [**Link**](https://arxiv.org/abs/2606.14251)
TOPIC TAG: Genomics
TLDR: Reframes histology-to-spatial-transcriptomics inference as a sparse, lattice-indexed field-prediction problem rather than dense-grid regression, using a dyadic encoder-decoder with sparse window attention and resolution-changing operators to predict gene expression directly from gigapixel H&E whole-slide images.
WHY IT MATTERS: Dense-grid approaches to H&E-to-expression prediction scale quadratically with whole-slide image resolution, which is a real deployment bottleneck for spatial transcriptomics imputation at clinical scale. A sparse, resolution-flexible architecture is a transferable pattern for any gigapixel-scale cross-modal prediction task in computational pathology.
CODE: Not released
---

---
TITLE: Benchmarking gene expression reconstruction from single-cell latent representations
AUTHORS: X. Fu, D. Klein, E. Antipov, A. Palma, A. Tejada-Lapuerta, M. Bahrami, L. B. Kummerle, M. Lubetzki, F. P. Casale, M. D. Luecken, F. J. Theis
SOURCE: bioRxiv | 10.64898/2026.06.18.733090 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.18.733090v1)
TOPIC TAG: Genomics
TLDR: A systematic benchmark from the Theis lab evaluating how well gene expression can be reconstructed from the latent embeddings produced by a range of single-cell foundation/representation-learning models, under one unified evaluation protocol.
WHY IT MATTERS: Single-cell foundation models are usually evaluated on downstream classification or clustering metrics, which obscures how much biological signal their latent space actually retains; reconstruction fidelity is a more direct probe of representation quality. As an MTEB-style benchmark for single-cell embeddings, this is immediately useful for anyone choosing or pretraining a single-cell representation-learning model.
CODE: Not released
---

---
TITLE: DesignMaster: A Multi-Conditional Diffusion Framework for Rational PROTAC Design
AUTHORS: Binze Shi, Jie Liu, Tong Pan, Yi Hao, Luke Isbel, Michael J Roy, Ashley P Ng, Xuequn Shang, Fuyi Li
SOURCE: bioRxiv | 10.64898/2026.06.15.732318 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.15.732318v1)
TOPIC TAG: Diffusion
TLDR: DesignMaster is an E(3)-equivariant graph-Transformer diffusion model for PROTAC linker design that injects linker-length and physicochemical constraints throughout the denoising process via a gated multi-condition fusion module, improving validity by 3.2% and recovery by 34.4% over prior baselines on PROTAC-DB 2.0/3.0.
WHY IT MATTERS: Most generative linker-design models treat physicochemical constraints as a post-hoc filter rather than a generation-time signal; fusing them directly into the diffusion trajectory via equivariant attention is a more principled way to keep generated linkers synthesizable and degrader-competent. The reported 51.78% RMSD reduction in a real BCPyr/6W7O case study suggests this generalizes beyond benchmark recovery metrics to genuinely usable degrader candidates.
CODE: Not released
---

---
TITLE: PertDiffBench: Benchmarking Diffusion Models for Single-Cell Perturbation Response Prediction
AUTHORS: Not specified in accessible abstract
SOURCE: bioRxiv | 10.64898/2026.06.13.732013 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.13.732013v1)
TOPIC TAG: Diffusion
TLDR: A standardized benchmark comparing diffusion-based perturbation-response predictors (e.g. scDiffusion) against simpler baselines (e.g. scGen) across unseen cell types, species, drugs, and stress conditions, finding no consistent advantage for diffusion models.
WHY IT MATTERS: Diffusion models are increasingly the default architecture choice for virtual-cell perturbation prediction, and this benchmark is a useful counterweight showing that architectural sophistication doesn't reliably translate into generalization gains for this task. It's directly relevant to anyone deciding whether to adopt a diffusion-based virtual-cell model versus a cheaper baseline.
CODE: Not released
---

---
TITLE: RNARL: Reinforcement Learning-Driven Unified Generative Framework for Multi-Objective RNA Codon Design
AUTHORS: Not specified in accessible abstract
SOURCE: bioRxiv | 10.64898/2026.06.12.732012 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.12.732012v1)
TOPIC TAG: Architecture
TLDR: An actor-critic RL framework with a Mixture-of-Experts gating network (experts specializing by sequence feature, e.g. serine-rich regions) jointly optimizing codon sequences for minimum free energy, codon adaptation index, and GC content, validated across 6 species and 5 RNA types.
WHY IT MATTERS: Codon optimization is usually treated as a single-objective combinatorial search; framing it as multi-objective RL with feature-specialized MoE experts lets the model trade off competing biophysical objectives (stability vs. translation efficiency vs. GC content) instead of optimizing one at the expense of the others. The MoE-gated expert specialization pattern is a reusable idea for other sequence-design tasks with multiple, sometimes-conflicting biophysical objectives.
CODE: Not released
---

---
TITLE: Back to Basics: Observed Statistics Are Sufficient to Predict Drug Responses (Rhaister)
AUTHORS: Not specified in accessible abstract
SOURCE: bioRxiv | 10.64898/2026.06.09.731197 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.09.731197v1)
TOPIC TAG: Clinical ML
TLDR: Rhaister predicts unmeasured drug-perturbation responses directly from screen-level summary statistics rather than a learned virtual-cell deep-learning model, matching or exceeding deep baselines on the Tahoe-100M-derived "Emerald Bay" dataset while training in seconds and predicting in milliseconds.
WHY IT MATTERS: This is a pointed "back to basics" challenge to the prevailing assumption that virtual-cell perturbation prediction requires expensive deep generative models — if simple observed statistics match deep models on held-out drug-cell combinations, it reframes what counts as a meaningful baseline for the whole virtual-cell-model subfield. Training in seconds instead of GPU-days makes it immediately practical for labs without large compute budgets to triage perturbation screens.
CODE: [**Code**](https://huggingface.co/collections/tahoebio/rhaister)
---

---
TITLE: Trustworthy Agentic Genomics Through Versioned Skill Libraries
AUTHORS: Manuel Corpas, Alfredo Iacoangeli, Mathieu Bourdenx, Mahmoud Aldraimli, Nathan Skene, Segun Fatumo, Heinner Guio
SOURCE: bioRxiv | 10.64898/2026.06.11.731523 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.11.731523v1)
TOPIC TAG: Clinical ML
TLDR: Benchmarks 9 frontier LLMs on 44,550 scored pharmacogenomic evaluations built from real star-allele diplotypes across >7,000 individuals and 3 ancestries, finding free-form LLM reasoning is clinically unsafe — even with RAG grounding, which increases lethal-class errors — and that versioned, executable "skill" libraries make pharmacogenomic mapping auditable and exact instead.
WHY IT MATTERS: This is a rare large-scale, quantitative demonstration that the standard "give the LLM the right context via RAG" fix does not just fail to help but actively increases the rate of the most dangerous error class in a real clinical-genomics task, directly undercutting an assumption widely baked into current agentic-bio tooling. Replacing free-form clinical reasoning with versioned, executable skills is a concrete, auditable alternative design pattern for any agentic genomics or clinical-decision-support system built on LLMs.
CODE: [**Code**](https://github.com/manuelcorpas/24-AGENTIC-PGX-BENCHMARK)
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Trustworthy Agentic Genomics Through Versioned Skill Libraries** (bioRxiv 10.64898/2026.06.11.731523)
This paper benchmarks 9 frontier LLMs on 44,550 real pharmacogenomic evaluations (actual star-allele diplotypes across >7,000 individuals, 3 ancestries) and finds free-form LLM clinical reasoning is unsafe — strikingly, adding RAG grounding *increases* the rate of lethal-class dosing errors rather than reducing it. The proposed fix replaces open-ended reasoning with versioned, executable "skill" libraries that make pharmacogenomic mapping exact and auditable. This is one of the most concrete, quantitative warnings to date against trusting RAG-grounded LLM agents in safety-critical clinical-genomics workflows, with a clear and immediately adoptable alternative design pattern.
Code/weights: [github.com/manuelcorpas/24-AGENTIC-PGX-BENCHMARK](https://github.com/manuelcorpas/24-AGENTIC-PGX-BENCHMARK)

**2. DesignMaster: A Multi-Conditional Diffusion Framework for Rational PROTAC Design** (bioRxiv 10.64898/2026.06.15.732318)
DesignMaster uses an E(3)-equivariant graph-Transformer diffusion model to generate PROTAC linkers, fusing length and physicochemical constraints directly into the denoising trajectory rather than filtering for them afterward, yielding a 34.4% recovery improvement and a 51.78% RMSD reduction in a real degrader case study (BCPyr/6W7O) over prior baselines. Folding design constraints into the generative process itself — instead of generate-then-filter — is a pattern with broad applicability across constrained molecular generation. It pushes PROTAC/degrader design closer to being a fully generative, constraint-aware pipeline rather than a search-and-filter one.
Code/weights: Not confirmed as released (a GitHub link was reported by some sources but could not be independently verified).

**3. Back to Basics: Observed Statistics Are Sufficient to Predict Drug Responses (Rhaister)** (bioRxiv 10.64898/2026.06.09.731197)
Rhaister predicts unmeasured drug-perturbation responses straight from screen-level summary statistics, matching or beating deep virtual-cell models on the Tahoe-100M-derived "Emerald Bay" dataset while training in seconds rather than GPU-days. As a deliberately simple baseline that holds up against the field's increasingly elaborate generative virtual-cell models, it forces a useful recalibration of what counts as a meaningful comparison point in perturbation-response prediction. Its near-zero compute cost also makes it immediately usable by labs without large-scale GPU infrastructure.
Code/weights: [huggingface.co/collections/tahoebio/rhaister](https://huggingface.co/collections/tahoebio/rhaister)

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 9
- By topic: Protein LM: 0 | Diffusion: 2 | Genomics: 2 | Architecture: 1 | General ML: 2 | Clinical ML: 2
- Sources: arXiv: 3 | bioRxiv: 6 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 2
