# Research Digest — 2026-06-25

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct WebFetch to arxiv.org, export.arxiv.org, biorxiv.org, and medrxiv.org/pubmed.ncbi.nlm.nih.gov again returned HTTP 403 in this environment, so discovery relied on three parallel WebSearch sweeps (by source/topic cluster) plus the Hugging Face MCP `paper_search` connector, followed by a dedicated verification pass that re-searched each shortlisted candidate individually to confirm title/authors/ID/date before inclusion. PubMed, medRxiv, and Papers With Code again contributed no confirmable last-24-72h items — PubMed indexing lags preprints by more than a few days, medRxiv turned up nothing on-topic in the window, and PWC's site-restricted search surfaced only stale author/database pages. The majority of raw candidates returned by this sweep (ProHiFlo, SurfDesign, AlloGen, Viral Proteins Reveal Geometry of PLMs, AgentPLM, RicciBind, CPES, AF_Cache, Flexible Kernels for Protein Property Prediction, Flexible Flows for Biological Sequence Design, GSS-Transformer, RAMMESI, LOGICA, Is It You or Your Environment?, MoE-Bind, TCRDiff, ViroBench, JEPA-DNA, TadA-Bench, ProtAff, Trustworthy Agentic Genomics via Versioned Skill Libraries, biomeStat, and Proto) were cross-checked line-by-line against the full prior digest history (497 titles through 2026-06-24) and excluded as duplicates already covered in earlier digests. Two remaining candidates' guessed DOIs were found to be wrong during verification and corrected (predNMD, Tiny Subsamples). A live-cell imaging enhancer-promoter biophysics paper and an "Evo 2 for bacteriophage genome design" candidate were excluded for insufficient ML-method content / unconfirmable detail respectively.

---

---
TITLE: How Post-Training Shapes Biological Reasoning Models
AUTHORS: Lukas Fesser, Hanlin Zhang, Michelle M. Li, Eric Wang, Bryan Perozzi, Shekoofeh Azizi, Sham M. Kakade, Marinka Zitnik
SOURCE: arXiv | 2606.16517 | [**Link**](https://arxiv.org/abs/2606.16517)
TOPIC TAG: General ML
TLDR: Trains and evaluates 100+ biological reasoning models under controlled variation of continued pretraining, SFT, and RL, finding that brief SFT followed by a larger RL budget gives the best in-distribution/out-of-distribution generalization tradeoff.
WHY IT MATTERS: Post-training recipes for biological LLMs are usually copied wholesale from general-domain pipelines without checking whether they generalize the same way on genomics/transcriptomics/protein tasks; this is one of the first controlled, large-scale ablations showing they don't — SFT alone causes an early OOD peak-then-decline that RL on top of it reverses. The result is directly actionable for anyone post-training a domain-specific biological reasoning model rather than a one-off benchmark finding.
CODE: Not released
---

---
TITLE: A Drug-Target Specificity Foundation Model for Off-target Prediction, Repurposing, and Generative Design (dtSFM)
AUTHORS: Sai T. Reddy et al.
SOURCE: bioRxiv | 10.64898/2026.06.08.730844 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.08.730844v1)
TOPIC TAG: Clinical ML
TLDR: Builds a drug-target specificity foundation model on the premise that Transformer softmax attention is mathematically isomorphic to the Boltzmann distribution governing equilibrium binding, training on 714,747 drug-protein interactions to predict off-targets and generate novel candidate molecules.
WHY IT MATTERS: Off-target prediction is usually bolted onto binding-affinity models as an afterthought, but framing attention itself as a thermodynamic binding model gives a principled reason why the architecture should transfer to off-target ranking; it ranks documented off-targets of approved kinase inhibitors in the top 0.6% of the genome. The generative decoder closing the loop (850/1,200 generated molecules matching AlphaFold3-confidence of approved drugs) makes this a rare specificity model that also designs, not just scores.
CODE: Not confirmed
---

