# Fedor Makovskiy — AI developer

**English** | [Русский](README.ru.md)

I build AI assistants over company documents, support bots and semantic search for businesses. Before launch I measure quality on the client's own questions, and I write up what did not work as openly as what did.

## What I do

- **Knowledge-base assistants**: employees ask in their own words and get an answer with a link to the source document.
- **Support bots** for websites and Telegram that answer by your rules and hand hard cases to a human.
- **Semantic search** for catalogs and websites: synonyms, typos, descriptions instead of product names.
- **Self-hosted LLMs** when data must stay inside the company: models compared on your tasks before buying hardware.
- **Audits of existing AI bots**: share of correct answers, error types, and cost per 1,000 answers on a cheaper model.

## Selected projects

| Project | What it shows |
|---|---|
| [alqira](https://github.com/makltd123/alqira) | Semantic search over ~147k Russian companies on a fine-tuned BGE-M3 ([public on Hugging Face](https://huggingface.co/makltd1/compas-bge-m3-ru)), evaluated on 1,000 queries and 63,600 query–company pairs |
| [ai-compute-optimizer](https://github.com/makltd123/ai-compute-optimizer) | On the first 60 HumanEval tasks a cheap model matched the expensive one (95% pass@1) at 1/13 of the cost; routing between models did not beat it |
| [degradation-detector](https://github.com/makltd123/degradation-detector) | Catches silent LLM quality drops: fresh adversarial test cases every run, an LLM judge and a t-test |
| [hiring-optimizer](https://github.com/makltd123/hiring-optimizer) | Resume parsing with a local LLM (Ollama), anonymization before the model, consent, erasure and export of personal data |
| [revirseing](https://github.com/makltd123/revirseing) | A PDF toolkit written from scratch; text extraction and form filling cross-checked with pypdf |
| [email-agent](https://github.com/makltd123/email-agent) | A Telegram bot for personal cold B2B email, used by a small group of people |

## Research

| Project | Finding |
|---|---|
| [negation-direction](https://github.com/makltd123/negation-direction) | Sentence embeddings have a stable negation direction, shared by English and Russian; used as an extra feature it cuts negation errors, e.g. 0.72 → 0.02 |
| [semantic-cryptography](https://github.com/makltd123/semantic-cryptography) | Noise and secret rotations do not stop re-identification of protected embeddings (99.9% and 100%) |
| [embedding-translator](https://github.com/makltd123/embedding-translator) | Translating embeddings between models closes only ~16–18% of the gap: re-embed instead |
| [drift-tracker](https://github.com/makltd123/drift-tracker) | Shows which clusters break when you switch embedding models and plans a partial re-index |

## Contacts

Telegram [@makltd1](https://t.me/makltd1) · Email makltd123@mail.ru · [Hugging Face](https://huggingface.co/makltd1)
