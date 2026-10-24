# Fedor Makovskiy — AI developer

**English** | [Русский](README.ru.md)

RAG assistants, semantic search and LLM evaluation. For businesses: assistants over company documents, support bots and search — services and prices on my website (coming soon), meanwhile [Telegram](https://t.me/makltd2).

## How I work

- **Evaluation first.** A fixed control set (questions, queries or unit tests) comes first; every change is measured on it.
- **LLM-as-judge, not trusted blindly.** Judge scores are paired with a simpler signal (similarity, unit tests) and treated as an early warning, not a replacement for human review.
- **Statistics, not eyeballing.** Welch's t-test against baseline runs, null baselines for "stability" metrics, several seeds where runs are noisy.
- **Reproducible runs.** Pinned seeds and data revisions, resumable experiments, raw results kept next to the summary.
- **Negative results are results.** If a hypothesis fails, the README says so (see ai-compute-optimizer and embedding-translator).

## Projects

| Project | Stack | Result |
|---|---|---|
| [alqira](https://github.com/makltd123/alqira) — semantic search over ~147k Russian companies (overview, code private) | BGE-M3 fine-tuned with triplet loss, Zilliz, Mistral for profile extraction, Node.js + Flask | Coverage on 1,000 queries (40 industries × 25 cities): 691 with best-match similarity ≥ 40%. LLM judge on 63,600 query–company pairs: judged relevance grows with the search score (4.0 → 6.1). Misspelled queries: −1.2% score, 73% top-5 overlap. Main limit: data coverage, not the model |
| [ai-compute-optimizer](https://github.com/makltd123/ai-compute-optimizer) — routing tasks across cheap / medium / strong models | Mistral API, HumanEval, pass@1 at temperature 0 | First 60 tasks: the cheap model matched the strong one (95%) at 1/13 of the cost. On all 164 tasks no router reached the 90% target or beat "everything to the cheap model"; run-to-run noise is the size of the differences |
| [degradation-detector](https://github.com/makltd123/degradation-detector) — silent LLM quality degradation | FastAPI, SQLite, React, sentence-transformers | Fresh adversarial mutations of past queries every run, judge scores on 3 axes + semantic similarity, Welch's t-test vs baseline runs. Prototype on synthetic data |
| [support-intelligence](https://github.com/makltd123/support-intelligence) — multi-agent RAG over support tickets | Mistral, Qdrant, Gradio | Orchestrator picks agents; each answers only from the 20 retrieved tickets and cites their numbers. Synthetic dataset, no accuracy measurement yet |
| [hiring-optimizer](https://github.com/makltd123/hiring-optimizer) — team selection from a candidate pool | FastAPI, Next.js, scipy (Hungarian algorithm, MILP), Ollama | Local LLM mode, regex anonymization before the model, PostgreSQL row-level security, consent / erasure / export of personal data |
| [revirseing](https://github.com/makltd123/revirseing) — PDF toolkit from scratch | Node.js, no PDF libraries | xref streams, filters, font encodings and CMaps, RC4/AES decryption, incremental updates. 39 tests; text extraction cross-checked with pypdf on files from 4 unrelated producers |

## Research

| Project | Method | Finding |
|---|---|---|
| [negation-direction](https://github.com/makltd123/negation-direction) | DiffMean on 8 bi-encoders (EN/RU), pre-registered criteria, control directions | A stable negation direction exists and is shared by English and Russian; at the output it acts mostly as a polarity flip. As an extra feature it cuts negation errors (e.g. 0.72 → 0.02), projecting it out hurts. Pitfall found: overlapping CV folds give ≈ 0.7 "stability" on pure noise |
| [semantic-cryptography](https://github.com/makltd123/semantic-cryptography) | 8 embedding defenses, 2 BEIR corpora × 2 models, linear alignment attack with ~100 known pairs | Noise schemes: 99.9% re-identified at half retrieval quality; secret rotation: 100%. Only information-destroying schemes (PQ) help, and their protection depends on the corpus |
| [embedding-translator](https://github.com/makltd123/embedding-translator) | Ridge, Procrustes, MLP and others, MiniLM → e5, leave-one-topic-out | A translator closes only ~16–18% of the gap to re-embedding; weak → strong is the hardest direction; "cosine to the original" (0.91) is misleading — the mean vector already gives 0.86 |
| [drift-tracker](https://github.com/makltd123/drift-tracker) | K-means clusters, per-cluster recall drift of top-5 retrieval | Shows which clusters break after an embedding model switch and plans a partial re-index. Prototype on a synthetic corpus |

## Models

[makltd1/compas-bge-m3-ru](https://huggingface.co/makltd1/compas-bge-m3-ru) — BGE-M3 (from deepvk/USER-bge-m3) fine-tuned for Russian B2B company search.

## Stack

Python · PyTorch · transformers · sentence-transformers · LoRA · FastAPI · Qdrant · Zilliz · PostgreSQL · SQLite · Node.js · Ollama · Mistral API · Docker

## Contacts

Telegram [@makltd2](https://t.me/makltd2) · Email makltd123@mail.ru
