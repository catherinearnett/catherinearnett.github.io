---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/taq.html
---
{% raw %}
# So you want to work on Tamasheq?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `taq` · macrolanguage `tmh`

**Language family:** **Afro-Asiatic** › Berber › Tuareg › Southern Tuareg ([Glottolog](https://glottolog.org/resource/languoid/id/tama1365))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Speakers:** about 2.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `tmh`, so includes other varieties

**Official / recognised in:** Mali

**Status:** Official language


## What does Tamasheq look and sound like?

**Written:** Omniglot has [a page on Tamasheq](https://www.omniglot.com/writing/tamasheq.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/taq/) has 1 video of Tamasheq speakers. Watch [Ibrahim speaking French, Zarma, Gourmanchéma, Hassaniyya, Tamasheq, Maasina Fulfulde](https://wikitongues.org/videos/ibrahim_20160229_fra-dje-gux-mey-taq-ffm/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                  |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                                |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                |
| FineWeb                | 1.2 MB (taq_Latn 0; taq_Tfng 0), equivalent to ≈0.9 MB of English after byte-premium scaling; 36.6 MB removed by filtering. This is ~1/43,313,998 of English data and ranks 196 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                            |

**By writing system:**

| Writing system    |   FineWeb | FineWeb, English-equivalent   |
|:------------------|----------:|:------------------------------|
| Latin (`Latn`)    |         0 | — (no byte premium yet)       |
| Tifinagh (`Tfng`) |         0 | — (no byte premium yet)       |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script); 2,009 sentences (Tfng script) — the same sentences in 200+ languages                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script); 1,358 sentences (Tfng script) — paired with English                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, fasttext, funlangid.
- **Eval datasets (1):** FLORES (n=300)
- **Best model:** GlotLID — F1 0.985 (P 1.000, R 0.970, FPR 0.00e+00) averaged over 1 dataset(s). Runner-up: OpenLID-v2 (F1 0.831).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.970 | 0.985 | 0.000 | ✓                |
| OpenLID-v2   |       0.926 |    0.753 | 0.831 | 0.000 | ✓                |
| fasttext     |       0.991 |    0.697 | 0.818 | 0.000 | ✓                |
| funlangid    |       0.530 |    0.650 | 0.584 | 0.004 | ✓                |
| AfroLID      |       0.427 |    0.127 | 0.195 | 0.007 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tamasheq to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tamasheq *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tamasheq and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tamasheq has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tamasheq?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tamasheq (and whether the model is exclusively tagged for Tamasheq or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **3** text-generation models are explicitly tagged for Tamasheq (0 original uploads, 3 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Tamasheq.
- Including tags inherited from base models: **8**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        3 | ████████████████████ |

### Largest models tagged for Tamasheq

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of          |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------|
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs)     | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base   |
| [McGill-NLP/AfriqueQwen3.5-4B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B-50Langs)     | 5.2B         |                   32 |   2026 | Qwen/Qwen3.5-4B-Base   |
| [McGill-NLP/AfriqueQwen3.5-0.8B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-0.8B-50Langs) | 1.1B         |                   32 |   2026 | Qwen/Qwen3.5-0.8B-Base |

### Largest models tagged *only* for Tamasheq

_none_

## What evals are available?

We analyzed categories of popular (base) language model evaluations:

  1. **Linguistic knowledge**. Ability to discriminate grammatical from ungrammatical sentences via minimal pairs, e.g. BLiMP and MultiBLiMP, and cloze-style word prediction, e.g. LAMBADA.
  2. **Pragmatics, discourse, and co-reference**. Understanding meaning beyond the literal sentence: pronoun resolution and Winograd-style coreference (e.g. WSC, WinoGrande, XWinograd), discourse coherence, figurative language and idioms, implicature, negation and presupposition.
  3. **Commonsense reasoning**. These tasks evaluate a combination of language understanding and world knowledge, e.g. HellaSwag-, PIQA-, COPA- and StoryCloze-style datasets.
  4. **Reading comprehension**. Answering questions about a given passage, e.g. Belebele.
  5. **Knowledge and open-domain QA**. World knowledge, e.g. MMLU.

We also consider available machine translation benchmarks, which can also be used for parallel NLL evaluations among other things.

We ordered these roughly in level of complexity and plot them in a pyramid shape, where we expect that the lower parts of the pyramid are filled in before the higher parts.

The scope of this analysis did not include classification tasks or tasks designed for bidirectional models, nor does it include post-trained model evals (e.g. instruction following) or tasks about reasoning, coding, and domain-specific material, e.g. medical or legal topics.

**2** benchmark datasets in the survey include Tamasheq.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Tfng) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Tfng) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tamasheq datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tamasheq? Does it make sense to train one?
  - ~0.9 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~11.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 9.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,498 papers (0.05%) (rank 155 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tamasheq

Here are up to ten papers published in 2026 that mention Tamasheq. None of the 9 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     | body only      |
| Completely Modular Fine-tuning for Dynamic Language Adaptation                                                                                | [2026.findings-eacl.252](https://aclanthology.org/2026.findings-eacl.252/)     | body only      |
| SrcMix: Mixing of Related Source Languages Benefits Extremely Low-resource Machine Translation                                                | [2026.findings-eacl.332](https://aclanthology.org/2026.findings-eacl.332/)     | body only      |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) | body only      |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   | body only      |
| Building a Dataset for French Accent Classification Evaluation: Are We There Yet?                                                             | [2026.lrec-1.450](https://aclanthology.org/2026.lrec-1.450/)                   | body only      |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   | body only      |
| Pantagruel: Unified Self-Supervised Encoders for French Text and Speech                                                                       | [2026.lrec-1.799](https://aclanthology.org/2026.lrec-1.799/)                   | body only      |

{% endraw %}
