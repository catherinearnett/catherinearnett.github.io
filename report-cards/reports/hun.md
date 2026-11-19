---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hun.html
---
{% raw %}
# So you want to work on Hungarian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hun`

**Language family:** **Uralic** › Hungaric ([Glottolog](https://glottolog.org/resource/languoid/id/hung1274))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 12.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Austria, Hungary

**Status:** Regional official language; Official language


## What does Hungarian look and sound like?

**Written (Hungarian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/hungarian.htm):

> Minden emberi lény szabadon születik és egyenlő méltósága és joga van. Az emberek, ésszel és lelkiismerettel bírván, egymással szemben testvéri szellemben kell hogy viseltessenek.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_hu.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hun/) has 6 videos of Hungarian speakers. Watch [Norbert speaking Hungarian](https://wikitongues.org/videos/norbert_20180402_hun/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 576,011 articles in hu.wikipedia; 2,885 active users. This is ~1/13 of English data and ranks 27 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                     |
| Common Crawl           | 11,363,660 pages per crawl on average, which is 0.5273% of the crawl (2026). This is ~1/78 of English data and ranks 20 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 98.57 GB (hun_Latn 98.57 GB), equivalent to ≈96.64 GB of English after byte-premium scaling; 89.43 GB removed by filtering. This is ~1/542 of English data and ranks 18 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 7.36 GB (hun_Latn 7.36 GB) (rank 31 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                         |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,800 sentences / 42,032 tokens in total: [UD_Hungarian-Szeged](https://github.com/UniversalDependencies/UD_Hungarian-Szeged) (1,800 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 19,424 lemmas, 1,036,931 inflected forms ([unimorph/hun](https://github.com/unimorph/hun))                                                                                                                                          |
| Wikidata labels        | 2,650,298 Wikidata items have a label in Hungarian. (Wikidata codes (labels): hu (2,650,298))                                                                                                                                       |
| Wordnets               | [Hungarian WordNet (HuWN)](http://www.inf.u-szeged.hu/rgai/HuWN) (size not listed); licence: OPEN FOR ACADEMIC USE MetaShare Commons NonCommercial-NoRedistribution (MSCommons_NoCOM-NC-NR).                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 301,037,139 sentence pairs with English across 57 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (67,930,371), [HPLT](https://opus.nlpl.eu/HPLT) (45,500,610), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (45,500,610), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (36,435,409), [NLLB](https://opus.nlpl.eu/NLLB) (36,435,409). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament ([hun](https://ebible.org/details.php?id=hun), by-sa 4.0).                                                                                                                                                                                                                                                       |
| Tatoeba                                                                                  | 444,190 sentences, 170,900 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/hun/none)).                                                                                                                                                                                                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                     |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.985, R 0.999, FPR 9.78e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.982).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.985 |    0.999 | 0.992 | 0.000 | ✓                |
| cld2         |       0.988 |    0.977 | 0.982 | 0.000 | ✓                |
| pyfranc      |       0.984 |    0.877 | 0.924 | 0.000 | ✓                |
| py3langid    |       0.869 |    0.996 | 0.919 | 0.002 | ✓                |
| funlangid    |       0.961 |    0.872 | 0.911 | 0.000 | ✓                |
| commonlingua |       0.865 |    0.946 | 0.896 | 0.001 | ✓                |
| OpenLID-v2   |       0.749 |    0.998 | 0.834 | 0.004 | ✓                |
| fasttext     |       0.613 |    0.998 | 0.715 | 0.009 | ✓                |
| cld3         |       0.576 |    0.977 | 0.689 | 0.015 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.974 |    0.993 | 0.983 |
| Tatoeba   | 300 |       0.971 |    1.000 | 0.985 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hungarian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hungarian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hungarian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hungarian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hungarian (and whether the model is exclusively tagged for Hungarian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **724** text-generation models are explicitly tagged for Hungarian (208 original uploads, 516 fine-tunes/quantisations/merges).
- **70** are tagged *only* for Hungarian.
- Including tags inherited from base models: **1,468**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       11 | █                    |
|   2023 |       26 | ██                   |
|   2024 |      126 | ████████             |
|   2025 |      249 | ████████████████     |
|   2026 |      312 | ████████████████████ |

### Largest models tagged for Hungarian

| model                                                                                                                     | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                 | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                     | 856.0B       |                  143 |   2025 | —               |
| [mindlab-research/Macaron-V1-Preview-744B-Merged](https://huggingface.co/mindlab-research/Macaron-V1-Preview-744B-Merged) | 753.9B       |                    4 |   2026 | zai-org/GLM-5.1 |
| [mindlab-research/Macaron-V1-Coding-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Coding-Venti)               | 753.3B       |                    4 |   2026 | —               |
| [mindlab-research/Macaron-V1-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Venti)                             | 753.3B       |                    4 |   2026 | —               |

### Largest models tagged *only* for Hungarian

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                  |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------|
| [emese-tech/folyo](https://huggingface.co/emese-tech/folyo)                                                           | 22.6B        |                    1 |   2026 | utter-project/EuroLLM-22B-2512 |
| [emese-tech/patak](https://huggingface.co/emese-tech/patak)                                                           | 9.2B         |                    1 |   2026 | utter-project/EuroLLM-9B       |
| [seyuyo/diktalo-e4b-GGUF](https://huggingface.co/seyuyo/diktalo-e4b-GGUF)                                             | 7.5B         |                    1 |   2026 | unsloth/gemma-4-E4B-it         |
| [boapps/szurkemarha-mistral](https://huggingface.co/boapps/szurkemarha-mistral)                                       | 7.2B         |                    1 |   2024 | —                              |
| [Bazsalanszky/Mistral-7b-0.1-alpaca-hun-gemini](https://huggingface.co/Bazsalanszky/Mistral-7b-0.1-alpaca-hun-gemini) | 7.2B         |                    1 |   2024 | unsloth/mistral-7b-bnb-4bit    |

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

**27** benchmark datasets in the survey include Hungarian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 9 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 9 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">9 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">3 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                   |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 13             | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 845            | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | WNLI                           | [HuWNLI](https://huggingface.co/datasets/NYTK/HuWNLI)                                               | 134            | Human translation + expert curation            |
| 2. Pragmatics, discourse & coreference | WSC                            | [HuWS](https://github.com/nytud/HuWS)                                                               | —              | Human translation + expert curation            |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                    | —              | Human translation (collected)                  |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                    |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,119          | Machine translation (GPT-3.5-turbo)            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,267          | Native (high-school exams)                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                              |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 19,625         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Hungarian has been part of the WMT translation task in **2** years (2008, 2009).

| Test set                                                                  | Direction(s)                             | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:-----------------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)                | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)        | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-hu_HU) | en → hu_HU                               | 998 segments           | ✅                |
| [WMT08 general task](https://www2.statmt.org/wmt08/)                      | English → Hungarian; Hungarian → English | 2,051 segments         | ✅                |
| [WMT09 general task](https://www2.statmt.org/wmt09/)                      | English → Hungarian; Hungarian → English | 3,027 segments         | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hungarian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hungarian? Does it make sense to train one?
  - ~96.64 GB English-equivalent text ≈ 24.16B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hungarian-only model is 22.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 296 of ~18,498 papers (1.60%) (rank 25 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Hungarian

Here are up to ten papers published in 2026 that mention Hungarian. None of the 296 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                  | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Evaluation Pitfalls and Challenges in Multimedia Event Extraction                                                      | [2026.acl-long.1426](https://aclanthology.org/2026.acl-long.1426/)       |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                              | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                 |
| Improving Medical Hallucination Detection with System Combination and Rule-based Customization                         | [2026.customnlp4u-1.14](https://aclanthology.org/2026.customnlp4u-1.14/) |
| NeuronMoE: Efficient Cross-Lingual Extension via Neuron-Guided Mixture-of-Experts                                      | [2026.eacl-long.117](https://aclanthology.org/2026.eacl-long.117/)       |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                             | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)             |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                    | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)             |
| Modular Approach to Automating Morphological Components in Grammar Engineering                                         | [2026.lrec-1.898](https://aclanthology.org/2026.lrec-1.898/)             |
| AmDi - Ambiguous Words Diachronic Dataset                                                                              | [2026.lrec-1.934](https://aclanthology.org/2026.lrec-1.934/)             |
| POS Tagging with Generative LLMs for Historical Germanic Low-Resource Languages: An Evaluation Against Fine-Tuned BERT | [2026.lt4hala-1.12](https://aclanthology.org/2026.lt4hala-1.12/)         |
| Omnivorous Agreement, like Uyghur Backness Harmony, is a Challenge for Tier-Based Strict Locality                      | [2026.scil-main.13](https://aclanthology.org/2026.scil-main.13/)         |

{% endraw %}
