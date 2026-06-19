# Research Digest — 2026-06-19

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Direct arXiv/bioRxiv/PubMed listing pages and the arXiv export API again returned HTTP 403 in this environment, so today's sweep relied entirely on web search. PubMed/NCBI E-utilities, Europe PMC, and Nature.com were all unreachable (403) via WebFetch as well — two independent search passes turned up no PubMed paper that could be confirmed (PMID + date) as posted in the last 24-48h, so PubMed contributes 0 verified items today rather than risk reporting an unverified/incorrect date. Hugging Face Papers and Papers With Code searches surfaced only items already covered in prior digests or papers several weeks old still trending in discussion, so neither contributes new items today. All candidates below were cross-checked against the full prior digest history (through 2026-06-18) and excluded if already covered. Today's set draws on three arXiv papers (submitted June 15-16) and five bioRxiv preprints (posted June 11-18) that had not yet surfaced in prior sweeps.

---

---
TITLE: Multiscale Reconstruction of Protein Conformations from Cryo-EM Images
AUTHORS: David Y. W. Thong, Ozan Öktem, Joakim Andén
SOURCE: arXiv | 2606.18058 | [**Link**](https://arxiv.org/abs/2606.18058)
TOPIC TAG: Protein LM
TLDR: Introduces a multiscale algorithm that recovers atomic-resolution protein structure directly from single-particle cryo-EM images by explicitly parameterizing the backbone in terms of bonds, torsion angles, and bond angles, achieving state-of-the-art RMSD/TM-score under high-noise, low-contrast simulated conditions.
WHY IT MATTERS: Most ML structure-prediction pipelines treat cryo-EM density maps as a downstream fitting target rather than reconstructing structure directly from raw noisy images; this closes that gap with a physically-grounded backbone prior instead of a learned black-box map-to-structure model. Robustness to electron-microscope model misspecification makes it a candidate building block for de novo structure determination pipelines that currently rely on AlphaFold-style priors alone.
CODE: Not released
---

---
TITLE: Generative Design of Antigen-Specific T-Cell Receptor Sequences with a Conditional Diffusion Model (TCRDiff)
AUTHORS: Yumeng Zhang, Wenhua Liang, Shuting Xu, Matthew Witney, Jamie Rossjohn, Xiao-Dong Su, Anthony W. Purcell, Feng Wang, Jiangning Song
SOURCE: bioRxiv | 10.64898/2026.06.10.730756 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.10.730756v1)
TOPIC TAG: Diffusion
TLDR: TCRDiff is a conditional denoising diffusion model that generates antigen-specific CDR3αβ TCR sequences conditioned on peptide-MHC targets and germline V-gene usage, with in vitro activation assays confirming generated TCRs specifically recognize the MAGE-A3 epitope with minimal off-target cross-reactivity.
WHY IT MATTERS: Most generative TCR/antibody design papers stop at in silico binding scores, but this one closes the loop with wet-lab functional validation against a real cancer-testis antigen — directly relevant given past clinical setbacks from off-target cross-reactivity in MAGE-A3-directed TCR therapies. Conditioning on germline V-gene usage alongside the pMHC target is a useful template for steering generative immune-receptor design toward developable, specificity-controlled candidates.
CODE: Not released
---

---
TITLE: MoE-Bind: Guiding De Novo Protein Binder Generation with Sparse Experts
AUTHORS: Not specified in accessible abstract
SOURCE: bioRxiv | 10.64898/2026.06.13.732043 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.13.732043v1)
TOPIC TAG: MoE
TLDR: Proposes a sequence-only, Mixture-of-Experts-guided architecture (using multi-head latent attention) for de novo protein binder generation against arbitrary target sequences, aimed at antibodies, enzyme inhibitors, and PPI modulators.
WHY IT MATTERS: The paper's core claim — that sparse architectural design rather than raw scale drives fast, structure-free, interpretable binder generation — pushes back against the prevailing scale-first trend in protein generative models. A structure-free MoE binder generator would be substantially cheaper to run than structure-conditioned diffusion/flow approaches for early-stage binder screening.
CODE: Not released
---

