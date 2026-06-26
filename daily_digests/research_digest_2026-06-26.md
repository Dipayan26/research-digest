# Research Digest — 2026-06-26

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct WebFetch to arxiv.org, biorxiv.org, and huggingface.co/papers again returned HTTP 403 in this environment, so discovery relied on four parallel WebSearch sweeps (general-ML/architecture arXiv, protein/genomics/clinical arXiv, bioRxiv/medRxiv/PubMed, and HF Papers/Semantic Scholar/Papers With Code), followed by a dedicated verification pass that re-searched each shortlisted candidate individually to confirm title/authors/ID/date before inclusion. PubMed, medRxiv, and Papers With Code again yielded no confirmable last-24-72h items — PubMed and medRxiv preprint indexing continues to lag by 1-3+ weeks, and PWC's site-restricted search surfaced no relevant "latest" listings. The HF Papers/Semantic Scholar sweep returned almost entirely papers already covered in earlier digests (DISCO, Lingshu-Cell, EpiFormer, "Language Modeling Materializes a World Model of Protein Biology") or items 1-4 months old — all excluded as duplicates or stale. Other candidates excluded as already covered in prior digests: "A High-Level Programming Language for Generative Biology with Proto" (covered 2026-06-24) and JEDEL (covered 2026-06-25). Candidates excluded for being outside the ~72h window despite topical relevance: SurfDesign, EasyNano, SoftMoE, ProbMoE, TCRDiff, BATTLE-AMP, GENATATORs, and several methylation/cfDNA papers. One candidate ("V3Cell") could not be independently re-confirmed on a second search pass and was dropped as likely a search-summarizer artifact.

---

