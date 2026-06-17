# Research Digest — 2026-06-17

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> All arXiv IDs and bioRxiv/medRxiv DOIs already covered in prior digests (full history through 2026-06-16) were cross-checked and excluded — including several papers re-surfaced by today's searches (e.g. ProHiFlo 2606.11243, AgentPLM 2606.02386, "Viral Proteins Reveal Geometry of Protein Language Models" 2606.12609, the pangenome-PLM bioRxiv paper 2026.06.04.730042, and the OCOO-T virtual-cell paper 2606.12838). Search-engine indexing of arXiv/bioRxiv/PubMed/HF Papers lags the live feed by roughly 1–5 days in this environment, so today's set draws on the most recent verifiable, not-yet-covered postings (mostly IDs in the 2606.04xxx–2606.15xxx range and bioRxiv DOIs from late April through mid-June 2026).

---

---
TITLE: Testing the Reliability of AI-Generated Protein Structures
AUTHORS: Amanda Xu et al. (Salzberg lab, Johns Hopkins)
SOURCE: bioRxiv | 2026.06.11.731682 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.11.731682v1)
TOPIC TAG: Protein LM
TLDR: Feeding AlphaFold2/ColabFold synthetic, biologically meaningless "fake" protein sequences, the authors find a roughly 1-in-435 false-positive rate where the model produces a high-confidence (high-pLDDT), well-folded structure for a non-real protein — and some flagged false positives turn out to correspond to real human pseudogenes.
WHY IT MATTERS: Structure-prediction confidence metrics like pLDDT are widely treated as ground-truth correctness signals across downstream pipelines (function annotation, drug-target triage, evolutionary analysis), but this work shows that confident folds can arise for sequences with no biological reality. It is a timely calibration check for anyone building automated pipelines on top of AlphaFold-class predictions, and surfaces pseudogene mis-annotation as a concrete failure mode.
CODE: Not released
---

---
TITLE: ProtAff: Protein Binding Affinity Prediction via LoRA-Finetuned ESM-2
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: bioRxiv | 2026.06.13.732058 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.13.732058v1)
TOPIC TAG: Protein LM
TLDR: LoRA-finetunes ESM-2 (650M) with a cross-attention head on 362,567 affinity measurements, reaching Spearman ρ=0.413 on the AdaptyvBio EGFR benchmark (vs. ρ=0.054 for AlphaFold3-based scoring) and using the model to design a Nipah-virus binder with Kd=0.132 nM, 2.8× better than the prior competition-winning binder.
WHY IT MATTERS: AF3-based affinity scoring is a popular but weak proxy for true binding strength; this result shows a lightweight, parameter-efficient finetune of a sequence-only pLM can beat structure-based scoring by a wide margin on a real wet-lab benchmark. The de novo Nipah binder result demonstrates the model is useful for live antiviral design campaigns, not just retrospective benchmarks.
CODE: Not released
---