---
TITLE: Large-Scale Prediction of Transcription Factor Binding Across Human Cell Types Informs Regulatory Genomics and Reveals Promiscuous Occupancy Associated with Chromatin Contacts
AUTHORS: E. Sonder, I. G. Aymergen, J. Sun, A. Feuvrier, G. Schratt, K. Gapp, J. Bohacek, M. D. Robinson, P.-L. Germain
SOURCE: bioRxiv | 10.64898/2026.06.17.732915 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.17.732915v1)
TOPIC TAG: Genomics
TLDR: Computationally predicts transcription factor binding across a large panel of human cell types and finds widespread "promiscuous" TF occupancy that correlates with chromatin contact regions rather than canonical motif-driven binding.
WHY IT MATTERS: A cell-type-broad TF binding resource is directly useful as ground truth/pretraining signal for regulatory genomic LMs (enhancer/promoter prediction, variant-effect models), and the promiscuous-occupancy finding complicates the standard motif-centric interpretation that most regulatory element predictors are built on. It strengthens the case for incorporating 3D chromatin contact features into TF binding and regulatory variant-effect models rather than relying on sequence motifs alone.
CODE: Not released
---

---
TITLE: Bioinf-Farma: Supervised Integration of Epitope Prediction and Recombinant Protein Developability for Automated Vaccine Candidate Prioritization
AUTHORS: Heather Bondi, Matteo Crespi, Marco Orlando, Francesco Lescai, Stefano A. Serapian, Giorgio Colombo, Mauro Fasano, Loredano Pollegioni, Gianluca Molla
SOURCE: bioRxiv | 10.64898/2026.06.15.732271 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.15.732271v1)
TOPIC TAG: General ML
TLDR: Builds a modular platform that jointly scores antigenicity and recombinant-expression feasibility for vaccine antigen candidates, combining AlphaFold DB/Boltz-2 structures with two supervised Random Forest meta-learners over six existing solubility and thermal-stability predictors into a single Expression Efficiency Score.
WHY IT MATTERS: Vaccine antigen pipelines typically optimize immunogenicity and manufacturability as separate, manually-reconciled steps; this stacks existing single-property predictors into one supervised prioritization score plus a web interface usable without programming. It is a practical "meta-model" pattern — combining several specialized predictors via a learned aggregator — that is reusable wherever multiple narrow property predictors need to be jointly optimized for candidate ranking.
CODE: Not released
---

