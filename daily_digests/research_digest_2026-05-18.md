# Research Digest — 2026-05-18

> **Coverage window:** arXiv submissions from May 14–18, 2026 (IDs ≥2605.13933, continuing from where the May 17 digest ended), plus catch-up papers from earlier in the 2605.XXXXX window not yet featured; bioRxiv preprints checked through May 17–18. Today's digest spotlights evolutionary protein diffusion (ICML 2026), multi-objective protein design with tree search, biologically-motivated antibody discrete diffusion, synthetic-biology RL, and a bioRxiv landmark discovery of non-canonical protein assemblies.

---
TITLE: Towards A Generative Protein Evolution Machine with DPLM-Evo
AUTHORS: Xinyou Wang et al.
SOURCE: arXiv | 2605.00182 | [**Link**](https://arxiv.org/abs/2605.00182)
TOPIC TAG: Protein LM / Diffusion
TLDR: DPLM-Evo replaces masking-based absorbing diffusion with an evolutionary noise process that explicitly predicts substitution, insertion, and deletion operations, decoupling a variable-length observed sequence space from an upsampled latent alignment space to make indel-aware protein generation tractable — achieving state-of-the-art single-sequence mutation effect prediction on ProteinGym at ICML 2026.
WHY IT MATTERS: All prior discrete diffusion protein LMs (DPLM, DPLM-2) use a masked absorbing state that biologically implies proteins emerge from nothing, contradicting the evolutionary reality of accumulated edits; DPLM-Evo's contextualized noising kernel produces biologically informed, context-dependent mutation patterns aligned with actual sequence divergence distributions. Beyond benchmarks, DPLM-Evo enables post-hoc optimization via explicit edit trajectories and variable-length scaffold growth — two capabilities essential for real directed evolution campaigns.
CODE: Not released

---

---
TITLE: MP2D: Constrained Monte Carlo Tree-Guided Diffusion for Multi-Objective Protein Sequence Design
AUTHORS: (arXiv 2605.05829 authors)
SOURCE: arXiv | 2605.05829 | [**Link**](https://arxiv.org/abs/2605.05829)
TOPIC TAG: Diffusion
TLDR: MP2D frames discrete diffusion denoising as a constrained sequential decision-making problem and uses Monte Carlo Tree Search with Pareto-based rewards to explore diverse denoising trajectories, combined with global iterative re-masking and re-optimization, outperforming multi-objective baselines on antimicrobial peptide and protein binder design without retraining the generative model.
WHY IT MATTERS: Multi-objective protein design with conflicting constraints (e.g., binding affinity vs. stability vs. toxicity) is beyond the reach of single-objective guidance methods and requires explicit exploration of the Pareto frontier; MP2D achieves this by using MCTS as a structured search layer on top of any pretrained diffusion model, enabling controllable multi-property tradeoffs without gradient-based guidance instability. The no-retraining property means the framework can be wrapped around ESM3, DPLM, or any future protein diffusion model as a plug-and-play search harness.
CODE: Not released

---

---
TITLE: Conditional Generation of Antibody Sequences with Classifier-Guided Germline-Absorbing Discrete Diffusion
AUTHORS: Justin Sanders et al.
SOURCE: arXiv | 2605.06720 | [**Link**](https://arxiv.org/abs/2605.06720)
TOPIC TAG: Diffusion / Protein LM
TLDR: Germline-absorbing diffusion replaces the masked absorbing state with the germline sequence as the diffusion endpoint, restricting learning to the somatic hypermutation trajectory and improving non-germline residue prediction accuracy from 26% to 46% (approaching the biological ceiling), while classifier-guided sampling enables conditional generation of antibodies with improved hydrophobicity and predicted binding affinity.
WHY IT MATTERS: Standard protein diffusion models are trained on the full sequence distribution and therefore predominantly memorize germline sequences, producing antibody designs that are too conservative and overlook the specific somatic variation patterns critical for high-affinity binding; germline-absorbing diffusion is the first principled correction to this bias using a biologically meaningful absorbing state derived from V(D)J recombination. Combined with off-the-shelf classifier guidance, the method significantly outperforms EvoProtGrad on the affinity-hydrophobicity Pareto tradeoff, providing a practical route to therapeutic antibody design.
CODE: Not released

---

---
TITLE: Learning the Interaction Prior for Protein-Protein Interaction Prediction: A Model-Agnostic Approach
AUTHORS: Ziqi Gao, Chenyi Zi, Zijing Liu, Ziqiao Meng, Yu Li, Jia Li
SOURCE: arXiv | 2605.09964 | [**Link**](https://arxiv.org/abs/2605.09964)
TOPIC TAG: Protein LM
TLDR: L3-PPI injects a biologically motivated graph prompt — built from virtual length-3 paths between protein pairs — into any PPI predictor as a plug-and-play classification head, encoding the "L3 rule" (multiple indirect three-hop connections indicate interaction likelihood) and consistently boosting performance over advanced competitors.
WHY IT MATTERS: Existing learning-based PPI predictors invest entirely in protein representation quality but use generic aggregation heads (concatenation, dot product) that discard the network-level interaction prior known to biologists; L3-PPI provides the missing structural inductive bias by prompting with virtual L3 paths without retraining the base encoder. The model-agnostic design means any current or future protein representation backbone instantly gains PPI network awareness, with direct applications to drug target identification and systems-level disease network modeling.
CODE: Not released

---

---
TITLE: Expanding Functional Protein Sequence Space Using High Entropy Generative Models
AUTHORS: (arXiv 2605.03578 authors)
SOURCE: arXiv | 2605.03578 | [**Link**](https://arxiv.org/abs/2605.03578)
TOPIC TAG: Protein LM / General ML
TLDR: Systematic comparison of fully-connected bmDCA, sparse progressive edge-activation (eaDCA), and edge-decimation (edDCA) Boltzmann machines on the Chorismate Mutase family identifies a maximum-entropy decimation checkpoint (meDCA) that optimally balances constraint satisfaction against distribution flexibility, generating more diverse and novel functional sequences than denser models.
WHY IT MATTERS: The conventional assumption that adding parameters to DCA/Boltzmann machine models monotonically improves generative quality is challenged here — excessive density collapses the generated distribution toward the training set, limiting exploration of functional sequence space; meDCA's sweet spot provides a principled model selection criterion applicable across protein families. The sparse model incidentally doubles as a more interpretable contact map, useful for identifying structurally and functionally critical residue pairs in directed evolution campaigns.
CODE: Not released

---

---
TITLE: FL-Sailer: Efficient and Privacy-Preserving Federated Learning for Scalable Single-Cell Epigenetic Data Analysis via Adaptive Sampling
AUTHORS: (arXiv 2605.04519 authors)
SOURCE: arXiv | 2605.04519 | [**Link**](https://arxiv.org/abs/2605.04519)
TOPIC TAG: Genomics / General ML
TLDR: FL-Sailer combines adaptive leverage score sampling with an invariant VAE architecture to enable privacy-preserving federated analysis of single-cell ATAC-seq data across institutions, substantially reducing communication cost while maintaining downstream cell-type annotation and chromatin accessibility prediction quality.
WHY IT MATTERS: Single-cell epigenomics datasets are fragmented across clinical and research centers that cannot share raw data; FL-Sailer is the first federated learning framework specifically designed for scATAC-seq, addressing the twin challenges of high sparsity (>95% zeros) and extreme dimensionality through principled adaptive subsampling. The invariant VAE architecture explicitly decouples biological variation from batch effects in the federated setting, making cross-institutional multi-omics integration feasible without a central data repository.
CODE: Not released

---

---
TITLE: Sequential Design of Genetic Circuits Under Uncertainty With Reinforcement Learning
AUTHORS: Michal Kobiela, Diego A. Oyarzún, Michael U. Gutmann
SOURCE: arXiv | 2605.06552 | [**Link**](https://arxiv.org/abs/2605.06552)
TOPIC TAG: General ML
TLDR: An amortized RL policy trained across a distribution of uncertain circuit parameters proposes adaptive experiment sequences for genetic circuit optimization under both intrinsic stochasticity and unknown lab-condition variability — without requiring expensive per-round Bayesian inference — outperforming non-adaptive baselines including Bayesian optimization on heterologous gene expression tasks.
WHY IT MATTERS: Iterative design-build-test-learn cycles for genetic circuits are bottlenecked by computationally expensive Bayesian inference steps between rounds; by amortizing the policy over the distribution of possible laboratory conditions, the RL agent effectively "learns to learn" about new experimental contexts through a single forward pass at test time. This is a compelling proof-of-concept that meta-learning approaches can accelerate synthetic biology design loops beyond what any single-round optimization strategy can achieve.
CODE: Not released

---

---
TITLE: GenCircuit-RL: Reinforcement Learning from Hierarchical Verification for Genetic Circuit Design
AUTHORS: Noah Flynn
SOURCE: arXiv | 2605.14215 | [**Link**](https://arxiv.org/abs/2605.14215)
TOPIC TAG: General ML
TLDR: GenCircuit-RL applies RL with hierarchical verification rewards (five levels from code execution through task-specific topology) and a four-stage curriculum to fine-tune an LLM for generating pysbol3 Python code that constructs verified genetic circuits in SBOL, benchmarked on SynBio-Reason — a new dataset of 4,753 circuits spanning six canonical circuit types and nine design tasks.
WHY IT MATTERS: Genetic circuit design has resisted automation because correctness is compositional: a syntactically valid program can produce structurally inconsistent or biologically unfeasible SBOL outputs; the hierarchical reward decomposes this hard sparse-reward problem into dense per-level feedback that stabilizes RL training. SynBio-Reason is the first large-scale benchmark to evaluate code-based genetic circuit design from repair through de novo generation, providing the infrastructure to measure progress as LLMs become increasingly capable molecular engineering assistants.
CODE: Not released

---

---
TITLE: AI-Guided Discovery of Atypical Protein Assemblies
AUTHORS: (The Sainsbury Laboratory, bioRxiv 2026.05.03.722499 authors)
SOURCE: bioRxiv | 10.64898/2026.05.03.722499 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.03.722499v1)
TOPIC TAG: Protein LM
TLDR: The Structural Novelty Index (SNI) is a quantitative framework that scores AlphaFold3-predicted protein complexes by their divergence from canonical architectures; applied to 637 NRC immune receptor proteins across 346 plant genomes, SNI identified NRC7 orthologs predicted to form non-hexameric assemblies — confirmed experimentally by negative-stain TEM as an unprecedented undecameric (11-mer) resistosome.
WHY IT MATTERS: AlphaFold and related structure predictors are deployed overwhelmingly to confirm expected folds; SNI is the first systematic framework to mine these predictions specifically for structurally deviant assemblies that may represent undiscovered functional mechanisms. The experimental validation of an 11-mer assembly — a structurally unprecedented configuration in the NLR immune receptor superfamily — demonstrates that AI-guided novelty screening can reveal genuinely new biology inaccessible to canonical functional annotation pipelines.
CODE: Not released

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

### 1. DPLM-Evo: Towards A Generative Protein Evolution Machine (ICML 2026)
**What, how, why it matters:** DPLM-Evo (arXiv 2605.00182) replaces the masked absorbing state of all prior discrete diffusion protein LMs with an evolutionary noise process that models substitutions, insertions, and deletions — the actual molecular events of Darwinian evolution. By decoupling a variable-length observed sequence from an upsampled latent alignment space, it makes indel-aware generation tractable with negligible overhead. Accepted to ICML 2026, it achieves state-of-the-art single-sequence mutation effect prediction on ProteinGym and enables post-hoc protein optimization via explicit, interpretable edit trajectories — closing a long-standing gap between the biological intuition of protein evolution and the mathematical machinery of generative models.
**Code / weights:** Not yet released — arXiv: https://arxiv.org/abs/2605.00182

---

### 2. Germline-Absorbing Discrete Diffusion for Antibody Design
**What, how, why it matters:** Sanders et al. (arXiv 2605.06720) identify a systematic and previously unaddressed flaw in applying generic discrete diffusion to antibody sequences: standard masked diffusion trains on the whole distribution, memorizing germline sequences and suppressing the somatic hypermutation variation that matters for binding. Replacing the absorbing state with the germline sequence redirects the diffusion trajectory to learn exactly the somatic variation landscape, boosting non-germline residue prediction from 26% to 46% — near the biological ceiling set by true variability. The approach pairs naturally with any off-the-shelf property classifier for conditional generation, making it a drop-in upgrade to any antibody design pipeline.
**Code / weights:** Not released — arXiv: https://arxiv.org/abs/2605.06720

---

### 3. AI-Guided Discovery of an Undecameric Plant Immune Receptor Assembly
**What, how, why it matters:** The SNI framework (bioRxiv 10.64898/2026.05.03.722499) turns the wealth of AlphaFold3 structure predictions into a discovery engine for biological novelty rather than confirmation of known folds. By scoring predicted assemblies against canonical architecture templates, SNI flagged NRC7 orthologs as atypical across multiple plant species — and negative-stain TEM confirmed an 11-mer resistosome, a completely new quaternary architecture in the NLR immune receptor family with potential implications for plant immunity engineering. This is the clearest demonstration to date that AI-predicted structures contain novel biology that active "novelty mining" pipelines can surface, validate, and exploit.
**Code / weights:** Not released — bioRxiv: https://www.biorxiv.org/content/10.64898/2026.05.03.722499v1

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 9
- By topic: Protein LM: 4 | Diffusion: 2 | Genomics: 1 | General ML: 2 | Clinical ML: 0
- Sources: arXiv: 8 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
