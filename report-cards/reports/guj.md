---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/guj.html
---
{% raw %}
# So you want to work on Gujarati?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `guj`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Gujaratic ([Glottolog](https://glottolog.org/resource/languoid/id/guja1252))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Gujr`

**Speakers:** about 65.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, South Africa

**Status:** Regional official language; Official language


## What does Gujarati look and sound like?

**Written:** Omniglot has [a page on Gujarati](https://www.omniglot.com/writing/gujarati.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/guj/) has 3 videos of Gujarati speakers. Watch [Sanjay speaking Gujarati](https://wikitongues.org/videos/sanjay_20200711_guj/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                     |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 30,937 articles in gu.wikipedia; 101 active users. This is ~1/244 of English data and ranks 76 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                  |
| Common Crawl           | 271,347 pages per crawl on average, which is 0.0126% of the crawl (2026). This is ~1/3,285 of English data and ranks 51 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                      |
| FineWeb                | 3.37 GB (guj_Gujr 3.37 GB; guj_Latn 0), equivalent to ≈1.56 GB of English after byte-premium scaling; 2.19 GB removed by filtering. This is ~1/15,840 of English data and ranks 57 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 5.49 GB (guj_Gujr 5.49 GB) (rank 36 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                          |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Gujarati (`Gujr`) | 3.37 GB   | 1.56 GB                       | 5.49 GB      | 2.54 GB                        |
| Latin (`Latn`)    | 0         | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 225 sentences / 2,187 tokens in total: [UD_Gujarati-GujTB](https://github.com/UniversalDependencies/UD_Gujarati-GujTB) (187 sentences), [UD_Gujarati-ShabdaSetu](https://github.com/UniversalDependencies/UD_Gujarati-ShabdaSetu) (38 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 397 lemmas, 7,505 inflected forms ([unimorph/guj](https://github.com/unimorph/guj))                                                                                                                                                                                                                                                     |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                          |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                        |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([guj2017](https://ebible.org/details.php?id=guj2017), by-sa 4.0).                                                                                                         |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Gujr script) — the same sentences in 200+ languages                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Gujr script) — paired with English                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_gu) en → gu: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_gu) en → gu: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=168), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.997 (P 1.000, R 0.993, FPR 0.00e+00) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.995).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       1.000 |    0.993 | 0.997 | 0.000 | ✓                |
| cld2         |       0.999 |    0.992 | 0.995 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| GlotLID      |       0.995 |    0.991 | 0.993 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.986 | 0.992 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.985 | 0.992 | 0.000 | ✓                |
| cld3         |       1.000 |    0.974 | 0.986 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.954 | 0.975 | 0.000 | ✗                |
| funlangid    |       0.924 |    0.555 | 0.691 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.967 | 0.983 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 168 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Gujarati to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Gujarati *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Gujarati and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Gujarati?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Gujarati (and whether the model is exclusively tagged for Gujarati or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **513** text-generation models are explicitly tagged for Gujarati (180 original uploads, 333 fine-tunes/quantisations/merges).
- **43** are tagged *only* for Gujarati.
- Including tags inherited from base models: **865**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███                  |
|   2023 |       27 | ██                   |
|   2024 |       69 | ██████               |
|   2025 |      155 | ██████████████       |
|   2026 |      226 | ████████████████████ |

### Largest models tagged for Gujarati

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Gujarati

| model                                                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-gu-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-gu-madlad-mean-slerp0305-emb)             | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-gu-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-gu-madlad-mean-slerp0305-emb-special) | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B         |
| [alphaedge-ai/Qwen3.5-4B-guj-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-guj-32768)                                                                                 | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |
| [alphaedge-ai/gemma-3-4b-it-guj-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-guj-32768)                                                                           | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [alphaedge-ai/Qwen3.5-2B-guj-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-guj-32768)                                                                                 | 1.8B         |                    1 |   2026 | Qwen3.5-2B              |

_56 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Gujarati.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | construction                                                     |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 7              | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                          |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 8,803          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 11,144         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                              | —              | Machine translation (from MMLU-Pro)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 4,827          | Native (Indian exams; some translated)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                        |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 154            | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

Gujarati has been part of the WMT translation task in **1** year (2019).

| Test set                                                                                            | Direction(s)                           | Size                          | Human reference   |
|:----------------------------------------------------------------------------------------------------|:---------------------------------------|:------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)              | 2,009 sentences (Gujr)        | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages)      | 1,358 sentences (Gujr)        | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-gu_IN)                           | en → gu_IN                             | 998 segments                  | ✅                |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                                                | English → Gujarati; Gujarati → English | 998 segments / 1,016 segments | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_gu) (training data)   | en → gu                                | size not listed               | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_gu) (training data) | en → gu                                | size not listed               | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Gujarati datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Gujarati? Does it make sense to train one?
  - ~2.54 GB English-equivalent text ≈ 0.64B tokens, enough for a compute-optimal model of ~31.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Gujarati-only model is 8.1B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 100 of ~18,498 papers (0.54%) (rank 60 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Gujarati

Here are up to ten papers published in 2026 that mention Gujarati. None of the 100 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                   | paper                                                                          | mentioned in   |
|:------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| A Multilingual Evaluation of LLM-Based High-School Mathematics Assistance Across Indian Languages                       | [2026.aacl-short.14](https://aclanthology.org/2026.aacl-short.14/)             | body only      |
| IndicDISCO-MT: A Discourse-Centric Benchmark for Evaluating Discourse Phenomena in Indian Language Machine Translation  | [2026.eamt-1.15](https://aclanthology.org/2026.eamt-1.15/)                     | body only      |
| Response-Aware User Memory Selection for LLM Personalization                                                            | [2026.emnlp-main.185](https://aclanthology.org/2026.emnlp-main.185/)           | body only      |
| Lost in Localization: Benchmarking Intralingual Cultural Adaptation in Large Language Models                            | [2026.findings-emnlp.1658](https://aclanthology.org/2026.findings-emnlp.1658/) | body only      |
| The Geometry of LLM-as-Judge: Why Inter-LLM Consensus Is Not Human Alignment                                            | [2026.findings-emnlp.1696](https://aclanthology.org/2026.findings-emnlp.1696/) | body only      |
| Contextualizing Toxicity: An Annotation Framework for Unveiling Pragmatics in Conversations of Online Discussion Forums | [2026.lrec-1.314](https://aclanthology.org/2026.lrec-1.314/)                   | body only      |
| The Riddle of Reflection: Evaluating Reasoning and Self-Awareness in Multilingual LLMs Using Indian Riddles             | [2026.lrec-1.430](https://aclanthology.org/2026.lrec-1.430/)                   | body only      |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                   | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               | body only      |
| Indic-TunedLens: Interpreting Multilingual Models in Indian Languages                                                   | [2026.vardial-1.14](https://aclanthology.org/2026.vardial-1.14/)               | body only      |
| Konkani Wordnet Resources                                                                                               | [2026.wildre-1.6](https://aclanthology.org/2026.wildre-1.6/)                   | body only      |

{% endraw %}