---
TITLE: EditorForge: An Active-Site-Aware Framework for Inverse-Folding-Based Protein Redesign
AUTHORS: Not specified in accessible abstract
SOURCE: bioRxiv | 10.64898/2026.06.08.730993 | [**Link**](https://www.biorxiv.org/content/10.64898/2026.06.08.730993v1)
TOPIC TAG: Protein LM
TLDR: Wraps fixed-backbone inverse folding in a constraint-and-audit framework that restricts redesign to a small residue "design envelope" around active sites using distance shields and sequence-window rules, applied to gene-editor proteins where catalytic residues must be preserved.
WHY IT MATTERS: Off-the-shelf inverse folding models redesign whole sequences and can silently perturb catalytic geometry; turning inverse folding into a controlled, auditable triage workflow (rather than broad unconstrained generation) is directly applicable to redesigning any enzyme or editor domain where a small number of residues are functionally non-negotiable. Releasing the constraint/audit code as a wrapper around existing inverse-folding models (rather than a new model) makes it immediately reusable on top of whatever backbone model a lab already uses.
CODE: [**Code**](https://github.com/anthonycehn-eng/EditorForge-An-Active-Site-Aware-Framework-for-Inverse-Folding-Based-Protein-Redesign)
---

---
TITLE: Comprehensive pKa Data Augmentation from Limited Real Data through an Engineered Models–Quantum Framework
AUTHORS: Wang Rui, Liu Dinghao, et al.
SOURCE: arXiv | 2606.17077 | [**Link**](https://arxiv.org/abs/2606.17077)
TOPIC TAG: General ML
TLDR: Combines ML-based empirical pKa prediction with quantum-chemistry energy calculations on top of the iBonD experimental pKa database to augment scarce high-quality pKa data, enabling large-scale regression-based pKa prediction across unlabeled molecular datasets.
WHY IT MATTERS: pKa is a first-order driver of ADMET behavior (ionization state, solubility, membrane permeability), and experimental pKa data is chronically scarce relative to other molecular properties; a hybrid ML+quantum augmentation pipeline directly addresses that bottleneck rather than just fitting a better model to the same small dataset. The approach generalizes to other physicochemical-property prediction tasks where quantum calculations are expensive but can supply weak labels at scale.
CODE: Not released
---

---
TITLE: Can Neurons Speak? Semantic Narration of Vision at Single-Cell Resolution
AUTHORS: Not specified in accessible abstract
SOURCE: arXiv | 2606.18667 | [**Link**](https://arxiv.org/abs/2606.18667)
TOPIC TAG: General ML
TLDR: NEURRATOR decodes single-neuron spike trains from Neuropixels recordings of mouse visual cortex into free-form natural-language scene descriptions, by mapping spikes into CLIP's patch-embedding space and using a multimodal LM plus sparse autoencoder to generate and validate the descriptions without any language-side training.
WHY IT MATTERS: Translating raw single-cell neural activity directly into interpretable natural language (rather than into a fixed decoded-stimulus class) is a multimodal representation-learning pattern — CLIP-space alignment of a non-text signal followed by language generation — that is directly transferable to other "decode a biological signal into language" problems such as describing single-cell transcriptomic states or chromatin profiles. It also demonstrates that no language-side fine-tuning is needed if the non-text encoder is aligned into an existing vision-language embedding space.
CODE: Not released
---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================

**1. Multiscale Reconstruction of Protein Conformations from Cryo-EM Images** (arXiv:2606.18058)
This paper reconstructs atomic-resolution protein structure directly from raw single-particle cryo-EM images rather than from an already-resolved density map, using an explicit backbone parameterization (bonds, torsion angles, bond angles) as a strong structural prior instead of a learned black-box mapping. It achieves state-of-the-art RMSD/TM-score under high-noise, low-contrast conditions and stays robust even when the electron-microscope image-formation model is misspecified. This is a meaningful step toward de novo structure determination pipelines that don't depend on AlphaFold-style sequence priors, which matters for proteins or conformational states poorly represented in training data.
Code/weights: Not released.

**2. Generative Design of Antigen-Specific T-Cell Receptor Sequences with a Conditional Diffusion Model (TCRDiff)** (bioRxiv 10.64898/2026.06.10.730756)
TCRDiff generates CDR3αβ TCR sequences conditioned on a peptide-MHC target and germline V-gene usage via conditional denoising diffusion, and — unlike most generative immune-receptor papers — backs this up with in vitro activation assays showing specific recognition of the MAGE-A3 cancer-testis antigen with minimal off-target cross-reactivity. Wet-lab functional validation is rare in this subfield and directly addresses the historical safety failure mode (off-target cross-reactivity) that has previously derailed MAGE-A3-targeted TCR therapies in the clinic. This is a strong template for specificity-controlled generative design in cancer immunotherapy.
Code/weights: Not released.

**3. Large-Scale Prediction of Transcription Factor Binding Across Human Cell Types** (bioRxiv 10.64898/2026.06.17.732915)
This study predicts TF binding across a broad panel of human cell types and finds that a substantial fraction of TF occupancy is "promiscuous" — better explained by chromatin contact structure than by canonical sequence motifs. That finding complicates the motif-centric assumptions baked into most current regulatory-element and variant-effect predictors, suggesting 3D chromatin context needs to be a first-class input rather than a post-hoc add-on. As a large cell-type-broad TF binding resource, it's also immediately useful as pretraining/evaluation signal for regulatory genomic foundation models.
Code/weights: Not released.

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 8
- By topic: Protein LM: 2 | Diffusion: 1 | Genomics: 1 | MoE: 1 | General ML: 3
- Sources: arXiv: 3 | bioRxiv: 5 | medRxiv: 0 | PubMed: 0 | HF Papers: 0 | PWC: 0
- Papers with code released: 1
