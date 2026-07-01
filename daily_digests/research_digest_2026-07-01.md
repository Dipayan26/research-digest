# Research Digest — 2026-07-01

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct fetches to arxiv.org, export.arxiv.org, biorxiv.org, and api.biorxiv.org again returned HTTP 403 at the network gateway in this environment (confirmed policy denial on `api.biorxiv.org:443`), so discovery relied entirely on WebSearch and the Hugging Face MCP `paper_search` connector, as in prior runs. WebSearch/engine indexing also lags true same-day arXiv postings by roughly 1–2 days — no arXiv IDs in the `2607.xxxxx` (July 1) range were indexed yet at run time, and bioRxiv/medRxiv/PubMed search snippets again showed no confirmable postings inside the strict last-24h window. To keep the digest useful, coverage below extends to the most recent *confirmed-new* arXiv postings (June 24–29) that were not already reported in a prior digest, deduplicated against the full digest history. One low-confidence bioRxiv candidate (date-uncertain, author list unverifiable behind the network block) was found and excluded rather than risk misattribution. Six papers survived dedup and verification this cycle.

---

---
TITLE: Beyond Drug Discovery: The Nanotechnology Molecular Optimization (NMO) Benchmark
AUTHORS: Matthias Blaschke, Daniel Kienzle, Zsuzsanna Koczor-Benda, Julian Lorenz, Rainer Lienhart, Fabian Pauly
SOURCE: arXiv | 2606.30170 | [**Link**](https://arxiv.org/abs/2606.30170)
TOPIC TAG: General ML
TLDR: NMO replaces the drug-discovery-flavored proxy oracles used in nearly all molecular-optimization benchmarks with quantum-simulation-based objectives from nanotechnology (phonon transport, thermoelectric efficiency, molecular optomechanics), and finds that advanced generative optimizers underperform simple genetic algorithms on these rugged, physics-constrained landscapes.
WHY IT MATTERS: Most generative molecular design methods are tuned and validated almost exclusively on pharma-flavored proxy metrics, which risks overfitting to leaderboard idiosyncrasies rather than genuine chemical-space search ability; NMO is a rare out-of-domain stress test that exposes this gap directly. The finding that state-of-the-art optimizers can lose to genetic algorithms once benchmarks move away from drug-like proxy oracles is a useful cautionary result for anyone building generative models intended to generalize beyond drug discovery (e.g., to biomaterials or enzyme active-site chemistry).
CODE: Not released
---

---
TITLE: Molexar: A Unified Multimodal Molecular Foundation Model for Drug Design
AUTHORS: Haoyu Lin, Yiyan Liao, Jinmei Pan, Xinliao Ling, Luhua Lai, Jianfeng Pei
SOURCE: arXiv | 2606.25865 | [**Link**](https://arxiv.org/abs/2606.25865)
TOPIC TAG: General ML
TLDR: Molexar is a single autoregressive decoder (Gemma2-based) trained on Fragment-SELFIES, a validity-preserving fragment-aware molecular language, then supervised-fine-tuned so the same decoder can generate molecules conditioned on scalar properties, pharmacophore fingerprints, protein sequences, or binding pockets via in-place condition-token replacement.
WHY IT MATTERS: Most conditional molecular generators need separate architectures or adapters per condition type (property-conditioned vs. structure-conditioned vs. pocket-conditioned); unifying all of these generation modes behind one autoregressive path and one fragment-based tokenization is a cleaner path toward general-purpose molecule generators. Reported 100% validity plus competitive target-conditioned generation on CrossDocked2020 suggests the fragment-tree tokenization is a meaningfully more robust string representation than plain SMILES/SELFIES for multimodal conditioning.
CODE: Not released
---

---
TITLE: Stable-Shift: Biologically Structured Prediction of Transcriptional Responses to Unseen Gene Perturbations
AUTHORS: Sajib Acharjee Dip, Liqing Zhang
SOURCE: arXiv | 2606.24940 | [**Link**](https://arxiv.org/abs/2606.24940)
TOPIC TAG: Genomics
TLDR: Stable-Shift predicts transcriptional responses to never-before-perturbed genes by fitting a low-rank response basis from training perturbations only and placing an unseen gene into that basis using STRING interactions, network structure, control-cell statistics, and GO annotations (integrated via graph convolution); it beats GEARS on the K562 Perturb-seq benchmark (0.592 vs. 0.569 cosine similarity).
WHY IT MATTERS: Extrapolating perturbation response to genes with zero perturbation data is the central open problem in in-silico Perturb-seq modeling, since exhaustive experimental screening of the genome is infeasible; a low-rank structured basis fit purely from biological priors (rather than requiring the model to have seen the gene perturbed) is a more principled inductive bias than nearest-neighbor-style baselines like GEARS. Beating GEARS with a simpler, more interpretable structured method — with reproducible code released — makes this a strong new baseline for the unseen-gene-perturbation task.
CODE: [**Code**](https://github.com/Sajib-006/PerturbGraph)
---

---
TITLE: PerturbCellRL: Verifier-Guided Reinforcement Learning for Single-Cell Perturbation Prediction
AUTHORS: Dongxia Wu, Mingyu Li, Yuhui Zhang, Anurendra Kumar, Emma Lundberg, Serena Yeung-Levy, Emily B. Fox
SOURCE: arXiv | 2606.27752 | [**Link**](https://arxiv.org/abs/2606.27752)
TOPIC TAG: Genomics
TLDR: PerturbCellRL post-trains a pretrained flow-matching single-cell transcriptomic generator with RL, using four cell-level verifier rewards (Pearson top-k similarity, RMSE top-k proximity, DE Spearman correlation, and pathway-activity consistency) so that individual generated cells — not just population-level statistics — are checked for biological plausibility.
WHY IT MATTERS: Prior generative single-cell perturbation models are optimized and evaluated almost entirely at the population/distribution level, which can hide individually implausible generated cells; verifier-guided RL alignment is a direct transplant of the "RLHF/RLAIF with a reward model" recipe from LLMs into single-cell biology, using biological consistency checks instead of human preference as the reward signal. Remaining competitive on population-level metrics while improving cell-level biological consistency suggests this alignment-style post-training is a promising general recipe for virtual-cell models beyond just this one generator.
CODE: Not released
---

---
TITLE: Towards Coevolution-Aware Ancestral Sequence Reconstruction
AUTHORS: Alya Zeinaty, Leonardo di Bari, Saverio Rossi, Pierre Barrat-Charlaix, Francesco Zamponi, Martin Weigt
SOURCE: arXiv | 2606.27942 | [**Link**](https://arxiv.org/abs/2606.27942)
TOPIC TAG: Protein LM
TLDR: This work combines standard phylogenetic ancestral-sequence-reconstruction inference with Direct Coupling Analysis (a generative Potts-model coevolution model) so that reconstructed ancestral protein sequences respect residue-residue epistatic constraints instead of assuming site-independent evolution.
WHY IT MATTERS: Nearly all ASR pipelines assume sites evolve independently, which the authors show causes maximum-a-posteriori reconstructions to over-concentrate on a single over-idealized sequence and independent posterior sampling to produce implausible ancestors that violate known structural couplings. Injecting a learned coevolution model into the reconstruction step is a concrete way for generative sequence models (already used for protein design) to improve a classical evolutionary-biology inference task, rather than the more common direction of evolutionary data only informing generative model training.
CODE: Not released
---

---
TITLE: Reconstructability of Evolutionary Intermediates in Generative Epistatic Landscapes
AUTHORS: Roberto Netti, Martin Weigt
SOURCE: arXiv | 2606.27983 | [**Link**](https://arxiv.org/abs/2606.27983)
TOPIC TAG: Protein LM
TLDR: Using generative epistatic sequence-landscape models as controlled ground-truth simulators of protein-family evolution, the authors show that maximum-likelihood point estimates of evolutionary intermediates can be residue-wise accurate yet statistically atypical, while conditional sampling better recovers the true ensemble of plausible evolutionary histories — and that reconstructability itself depends on the local mutability of the fitness landscape.
WHY IT MATTERS: This directly questions a default assumption in generative-model evaluation — that the single best point prediction is the "right" one to report — by showing point estimates and distributional faithfulness can diverge sharply for evolutionary reconstruction tasks. The landscape-topology-dependent predictability result (constrained regions preserve path information; permissive regions erase it) gives a concrete, testable criterion for when any coevolution-based generative model's ancestral/intermediate predictions should or shouldn't be trusted.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

- **TITLE: Beyond Drug Discovery: The Nanotechnology Molecular Optimization (NMO) Benchmark**
  Why this is the highlight: NMO is a genuinely out-of-distribution stress test for generative molecular design, replacing pharma proxy oracles with real quantum-simulated physical objectives (phonon transport, thermoelectric efficiency, optomechanics) drawn from nanotechnology rather than drug discovery. It imposes hard structural constraints and rugged fitness landscapes that most molecular generators have never been evaluated against, and the headline finding — that advanced optimizers lose to plain genetic algorithms once the drug-like proxy crutch is removed — is a sharp, actionable warning about benchmark overfitting in the field. This matters broadly because the same generative architectures (VAEs, RL-based molecule optimizers, diffusion models) used for drug design are increasingly repurposed for materials and enzyme design, where this benchmark suggests current methods may be far weaker than leaderboards imply.
  Code/weights: Not released.

- **TITLE: Stable-Shift: Biologically Structured Prediction of Transcriptional Responses to Unseen Gene Perturbations**
  Why this is the highlight: Stable-Shift tackles the hardest and most practically important version of the Perturb-seq prediction task — genes with zero perturbation data at training time — by fitting a low-rank response basis from known perturbations and locating unseen genes in that basis using STRING interactions, network structure, and GO annotations via graph convolution. It beats the widely-used GEARS baseline on the standard K562 benchmark while being simpler and more interpretable, and the authors released working code. This is a strong, reproducible new baseline for exactly the use case — extrapolating to genes nobody has wet-lab screened yet — that determines how useful in-silico perturbation models actually are for prioritizing real experiments.
  Code/weights: [Code](https://github.com/Sajib-006/PerturbGraph).

- **TITLE: PerturbCellRL: Verifier-Guided Reinforcement Learning for Single-Cell Perturbation Prediction**
  Why this is the highlight: PerturbCellRL transplants the "pretrain, then RL-align against a verifier reward" recipe — the same recipe behind RLHF/RLAIF for LLMs — into single-cell virtual-cell modeling, post-training a flow-matching generator against four biologically-grounded cell-level reward signals instead of population-level distributional losses. This targets a real blind spot in current single-cell generative models: matching aggregate statistics while individual generated cells can still be biologically implausible. Coming from a strong cross-institution team (Stanford/collaborators including Emma Lundberg and Emily Fox), this is an early and well-executed example of alignment-style post-training being adapted for virtual cell models, a direction likely to generalize to other omics generators.
  Code/weights: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 6
- By topic: Protein LM: 2 | Diffusion: 0 | Genomics: 2 | Architecture: 0 | General ML: 2 | Clinical: 0
- Sources: arXiv: 6 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 1