---
TITLE: NatureBench: Can Coding Agents Match the Published SOTA of Nature-Family Papers?
AUTHORS: Not fully confirmed (FrontisAI-affiliated team)
SOURCE: arXiv | 2606.24530 | [**Link**](https://arxiv.org/abs/2606.24530)
TOPIC TAG: General ML
TLDR: Introduces NatureBench, a 90-task cross-discipline benchmark distilled from peer-reviewed Nature-family papers (including biology/genomics) run through a containerized "NatureGym" pipeline, finding the strongest of 10 frontier coding-agent configurations beats published SOTA on only 17.8% of tasks.
WHY IT MATTERS: Most agent-for-science benchmarks reward methodological translation — converting a novel scientific problem into a familiar supervised-learning recipe — rather than genuine invention, and NatureBench's failure analysis makes that gap explicit and measurable rather than anecdotal. For a field increasingly leaning on agentic pipelines for computational biology discovery, this is a sobering, reproducible yardstick for how far current agents actually are from matching domain-expert SOTA.
CODE: [**Code**](https://github.com/FrontisAI/NatureBench)
---

---
TITLE: Sesame: Structure-Aware Molecular Generation via Spatial Density-Map Conditioning
AUTHORS: Konstantin Yatsenko, Arvind Thiagarajan (Tessel Biosciences, Inc.)
SOURCE: arXiv | 2606.23856 | [**Link**](https://arxiv.org/abs/2606.23856)
TOPIC TAG: Diffusion
TLDR: Builds a diffusion-based molecular generator with a "spatial pairformer" module that represents both the partial molecule and the surrounding protein pocket as continuous spatial density maps, rather than discrete graphs, to drive fragment-growing and lead optimization.
WHY IT MATTERS: Fragment-growing methods typically condition on discrete atom/graph representations of the scaffold and pocket, which forces awkward handling of partial/incomplete structures; representing both sides of the interaction as continuous density fields is a more natural fit for diffusion generation and sidesteps that discretization problem. This gives medicinal chemists a generative tool aimed squarely at the most common real-world design step — growing a fragment hit into a lead — rather than unconditional de novo generation.
CODE: Not confirmed
---

---
TITLE: ComplexDesign: Sequence-Hallucination Design of Protein Binders Bridging Multiple Proteins
AUTHORS: J. Xu, M. Ren, N. Qi, X. Zhang, Z. He, C. Yu, D. Bu
SOURCE: bioRxiv | 10.64898/2026.06.21.733655 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733655v1)
TOPIC TAG: Protein LM
TLDR: Extends sequence-hallucination-based binder design beyond single-target binders to generate proteins that simultaneously bridge and bind multiple distinct protein targets at once.
WHY IT MATTERS: Nearly all de novo binder design work (RFdiffusion-style hallucination/diffusion methods included) targets one protein at a time; designing a single sequence that bridges two or more targets is a structurally harder constraint-satisfaction problem with direct applications to multi-specific binders, molecular glues, and induced-proximity therapeutics. Demonstrating this is tractable with a hallucination-based approach (rather than a purpose-built diffusion architecture) suggests the technique generalizes further than previously shown.
CODE: Not confirmed
---

---
TITLE: Molexar: A Unified Multimodal Molecular Foundation Model for Drug Design
AUTHORS: Haoyu Lin, Yiyan Liao, Jinmei Pan, Xinliao Ling, Luhua Lai, Jianfeng Pei
SOURCE: arXiv | 2606.25865 | [**Link**](https://arxiv.org/abs/2606.25865)
TOPIC TAG: Architecture
TLDR: Pretrains an autoregressive decoder on a fragment-aware "Fragment-SELFIES" molecular language, then fine-tunes the same decoder on condition-molecule pairs (scalar properties, pharmacophores, protein sequences, binding pockets) by in-place replacement of value-token embeddings, unifying many conditional generation modes in one shared path.
WHY IT MATTERS: Molecular generation models usually need separate architectures or heads per conditioning type (property-conditioned, pocket-conditioned, pharmacophore-conditioned), fragmenting both training data and tooling; collapsing all of these into one autoregressive path via embedding substitution is a simpler, more reusable design. The fragment-aware molecular language with validity-preserving decoding also directly targets the chronic problem of generative chemistry models proposing invalid structures.
CODE: Not confirmed
---

---
TITLE: Computational Redesign of an Antifreeze Protein Using Deep Learning
AUTHORS: C. Calia, A. J. Altunc, R. J. Eufemio, B. O. Alvarado, J. D. Huynh, E. Oh, M. Burkart, K. Meister, F. Paesani
SOURCE: bioRxiv | 10.64898/2026.06.21.733612 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733612v1)
TOPIC TAG: Protein LM
TLDR: Combines deep learning, molecular dynamics, and interpretable ML to rationally redesign a Tenebrio molitor antifreeze protein for improved ice/hydrate-binding activity, with the reported "Chill+" pipeline producing designed variants where the large majority outperform the wild type on hydrate inhibition.
WHY IT MATTERS: Antifreeze/ice-binding proteins are an unusual structure-function regime (binding to a non-protein, non-small-molecule surface) that most general-purpose protein design tools aren't built for, so a dedicated DL + MD + interpretable-ML pipeline fills a real methodological gap. The interpretability component is notable specifically because it lets the redesign cycle be guided by mechanistic insight into hydrate binding rather than black-box optimization alone, which matters for a property as physically constrained as ice nucleation.
CODE: Not confirmed
---

---
TITLE: ML-MAWS: Alignment-Free Maximum Likelihood Phylogeny Estimation Using Minimal Absent Words
AUTHORS: Papri Saha, Sudipta Kumar Das, Anonnya Sarkar, Md. Manzurul Hasan
SOURCE: arXiv | 2606.25584 | [**Link**](https://arxiv.org/abs/2606.25584)
TOPIC TAG: Genomics
TLDR: Encodes minimal absent words (computed in linear time via a suffix automaton) as a binary presence/absence character matrix and performs maximum-likelihood phylogenetic tree inference under the Lewis Mkv model with ascertainment-bias correction, avoiding multiple sequence alignment entirely.
WHY IT MATTERS: Alignment-free phylogenetics methods are usually distance-based and sacrifice the statistical power of full maximum-likelihood inference for speed; this is one of the first to keep ML-based tree estimation while still avoiding the alignment step, which is the actual scalability bottleneck for genome-scale phylogenomics. Because it's alignment-agnostic by construction, it should be directly useful for divergent or structurally rearranged genomes where MSA quality itself is the limiting factor.
CODE: Not confirmed
---

---
TITLE: CABS-flex standalone 3: An Open Command-Line Platform for Protein Flexibility Simulation, Peptide Structure Modeling, and Protein-Peptide Docking
AUTHORS: Chandran Nithin, Karol Wroblewski, Piotr Szukalo, Ayomide Fasemire, Aleksander Kuriata, Mateusz Kurcinski, Andrzej Kolinski, Sebastian Kmiecik
SOURCE: arXiv | 2606.24487 | [**Link**](https://arxiv.org/abs/2606.24487)
TOPIC TAG: General ML
TLDR: Releases a unified, open-source command-line successor to CABS-flex/CABS-dock that combines coarse-grained protein flexibility simulation, peptide structure modeling, and global/information-guided protein-peptide docking with deep-learning-based all-atom reconstruction (cg2all).
WHY IT MATTERS: Coarse-grained CABS-based tools have been a long-standing structural-bioinformatics workhorse but historically shipped as separate, harder-to-script web-server-first tools; consolidating flexibility simulation, peptide modeling, and docking into one scriptable command-line package with a learned all-atom reconstruction step makes it far more usable inside modern automated structure-prediction pipelines. It's a methods/infrastructure release rather than a new model, but the kind of tooling consolidation that directly lowers the barrier to running physics-based flexibility analysis alongside deep-learning structure predictors.
CODE: Open-source release implied (exact repository URL not confirmed in available sources)
---

---
TITLE: Learning Subset-Shared Invariances for Domain Generalization with Mixture-of-Experts
AUTHORS: Tien-Hung Nguyen, Tien-Dat Tran, M.-Duong Nguyen, Kok-Seng Wong
SOURCE: arXiv | 2606.25665 | [**Link**](https://arxiv.org/abs/2606.25665)
TOPIC TAG: MoE
TLDR: Proposes a mixture-of-experts approach to domain generalization that learns invariances shared across subsets of training domains, rather than forcing one global invariance shared by all domains.
WHY IT MATTERS: Most invariance-learning approaches to domain generalization assume a single representation must be invariant across every domain simultaneously, which is often too strong an assumption when domains cluster into related groups (e.g., batches/cohorts/assay types in omics data); routing to subset-shared invariances via MoE is a more realistic relaxation of that assumption. While not a biology paper itself, the subset-invariance framing maps directly onto the batch-effect and cross-cohort generalization problems that recur throughout single-cell, spatial, and clinical genomics ML.
CODE: Not confirmed
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. NatureBench: Can Coding Agents Match the Published SOTA of Nature-Family Papers?**
NatureBench distills 90 tasks directly from peer-reviewed Nature-family papers and runs them through a containerized "NatureGym" pipeline so that AI coding agents are evaluated against the actual published SOTA result, not a synthetic proxy. The headline finding — the best of 10 frontier agent configurations beats published SOTA on only 17.8% of tasks, and mostly by translating problems into familiar supervised-learning recipes rather than inventing new methods — is a rare, reproducible measurement of agentic-science capability rather than a demo. For computational biology specifically, where agentic discovery pipelines are increasingly proposed as a force multiplier, this is a concrete bar showing how far current systems are from matching domain-expert results.
Code: [GitHub](https://github.com/FrontisAI/NatureBench).

**2. Sesame: Structure-Aware Molecular Generation via Spatial Density-Map Conditioning**
Sesame's core idea is to represent both the partial molecule being grown and the surrounding protein pocket as continuous spatial density maps rather than discrete graphs, then condition a diffusion model on that shared continuous representation via a "spatial pairformer" module. This is a more natural fit for the diffusion process itself and directly targets fragment-growing/lead-optimization — the step most chemists actually iterate on, rather than unconditional de novo generation. It's a structurally different conditioning strategy from the graph- and point-cloud-based approaches that dominate current molecular diffusion work.
Code: Not confirmed.

**3. ComplexDesign: Sequence-Hallucination Design of Protein Binders Bridging Multiple Proteins**
ComplexDesign pushes sequence-hallucination-based binder design — previously demonstrated mainly for single-target binders — into the harder regime of designing one protein sequence that simultaneously binds two or more distinct targets. That's a meaningfully different constraint-satisfaction problem than standard binder design, with direct relevance to multi-specific binders and induced-proximity/molecular-glue-style therapeutics. Showing this works with a hallucination-based approach (rather than a bespoke multi-target diffusion architecture) is evidence the technique generalizes further than prior single-target demonstrations suggested.
Code: Not confirmed.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 8
- By topic: Protein LM: 2 | Diffusion: 1 | Genomics: 1 | Architecture: 1 | MoE: 1 | General ML: 2 | Clinical: 0
- Sources: arXiv: 6 | bioRxiv: 2 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 1
