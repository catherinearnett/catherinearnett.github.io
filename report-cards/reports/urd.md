---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/urd.html
---
{% raw %}
# So you want to work on Urdu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `urd`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Hindustani ([Glottolog](https://glottolog.org/resource/languoid/id/urdu1245))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Arab`

**Speakers:** about 313.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, Pakistan, South Africa

**Status:** Regional official language; Official language


## What does Urdu look and sound like?

**Written:** Omniglot has [a page on Urdu](https://www.omniglot.com/writing/urdu.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/urd/) has 7 videos of Urdu speakers. Watch [See all](https://wikitongues.org/videos/?language=urd).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                          |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 707,617 articles in ur.wikipedia; 398 active users. This is ~1/11 of English data and ranks 24 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                       |
| Common Crawl           | 690,303 pages per crawl on average, which is 0.0320% of the crawl (2026). This is ~1/1,291 of English data and ranks 44 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                           |
| FineWeb                | 7.07 GB (urd_Arab 6.94 GB; urd_Latn 0.13 GB), equivalent to ≈4.16 GB of English after byte-premium scaling; 3.78 GB removed by filtering. This is ~1/7,556 of English data and ranks 43 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 3.29 GB (urd_Arab 3.29 GB) (rank 52 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                               |

**By writing system:**

| Writing system   | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Arabic (`Arab`)  | 6.94 GB   | — (no byte premium yet)       | 3.29 GB      | 1.92 GB                        |
| Latin (`Latn`)   | 0.13 GB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                            |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 5,130 sentences / 138,077 tokens in total: [UD_Urdu-UDTB](https://github.com/UniversalDependencies/UD_Urdu-UDTB) (5,130 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 182 lemmas, 12,572 inflected forms ([unimorph/urd](https://github.com/unimorph/urd))                                                                                                                                   |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                         |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                      |
| Bible translations (eBible corpus) | **Yes** — 4 translations: full Bible ([urd](https://ebible.org/details.php?id=urd), by-sa 4.0); full Bible ([urdgvh](https://ebible.org/details.php?id=urdgvh), by-nc-nd 4.0); full Bible ([urdgvr](https://ebible.org/details.php?id=urdgvr), by-nc-nd 4.0); full Bible ([urdgvu](https://ebible.org/details.php?id=urdgvu), by-nc-nd 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                   |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=204), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=108), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.965 (P 0.988, R 0.948, FPR 8.67e-05) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.940).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.988 |    0.948 | 0.965 | 0.000 | ✓                |
| commonlingua |       0.954 |    0.932 | 0.940 | 0.001 | ✓                |
| cld2         |       0.885 |    0.970 | 0.914 | 0.002 | ✓                |
| funlangid    |       0.974 |    0.864 | 0.911 | 0.000 | ✓                |
| OpenLID-v2   |       0.868 |    0.983 | 0.909 | 0.002 | ✓                |
| fasttext     |       0.832 |    0.982 | 0.886 | 0.003 | ✓                |
| pyfranc      |       0.823 |    0.909 | 0.851 | 0.002 | ✓                |
| py3langid    |       0.720 |    0.983 | 0.815 | 0.005 | ✓                |
| cld3         |       0.676 |    0.962 | 0.781 | 0.007 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 204 |       0.993 |    0.740 | 0.848 |
| Wikipedia | 300 |       0.986 |    0.957 | 0.971 |
| Tatoeba   | 300 |       0.977 |    0.993 | 0.985 |
| UDHR-LID  | 108 |       0.973 |    1.000 | 0.986 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Urdu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Urdu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Urdu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Urdu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Urdu (and whether the model is exclusively tagged for Urdu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **534** text-generation models are explicitly tagged for Urdu (201 original uploads, 333 fine-tunes/quantisations/merges).
- **54** are tagged *only* for Urdu.
- Including tags inherited from base models: **1,035**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       43 | ███                  |
|   2023 |       36 | ███                  |
|   2024 |       52 | ████                 |
|   2025 |      122 | █████████            |
|   2026 |      281 | ████████████████████ |

### Largest models tagged for Urdu

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                   | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Urdu

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [1-800-LLMs/OSS20B_UR](https://huggingface.co/1-800-LLMs/OSS20B_UR)                                               | 21.5B        |                    1 |   2025 | openai/gpt-oss-20b        |
| [azherali/Riazi-8B-Instruct](https://huggingface.co/azherali/Riazi-8B-Instruct)                                   | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base        |
| [ai4bharat/hercule-ur](https://huggingface.co/ai4bharat/hercule-ur)                                               | 8.0B         |                    1 |   2024 | meta-llama/Llama-3.1-8B   |
| [mahwizzzz/Qalb-1.0-8B-DPO](https://huggingface.co/mahwizzzz/Qalb-1.0-8B-DPO)                                     | 8.0B         |                    1 |   2026 | unsloth/Meta-Llama-3.1-8B |
| [Khurram123/Qwen-Urdu-Shaheen-7B-Instruct-v1](https://huggingface.co/Khurram123/Qwen-Urdu-Shaheen-7B-Instruct-v1) | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B           |

_87 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Urdu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 8 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 8 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">3 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                                                 | # test items   | construction                                                        |
|:------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | UrBLiMP                                                                                                                 | 5,696          | Treebank/corpus-extracted + manual perturbation                     |
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 60             | Treebank-based (automatic)                                          |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 550            | Treebank-based (automatic, UD + UniMorph)                           |
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        | 500            | Human translation                                                   |
| 3. Commonsense reasoning      | COPA                           | [Owos/xcopa](https://huggingface.co/datasets/Owos/xcopa)                                                                | 500            | Machine translation (Google)                                        |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                             |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (2 varieties/pairs)                                       | 1,800          | Human translation (professional)                                    |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                           | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                            |
| Machine translation           |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (2 varieties/pairs)                                         | 1,708          | Human translation via English pivot                                 |
| Machine translation           |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                                 | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)                      |
| Machine translation           |                                | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                           | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                          | —              | Human translation (professional, from English)                      |
| Machine translation           |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 1,663          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation           |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                               | 998            | Human translation (professional) + post-edits                       |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Urdu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Urdu? Does it make sense to train one?
  - ~4.16 GB English-equivalent text ≈ 1.04B tokens, enough for a compute-optimal model of ~52.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Urdu-only model is 21.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 287 of ~18,498 papers (1.55%) (rank 27 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Urdu

Here are up to ten papers published in 2026 that mention Urdu. None of the 287 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                | paper                                                                      | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| A Stylometric and Statistical Pipeline for Urdu AI-Generated Text Classification                                                     | [2026.abjadnlp-1.58](https://aclanthology.org/2026.abjadnlp-1.58/)         | body only      |
| AbjadStyleTransfer: Authorship Style Transfer for Arabic-Script Languages at AbjadNLP 2026                                           | [2026.abjadnlp-1.70](https://aclanthology.org/2026.abjadnlp-1.70/)         | body only      |
| IndicMedDialog: A Parallel Multi-Turn Medical Dialogue Dataset for Accessible Healthcare in Indic Languages                          | [2026.bionlp-1.84](https://aclanthology.org/2026.bionlp-1.84/)             | body only      |
| Cross-Domain Evaluation of Transformer-Based Models for Punjabi Speech Emotion Recognition                                           | [2026.chipsal-1.7](https://aclanthology.org/2026.chipsal-1.7/)             | body only      |
| Camellia: Benchmarking Cultural Biases in LLMs for Asian Languages                                                                   | [2026.emnlp-main.783](https://aclanthology.org/2026.emnlp-main.783/)       | body only      |
| Indic-CodecFake meets SATYAM: Towards Detecting Neural Audio Codec Synthesized Speech Deepfakes in Indic Languages                   | [2026.findings-acl.2159](https://aclanthology.org/2026.findings-acl.2159/) | body only      |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                                            | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)               | body only      |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                                 | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)               | body only      |
| ShahiEmotion: A Benchmark Dataset for Punjabi Shahmukhi Emotion Detection                                                            | [2026.mellm-1.20](https://aclanthology.org/2026.mellm-1.20/)               | body only      |
| PingAn-NLP at SemEval-2026 Task 9: Multi-Stage Alignment via GRPO and Tiered Ensemble Voting for Multilingual Polarization Detection | [2026.semeval-1.354](https://aclanthology.org/2026.semeval-1.354/)         | body only      |

{% endraw %}
