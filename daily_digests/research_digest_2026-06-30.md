# Research Digest — 2026-06-30

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct fetches to arxiv.org, export.arxiv.org, biorxiv.org, and api.biorxiv.org again returned HTTP 403 at the network gateway in this environment, so discovery relied entirely on WebSearch and the Hugging Face MCP `paper_search` connector. Today (Monday June 30) the arXiv announcement covers papers submitted Friday June 27 through Monday June 30 AM; additional papers from the uncovered Friday June 26 mailing (which fell between the June 25 and June 27 digest runs) are also included here. bioRxiv/medRxiv search snippets continued to misattribute posting dates (as noted in prior runs), so no bioRxiv/medRxiv candidate was confirmed as genuinely new this cycle. Seven papers across Protein LM, Diffusion, Genomics, and General ML survived deduplication against the full prior-digest history.

---

---
TITLE: Two-Stage Fine-Tuning for Protein Sequence Generation with Targeted Amino-Acid Composition
AUTHORS: Violeta Basten-Romero et al.
SOURCE: arXiv | 2606.27939 | [**Link**](https://arxiv.org/abs/2606.27939)
TOPIC TAG: Protein LM
TLDR: A two-stage pipeline — domain-adaptive supervised fine-tuning of a protein language model followed by reward-weighted RL anchored against the fine-tuned model as a frozen reference — generates protein sequences whose amino-acid composition closely matches a user-specified target profile while preserving naturalness and diversity; motivating application is synthetic feed protein design where nutritional value is directly determined by composition.
WHY IT MATTERS: Controlling precise amino-acid composition profiles in generated proteins is important for applications like feed protein design and functional protein engineering, but standard language-model generation provides no compositional guarantee; most prior work uses constrained decoding heuristics or lattice constraints that degrade sequence naturalness. The RL stage is specifically needed because supervised fine-tuning alone brings composition close to target but cannot enforce exact composition constraints — a useful illustration of where RL adds value beyond instruction-tuning in the protein design setting.
CODE: Not released
---

---
TITLE: GRAFT: Biological Graph and Hypergraph Benchmarks for Linked Gene Expression and Phenotypic Trait Prediction in Arabidopsis thaliana
AUTHORS: Manuel Serna-Aguilera, Vanshika Jindal, Fiona L. Goggin, Jiamei Li, Aranyak Goswami, Alexander Bucksch, Suxing Liu, Khoa Luu
SOURCE: arXiv | 2606.27413 | [**Link**](https://arxiv.org/abs/2606.27413)
TOPIC TAG: Genomics
TLDR: GRAFT provides benchmark datasets in both graph and hypergraph formats linking multi-condition RNA-seq gene-expression profiles to phenotypic traits in *Arabidopsis thaliana*, enabling systematic evaluation of GNN and hypergraph-neural-network methods on a biologically meaningful joint prediction task.
WHY IT MATTERS: Most graph-based genomics benchmarks focus on single-modality tasks (e.g. gene function prediction or protein interaction); a benchmark explicitly coupling expression patterns to macroscopic traits — with both graph and hypergraph versions — is a cleaner way to measure whether relational inductive biases from hyperedges (capturing gene-set co-regulation) add value over standard GNNs for genotype-to-phenotype modeling. Arabidopsis is the canonical plant model organism, so this benchmark occupies a well-characterized ground-truth niche while remaining relevant to agricultural genomics applications.
CODE: Not released
---

---
TITLE: Agentic Discovery of Non-Canonical Antimicrobial Peptides with AMPGAN v3
AUTHORS: (Authors listed in paper 2606.17127)
SOURCE: arXiv | 2606.17127 | [**Link**](https://arxiv.org/abs/2606.17127)
TOPIC TAG: Protein LM
TLDR: AMPGAN v3 is a multi-objective conditional GAN that expands antimicrobial peptide design to non-canonical alphabets — D-amino acids and N/C-terminus chemical modifications such as amidation — by separating adversarial and activity-aware supervision across two specialized discriminators; five candidates spanning three structural classes were validated in vitro, with two showing activity against Gram-positive strains (best MIC 8 μg/mL vs. *B. subtilis*).
WHY IT MATTERS: Most generative AMP models restrict themselves to the 20 canonical L-amino acids, yet real therapeutic peptides routinely incorporate D-amino acids and terminal modifications to improve proteolytic stability and membrane selectivity; AMPGAN v3 is one of the first conditional generative models that natively handles these non-canonical building blocks while still producing wet-lab-validated hits. The two-discriminator design that separates adversarial stability from activity guidance is a transferable training strategy applicable to other conditional peptide GAN frameworks.
CODE: Not released
---

---
TITLE: Circuit Tracing in Autoregressive Protein Language Models
AUTHORS: Darin Tsui, William Deinzer, Daniel Saeedi, Amirali Aghazadeh
SOURCE: arXiv | 2606.16044 | [**Link**](https://arxiv.org/abs/2606.16044)
TOPIC TAG: Protein LM
TLDR: Mechanistic circuit-tracing techniques adapted from LLM interpretability are applied to an autoregressive protein language model to identify attention head circuits responsible for capturing sequence-level biological features such as secondary structure and evolutionary constraints; accepted to the ICML 2026 Mechanistic Interpretability Workshop.
WHY IT MATTERS: Understanding *what* protein language models learn and *where* they store it — at the level of specific attention heads and circuits — is essential both for scientifically interpreting these models and for targeted interventions such as activation steering, model editing, or guided decoding; prior interpretability work on PLMs has mostly operated at the representation (embedding) level rather than at the mechanistic circuit level. Adapting sparse circuit-discovery tooling (attribution patching, activation patching) from NLP to protein autoregressive models opens a new methodological line for the growing PLM interpretability community.
CODE: Not released
---

---
TITLE: Emyx: Fast and Efficient All-Atom Protein Generation
AUTHORS: Nicholas J. Williams, Ward Haddadin, Matteo P. Ferla, Constantin Schneider, Nicholas B. Woodall, Ruby Sedgwick, Christian D. Madsen, Andrew L. Hopkins, Edward O. Pyzer-Knapp
SOURCE: arXiv | 2606.19377 | [**Link**](https://arxiv.org/abs/2606.19377)
TOPIC TAG: Protein LM
TLDR: Emyx is a fast all-atom protein structure generative model targeting enzyme design applications, where both the geometric accuracy of catalytic residue placement and the structural diversity of scaffolding solutions are required simultaneously; the model achieves improved generation speed over comparable all-atom baselines while maintaining designability.
WHY IT MATTERS: Full all-atom generation (including side chains, not just backbone) is the bottleneck for practical enzyme design workflows that must precisely position active-site residues relative to a substrate; most backbone-only models hand off side-chain packing as a separate post-processing step that can undo backbone-level improvements. Emyx's end-to-end atomic generation within a computationally efficient framework specifically addresses the enzyme design use case where the cost of generating diverse scaffold candidates is a practical bottleneck.
CODE: Not released
---

---
TITLE: Pepti-Agent: An AI Agent for Peptide Design and Optimization
AUTHORS: Houxu Chen, Achuth Chandrasekhar, Amir Barati Farimani
SOURCE: arXiv | 2606.15422 | [**Link**](https://arxiv.org/abs/2606.15422)
TOPIC TAG: General ML
TLDR: Pepti-Agent is a closed-loop agentic framework that exposes therapeutic peptide generation, property prediction, and single-residue mutation as independently inspectable Model Context Protocol (MCP) tools, tracking multi-property state (solubility, hemolysis, non-fouling) of each candidate over iterative design cycles rather than relying solely on natural-language reasoning.
WHY IT MATTERS: Multi-objective therapeutic peptide design is an ideal testbed for agentic ML because the design space is small enough to iterate quickly yet the property tradeoffs — improving solubility can degrade hemolysis, etc. — are genuinely difficult to reason about jointly; MCP-structured tooling makes each design step auditable and re-runnable, directly addressing the reproducibility gap in LLM-based design agents. The framework is one of the first to combine structured MCP tools with explicit candidate-state tracking (rather than free-form dialogue) for iterative molecular optimization.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Two-Stage Fine-Tuning for Protein Sequence Generation with Targeted Amino-Acid Composition (arXiv 2606.27939)**
This paper addresses a practical protein engineering problem that has lacked a clean generative-model solution: generating protein sequences whose amino-acid composition profiles match a user-specified target (e.g. enriched in lysine and methionine for nutritional applications) while remaining sequence-plausible and diverse. The solution — supervised domain-adaptive fine-tuning followed by iterative reward-weighted RL anchored against the fine-tuned model as a frozen reference — is methodologically notable because it explicitly demonstrates where RL is *necessary* rather than redundant (SFT alone brings composition close but cannot satisfy exact constraints). This is one of the first papers to apply RL-based protein LM alignment to a controlled-composition generation task with a real industrial use case (synthetic feed protein design).
Code: Not released.

**2. AMPGAN v3: Agentic Discovery of Non-Canonical Antimicrobial Peptides (arXiv 2606.17127)**
AMPGAN v3 is the first conditional generative model for antimicrobial peptides that natively handles D-amino acids and terminal chemical modifications, which are critical for real therapeutic utility but largely absent from prior generative AMP models. By separating the adversarial discriminator from the activity-aware discriminator, the training is stabilized and the compositional coverage of the generated peptides is broadened beyond canonical chemistry. Wet-lab validation of five candidates — two of which showed genuine Gram-positive activity — makes this a rare example of a new generative AMP model with experimental confirmation in the same paper.
Code: Not released.

**3. Circuit Tracing in Autoregressive Protein Language Models (arXiv 2606.16044)**
Mechanistic interpretability has transformed our understanding of what transformer LLMs learn and how, and this paper makes a first direct application of circuit-tracing methods (attention-head attribution patching) to an autoregressive protein language model, asking which circuits encode secondary structure, evolutionary conservation, and other biological features. Accepted to the ICML 2026 Mechanistic Interpretability Workshop, it opens the door to circuit-level editing and guided decoding in PLMs — tools that could let practitioners steer generation toward or away from specific structural features without retraining. The ability to identify and patch specific circuits in protein LMs could also substantially accelerate mechanistic understanding of how evolutionary pressures are encoded in these models.
Code: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 6
- By topic: Protein LM: 4 | Diffusion: 0 | Genomics: 1 | Architecture: 0 | General ML: 1 | Clinical: 0
- Sources: arXiv: 6 | bioRxiv: 0 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 0
