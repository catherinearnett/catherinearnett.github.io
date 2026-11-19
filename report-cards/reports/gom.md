---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gom.html
---
{% raw %}
# So you want to work on Konkani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gom` · macrolanguage `kok`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Marathi-Konkani ([Glottolog](https://glottolog.org/resource/languoid/id/goan1235))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Writing systems:** `Deva` and `Latn`

**Speakers:** about 4.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `kok`, so includes other varieties

**Official / recognised in:** India

**Status:** Regional official language


## What does Konkani look and sound like?

**Written:** Omniglot has [a page on Konkani](https://www.omniglot.com/writing/konkani.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/gom/) has 1 video of Konkani speakers. Watch [Savio speaking Mangalorean Konkani](https://wikitongues.org/videos/savio_20200711_gom/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                 |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,644 articles in gom.wikipedia; 10 active users. This is ~1/2,071 of English data and ranks 125 of the 168 languages in the set with any data in Wikipedia; 164 have none.                            |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                               |
| FineWeb                | 16.9 MB (gom_Deva 10.0 MB; gom_Latn 10.0 MB); 0.25 GB removed by filtering. This is ~1/3,165,464 of English data and ranks 131 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 22.8 MB (gom_Deva 23.0 MB) (rank 149 of the 166 languages in the set that have any; 166 have none)                                                                                                     |

**By writing system:**

| Writing system      | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Devanagari (`Deva`) | 10.0 MB   | — (no byte premium yet)       | 23.0 MB      | 8.9 MB                         |
| Latin (`Latn`)      | 10.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                   |
| UniMorph               | **None found**                                                                                                   |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                   |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (4):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=10), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.914 (P 0.933, R 0.897, FPR 2.84e-04) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.858).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.933 |    0.897 | 0.914 | 0.000 | ✓                |
| fasttext     |       0.850 |    0.883 | 0.858 | 0.000 | ✓                |
| py3langid    |       0.803 |    0.795 | 0.794 | 0.001 | ✓                |
| funlangid    |       0.724 |    0.811 | 0.724 | 0.001 | ✓                |
| commonlingua |       0.717 |    0.808 | 0.716 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  10 |       0.800 |    0.800 | 0.800 |
| CommonLID | 300 |       0.941 |    0.897 | 0.918 |
| Wikipedia | 300 |       0.993 |    0.907 | 0.948 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Konkani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Konkani *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Konkani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Konkani has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Konkani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Konkani (and whether the model is exclusively tagged for Konkani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **69** text-generation models are explicitly tagged for Konkani (47 original uploads, 22 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Konkani.
- Including tags inherited from base models: **101**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        6 | ██                   |
|   2025 |        1 | █                    |
|   2026 |       60 | ████████████████████ |

### Largest models tagged for Konkani

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |
| [chinmaykumar-vyas/sarvam-105b](https://huggingface.co/chinmaykumar-vyas/sarvam-105b)       | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Konkani

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                             |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------------------|
| [konkani/mistral-7b-instruct-konkani-awq](https://huggingface.co/konkani/mistral-7b-instruct-konkani-awq)   | 7.2B         |                    1 |   2026 | mistralai/Mistral-7B-Instruct-v0.2        |
| [konkani/mistral-7b-instruct-konkani-lora](https://huggingface.co/konkani/mistral-7b-instruct-konkani-lora) | 7.0B         |                    1 |   2026 | togethercomputer/Mistral-7B-Instruct-v0.2 |
| [nischay185/konkani-qwen2-1.5b-v3-full](https://huggingface.co/nischay185/konkani-qwen2-1.5b-v3-full)       | 1.5B         |                    1 |   2026 | Qwen/Qwen2-1.5B                           |

_7 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Konkani.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                | # test items   | construction                                                     |
|:------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                       | 500            | Human translation                                                |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)             | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) | 100            | Native (community-written, peer-verified)                        |
| Machine translation           |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                            | 854            | Human translation via English pivot                              |
| Machine translation           |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           |                                | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                          | —              | Human translation (professional, from English)                   |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Konkani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Konkani? Does it make sense to train one?
  - ~8.9 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~111.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Konkani-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 27 of ~18,498 papers (0.15%) (rank 116 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Goan Konkani | Konkani

Here are up to ten papers published in 2026 that mention Konkani. None of the 27 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                | paper                                                                          | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| Paramanu: Compact and Competitive Monolingual Language Models for Low-Resource Morphologically Rich Indian Languages | [2026.acl-long.1922](https://aclanthology.org/2026.acl-long.1922/)             | body only      |
| BhashaSutra: A Task-Centric Unified Survey of Indian NLP Datasets, Corpora, and Resources                            | [2026.acl-long.551](https://aclanthology.org/2026.acl-long.551/)               | body only      |
| Evaluating Cross-lingual Knowledge Consistency in Code-Mixed vis-a-vis Indian Languages using IndicKLAR              | [2026.findings-emnlp.1655](https://aclanthology.org/2026.findings-emnlp.1655/) | body only      |
| Mining Naturally Romanized Seed Corpora without Romanizations                                                        | [2026.lrec-1.234](https://aclanthology.org/2026.lrec-1.234/)                   | body only      |
| CEFR-Annotated WordNet: LLM-Based Proficiency-Guided Semantic Database for Language Learning                         | [2026.lrec-1.292](https://aclanthology.org/2026.lrec-1.292/)                   | body only      |
| When Words Don’t Mean What They Say: Figurative Understanding in Bengali Idioms                                      | [2026.lrec-1.546](https://aclanthology.org/2026.lrec-1.546/)                   | body only      |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               | body only      |
| An Idiom Benchmark for Turkish                                                                                       | [2026.mwe-1.12](https://aclanthology.org/2026.mwe-1.12/)                       | body only      |
| Dialect Matters: Cross-Lingual ASR Transfer for Low-Resource Indic Language Varieties                                | [2026.vardial-1.12](https://aclanthology.org/2026.vardial-1.12/)               | body only      |
| Konkani Daan: A Community-Driven Culturally Grounded Speech Corpus for Low-Resource ASR                              | [2026.wildre-1.3](https://aclanthology.org/2026.wildre-1.3/)                   | body only      |

{% endraw %}
