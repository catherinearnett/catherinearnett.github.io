---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ron.html
---
{% raw %}
# So you want to work on Romanian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ron`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Eastern Romanian ([Glottolog](https://glottolog.org/resource/languoid/id/roma1327))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 20.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Moldova, Romania

**Status:** Official and national language; Official language


## What does Romanian look and sound like?

**Written (Romanian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/romanian.htm):

> Toate ființele umane se nasc libere și egale în demnitate și în drepturi. Ele sunt înzestrate cu rațiune și conștiință și trebuie să se comporte unele față de altele în spiritul fraternității.
> A recording of this text by Georgescu Alexandru Cristian

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ro.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ron/) has 3 videos of Romanian speakers. Watch [Raluca speaking Romanian](https://wikitongues.org/videos/raluca_20170421_ron/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 550,414 articles in ro.wikipedia; 1,880 active users. This is ~1/14 of English data and ranks 28 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                      |
| Common Crawl           | 12,147,112 pages per crawl on average, which is 0.5638% of the crawl (2026). This is ~1/73 of English data and ranks 18 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                            |
| FineWeb                | 91.75 GB (ron_Latn 91.75 GB; ron_Cyrl 6.0 MB), equivalent to ≈82.28 GB of English after byte-premium scaling; 76.76 GB removed by filtering. This is ~1/582 of English data and ranks 20 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 7.87 GB (ron_Latn 7.87 GB) (rank 26 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                |

**By writing system:**

| Writing system    | FineWeb                           | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:----------------------------------|:------------------------------|:-------------|:-------------------------------|
| Latin (`Latn`)    | 91.75 GB (+76.75 GB filtered out) | 82.27 GB                      | 7.87 GB      | 7.06 GB                        |
| Cyrillic (`Cyrl`) | 5.7 MB (+5.9 MB filtered out)     | 3.4 MB                        | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 6 treebanks, 40,720 sentences / 942,149 tokens in total: [UD_Romanian-ArT](https://github.com/UniversalDependencies/UD_Romanian-ArT) (50 sentences), [UD_Romanian-MolDoRo](https://github.com/UniversalDependencies/UD_Romanian-MolDoRo) (30 sentences), [UD_Romanian-Nonstandard](https://github.com/UniversalDependencies/UD_Romanian-Nonstandard) (26,225 sentences), [UD_Romanian-RRT](https://github.com/UniversalDependencies/UD_Romanian-RRT) (9,524 sentences), [UD_Romanian-SiMoNERo](https://github.com/UniversalDependencies/UD_Romanian-SiMoNERo) (4,681 sentences), [UD_Romanian-TueCL](https://github.com/UniversalDependencies/UD_Romanian-TueCL) (210 sentences). All have POS tags, dependency syntax, lemmas. |
| UniMorph               | 4,405 lemmas, 80,266 inflected forms ([unimorph/ron](https://github.com/unimorph/ron))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Wikidata labels        | 6,751,178 Wikidata items have a label in Romanian. (Wikidata codes (labels): ro (6,751,178))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Wordnets               | [Romanian Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-ro-1.4.tar.xz): 56,026 synsets, 52,600 words, 84,638 senses; licence: https://creativecommons.org/licenses/by-sa/; [BalkaNet](http://www.dblab.upatras.gr/balkanet/) (size not listed); [MultiWordNet](http://multiwordnet.fbk.eu/english/home.php) (size not listed); licence: CC-BY 3.0.                                                                                                                                                                                                                                                                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 390,056,167 sentence pairs with English across 80 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (100,540,377), [NLLB](https://opus.nlpl.eu/NLLB) (55,607,023), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (55,607,023), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (54,481,584), [HPLT](https://opus.nlpl.eu/HPLT) (54,481,584).    |
| Bible translations (eBible corpus)                                                       | **Yes** — 4 translations: full Bible ([ron1924](https://ebible.org/details.php?id=ron1924), Public Domain); New Testament ([ronlsb](https://ebible.org/details.php?id=ronlsb), Public Domain); portions ([ronBayash](https://ebible.org/details.php?id=ronBayash), by 4.0); portions ([ronludari](https://ebible.org/details.php?id=ronludari), by-sa 4.0). |
| Tatoeba                                                                                  | 41,983 sentences, 31,987 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ron/none)).                                                                                                                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=97), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.990 (P 0.984, R 0.995, FPR 1.06e-04) averaged over 5 dataset(s). Runner-up: commonlingua (F1 0.956).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.984 |    0.995 | 0.990 | 0.000 | ✓                |
| commonlingua |       0.977 |    0.938 | 0.956 | 0.000 | ✓                |
| OpenLID-v2   |       0.921 |    0.994 | 0.953 | 0.001 | ✓                |
| cld2         |       0.948 |    0.951 | 0.947 | 0.001 | ✓                |
| fasttext     |       0.907 |    0.994 | 0.946 | 0.001 | ✓                |
| py3langid    |       0.850 |    0.996 | 0.912 | 0.002 | ✓                |
| pyfranc      |       0.967 |    0.858 | 0.900 | 0.000 | ✓                |
| funlangid    |       0.925 |    0.870 | 0.891 | 0.001 | ✓                |
| cld3         |       0.782 |    0.955 | 0.851 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.971 |    0.990 | 0.980 |
| UDHR-LID  |  97 |       0.970 |    1.000 | 0.985 |
| Wikipedia | 300 |       0.983 |    0.987 | 0.985 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Romanian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Romanian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Romanian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Romanian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Romanian (and whether the model is exclusively tagged for Romanian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **968** text-generation models are explicitly tagged for Romanian (267 original uploads, 701 fine-tunes/quantisations/merges).
- **73** are tagged *only* for Romanian.
- Including tags inherited from base models: **1,892**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |       27 | █                    |
|   2024 |      280 | ███████████████      |
|   2025 |      375 | ████████████████████ |
|   2026 |      276 | ███████████████      |

### Largest models tagged for Romanian

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                                      |
| [kepom/Kimi-K2.7-Code](https://huggingface.co/kepom/Kimi-K2.7-Code)                                     | 1.1T         |                    2 |   2026 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |

### Largest models tagged *only* for Romanian

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                               |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [iulio/FiscMind-AI-v9-GGUF](https://huggingface.co/iulio/FiscMind-AI-v9-GGUF)                                 | 12.2B        |                    1 |   2026 | unsloth/mistral-nemo-instruct-2407-bnb-4bit |
| [la2ydev/RoGemma2-9b-Instruct](https://huggingface.co/la2ydev/RoGemma2-9b-Instruct)                           | 9.2B         |                    1 |   2024 | OpenLLM-Ro/RoGemma2-9b-Instruct             |
| [OpenLLM-Ro/RoGemma-7b-Instruct-2024-06-28](https://huggingface.co/OpenLLM-Ro/RoGemma-7b-Instruct-2024-06-28) | 8.5B         |                    1 |   2024 | google/gemma-7b                             |
| [legraphista/RoGemma-7b-Instruct-IMat-GGUF](https://huggingface.co/legraphista/RoGemma-7b-Instruct-IMat-GGUF) | 8.5B         |                    1 |   2024 | OpenLLM-Ro/RoGemma-7b-Instruct              |
| [ssmits/Falcon2-8B-Romanian](https://huggingface.co/ssmits/Falcon2-8B-Romanian)                               | 8.1B         |                    1 |   2024 | tiiuae/falcon-11B                           |

_97 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Romanian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                          |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 246            | Treebank-based (automatic)                            |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,056          | Treebank-based (automatic, UD + UniMorph)             |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [ro_winogrande (OpenLLM-Ro)](https://huggingface.co/datasets/OpenLLM-Ro/ro_winogrande)              | —              | Machine translation                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                           |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)            |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,245          | Machine translation (GPT-3.5-turbo)                   |
| 3. Commonsense reasoning               | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (GPT-4o-mini, automated pipeline) |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                               |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)            |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                      |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | MT + community post-editing                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                              |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)        |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 6,632          | Native (crowdsourced Tatoeba sentence pairs)          |

### Standard machine translation test sets

Romanian has been part of the WMT translation task in **2** years (2016, 2025).

| Test set                                                                  | Direction(s)                           | Size                               | Human reference             |
|:--------------------------------------------------------------------------|:---------------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)              | 2,009 sentences (Latn)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)      | 1,358 sentences (Latn)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-ro_RO) | en → ro_RO                             | 998 segments                       | ✅                          |
| [WMT16 general task](https://www2.statmt.org/wmt16/)                      | English → Romanian; Romanian → English | 1,999 segments                     | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Romanian                     | 87 documents (36,770 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Romanian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Romanian? Does it make sense to train one?
  - ~82.28 GB English-equivalent text ≈ 20.57B tokens, enough for a compute-optimal model of ~1.0B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Romanian-only model is 12.2B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 211 of ~18,498 papers (1.14%) (rank 33 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Romanian

Here are up to ten papers published in 2026 that mention Romanian. None of the 211 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                                              |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)                 |
| Disentangling Meaning and Language Components in Diverse Multilingual Sentence Embeddings                                   | [2026.acl-srw.102](https://aclanthology.org/2026.acl-srw.102/)                     |
| MemeLens: Multilingual Multitask VLMs for Memes                                                                             | [2026.emnlp-main.2290](https://aclanthology.org/2026.emnlp-main.2290/)             |
| PolERo: Studying Political Evasion in Romanian                                                                              | [2026.emnlp-main.2688](https://aclanthology.org/2026.emnlp-main.2688/)             |
| Representation Collapse in Machine Translation Through the Lens of Angular Dispersion                                       | [2026.findings-eacl.126](https://aclanthology.org/2026.findings-eacl.126/)         |
| PATCH: Mitigating PII Leakage in Language Models with Privacy-Aware Targeted Circuit PatcHing                               | [2026.findings-eacl.271](https://aclanthology.org/2026.findings-eacl.271/)         |
| Register-based data selection for multilingual LLMs                                                                         | [2026.findings-emnlp.4](https://aclanthology.org/2026.findings-emnlp.4/)           |
| Estonian WinoGrande Dataset: Comparative Analysis of LLM Performance on Human and Machine Translation                       | [2026.lrec-1.549](https://aclanthology.org/2026.lrec-1.549/)                       |
| asetclarity at SemEval-2026 Task 6: An Imbalance-Aware RoBERTa Cross-Encoder for Political Response Clarity Classification  | [2026.semeval-1.146](https://aclanthology.org/2026.semeval-1.146/)                 |
| Mitigating Language Bias in Multilingual Sentence Embeddings for Cross-Lingual Similarity Estimation                        | [2026.starsem-conference.26](https://aclanthology.org/2026.starsem-conference.26/) |

{% endraw %}