---
TITLE: ProtGPT3: An Open-Source Family of Promptable and Aligned Protein Language Models
AUTHORS: Garibbo et al. (senior author Noelia Ferruz, CRG Barcelona)
SOURCE: bioRxiv | 2026.06.04.730041 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.04.730041)
TOPIC TAG: Protein LM
TLDR: Introduces a 112M–10B parameter family of promptable protein language models with post-training alignment for controlled generation, showing few-shot prompting can rival task-specific fine-tuning, validated on a low-data defluorinase design task that yielded soluble, expressed enzymes.
WHY IT MATTERS: Most generative pLMs require fine-tuning per design task; an aligned, promptable family that matches fine-tuned performance via in-context prompting would substantially lower the barrier for labs without large compute budgets to do custom protein design. Released weights/code make this immediately usable infrastructure for the field.
CODE: [**Code**](https://huggingface.co/collections/AI4PD/protgpt3-family)
---

---
TITLE: RicciBind: Curvature-Guided Geometric Representation for Protein-Ligand Binding Affinity Prediction
AUTHORS: Li, Ren, Li, Huang, Pan, Tang, Yan et al.
SOURCE: arXiv | 2606.14159 | [**Link**](https://arxiv.org/abs/2606.14159)
TOPIC TAG: Protein LM
TLDR: Encodes local binding-pocket geometric tightness via discrete Ricci curvature on protein-ligand interaction graphs, combined with optimal-transport cross-domain alignment between unbound and bound conformations, reporting state-of-the-art results on standard binding-affinity and virtual-screening benchmarks.
WHY IT MATTERS: Most affinity predictors treat structure as a fixed graph without explicitly modeling local geometric strain at the interface; curvature-based descriptors give a physically motivated, interpretable signal of binding-induced deformation. This complements (and could be benchmarked directly against) the same-week CPES paper using Hessian-based curvature, suggesting curvature-aware geometry is an emerging useful inductive bias for DTI models.
CODE: Not released
---

---
TITLE: Curvature-Informed Potential Energy Surface (CPES) for Protein-Ligand Binding Affinity Prediction
AUTHORS: Peng-Fei Sun, Chuan-Xian Ren, Hong Yan
SOURCE: arXiv | 2606.14217 | [**Link**](https://arxiv.org/abs/2606.14217)
TOPIC TAG: Protein LM
TLDR: Derives curvature spectral descriptors from the Hessian of the protein-ligand potential energy surface and applies spectral cross-attention between unbound and bound ligand/protein states to capture binding-induced conformational change, improving affinity prediction accuracy with physically interpretable features.
WHY IT MATTERS: Provides a physics-grounded alternative to purely learned geometric encodings for affinity prediction, directly tying model internals to energetic conformational change rather than opaque embeddings. Useful for groups that need interpretability alongside accuracy in lead-optimization pipelines.
CODE: Not released
---

---
TITLE: Pepti-Agent: An AI Agent for Peptide Design and Optimization
AUTHORS: Houxu Chen, Achuth Chandrasekhar, Amir Barati Farimani
SOURCE: arXiv | 2606.15422 | [**Link**](https://arxiv.org/abs/2606.15422)
TOPIC TAG: Protein LM
TLDR: Builds an LLM-agent framework that interleaves peptide sequence generation with external property-prediction and optimization tool calls in an iterative design loop, aiming to automate peptide therapeutic design and optimization end-to-end.
WHY IT MATTERS: Agentic, tool-augmented design loops (in the spirit of AgentPLM for proteins) are emerging as a general pattern for biomolecule design that combines generative models with verifiable external tools, reducing reliance on a single model's implicit knowledge. Peptides are a fast-growing therapeutic modality, and an agent framework could meaningfully shorten design-test cycles versus manual iteration.
CODE: Not released
---

---
TITLE: CisTransCell: Single-Cell Perturbation Prediction via Gene Function, Regulatory Control, and Cellular Context
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.13713 | [**Link**](https://arxiv.org/abs/2606.13713)
TOPIC TAG: Genomics
TLDR: Augments gene representations with regulatory-sequence and coding-sequence priors alongside cellular context to predict single-cell transcriptional perturbation responses in a zero-shot setting, targeting generalization to perturbations unseen during training.
WHY IT MATTERS: Most virtual-cell perturbation models struggle to generalize beyond the perturbations seen in training data, limiting their use for prioritizing novel CRISPR or drug perturbations in silico. Grounding gene representations in regulatory/coding biology rather than expression statistics alone is a promising route to genuine zero-shot generalization in perturbation biology.
CODE: Not released
---

---
TITLE: Dynamic Linear Attention
AUTHORS: (Authors not fully confirmed; Ohio State, Michigan, ByteDance)
SOURCE: arXiv | 2606.10650 | [**Link**](https://arxiv.org/abs/2606.10650)
TOPIC TAG: Architecture
TLDR: Introduces "information-aware dynamic state merging" for multi-state linear attention, adaptively setting state-merging boundaries based on token-level information variation instead of a fixed merging policy, reducing error accumulation over long sequences.
WHY IT MATTERS: Linear-attention models are increasingly used as efficient backbones for long-context genomic and protein sequence modeling, but fixed-policy state merging causes compounding errors over very long contexts (e.g. whole-chromosome DNA). A dynamic, information-aware merging rule is a architecture-level improvement directly transferable to long-context bio foundation models without redesigning the underlying sequence model.
CODE: Not released
---

---
TITLE: AF_Cache: Efficient Pipeline for Running AlphaFold for High-Throughput Protein-Protein Interaction Prediction
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.04566 | [**Link**](https://arxiv.org/abs/2606.04566)
TOPIC TAG: Protein LM
TLDR: A Nextflow pipeline that accelerates AlphaFold2/AlphaFold3-based PPI prediction through GPU-accelerated MSA generation and feature caching, enabling high-throughput proteome-scale interaction screening.
WHY IT MATTERS: AlphaFold-based PPI screening is accurate but prohibitively slow to run at proteome scale due to repeated MSA computation; caching shared features across queries is a practical systems-level fix that could make co-folding-based interactome screens routine rather than exceptional. This is infrastructure work that directly unblocks larger-scale PPI studies using existing accurate models.
CODE: Not released
---

---
TITLE: A Systematic Investigation of Molecular Encoding Methods for Drug Property Predictions Across Neural Network and Transformer Encoder-Based Models
AUTHORS: Chen, Yeh
SOURCE: arXiv | 2606.08973 | [**Link**](https://arxiv.org/abs/2606.08973)
TOPIC TAG: General ML
TLDR: Benchmarks topological, substructure-based, and string-based molecular encodings across MLP and Transformer-encoder architectures on seven toxicity/mutagenicity/side-effect datasets, finding average AUC above 0.9 but with encoding choice mattering more than architecture choice on several tasks.
WHY IT MATTERS: Encoding choice is often treated as a minor implementation detail in drug-property ML papers, but this systematic sweep quantifies how much it actually matters relative to model architecture. It is a useful practical reference for anyone setting up a new ADMET or toxicity prediction pipeline who needs to choose a representation before tuning a model.
CODE: Not released
---

---
TITLE: When Do Three-Dimensional Conformer Ensembles Improve Molecular Property Prediction Beyond Two-Dimensional Fingerprints? A Systematic Study
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2606.08825 | [**Link**](https://arxiv.org/abs/2606.08825)
TOPIC TAG: General ML
TLDR: Systematically compares 3D conformer-ensemble representations against 2D molecular fingerprints across property-prediction tasks, characterizing the conditions (property type, conformational flexibility) under which the extra cost of 3D ensemble generation pays off.
WHY IT MATTERS: Generating conformer ensembles is computationally expensive, so knowing in advance when it's actually worth it versus a cheap 2D fingerprint is directly actionable for drug-discovery pipeline design. Companion piece to the molecular-encoding benchmark above; together they give practical, task-conditioned representation-choice guidance.
CODE: Not released
---

---
TITLE: Relational Biological Structure Improves Fine-Mapping of Causal GWAS Variants Under Weak Signal
AUTHORS: Ehsan Estaji, Shi-Wei Zhao, Zhao-Yang Chen, Shuai Nie, Jian-Feng Mao
SOURCE: bioRxiv | 2026.05.15.725513 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.05.15.725513v1)
TOPIC TAG: Clinical ML
TLDR: Proposes graph-augmented fine-mapping (GAFM) using hierarchical belief propagation over a variant-gene-pathway factor graph to identify causal GWAS variants under weak statistical signal, outperforming SuSiE and recovering known causal genes (LDLR, APOE, LPL, GCKR, ANGPTL3) across four Pan-UK Biobank ancestries at single-variant resolution.
WHY IT MATTERS: Standard fine-mapping methods like SuSiE rely purely on statistical co-localization and struggle in underpowered or multi-ancestry GWAS settings; injecting biological relational structure (gene networks, pathways) as a prior is a principled way to recover signal that pure statistics miss. Cross-ancestry validation against well-established causal genes gives real confidence this generalizes beyond the training population.
CODE: Not released
---

---
TITLE: WTKO-CNN: Deep Learning Reveals Sequence Motifs Distinguishing Wild-Type and Knockout ATAC-seq Peaks
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: arXiv | 2605.24034 | [**Link**](https://arxiv.org/abs/2605.24034)
TOPIC TAG: Genomics
TLDR: Trains a CNN with attention-based saliency maps and k-mer clustering on wild-type vs. knockout ATAC-seq peaks to discover regulatory DNA motifs whose accessibility depends on the knocked-out factor.
WHY IT MATTERS: Connecting chromatin-accessibility changes back to specific causal sequence motifs is a long-standing challenge in regulatory genomics; saliency-guided motif discovery from a simple, interpretable CNN offers a lightweight alternative to large genomic foundation models for hypothesis generation in a specific knockout experiment.
CODE: Not released
---

---
TITLE: Scoring Gene Importance by Interpreting Single-Cell Foundation Models
AUTHORS: (Authors not fully retrieved) et al.
SOURCE: PubMed | PMID 42204361 | [**Link**](https://pubmed.ncbi.nlm.nih.gov/42204361/)
TOPIC TAG: Genomics
TLDR: Interprets internal representations of single-cell foundation models (e.g. Geneformer-class models) to derive gene-importance scores for cell-state representation, without requiring task-specific supervised labels.
WHY IT MATTERS: Single-cell foundation models are increasingly used as black-box embedding generators, but extracting biologically meaningful gene rankings from them could turn them into discovery tools for driver genes and biomarkers, not just representation learners. This adds to a growing line of interpretability work (sparse autoencoders, attribution methods) aimed at making scFMs scientifically actionable rather than purely predictive.
CODE: Not released
---

---
TITLE: Aiki-GeNano: Multi-Stage Preference Optimization for Generative Design of Developable Nanobodies
AUTHORS: Aikium team
SOURCE: bioRxiv | 2026.04.28.721526 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.04.28.721526v1)
TOPIC TAG: Protein LM
TLDR: Trains a nanobody generator via SFT on 1.35M nanobody-epitope pairs followed by DPO on 522,800 developability-preference pairs and a Group Reward-Decoupled Policy Optimization stage, raising predicted melting temperature by 6.6°C across 65 epitopes while preserving humanness and solubility.
WHY IT MATTERS: Most generative antibody/nanobody design work optimizes binding alone and treats developability (stability, solubility, manufacturability) as a downstream filter; baking developability preferences directly into the RLHF-style training loop via DPO could substantially cut attrition in later-stage antibody engineering. It's a concrete demonstration of RLHF/DPO techniques, originally developed for language models, transferring effectively to biomolecule generative design.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Testing the Reliability of AI-Generated Protein Structures** (bioRxiv 2026.06.11.731682)
The Salzberg lab fed AlphaFold2/ColabFold deliberately fake, biologically meaningless sequences and found the models produce confident, well-folded, high-pLDDT structures roughly 1 in every 435 times — with some of these "false positive" folds corresponding to real human pseudogenes. This is a foundational calibration result: confidence scores from structure predictors are widely treated as correctness proxies across annotation, drug-target, and evolutionary-analysis pipelines built on top of AlphaFold, and this paper shows that trust is not fully warranted. Any lab running large-scale automated structure prediction on noisy or speculative sequence sets should treat this as a required sanity check going forward.
Code/weights: Not released.

**2. ProtAff: Protein Binding Affinity Prediction via LoRA-Finetuned ESM-2** (bioRxiv 2026.06.13.732058)
ProtAff shows that a lightweight LoRA finetune of ESM-2 with cross-attention, trained on ~360K affinity measurements, beats AlphaFold3-based affinity scoring by a wide margin (Spearman ρ=0.413 vs. 0.054) on a real wet-lab benchmark — and the team used it to design a Nipah-virus binder with Kd=0.132 nM, beating the previous best competition entry by 2.8×. It's a clean demonstration that sequence-only pLM finetuning can outcompete expensive structure-based scoring for affinity, and the live antiviral binder result moves this beyond benchmark numbers into a real design win. This is directly actionable for any group running binder-design or affinity-ranking campaigns who currently leans on AF3 confidence/PAE as an affinity proxy.
Code/weights: Not released.

**3. ProtGPT3: An Open-Source Family of Promptable and Aligned Protein Language Models** (bioRxiv 2026.06.04.730041)
From Noelia Ferruz's group at CRG Barcelona, ProtGPT3 is a 112M–10B parameter family of protein language models with post-training alignment specifically for controllable, promptable generation — few-shot prompting was shown to rival task-specific fine-tuning, including on a genuinely low-data defluorinase enzyme-design task that produced soluble, expressed proteins. This matters because it lowers the compute and data barrier for custom protein design considerably: labs without resources to fine-tune large models can instead prompt a pretrained, aligned model directly. Weights and code are released as a Hugging Face collection, making this immediately usable infrastructure.
Code/weights: https://huggingface.co/collections/AI4PD/protgpt3-family

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 15
- By topic: Protein LM: 8 | Diffusion: 0 | Genomics: 3 | Architecture: 1 | General ML: 2 | Clinical ML: 1
- Sources: arXiv: 9 | bioRxiv: 5 | medRxiv: 0 | PubMed: 1 | HF Papers: 0 | PWC: 0
- Papers with code released: 1 (ProtGPT3)
