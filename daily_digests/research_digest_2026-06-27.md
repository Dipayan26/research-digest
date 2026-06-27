# Research Digest — 2026-06-27

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct fetches to arxiv.org, export.arxiv.org, biorxiv.org, and api.biorxiv.org again returned HTTP 403 at the network gateway in this environment (confirmed via four parallel research passes plus a manual `$HTTPS_PROXY/__agentproxy/status` check showing repeated `connect_rejected` entries for `export.arxiv.org`, `arxiv.org`, and `api.biorxiv.org`), so discovery again relied entirely on WebSearch plus the Hugging Face MCP `paper_search` connector. bioRxiv/medRxiv search-engine snippets also misattributed posting dates by months on multiple candidates (e.g. a "Dynamic genomic constraints..." preprint indexed as 2026-06-25 was independently verified to actually be dated 2025-08-21), so no bioRxiv/medRxiv candidate could be confirmed as genuinely new this cycle. Of the raw candidates surfaced (BioMatrix, JEDEL, AgentPLM, ProHiFlo, Viral Proteins Reveal Geometry of PLMs, GRAINS, CompressKV, Fisher Alignment at Vocabulary Scale, "Does MoE Actually Help Inference on Consumer/Edge Hardware"), most were cross-checked against the full prior-digest history (404 titles through 2026-06-25) and excluded as duplicates already covered (BioMatrix and JEDEL were both already in the 2026-06-25 digest) or as out of scope (GRAINS is a storage-hardware/systems paper, not an ML model; CompressKV and the MoE-inference study are general-purpose LLM infra work with no demonstrated biological application; Fisher Alignment only tangentially touches protein/genomic vocabularies as one example domain among several). HF Papers' semantic search surfaced no items dated in the last 24-72h (its index is not recency-sorted); PubMed, medRxiv, and Papers With Code again contributed no confirmable last-24-72h items.

---

