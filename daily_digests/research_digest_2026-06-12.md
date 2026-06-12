# Research Digest — 2026-06-12

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.

---

---
TITLE: m6A-FORM: A Foundation Model for Decoding N6-methyladenosine Biology
AUTHORS: [Authors from 2606.12219] et al.
SOURCE: arXiv | 2606.12219 | [**Link**](https://arxiv.org/abs/2606.12219)
TOPIC TAG: Genomics
TLDR: Pretrains a transformer foundation model on ~22M MeRIP-seq peak-derived RNA sequences from 143 human studies, then fine-tunes on single-nucleotide m6A annotations to reach PR-AUC 0.635 / ROC-AUC 0.988 for m6A site prediction, beating prior methods by ≥0.14 PR-AUC with much faster inference.
WHY IT MATTERS: Most existing m6A predictors use computationally costly adenosine-centered formulations prone to false positives; using peak-level priors for pretraining gives a more efficient and biologically grounded foundation. The same model adapts to predict binding sites for 19 m6A-associated regulators and YTHDF2-bound degradation-linked sites, making it a reusable backbone for epitranscriptomic regulatory studies.
CODE: Not released
---

---
TITLE: Interpretable enzyme function prediction via sparse autoencoder features of ESMC across the microbial protein universe
AUTHORS: Yue Hu, Wanyu Cheng, Junqing Wang, Yingchao Liu
SOURCE: arXiv | 2606.12209 | [**Link**](https://arxiv.org/abs/2606.12209)
TOPIC TAG: Protein LM
TLDR: Trains a sparse autoencoder (16,384-dim codebook, GPT-5-annotated concepts) on ESMC-6B activations and shows the resulting binary features predict enzyme commission numbers for 4,868 microbial enzymes across 161 EC3 subclasses at 78.9% top-1 / 88.5% top-5 accuracy — 37.6 points above 3-mer baselines — with no task-specific training.
WHY IT MATTERS: Annotating "enzyme dark matter" in microbial genomes/metagenomes is a major bottleneck for functional metagenomics, and this shows mechanistic-interpretability features from large pLMs can double as cheap, GPU-light, human-interpretable function predictors. It extends the growing trend (cf. InterPLM, VFUSE) of using SAE features as a general-purpose interface to pLM "knowledge" beyond just generative safety auditing.
CODE: Not released
---

---
TITLE: Flow Matching with In-Context Priors for Out-of-Distribution Brain Dynamics
AUTHORS: Sam Gijsen, Michał Łukomski, Marc-André Schulz, Kerstin Ritter
SOURCE: arXiv | 2606.11833 | [**Link**](https://arxiv.org/abs/2606.11833)
TOPIC TAG: Flow Matching
TLDR: Proposes a per-timestep-conditioned diffusion transformer that injects compositional language and optional spatial priors in-context to generate realistic fMRI brain dynamics for cognitive tasks never seen during training, enabling zero-shot generalization to novel task compositions.
WHY IT MATTERS: Generative models of biological time series have largely been stuck with categorical conditioning, limiting compositional generalization; this in-context flow-matching recipe is a template directly transferable to other biological time-series domains (e.g., single-cell trajectories, electrophysiology) where novel experimental conditions are common and labeled data is scarce. The authors frame this as enabling "counterfactual" in-silico experiment design before costly empirical validation — a pattern with clear analogues in wet-lab experimental planning.
CODE: Not released
---

---
TITLE: Integrating gene regulatory priors into Transformer attention with scTransformer for interpretable scRNA-seq analysis
AUTHORS: [Authors from 2606.09558] et al.
SOURCE: arXiv | 2606.09558 | [**Link**](https://arxiv.org/abs/2606.09558)
TOPIC TAG: Genomics
TLDR: Introduces scTransformer, which constrains self-attention according to known gene regulatory network structure rather than treating genes as independent features, and shows the regulatory prior preserves predictive performance at scale while improving robustness to noise/batch effects and reproducibility of inferred regulatory modules.
WHY IT MATTERS: Most large single-cell foundation models learn gene-gene relationships purely from data, sacrificing interpretability and sometimes robustness; this is among the first to bake curated regulatory priors directly into attention computation for scRNA-seq transformers. A biologically constrained attention mechanism could become a standard add-on for single-cell foundation models that need both scale and mechanistic interpretability.
CODE: Not released
---

---
TITLE: Representation-Aware Advantage Estimation: Your Reward Model Provides More Than A Scalar Output
AUTHORS: Guozheng Li, Xiyan Fu, Yiwen Guo
SOURCE: arXiv | 2606.10528 | [**Link**](https://arxiv.org/abs/2606.10528)
TOPIC TAG: General ML
TLDR: Proposes Graph-based Advantage Estimation (GraphAE), which treats a sampled group of RLHF rollouts as a graph with edges weighted by similarity in reward-model hidden-state space, then propagates advantages across the graph to give richer, less noisy training signals than scalar rewards alone.
WHY IT MATTERS: RLHF/RLAIF pipelines for biological sequence design (e.g., reward-guided protein or molecule generation) typically discard the rich semantic structure in reward-model hidden states in favor of a single scalar; GraphAE's graph-propagation trick is directly applicable to any setting where a learned reward/fitness model scores batches of candidate sequences or molecules. This could improve sample efficiency of preference-optimization loops used in directed evolution and binder design.
CODE: Not released
---

---
TITLE: In-Context Learning for Latent Space Bayesian Optimization
AUTHORS: Tuan A. Vu, Harri Lähdesmäki, Julien Martinelli
SOURCE: arXiv | 2606.09664 | [**Link**](https://arxiv.org/abs/2606.09664)
TOPIC TAG: General ML
TLDR: Continues pretraining tabular foundation-model BO surrogates (TabPFN/TabICL-style) on synthetic optimization tasks defined over a molecular VAE's latent space, with a regularizer anchoring to the original checkpoint, to close the gap between regression-style pretraining and the very different latent-to-objective maps seen in latent-space Bayesian optimization.
WHY IT MATTERS: Latent-space BO over molecule/protein VAEs is a core tool for sample-efficient wet-lab experimental design, but in-context regression surrogates are pretrained on tasks that don't resemble these latent optimization landscapes. A continued-pretraining recipe that specifically targets this mismatch could make foundation-model BO surrogates practical drop-in replacements for Gaussian processes in molecular and protein optimization loops.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. m6A-FORM: A Foundation Model for Decoding N6-methyladenosine Biology**
arXiv:2606.12219 | [Link](https://arxiv.org/abs/2606.12219)

m6A-FORM pretrains on ~22M MeRIP-seq peak-derived sequences (143 human studies) and then fine-tunes on single-nucleotide-resolution m6A annotations, hitting ROC-AUC 0.988 and a 0.14+ PR-AUC improvement over prior predictors while running substantially faster. Its peak-prior pretraining strategy avoids the costly adenosine-centered scanning used by earlier methods, and the same backbone transfers to predicting binding sites for 19 m6A regulators and degradation-linked YTHDF2 sites. This positions it as a strong reusable foundation for epitranscriptomic regulatory modeling, an area still underserved by general genomic LMs.
Code: Not released

**2. Interpretable enzyme function prediction via sparse autoencoder features of ESMC across the microbial protein universe**
arXiv:2606.12209 | [Link](https://arxiv.org/abs/2606.12209)

By training a large (16,384-dim) sparse autoencoder on ESMC-6B activations and annotating each latent feature with GPT-5, this work turns mechanistic-interpretability features into a zero-training-cost enzyme function classifier, achieving 78.9% top-1 / 88.5% top-5 EC-number accuracy — a 37.6-point jump over k-mer baselines. It is a notable demonstration that SAE features extracted from frontier protein LMs aren't just useful for safety auditing (cf. yesterday's VFUSE) but can directly serve as interpretable, GPU-light functional annotation tools for the vast unannotated microbial protein universe.
Code: Not released

**3. Integrating gene regulatory priors into Transformer attention with scTransformer for interpretable scRNA-seq analysis**
arXiv:2606.09558 | [Link](https://arxiv.org/abs/2606.09558)

scTransformer constrains attention computation using known gene regulatory network structure instead of letting genes attend freely, and shows this regulatory prior improves robustness to noise/batch effects and the reproducibility of inferred regulatory modules without sacrificing scale-dependent predictive performance. As single-cell foundation models grow ever larger and more opaque, this offers a concrete mechanism for injecting decades of curated regulatory biology directly into the architecture rather than hoping it emerges from data alone.
Code: Not released

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 6
- By topic: Protein LM: 1 | Diffusion: 0 | Text Diffusion: 0 | Flow Matching: 1 | Genomics: 2 | Architecture: 0 | MoE: 0 | General ML: 2 | Clinical ML: 0
- Sources: arXiv: 6 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