---
TITLE: DeepBD: A Grounded Agentic Workflow for Variant Prioritization and Diagnosis of Genetic Birth Defects
AUTHORS: Shiyu Li, Ziqi Yan, Zhihao Wu, Jielong Lu, Weiran Liao, Jiajun Yu, Genjie Li, Zeyu Chu, Jiajun Bu, Haishuai Wang
SOURCE: arXiv | 2606.24779 | [**Link**](https://arxiv.org/abs/2606.24779)
TOPIC TAG: Clinical ML
TLDR: An LLM-driven agentic pipeline combining case structuring, a pretrained evidence engine, specialist evidence modules, and a grounded review layer prioritizes causal variants for genetic birth defects, reaching Recall@1 of 0.658 and Recall@10 of 0.929 on 18,622 fetal/infant cases — beating Exomiser, DeepRare, and prompted-LLM reranking.
WHY IT MATTERS: Most "LLM for variant prioritization" work is a thin prompting wrapper around existing tools; DeepBD instead grounds each reasoning step in retrieved evidence and validates on a real clinical cohort nearly two orders of magnitude larger than typical rare-disease benchmarks. Beating Exomiser and DeepRare head-to-head on recall is a meaningful bar to clear for an agentic system in a domain where false negatives have direct clinical consequences.
CODE: Not confirmed
---

---
TITLE: EurekAgent: Agent Environment Engineering is All You Need For Autonomous Scientific Discovery
AUTHORS: Amy Xin, Jiening Siow, Junjie Wang, Zijun Yao, Fanjin Zhang, Jian Song, Lei Hou, Juanzi Li
SOURCE: arXiv | 2606.13662 | [**Link**](https://arxiv.org/abs/2606.13662)
TOPIC TAG: General ML
TLDR: Argues that the bottleneck for autonomous scientific-discovery agents has shifted from workflow design to "environment engineering" — shaping resources, constraints, and interfaces to suppress reward hacking — and shows SOTA results across math, kernel engineering, and ML discovery tasks for under $11 in total API cost.
WHY IT MATTERS: Most agentic-science papers iterate on prompting or tool-calling scaffolds while treating the execution environment as fixed; this flips the emphasis and gets a new SOTA circle-packing result as a side effect, suggesting environment design has been an underexplored lever. The extremely low compute cost reported is also a useful data point for anyone weighing whether agentic discovery pipelines are practically affordable yet.
CODE: [**Code**](https://github.com/THU-Team-Eureka/EurekAgent)
---

---
TITLE: BioMatrix: Towards a Comprehensive Biological Foundation Model Spanning the Modality Matrix of Sequences, Structures, and Language
AUTHORS: Qizhi Pei et al.
SOURCE: arXiv | 2606.22138 | [**Link**](https://arxiv.org/abs/2606.22138)
TOPIC TAG: Architecture
TLDR: A decoder-only multimodal foundation model built on Qwen3 (1.7B/4B) natively integrates sequence, structure, and natural-language modalities for both molecules and proteins in a shared discrete token space, continually pretrained on 304.4B tokens of mixed general and cross-modal biological text.
WHY IT MATTERS: Sequence-structure-language unification is usually attempted with bespoke architectures trained from scratch; starting from a strong general-purpose LLM backbone and continually pretraining on cross-modal biological corpora is a cheaper, more reusable path to the same goal and inherits general reasoning ability for free. Spanning both molecules and proteins in one shared token space (rather than two separate specialist models) is also a more unified setup than most prior multimodal bio-LM work.
CODE: Not confirmed
---

---
TITLE: HiST: A Hierarchical Sparse Transformer for Cross-Modal Spatial Transcriptomics Modeling
AUTHORS: Weiyi Wu, Xinwen Xu, Xingjian Diao, Siting Li, Zhi Wei, Alma Andersson, Jiang Gui
SOURCE: arXiv | 2606.14251 | [**Link**](https://arxiv.org/abs/2606.14251)
TOPIC TAG: Genomics
TLDR: Treats spatial transcriptomics measurement locations as a lattice-indexed sparse field rather than a dense image, building a dyadic encoder-decoder with sparse window attention and resolution-changing operators to infer gene expression from H&E histology at multiple scales. Accepted to ICML 2026.
WHY IT MATTERS: Most histology-to-expression models densify the tissue into a regular grid and pay a real compute cost for mostly-empty space; operating directly on the sparse, irregular set of actually-measured spots is a more natural inductive bias for spot-based ST platforms and should scale better to whole-slide resolution. The multiscale resolution-changing design also gives a principled way to transfer across ST platforms with different spot densities.
CODE: Not confirmed
---

---
TITLE: Measurement noise limits the advantage of nonlinear models over linear models in biomedical prediction
AUTHORS: Marc-André Schulz, Kerstin Ritter
SOURCE: arXiv | 2606.18420 | [**Link**](https://arxiv.org/abs/2606.18420)
TOPIC TAG: General ML
TLDR: Shows across 140 UK Biobank prediction tasks that flexible models (deep nets, GBTs, kernel methods) often fail to beat linear regression not because of model limitations but because measurement noise attenuates higher-order nonlinear structure by the k-th power of feature reliability for a degree-k interaction.
WHY IT MATTERS: "Deep learning barely beats linear regression on tabular biomedical data" is a recurring, often hand-waved observation in the field; this gives a precise statistical mechanism for why, which changes the diagnosis from "models aren't good enough" to "the data's noise floor caps what any nonlinear model can extract." That reframing has direct implications for how much investment in model complexity is actually justified for a given biomedical dataset's measurement reliability.
CODE: Not confirmed
---

---
TITLE: A mathematical framework for centromere-aware evaluation of human genome assemblies
AUTHORS: Luca Franco, Matteo Migliarini, Matteo Tommaso Ungaro, Egnald Çela, Luca Corda, Andreas Giannis, Ester Mondelli, Fabio Galasso, Simona Giunta
SOURCE: arXiv | 2606.11276 | [**Link**](https://arxiv.org/abs/2606.11276)
TOPIC TAG: Genomics
TLDR: Reframes centromere assembly evaluation as a distributional comparison problem — computing genomic distances between functional motifs and comparing inter-motif distance distributions across assemblies via KL divergence and Jaccard similarity — and applies it genome-wide to current human T2T assemblies.
WHY IT MATTERS: Centromeric and other repeat-rich regions are exactly where standard alignment-based assembly QC breaks down, leaving assemblers without a reliable accuracy signal in the hardest part of the genome; a motif-distribution-based metric sidesteps the alignment problem entirely. As T2T assemblies become the reference standard, having a principled way to rank assembly quality specifically in centromeres matters for any downstream variant-calling or comparative-genomics pipeline that touches them.
CODE: Not confirmed
---

---
TITLE: Contrastive and Adaptive Multi-modal Masked Autoencoder for Spatial Transcriptomics
AUTHORS: Not fully confirmed
SOURCE: arXiv | 2606.21156 | [**Link**](https://arxiv.org/abs/2606.21156)
TOPIC TAG: Genomics
TLDR: A masked-autoencoder framework adaptively selects informative tissue regions via a learned bio-saliency/learning-to-rank score, then aligns histology images with measured gene expression through a contrastive cross-modal encoder to predict whole-slide transcriptomic profiles while mitigating cross-slide batch effects.
WHY IT MATTERS: Uniform random masking (standard MAE practice) wastes capacity on uninformative tissue background in histology-to-expression prediction; learning which regions actually carry transcriptomic signal before masking is a more sample-efficient use of the pretraining budget. Explicitly targeting cross-slide batch effects in the objective also addresses one of the most practically annoying failure modes when deploying these models across cohorts from different scanners/sites.
CODE: Not confirmed
---

---
TITLE: JEDEL: Zero-Shot DNA-Encoded Library Design for Early-Stage Drug Discovery
AUTHORS: Zygimantas Jocys, Zhanxing Zhu, Henriette M. G. Willems, Katayoun Farrahi
SOURCE: arXiv | 2606.23745 | [**Link**](https://arxiv.org/abs/2606.23745)
TOPIC TAG: General ML
TLDR: JEDEL maps the 3D pharmacophore geometry of known active ligands directly to synthesis-ready DNA-encoded library designs built from purchasable building blocks and validated chemical reactions, in a zero-shot setting.
WHY IT MATTERS: Generative molecule-design methods routinely propose structures with no feasible synthesis route, creating a costly gap between in silico hits and physically makeable compounds; going straight from pharmacophore geometry to a synthesizable combinatorial library design closes that gap by construction. For DEL-based early discovery specifically, this could meaningfully cut the iteration time between a computational hit and an actual physical screening library.
CODE: Not confirmed
---

---
TITLE: Reduced-Alphabet QUBO/Ising Formulation for Constraint-Driven Cyclic Peptide Sequence Design
AUTHORS: Yan Zhou, Yuqi Wang, Xin Li (author list medium-confidence — could not independently cross-verify against a second source)
SOURCE: arXiv | 2606.23253 | [**Link**](https://arxiv.org/abs/2606.23253)
TOPIC TAG: General ML
TLDR: Groups amino acids into physicochemical/interaction-based residue classes and encodes cyclic peptide design as a QUBO/Ising objective combining validity, cyclization, target-compatibility, motif, and developability constraints, generalizing across head-to-tail, disulfide-bridged, stapled, and bicyclic peptide formats.
WHY IT MATTERS: Cyclic peptide design is usually tackled with continuous generative models that need extra post-hoc filtering for hard combinatorial constraints (cyclization geometry, disulfide topology); folding those constraints directly into a discrete QUBO objective is a more native fit and is solvable on quantum or quantum-inspired annealers as the hardware matures. Reducing the amino-acid alphabet to interaction-based classes also keeps the qubit/variable count tractable, which is the main practical bottleneck for combinatorial-optimization approaches to sequence design.
CODE: Not confirmed
---

---
TITLE: Tiny Subsamples and Upsampling Tame Big Data Evolutionary Analysis in Phylogenomics
AUTHORS: Sudhir Kumar, Koichiro Tamura, Sudip Sharma
SOURCE: bioRxiv | 10.64898/2026.06.21.733599 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733599v1)
TOPIC TAG: Genomics
TLDR: Shows that tiny random subsamples of site patterns from a full sequence alignment, when upsampled back to the full alignment's site count, recover the same optimal substitution model and rate-parameter estimates as the full dataset — cutting maximum-likelihood phylogenomic compute by orders of magnitude.
WHY IT MATTERS: Genome-scale phylogenomics is increasingly compute-bound at the model-selection and parameter-estimation step rather than tree search itself, and this gives a simple, statistically grounded shortcut rather than just throwing more hardware at the problem. Because the subsample-upsample trick is model-agnostic, it should drop directly into existing ML/IQ-TREE-style pipelines without requiring a new inference algorithm.
CODE: Not confirmed
---

---
TITLE: predNMD: Prediction of Nonsense-Mediated mRNA Decay for Improved Clinical Variant Pathogenicity Classification
AUTHORS: Y. Su, S. E. Brenner
SOURCE: bioRxiv | 10.64898/2026.06.21.733583 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733583v1)
TOPIC TAG: Clinical ML
TLDR: predNMD is a Random Forest/SHAP-based classifier predicting whether premature-termination-codon transcripts escape or undergo nonsense-mediated decay, aimed at distinguishing NMD-aggravated from NMD-ameliorated disease mechanisms for clinical variant interpretation.
WHY IT MATTERS: ACMG/ClinVar-style pathogenicity classification for nonsense and frameshift variants largely ignores whether the resulting transcript is actually degraded by NMD, which directly determines disease mechanism and severity; a dedicated predictor closes a real gap in current variant-interpretation pipelines. SHAP-based interpretability also gives clinical geneticists a way to inspect which sequence features drove a given NMD call, rather than treating it as a black-box flag.
CODE: Project page (code release pending): [**Code**](https://compbio.berkeley.edu/proj/prednmd/)
---

---
TITLE: MMGNN: Multi-level, Multi-color Graph Neural Networks for Molecular Property Prediction
AUTHORS: Trung Nguyen, Duc Duy Nguyen
SOURCE: arXiv | 2606.20906 | [**Link**](https://arxiv.org/abs/2606.20906)
TOPIC TAG: Architecture
TLDR: Decomposes molecular graphs into overlapping atom-type-pair "colored" subgraphs — chemical-colored for 2D covalent connectivity, geometric-colored for 3D spatial proximity — and applies a shared message-passing backbone per subgraph before aggregating to atom/molecule-level representations, evaluated on 8 MoleculeNet benchmarks with scaffold splits.
WHY IT MATTERS: Standard molecular GNNs mix all atom-pair types into one homogeneous message-passing pass, which can wash out chemically distinct interaction signals; decomposing by atom-type-pair color before sharing a backbone is a structurally motivated way to preserve that distinction without blowing up parameter count. Using scaffold splits rather than random splits for evaluation also makes the reported gains a more honest test of generalization to genuinely new molecular scaffolds.
CODE: Not confirmed
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. How Post-Training Shapes Biological Reasoning Models**
This is a large, controlled ablation — 100+ models — isolating exactly what continued pretraining, supervised fine-tuning, and reinforcement learning each contribute to a biological reasoning model's in-distribution versus out-of-distribution generalization, rather than the usual single-recipe benchmark paper. The key finding, that SFT alone produces an early OOD peak followed by decline which a sufficiently large RL budget on top reverses, gives a concrete, actionable recipe (brief SFT + larger RL) instead of a vague "RL helps" claim. Because nearly every domain-specific biological LLM currently copies post-training recipes wholesale from general-domain NLP, this result is directly relevant to how the whole field should be training these models going forward.
Code: Not released.

**2. A Drug-Target Specificity Foundation Model for Off-target Prediction, Repurposing, and Generative Design (dtSFM)**
dtSFM's central move is theoretical as much as empirical: it argues Transformer softmax attention is mathematically isomorphic to the Boltzmann distribution that governs real molecular binding at thermal equilibrium, then trains on 714,747 drug-protein interactions to exploit that correspondence for off-target prediction. The practical payoff is substantial — it ranks documented off-targets of approved kinase inhibitors in the top 0.6% of the genome, and its generative decoder produces novel molecules for 16 targets with structural confidence matching approved drugs for 71% of candidates. Off-target risk and repurposing are usually handled by separate, narrower models; unifying prediction and generation under one specificity-aware foundation model is a genuinely new framing for drug-target modeling.
Code: Not confirmed.

**3. DeepBD: A Grounded Agentic Workflow for Variant Prioritization and Diagnosis of Genetic Birth Defects**
DeepBD grounds every step of its LLM-driven variant-prioritization pipeline in retrieved evidence rather than relying on free-form generation, then validates on a clinical cohort of 18,622 fetal/infant cases — far larger than the handful-of-hundreds benchmarks typical in rare-disease ML. Beating established tools like Exomiser and DeepRare on Recall@1 through Recall@10, and outperforming naively-prompted LLM reranking, demonstrates the grounding actually buys real accuracy rather than just interpretability theater. In a domain where a missed causal variant has direct clinical stakes, that head-to-head improvement over the incumbent tools is the right bar for an agentic genomics system to clear.
Code: Not confirmed.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 14
- By topic: Protein LM: 0 | Diffusion: 0 | Genomics: 4 | Architecture: 2 | General ML: 5 | Clinical: 3
- Sources: arXiv: 11 | bioRxiv: 3 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 (EurekAgent cross-listed on HF Papers, counted under arXiv) | PWC: 0
- Papers with code released: 1