---
TITLE: Sesame: Structure-Aware Molecular Generation via Spatial Density-Map Conditioning
AUTHORS: Konstantin Yatsenko, Arvind Thiagarajan
SOURCE: arXiv | 2606.23856 | [**Link**](https://arxiv.org/abs/2606.23856)
TOPIC TAG: Diffusion
TLDR: A diffusion-based molecular generator uses a "spatial pairformer" module to condition joint denoising of atom types, bond types, and 3D positions on partial structure represented as continuous spatial density maps, supporting both de novo generation and fragment-conditioned lead optimization.
WHY IT MATTERS: Most structure-conditioned molecule generators require explicit pocket graphs or discrete atom sets as conditioning input; using continuous spatial density maps instead is a more flexible representation that unifies de novo design and scaffold-growing lead optimization in a single model rather than two separate pipelines. The model also uses trajectory fine-tuning on its own rollouts, and comes out of a biotech (Tessel Biosciences) rather than an academic benchmark exercise, suggesting a deployment-oriented rather than leaderboard-oriented design target.
CODE: Not confirmed
---

---
TITLE: scBench-Long: Verifiable Benchmarking of Long-Horizon Single-Cell Biology
AUTHORS: Ian Diks, Zhen Yang, Arjun Banerjee, Tim Proctor, Kenny Workman
SOURCE: arXiv | 2606.26563 | [**Link**](https://arxiv.org/abs/2606.26563)
TOPIC TAG: General ML
TLDR: A 21-task benchmark requires AI agents to recover real scientific conclusions directly from raw or near-raw single-cell datasets (paired scRNA/TCR-seq, RNA+ATAC regulatory inference, cross-species transcriptomics, immune repertoires) without being given a prescribed analysis method, extending LatchBio's earlier scRNA-seq-focused scBench to long-horizon, open-ended reasoning.
WHY IT MATTERS: Existing single-cell agent benchmarks (including the original scBench) mostly test short, well-scoped analysis steps with a known target metric; requiring an agent to independently reconstruct a paper's actual scientific conclusion from minimally processed data is a substantially harder and more realistic test of whether agentic systems can do single-cell biology rather than pattern-match familiar pipelines. As agentic bioinformatics tools proliferate, a verifiable, conclusion-level benchmark like this is exactly the missing piece for separating genuine analytical capability from benchmark-specific overfitting.
CODE: Not confirmed (predecessor scBench's code is at [**Code**](https://github.com/latchbio/scbench); this benchmark's own repo was not found)
---

---
TITLE: Residue-Level Attributions in Protein Language Models Do Not Recover Allergen Epitopes
AUTHORS: Jianzhou Yao, Anxiong Song, Katja Baerenfaller, Damir Zhakparov
SOURCE: arXiv | 2606.22181 | [**Link**](https://arxiv.org/abs/2606.22181)
TOPIC TAG: Protein LM
TLDR: Introduces an epitope-grounded residue-level benchmark and finds that classification-head attribution methods on frozen ESM-2, multi-task ESM-2, and DeepPlantAllergy fail to align with annotated allergen epitopes any better than random, despite the underlying classifiers achieving strong protein-level accuracy; saturation mutagenesis suggests the models instead rely on physicochemical/compositional sequence features.
WHY IT MATTERS: Interpretability claims for protein-LM classifiers are usually asserted rather than rigorously tested against ground-truth functional sites; this is a clean negative result showing attribution faithfulness does not follow from classification accuracy. That has direct implications for any downstream pipeline — e.g. epitope mapping for vaccine or immunotherapy design — that leans on PLM attributions to localize functional residues, and the saturation-mutagenesis control is a more rigorous validation than is typical in PLM-interpretability work.
CODE: Not confirmed
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Sesame: Structure-Aware Molecular Generation via Spatial Density-Map Conditioning**
Sesame's central design choice — conditioning a diffusion model on continuous spatial density maps rather than discrete pocket graphs — lets one model handle both unconditional de novo molecule generation and fragment-conditioned lead optimization, which are usually split across separate tools. The "spatial pairformer" module jointly denoises atom identity, bonds, and 3D position, and a trajectory-finetuning step on the model's own rollouts pushes quality further after pretraining. Coming from a drug-discovery biotech rather than an academic group, it reads as aimed at real lead-optimization workflows rather than benchmark leaderboards.
Code: Not confirmed.

**2. scBench-Long: Verifiable Benchmarking of Long-Horizon Single-Cell Biology**
scBench-Long raises the bar for single-cell agent benchmarks by requiring agents to recover an actual published scientific conclusion from near-raw data, with no prescribed analysis method — spanning melanoma CD8 T-cell reactivity, cross-species chimera development, and COVID-19 lung pathology, among others. This is a meaningfully harder test than the short, well-scoped tasks in most existing single-cell benchmarks (including its own predecessor, scBench), and verifiable conclusion-level grading is hard to game by memorizing known pipelines. As more groups deploy LLM agents for omics analysis, this kind of benchmark is what will actually distinguish capable agents from ones that recognize familiar problem shapes.
Code: Not confirmed (predecessor's code at github.com/latchbio/scbench).

**3. Residue-Level Attributions in Protein Language Models Do Not Recover Allergen Epitopes**
This paper takes a common but rarely-tested assumption — that attribution methods on protein-LM classifiers point to biologically meaningful residues — and shows it fails for allergen epitope localization across three different model setups, despite high protein-level classification accuracy. The saturation-mutagenesis control, which finds the classifiers leaning on physicochemical/compositional features instead of epitope-specific signal, is a notably more rigorous validation than typical interpretability papers in this space attempt. It's a useful caution for anyone using PLM attributions as a stand-in for wet-lab epitope mapping.
Code: Not confirmed.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 3
- By topic: Protein LM: 1 | Diffusion: 1 | Genomics: 0 | Architecture: 0 | General ML: 1 | Clinical: 0
- Sources: arXiv: 3 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
