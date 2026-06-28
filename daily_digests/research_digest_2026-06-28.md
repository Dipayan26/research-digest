# Research Digest — 2026-06-28

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct fetches to arxiv.org and biorxiv.org again returned HTTP 403 at the network gateway in this environment, so discovery relied on WebSearch plus the Hugging Face MCP `paper_search` connector, cross-checked against arXiv ID numbering (`2606.2xxxx`+ ≈ late June 2026) and search-snippet "posted N days ago" phrasing to confirm dates. Genuinely new (≤~5 day) candidates were sparse again: several initial hits — AgentPLM, ProHiFlo, Viral Proteins Reveal Geometry of PLMs, "How Post-Training Shapes Biological Reasoning Models", MMGNN, MoE-Bind, AROMA, Chreode — were excluded as duplicates of papers already covered in earlier digests (2026-06-03, 06-15, 06-16, 06-25, 06-25 respectively) or as too old once dated precisely. A "Circuit Tracing in Autoregressive Protein Language Models" workshop paper (Tsui et al., ICML 2026 Mech-Interp Workshop) surfaced repeatedly but its arXiv ID/posting date could not be confirmed via search, so it was excluded rather than guessed. PubMed, medRxiv, Papers With Code, and HF Papers' semantic search again contributed no independently confirmable last-24–72h items; the four papers below were corroborated across at least two independent searches each.

---

---
TITLE: Molexar: A Unified Multimodal Molecular Foundation Model for Drug Design
AUTHORS: Haoyu Lin et al.
SOURCE: arXiv | 2606.25865 | [**Link**](https://arxiv.org/abs/2606.25865)
TOPIC TAG: Protein LM
TLDR: Molexar is a Fragment-SELFIES-based autoregressive molecular foundation model that shares one decoder across unconditional generation, property/pharmacophore-conditioned generation, and protein-pocket-conditioned (CrossDocked2020) molecule design, reaching 100% validity with competitive target-conditioned generation.
WHY IT MATTERS: Most molecular generative models specialize in either property-conditioned design or structure-based (pocket-conditioned) design, requiring separate pipelines; Molexar's in-place condition-token injection unifies both modes in a single autoregressive path. The fragment-aware, validity-preserving string representation (Fragment-SELFIES) is also a notable departure from plain SELFIES/SMILES tokenization for foundation-model pretraining at scale.
CODE: Not confirmed
---

---
TITLE: ComplexDesign: Sequence-Hallucination Design of Protein Binders Bridging Multiple Proteins
AUTHORS: Jing Xu, Milong Ren, Ning Qi, Xinru Zhang, Zaikai He, Chungong Yu, Dongbo Bu
SOURCE: bioRxiv | 10.64898/2026.06.21.733655 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.21.733655v1)
TOPIC TAG: Protein LM
TLDR: A structure-prediction-guided sequence-hallucination method jointly folds multiple protein chains and optimizes inter-chain interfaces, achieving >50% design success on unconditional dimer/trimer/tetramer complexes and high-confidence ternary complexes for 8/10 multi-target binder cases.
WHY IT MATTERS: De novo binder design has mostly targeted single binder-target pairs; bridging two independent target proteins into one ternary complex is a substantially harder multi-body design problem with applications in induced-proximity therapeutics (e.g. molecular glues, bispecifics). Extending hallucination-based design beyond binary interfaces to trimers/tetramers and bridging complexes is a meaningful capability jump for the approach.
CODE: Not confirmed
---

