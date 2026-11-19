---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sat.html
---
{% raw %}
# So you want to work on Santali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sat`

**Language family:** **Austroasiatic** › Mundaic › North Munda › … › Santalic ([Glottolog](https://glottolog.org/resource/languoid/id/sant1410))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Olck`

**Speakers:** about 7.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India

**Status:** Regional official language


## What does Santali look and sound like?

**Written (Devanagari alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/santali.htm):

> जत लेकान मोन आर अधिकार रेयाक आधार रे मुचोत धाबिच स्वतन्त्र आर सुमान को हुयुकआ। उनको हो बुद्धि आर बुझहौ को आगु तोरा बाका दानेच आर मिक हड आर दोसार हड र आप्नार रेयाक व्यवहार हुयुक जोरुडा।

**Written (Bengali alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/santali.htm):

> জত লেকান মোন আর ধiকার রেযাক আধার রে মুচোত ধাবiচ সৱতনতর আর সুমান কো হুযুকআ। উনকো হো বুদধi আর বুছহৌ কো আগু তোরা বাকা দানেচ আর মiক হড আর দোসার হড র আপনার রেযাক ৱযৱহার হুযুক জোরুডা।

**Written (Odia alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/santali.htm):

> ଜତ ଲେକାନ ମୋନ ଆର ଅଧିକାର ରେଯାକ ଆଧାର ରେ ମୁଚୋତ ଧାବିଚ ସୱତନତର ଆର ସୁମାନ କୋ ହୁଯୁକଆ। ଉନକୋ ହୋ ବୁଦଧି ଆର ବୁଝହୌ କୋ ଆଗୁ ତୋରା ବାକା ଦାନେଚ ଆର ମିକ ହଡ ଆର ଦୋସାର ହଡ ର ଆପନାର ରେଯାକ ୱଯୱହାର ହୁଯୁକ ଜୋରୁଡା।

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/sat/) has 2 videos of Santali speakers. Watch [Sathi speaking Santhali](https://wikitongues.org/videos/sathi_20181003_sat/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 16,112 articles in sat.wikipedia; 36 active users. This is ~1/468 of English data and ranks 87 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                    |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                     |
| FineWeb                | 3.3 MB (sat_Olck 3.0 MB; sat_Latn 0), equivalent to ≈1.3 MB of English after byte-premium scaling; 16.0 MB removed by filtering. This is ~1/16,388,740 of English data and ranks 178 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 26.0 MB (sat_Olck 26.0 MB) (rank 147 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                           |

**By writing system:**

| Writing system    | FineWeb                        | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:-------------------------------|:------------------------------|:-------------|:-------------------------------|
| Ol Chiki (`Olck`) | 2.9 MB (+14.3 MB filtered out) | 1.0 MB                        | 26.0 MB      | 9.3 MB                         |
| Latin (`Latn`)    | 0.4 MB (+1.7 MB filtered out)  | 0.3 MB                        | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                              |
|:-----------------------|:-----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                           |
| UniMorph               | **None found**                                                                           |
| Wikidata labels        | 324,899 Wikidata items have a label in Santali. (Wikidata codes (labels): sat (324,899)) |
| Wordnets               | **None found**                                                                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 99,077 sentence pairs with English across 4 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (78,625), [wikimedia](https://opus.nlpl.eu/wikimedia) (16,441), [translatewiki](https://opus.nlpl.eu/translatewiki) (3,722), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (289).                                                                                                                                                                                |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                                                                |
| Tatoeba                                                                                  | 6,331 sentences, 5,650 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/sat/none)).                                                                                                                                                                                                                                                                                                                                      |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Olck script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Olck script) — paired with English                                                                                                                                                                                                                                                                                                                                                                                                        |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sat) en → sat: size not listed; [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sat-Latn) en → sat-Latn: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sat) en → sat: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sat-Latn) en → sat-Latn: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid.
- **Eval datasets (4):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 1.000, R 0.985, FPR 0.00e+00) averaged over 4 dataset(s). Runner-up: commonlingua (F1 0.991).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.985 | 0.992 | 0.000 | ✓                |
| commonlingua |       0.998 |    0.985 | 0.991 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.978 | 0.989 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.978 | 0.989 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.962 | 0.981 | 0.000 | ✗                |
| funlangid    |       0.969 |    0.954 | 0.961 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.940 | 0.969 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Santali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Santali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Santali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Santali has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Santali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Santali (and whether the model is exclusively tagged for Santali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **56** text-generation models are explicitly tagged for Santali (41 original uploads, 15 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Santali.
- Including tags inherited from base models: **90**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        2 | █                    |
|   2025 |        1 | █                    |
|   2026 |       53 | ████████████████████ |

### Largest models tagged for Santali

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |
| [chinmaykumar-vyas/sarvam-105b](https://huggingface.co/chinmaykumar-vyas/sarvam-105b)       | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Models tagged *only* for Santali

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/sat_olck_5mb](https://huggingface.co/goldfish-models/sat_olck_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/sat_olck_full](https://huggingface.co/goldfish-models/sat_olck_full) |                    1 |   2024 | —               |

_3 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Santali.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | COPA               | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                     |            500 | Human translation                             |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            196 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                                  | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                   | multi-way (all languages)         | 2,009 sentences (Olck) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                               | ↔ English (and 8 pivot languages) | 1,358 sentences (Olck) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sat) (training data)        | en → sat                          | size not listed        | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sat-Latn) (training data)   | en → sat-Latn                     | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sat) (training data)      | en → sat                          | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sat-Latn) (training data) | en → sat-Latn                     | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Santali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Santali? Does it make sense to train one?
  - ~9.3 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~115.9K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 106.1B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 18 of ~18,498 papers (0.10%) (rank 129 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Santali

Here are up to ten papers published in 2026 that mention Santali. None of the 18 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Combining Distantly Supervised Models with In Context Learning for Monolingual and Cross-Lingual Relation Extraction                          | [2026.acl-long.2109](https://aclanthology.org/2026.acl-long.2109/)         |
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                                                            | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)         |
| Script Is Not Preprocessing: Tokenizer-Mediated Transfer in Endangered Language Machine Translation                                           | [2026.emnlp-main.1715](https://aclanthology.org/2026.emnlp-main.1715/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Stable Scores, Failed Retrieval: Diagnosing RAG Evaluation in Low-Resource Indic Languages                                                    | [2026.groundlm-1.48](https://aclanthology.org/2026.groundlm-1.48/)         |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                      | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)               |
| ADI-IITP: Reward-Guided Preference Optimization for Low-Resource English-Assamese Machine Translation                                         | [2026.wmt-main.146](https://aclanthology.org/2026.wmt-main.146/)           |
| EROL: Transformer-Based Multilingual Translation for Northeastern Indian Language Pairs                                                       | [2026.wmt-main.148](https://aclanthology.org/2026.wmt-main.148/)           |

{% endraw %}
