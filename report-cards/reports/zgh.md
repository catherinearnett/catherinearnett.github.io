---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/zgh.html
---
{% raw %}
# So you want to work on Tamazight?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `zgh`

**Language family:** **Afro-Asiatic** › Berber › Kabyle-Atlas Berber › … › Central Moroccan Berber. Glottolog treats Standard Moroccan Tamazight as a variety of Central Moroccan Berber ([Glottolog](https://glottolog.org/resource/languoid/id/stan1324))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Speakers:** about 8.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Morocco

**Status:** Official language


## What does Tamazight look and sound like?

**Written:** Omniglot has [a page on Tamazight](https://www.omniglot.com/writing/tamazight.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/zgh/) has 1 video of Tamazight speakers. Watch [Moulid speaking Amazighe (Tifinagh)](https://wikitongues.org/videos/moulid_20250426_zgh/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 12,308 articles in zgh.wikipedia; 50 active users. This is ~1/613 of English data and ranks 98 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                   |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                    |
| FineWeb                | 0.3 MB (zgh_Tfng 0), equivalent to ≈0.1 MB of English after byte-premium scaling; 1.4 MB removed by filtering. This is ~1/187,449,283 of English data and ranks 229 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                |
|:-----------------------|:-------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                             |
| UniMorph               | **None found**                                                                             |
| Wikidata labels        | 159,481 Wikidata items have a label in Tamazight. (Wikidata codes (labels): zgh (159,481)) |
| Wordnets               | **None found**                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                   |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 5,699 sentence pairs with English across 3 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (4,126), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (1,432), [wikimedia](https://opus.nlpl.eu/wikimedia) (141). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                   |
| Tatoeba                                                                                  | 20,777 sentences, 14,966 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/zgh/none)).                                                                                                       |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Tfng script) — the same sentences in 200+ languages                                                                                                                                                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                             |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=61)
- **Best model:** GlotLID — F1 0.983 (P 0.994, R 0.972, FPR 1.70e-05) averaged over 3 dataset(s). Runner-up: OpenLID-v2 (F1 0.971).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.994 |    0.972 | 0.983 | 0.000 | ✓                |
| OpenLID-v2   |       0.989 |    0.954 | 0.971 | 0.000 | ✓                |
| commonlingua |       0.879 |    0.962 | 0.909 | 0.001 | ✓                |
| pyfranc      |       0.887 |    0.921 | 0.891 | 0.001 | ✗                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  61 |       0.983 |    0.951 | 0.967 |
| Tatoeba   | 300 |       1.000 |    0.967 | 0.983 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tamazight to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tamazight *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tamazight and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tamazight has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tamazight?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tamazight (and whether the model is exclusively tagged for Tamazight or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Tamazight (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Tamazight.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Models tagged for Tamazight

None of these has a known parameter count:

| model                                                 |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------|---------------------:|-------:|:----------------|
| [wikilangs/zgh](https://huggingface.co/wikilangs/zgh) |                    2 |   2026 | —               |

### Largest models tagged *only* for Tamazight

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Tamazight.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level               | task   | dataset                                                                                                  |   # test items | construction                                 |
|:--------------------|:-------|:---------------------------------------------------------------------------------------------------------|---------------:|:---------------------------------------------|
| Machine translation |        | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) (2 varieties/pairs) |         26,117 | Native (crowdsourced Tatoeba sentence pairs) |

### Standard machine translation test sets

| Test set                                                                | Direction(s)              | Size                   | Human reference   |
|:------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages) | 2,009 sentences (Tfng) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tamazight datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tamazight? Does it make sense to train one?
  - ~0.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~1.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 12 of ~18,498 papers (0.06%) (rank 142 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Standard Moroccan Tamazight | Tamazight

Here are up to ten papers published in 2026 that mention Tamazight. None of the 12 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| TranslatePsy-AfriSLM: High-Quality Data Scaling For Low-Resource Machine Translation                                                          | [2026.emnlp-main.1686](https://aclanthology.org/2026.emnlp-main.1686/)     |
| An Empirical Study of Many-Shot In-Context Learning for Machine Translation of Low-Resource Languages                                         | [2026.findings-aacl.142](https://aclanthology.org/2026.findings-aacl.142/) |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Completely Modular Fine-tuning for Dynamic Language Adaptation                                                                                | [2026.findings-eacl.252](https://aclanthology.org/2026.findings-eacl.252/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| DATASHI: A Parallel English–Tashlhiyt Corpus for Orthography Normalization and Low-Resource Language Processing.                              | [2026.lrec-1.153](https://aclanthology.org/2026.lrec-1.153/)               |
| Structured Partial Predictability in Non-Concatenative Morphology: The Case of Tashlhiyt Berber                                               | [2026.slide-1.11](https://aclanthology.org/2026.slide-1.11/)               |
| Syllable Structures Across Arabic Varieties                                                                                                   | [2026.vardial-1.21](https://aclanthology.org/2026.vardial-1.21/)           |
| FIÙR: A Benchmark Dataset for Eastern Lombard Machine Translation                                                                             | [2026.wmt-main.199](https://aclanthology.org/2026.wmt-main.199/)           |

{% endraw %}