---
TITLE: CABS-flex Standalone 3: An Open Command-Line Platform for Protein Flexibility Simulation, Peptide Structure Modeling, and Protein-Peptide Docking
AUTHORS: Chandran Nithin, Karol Wroblewski, Piotr Szukalo, Ayomide Fasemire, Aleksander Kuriata, Mateusz Kurcinski, Andrzej Kolinski, Sebastian Kmiecik
SOURCE: arXiv | 2606.24487 | [**Link**](https://arxiv.org/abs/2606.24487)
TOPIC TAG: Protein LM
TLDR: A Python 3 rewrite of the CABS-flex/CABS-dock coarse-grained simulation ecosystem adds linear/cyclic peptide modeling, information-guided protein-peptide docking, and deep-learning-based all-atom reconstruction (via cg2all) on top of fast CABS sampling.
WHY IT MATTERS: This is a widely-used structural bioinformatics toolkit (prior CABS-flex versions have thousands of citations), not a novel learned model — but folding cg2all-based all-atom reconstruction directly into a coarse-grained sampling pipeline is a practical bridge between fast classical conformational sampling and deep-learning structure refinement that downstream ML-for-biology pipelines (e.g. ensemble generation for binder/peptide design) can plug into directly.
CODE: Open-source command-line package (repository link not found in available sources — check the arXiv listing)
---

---
TITLE: MedRLM: Recursive Multimodal Health Intelligence for Long-Context Clinical Reasoning, Sensor-Guided Screening, Evidence-Grounded Decision Support, and Community-to-Tertiary Referral Optimization
AUTHORS: Aueaphum Aueawatthanaphisut
SOURCE: arXiv | 2606.20164 | [**Link**](https://arxiv.org/abs/2606.20164)
TOPIC TAG: Clinical ML
TLDR: MedRLM treats a patient case as an external environment that specialized agents (text, longitudinal EHR, imaging, sensor streams, guideline retrieval) recursively inspect and decompose, linked via a "Clinical Evidence Graph Memory," with sensor-triggered deeper reasoning and uncertainty-gated clinician review.
WHY IT MATTERS: Most clinical LLM/RAG systems compress all patient context into a single long prompt, which is fragile when evidence is scattered across EHR, imaging, and sensor modalities; recursive agentic decomposition with an explicit evidence graph is a more auditable alternative aimed at real workflow constraints (referral triage, uncertainty-aware escalation) rather than single-shot QA benchmarks.
CODE: Not confirmed
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. ComplexDesign: Sequence-Hallucination Design of Protein Binders Bridging Multiple Proteins**
ComplexDesign pushes hallucination-based protein design past the usual single binder-target pair into multi-body territory: jointly folding and optimizing interfaces across trimers and tetramers, and — most notably — designing a single binder that bridges two independent target proteins into a ternary complex. It reports >50% success on unconditional multimer design and confident ternary complexes for 8 of 10 bridging targets, which is a hard regime for existing structure-hallucination methods. This kind of multi-target bridging is directly relevant to induced-proximity drug modalities like molecular glues and bispecific binders.
Code: Not confirmed.

**2. Molexar: A Unified Multimodal Molecular Foundation Model for Drug Design**
Molexar collapses property-conditioned and structure/pocket-conditioned molecule generation into one autoregressive decoder by injecting conditions as in-place token replacements, built on a new fragment-aware string representation (Fragment-SELFIES) rather than plain SMILES/SELFIES. It reaches 100% validity in unconditional/fragment-constrained generation and stays competitive with specialized pocket-conditioned generators on CrossDocked2020. Unifying these usually-separate generation modes in one pretrained-then-finetuned model is a practical step toward a single foundation model for drug-design workflows.
Code: Not confirmed.

**3. MedRLM: Recursive Multimodal Health Intelligence**
Rather than stuffing a patient's entire record into one long prompt, MedRLM coordinates specialized agents over text, longitudinal EHR, imaging, and sensor streams through a recursive inspect-decompose-retrieve-verify loop, backed by a Clinical Evidence Graph Memory and uncertainty-gated escalation to clinicians. The sensor-triggered deeper-reasoning mechanism and referral-optimization framing target real triage workflows rather than static QA accuracy. It's a useful example of agentic decomposition applied to long-context, multimodal clinical reasoning where single-shot prompting tends to be fragile.
Code: Not confirmed.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 4
- By topic: Protein LM: 3 | Diffusion: 0 | Genomics: 0 | Architecture: 0 | General ML: 0 | Clinical: 1
- Sources: arXiv: 3 | bioRxiv: 1 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0 confirmed (CABS-flex standalone 3 is described as open-source but no repository link could be confirmed)
