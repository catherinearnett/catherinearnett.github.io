---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pan.html
---
{% raw %}
# So you want to work on Punjabi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pan`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Eastern Panjabic ([Glottolog](https://glottolog.org/resource/languoid/id/panj1256))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Guru`

**Speakers:** about 219.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India

**Status:** Regional official language


## What does Punjabi look and sound like?

**Written:** Omniglot has [a page on Punjabi](https://www.omniglot.com/writing/punjabi.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/pan/) has 3 videos of Punjabi speakers. Watch [Randeep speaking Powadhi Punjabi](https://wikitongues.org/videos/randeep_20160419_pan/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 59,762 articles in pa.wikipedia; 145 active users. This is ~1/126 of English data and ranks 69 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                |
| Common Crawl           | 191,376 pages per crawl on average, which is 0.0089% of the crawl (2026). This is ~1/4,658 of English data and ranks 57 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                                                                                                                                    |
| FineWeb                | 1.61 GB (pan_Guru 1.59 GB; pan_Latn 10.0 MB), equivalent to ≈0.72 GB of English after byte-premium scaling (⚠️ only 99% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 2.02 GB removed by filtering. This is ~1/33,256 of English data and ranks 65 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 5.60 GB (pan_Guru 5.60 GB) (rank 35 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                        |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Gurmukhi (`Guru`) | 1.59 GB   | 0.72 GB                       | 5.60 GB      | 2.52 GB                        |
| Latin (`Latn`)    | 10.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                   |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 493 sentences / 8,428 tokens in total: [UD_Punjabi-CS](https://github.com/UniversalDependencies/UD_Punjabi-CS) (113 sentences), [UD_Punjabi-DYZ](https://github.com/UniversalDependencies/UD_Punjabi-DYZ) (243 sentences), [UD_Punjabi-Rang](https://github.com/UniversalDependencies/UD_Punjabi-Rang) (137 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                                                                                                                                                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                                            |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([pan](https://ebible.org/details.php?id=pan), by-sa 4.0).                                                                                                                                                                                                                                                                                                                                                     |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Guru script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                               |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Guru script) — paired with English                                                                                                                                                                                                                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pa-Arab) en → pa-Arab: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_pa) en → pa: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pa) en → pa: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pa-Arab) en → pa-Arab: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=217), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.998 (P 1.000, R 0.996, FPR 0.00e+00) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.997).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       1.000 |    0.996 | 0.998 | 0.000 | ✓                |
| cld2         |       0.999 |    0.994 | 0.997 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.994 | 0.997 | 0.000 | ✓                |
| GlotLID      |       0.997 |    0.994 | 0.995 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.990 | 0.995 | 0.000 | ✓                |
| commonlingua |       0.990 |    0.996 | 0.993 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.976 | 0.988 | 0.000 | ✗                |
| cld3         |       1.000 |    0.976 | 0.988 | 0.000 | ✓                |
| funlangid    |       0.880 |    0.949 | 0.903 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.987 | 0.993 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| Tatoeba   | 217 |       1.000 |    0.995 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Punjabi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Punjabi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Punjabi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Punjabi has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Punjabi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Punjabi (and whether the model is exclusively tagged for Punjabi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **466** text-generation models are explicitly tagged for Punjabi (177 original uploads, 289 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Punjabi.
- Including tags inherited from base models: **818**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███                  |
|   2023 |       27 | ███                  |
|   2024 |       52 | █████                |
|   2025 |      144 | ██████████████       |
|   2026 |      207 | ████████████████████ |

### Largest models tagged for Punjabi

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                 | 176.2B       |                   37 |   2026 | —                                      |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                                 | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Punjabi

| model                                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [mahnoornaeem47/Llama-3.1-8B-Punjabi-Shahmukhi-QA-adapter](https://huggingface.co/mahnoornaeem47/Llama-3.1-8B-Punjabi-Shahmukhi-QA-adapter) | 8.0B         |                    1 |   2026 | meta-llama/Llama-3.1-8B       |
| [alphaedge-ai/Qwen3.5-4B-pan-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-pan-32768)                                               | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-pan-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-pan-32768)                                         | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-pan](https://huggingface.co/ptrdvn/kakugo-3B-pan)                                                                         | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [amanpreetsingh459/gemma-2-2b-it-punjabi-finetuned](https://huggingface.co/amanpreetsingh459/gemma-2-2b-it-punjabi-finetuned)               | 2.6B         |                    1 |   2024 | google/gemma-2-2b             |

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

**18** benchmark datasets in the survey include Punjabi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 5 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 5 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | construction                                                     |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                          | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                |
| 3. Commonsense reasoning      | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                            | 11,420         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension      | QA – extractive RC            | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)               | 1,542          | Native                                                           |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | IndicMMLU-Pro                                                                                       | —              | Machine translation (from MMLU-Pro)                              |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                              | 4,099          | Native (Indian exams; some translated)                           |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 87             | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

| Test set                                                                                                 | Direction(s)                      | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                  | multi-way (all languages)         | 2,009 sentences (Guru) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                              | ↔ English (and 8 pivot languages) | 1,358 sentences (Guru) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-pa_IN)                                | en → pa_IN                        | 998 segments           | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pa-Arab) (training data)   | en → pa-Arab                      | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_pa) (training data)        | en → pa                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pa) (training data)      | en → pa                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_pa-Arab) (training data) | en → pa-Arab                      | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Punjabi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Punjabi? Does it make sense to train one?
  - ~2.52 GB English-equivalent text ≈ 0.63B tokens, enough for a compute-optimal model of ~31.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Punjabi-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 110 of ~18,498 papers (0.59%) (rank 55 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Punjabi

Here are up to ten papers published in 2026 that mention Punjabi. None of the 110 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                                                  | paper                                                                        | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|:---------------|
| Framing Political Bias in Multilingual LLMs Across Pakistani Languages                                                                                                                 | [2026.acl-long.1689](https://aclanthology.org/2026.acl-long.1689/)           | body only      |
| Crosslingual Disparities in LLM Performance: Challenges for MT as Mitigation                                                                                                           | [2026.amta-research.9](https://aclanthology.org/2026.amta-research.9/)       | body only      |
| Cross-Domain Evaluation of Transformer-Based Models for Punjabi Speech Emotion Recognition                                                                                             | [2026.chipsal-1.7](https://aclanthology.org/2026.chipsal-1.7/)               | body only      |
| Script Gap: Evaluating LLM Triage on Indian Languages in Native vs Romanized Scripts in a Real-World Setting                                                                           | [2026.emnlp-industry.144](https://aclanthology.org/2026.emnlp-industry.144/) | body only      |
| ALEE: Any-Language Evaluation of Embeddings via English-Centric Minimal Pairs                                                                                                          | [2026.emnlp-main.63](https://aclanthology.org/2026.emnlp-main.63/)           | body only      |
| VGU-M.Tech-AI at SemEval-2026: Multilingual Multi-Label Classification of Online Polarization Types via Weighted Transformer Fine-Tuning and Adaptive Per-Label Threshold Optimization | [2026.semeval-1.183](https://aclanthology.org/2026.semeval-1.183/)           | body only      |
| PingAn-NLP at SemEval-2026 Task 9: Multi-Stage Alignment via GRPO and Tiered Ensemble Voting for Multilingual Polarization Detection                                                   | [2026.semeval-1.354](https://aclanthology.org/2026.semeval-1.354/)           | body only      |
| Sagarmatha at SemEval-2026 Task 9: Heterogeneous Ensembling and Hierarchical Task Conditioning for Multilingual Latent Distributional Divergence Modeling                              | [2026.semeval-1.382](https://aclanthology.org/2026.semeval-1.382/)           | body only      |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                                                               | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)                 | body only      |
| North Small Translate: Advanced Cost-Effective Translation (Cohere CAT+)                                                                                                               | [2026.wmt-main.70](https://aclanthology.org/2026.wmt-main.70/)               | body only      |

{% endraw %}
