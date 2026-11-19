---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nya.html
---
{% raw %}
# So you want to work on Chewa?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nya`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Nyanjaic ([Glottolog](https://glottolog.org/resource/languoid/id/nyan1308))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 18.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Zimbabwe

**Status:** Official language


## What does Chewa look and sound like?

**Written:** no Omniglot page found for Chewa.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/nya/) has 3 videos of Chewa speakers. Watch [Chabota speaking Simplified Nyanja](https://wikitongues.org/videos/chabota_20180728_nya/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,161 articles in ny.wikipedia; 14 active users. This is ~1/6,500 of English data and ranks 153 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 17,025 pages per crawl on average, which is 0.0008% of the crawl (2026). This is ~1/52,365 of English data and ranks 92 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 0.17 GB (nya_Latn 0.17 GB), equivalent to ≈0.14 GB of English after byte-premium scaling; 0.26 GB removed by filtering. This is ~1/315,828 of English data and ranks 99 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.58 GB (nya_Latn 0.58 GB) (rank 87 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                         |
|:-----------------------|:------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                      |
| UniMorph               | 227 lemmas, 4,370 inflected forms ([unimorph/nya](https://github.com/unimorph/nya)) |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._      |
| Wordnets               | **None found**                                                                      |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                        |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([nya](https://ebible.org/details.php?id=nya), by-sa 4.0).                                                                                                                 |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                            |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ny) en → ny: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ny) en → ny: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=42), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.957 (P 0.955, R 0.958, FPR 7.69e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.908).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.955 |    0.958 | 0.957 | 0.000 | ✓                |
| OpenLID-v2   |       0.855 |    0.979 | 0.908 | 0.002 | ✓                |
| cld2         |       0.876 |    0.930 | 0.898 | 0.002 | ✓                |
| fasttext     |       0.878 |    0.860 | 0.862 | 0.001 | ✓                |
| AfroLID      |       0.973 |    0.764 | 0.846 | 0.000 | ✓                |
| funlangid    |       0.864 |    0.758 | 0.805 | 0.000 | ✓                |
| pyfranc      |       0.852 |    0.748 | 0.793 | 0.001 | ✓                |
| commonlingua |       0.716 |    0.782 | 0.734 | 0.003 | ✓                |
| cld3         |       0.405 |    0.958 | 0.544 | 0.032 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  42 |       0.750 |    0.786 | 0.767 |
| Wikipedia | 300 |       0.993 |    0.967 | 0.980 |
| UDHR-LID  | 116 |       0.991 |    1.000 | 0.996 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chewa to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Chewa *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chewa and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Chewa has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Chewa?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chewa (and whether the model is exclusively tagged for Chewa or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **199** text-generation models are explicitly tagged for Chewa (91 original uploads, 108 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Chewa.
- Including tags inherited from base models: **363**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████████          |
|   2023 |       24 | ████████             |
|   2024 |       35 | ███████████          |
|   2025 |       40 | ████████████         |
|   2026 |       64 | ████████████████████ |

### Largest models tagged for Chewa

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Chewa

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-nya-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-nya](https://huggingface.co/ptrdvn/kakugo-3B-nya)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-nya-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-nya-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-nya-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Chewa.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                              |   # test items | construction                                   |
|:------------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          2,751 | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                |         14,042 | Machine translation (Google Translate)         |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             23 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ny) (training data)   | en → ny                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ny) (training data) | en → ny                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chewa datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chewa? Does it make sense to train one?
  - ~0.48 GB English-equivalent text ≈ 0.12B tokens, enough for a compute-optimal model of ~6.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Chewa-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 17 of ~18,498 papers (0.09%) (rank 131 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nyanja | Chewa

Here are up to ten papers published in 2026 that mention Chewa. None of the 17 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                             | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)         |
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages                | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)           |
| Safety of Large Language Models Beyond English: A Systematic Literature Review of Risks, Biases, and Safeguards       | [2026.eacl-long.44](https://aclanthology.org/2026.eacl-long.44/)           |
| TranslatePsy-AfriSLM: High-Quality Data Scaling For Low-Resource Machine Translation                                  | [2026.emnlp-main.1686](https://aclanthology.org/2026.emnlp-main.1686/)     |
| Text4Speech: Text-Driven Training for Massively Multilingual Speech Understanding                                     | [2026.emnlp-main.2427](https://aclanthology.org/2026.emnlp-main.2427/)     |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| TukaBench: A Culturally Grounded Jailbreak Benchmark for African Languages                                            | [2026.emnlp-main.692](https://aclanthology.org/2026.emnlp-main.692/)       |
| UbuntuGuard: A Culturally-Grounded Policy Benchmark for Equitable AI Safety in African Languages.                     | [2026.findings-acl.1663](https://aclanthology.org/2026.findings-acl.1663/) |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                            | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| RunyaNER: Auxiliary Language Selection for Runyankore NER                                                             | [2026.mrl-1.38](https://aclanthology.org/2026.mrl-1.38/)                   |

{% endraw %}
