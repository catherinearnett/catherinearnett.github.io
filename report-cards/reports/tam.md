---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tam.html
---
{% raw %}
# So you want to work on Tamil?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tam`

**Language family:** **Dravidian** › South Dravidian › South Dravidian I › … › Tamil-Paliyan ([Glottolog](https://glottolog.org/resource/languoid/id/tami1289))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Taml`

**Speakers:** about 90.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, Singapore, South Africa, Sri Lanka

**Status:** Regional official language; Official language; Official and national language


## What does Tamil look and sound like?

**Written:** Omniglot has [a page on Tamil](https://www.omniglot.com/writing/tamil.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tam/) has 7 videos of Tamil speakers. Watch [See all](https://wikitongues.org/videos/?language=tam).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 191,848 articles in ta.wikipedia; 446 active users. This is ~1/39 of English data and ranks 46 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                |
| Common Crawl           | 1,009,629 pages per crawl on average, which is 0.0468% of the crawl (2026). This is ~1/883 of English data and ranks 36 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                                                                                                                                    |
| FineWeb                | 9.52 GB (tam_Taml 9.51 GB; tam_Latn 10.0 MB), equivalent to ≈3.48 GB of English after byte-premium scaling (⚠️ only 100% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 9.94 GB removed by filtering. This is ~1/5,609 of English data and ranks 41 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.03 GB (tam_Taml 9.03 GB) (rank 17 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                        |

**By writing system:**

| Writing system   | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Tamil (`Taml`)   | 9.51 GB   | 3.48 GB                       | 9.03 GB      | 3.31 GB                        |
| Latin (`Latn`)   | 10.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 1,134 sentences / 11,171 tokens in total: [UD_Tamil-MWTT](https://github.com/UniversalDependencies/UD_Tamil-MWTT) (534 sentences), [UD_Tamil-TTB](https://github.com/UniversalDependencies/UD_Tamil-TTB) (600 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                  |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                  |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY; [Tamil WordNet](http://www.au-kbc.org/research_areas/nlp/projects/tamil_wordnet.html) (size not listed); licence: OPEN.                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                            |
|:-----------------------------------|:-------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([tam2017](https://ebible.org/details.php?id=tam2017), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                             |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=81), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=69), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.999 (P 0.999, R 0.999, FPR 4.63e-06) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.998).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.999 |    0.999 | 0.999 | 0.000 | ✓                |
| cld2         |       0.998 |    0.999 | 0.998 | 0.000 | ✓                |
| py3langid    |       0.997 |    0.999 | 0.998 | 0.000 | ✓                |
| GlotLID      |       0.998 |    0.995 | 0.997 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.989 | 0.993 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.986 | 0.993 | 0.000 | ✓                |
| cld3         |       1.000 |    0.984 | 0.992 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.953 | 0.975 | 0.000 | ✗                |
| funlangid    |       0.982 |    0.930 | 0.954 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.993 | 0.995 |
| CommonLID |  81 |       1.000 |    1.000 | 1.000 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  69 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tamil to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tamil *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tamil and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tamil has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Tamil?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tamil (and whether the model is exclusively tagged for Tamil or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **763** text-generation models are explicitly tagged for Tamil (250 original uploads, 513 fine-tunes/quantisations/merges).
- **63** are tagged *only* for Tamil.
- Including tags inherited from base models: **1,302**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       45 | ███                  |
|   2023 |       45 | ███                  |
|   2024 |      102 | ██████               |
|   2025 |      222 | █████████████        |
|   2026 |      349 | ████████████████████ |

### Largest models tagged for Tamil

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [newzyerror/fluidity-vapour-4.1](https://huggingface.co/newzyerror/fluidity-vapour-4.1)               | 753.3B       |                    4 |   2026 | fluidity-vapour-4.1                    |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                 | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Tamil

| model                                                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [1-800-LLMs/OSS20B_TA](https://huggingface.co/1-800-LLMs/OSS20B_TA)                                                                                                           | 21.5B        |                    1 |   2025 | openai/gpt-oss-20b      |
| [akdiwahar/KavithaSaaram-9b-it](https://huggingface.co/akdiwahar/KavithaSaaram-9b-it)                                                                                         | 9.2B         |                    1 |   2025 | google/gemma-2-9b       |
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-ta-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-ta-madlad-mean-slerp0305-emb)             | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [Hemanth-thunder/tamil-llama3-8B-open-instruct-v1-SFT-test](https://huggingface.co/Hemanth-thunder/tamil-llama3-8B-open-instruct-v1-SFT-test)                                 | 8.0B         |                    1 |   2024 | —                       |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-ta-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-ta-madlad-mean-slerp0305-emb-special) | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B         |

_102 tagged models have unknown parameter counts and are not ranked by size._

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

**29** benchmark datasets in the survey include Tamil.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 5 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 8 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 5 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 8 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                        |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [LINDSEA (SEA-HELM)](https://github.com/aisingapore/BHASA)                                                              | 200            | Hand-written (expert)                                               |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 382            | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                                  | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated)              | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                                             | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 8,413          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                                | 10,059         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)                                   | 1,804          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | [chaii](https://www.kaggle.com/c/chaii-hindi-and-tamil-question-answering)                                              | 368            | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                           | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                                  | 6,372          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  | 100            | Native (community-written, peer-verified)                           |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (2 varieties/pairs)                                         | 1,708          | Human translation via English pivot                                 |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                                 | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    |                                | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                           | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                          | —              | Human translation (professional, from English)                      |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 356            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                               | 998            | Human translation (professional) + post-edits                       |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tamil datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tamil? Does it make sense to train one?
  - ~3.48 GB English-equivalent text ≈ 0.87B tokens, enough for a compute-optimal model of ~43.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tamil-only model is 21.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 340 of ~18,498 papers (1.84%) (rank 20 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tamil

Here are up to ten papers published in 2026 that mention Tamil. None of the 340 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                    | paper                                                                                | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------|:---------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                                    | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)                   | body only      |
| ByteBuilders@DravidianLangTech 2026: Transformer-Based Weighted Ensemble for Political Multiclass Sentiment Analysis of Tamil X (Twitter) Comments       | [2026.dravidianlangtech-1.20](https://aclanthology.org/2026.dravidianlangtech-1.20/) | body only      |
| Dialectmind@DravidianLang Tech 2026: Zero-Shot Dialectal Tamil Automatic Speech Recognition Using a Large Pretrained Conformer Model                     | [2026.dravidianlangtech-1.32](https://aclanthology.org/2026.dravidianlangtech-1.32/) | body only      |
| M4FC: a Multimodal, Multilingual, Multicultural, Multitask Real-World Fact-Checking Dataset                                                              | [2026.findings-emnlp.42](https://aclanthology.org/2026.findings-emnlp.42/)           | body only      |
| BanglaLlama: LLaMA for Bangla Language                                                                                                                   | [2026.loreslm-1.7](https://aclanthology.org/2026.loreslm-1.7/)                       | body only      |
| NEUNI@LT-EDI 2026: Counter Narrative Generation on Homophobic and Transphobic Comments                                                                   | [2026.ltedi-1.24](https://aclanthology.org/2026.ltedi-1.24/)                         | body only      |
| Dual-Axis Compositional Contrastive Few-Shot Learning using Prototypes Across Linguistic and Semantic Dimensions for Indic Low-Resource Multilingual NLU | [2026.ltedi-1.3](https://aclanthology.org/2026.ltedi-1.3/)                           | body only      |
| Polyglot-Lion: Efficient Multilingual ASR for Singapore via Balanced Fine-Tuning of Qwen3-ASR                                                            | [2026.mellm-1.18](https://aclanthology.org/2026.mellm-1.18/)                         | body only      |
| CPS Lab 1@MMLow 2026: Hierarchical Multimodal Classification of Tamil Political Memes via Logit-Conditioned Stance-Target Prediction                     | [2026.mmlow-main.11](https://aclanthology.org/2026.mmlow-main.11/)                   | body only      |
| PlurVA-LLM-2026 Shared Task Track-1: Curriculum Fine-Tuning with Soft Labels and Positional Consistency for Cross-Cultural Value Alignment               | [2026.plurvallm-1.14](https://aclanthology.org/2026.plurvallm-1.14/)                 | body only      |

{% endraw %}
