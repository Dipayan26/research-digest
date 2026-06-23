# Research Digest — 2026-06-23

> Auto-generated daily digest of ML × computational biology preprints.
> Sources searched: arXiv (cs.LG, cs.AI, q-bio.BM, q-bio.QM, q-bio.GN, stat.ML, cs.NE), bioRxiv, medRxiv, PubMed, Hugging Face Papers, Semantic Scholar, Papers With Code.
>
> Note: This is the **third consecutive day** (following 2026-06-21 and 2026-06-22) with zero qualifying papers, and three parallel research passes today pinned down the cause precisely rather than just re-describing the symptom. Direct fetch access returns HTTP 403 in this environment for: `arxiv.org` listing pages, `export.arxiv.org` (including the official arXiv API, confirmed via both WebFetch and `curl`), `biorxiv.org` listing/collection/content pages, `pubmed.ncbi.nlm.nih.gov` search results, and `huggingface.co/papers` (both the general listing and per-date pages). The `api.biorxiv.org` REST endpoint (which historically is not blocked the way the HTML site is) is also not in this environment's network egress allowlist. The Hugging Face MCP connector (`hf_hub_query`) failed to connect on every attempt today; the HF `paper_search` semantic-search tool did connect but ranks by relevance/popularity rather than recency, so it cannot be used to find "papers from the last 24h." With direct access closed off, all three search passes (arXiv/Semantic Scholar; bioRxiv/medRxiv; PubMed/HF Papers/PWC) relied on 25-35 WebSearch queries each — by topic keyword, by exact date string ("2026-06-22"/"2026-06-23"), by `site:` filters, and by brute-force arXiv-ID-range and bioRxiv-DOI-pattern probing for the June 22-23 date stamps. In every pass, the freshest verifiably-dated, in-scope item found was from 2026-06-21 or earlier — WebSearch's index for these sources appears to lag real-time posting by roughly 1-10 days depending on the source, and nothing from 06-22/06-23 has been indexed yet. No item met both the strict 24-48h date requirement and the topic/dedupe bar, so nothing is reported below rather than padding the list with stale or unverifiable items.
>
> **Recommendation for fixing this at the root**: add `api.biorxiv.org` to the network egress allowlist (its JSON endpoint `https://api.biorxiv.org/details/biorxiv/<start>/<end>/0` is typically open even when the HTML site isn't) and investigate why the Hugging Face MCP server (`hf_hub_query`) consistently fails to connect — those two changes alone would restore two of the seven sources to full reliability.

---

==============================================================
HIGHLIGHTS OF THE DAY
==============================================================
None — no qualifying papers found today (third consecutive day; root cause identified above as an infrastructure/tooling gap, not a lull in the field).

==============================================================
DAILY STATS
==============================================================
- Total papers found today: 0
- By topic: Protein LM: 0 | Diffusion: 0 | Genomics: 0 | Architecture: 0 | General ML: 0 | Clinical: 0
- Sources: arXiv: 0 (403 on listing pages + API) | bioRxiv: 0 (403 on listing/content pages) | medRxiv: 0 | PubMed: 0 (403 on search) | HF Papers: 0 (403 on listing; MCP connector failed) | PWC: 0
- Papers with code released: 0
