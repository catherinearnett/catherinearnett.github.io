---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/swh.html
---
{% raw %}
# So you want to work on Swahili?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `swh` · macrolanguage `swa`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Mombasa-Lamu-Inland Swahili ([Glottolog](https://glottolog.org/resource/languoid/id/swah1253))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 194.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `swa`, so includes other varieties

**Official / recognised in:** Kenya, Rwanda, Tanzania, Uganda

**Status:** Official language


## What does Swahili look and sound like?

**Written (Latin alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/swahili.htm):

> Watu wote wamezaliwa huru, hadhi na haki zao ni sawa. Wote wamejaliwa akili na dhamiri, hivyo yapasa watendeane kindugu.

**Written (Arabic script)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/swahili.htm):

> Arabic script text provided by Ahmed Elshikh

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_swahili.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/swh/) has 7 videos of Swahili speakers. Watch [See all](https://wikitongues.org/videos/?language=swh).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 132,705 articles in sw.wikipedia; 215 active users. ⚠️ NB: recorded under the macrolanguage code `swa`, which can include other varieties of Swahili.                                                                                          |
| Common Crawl           | 252,345 pages per crawl on average, which is 0.0117% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `swa`, which can include other varieties of Swahili.                                                                    |
| FineWeb                | 1.44 GB (swh_Latn 1.44 GB), equivalent to ≈1.35 GB of English after byte-premium scaling; 2.40 GB removed by filtering. This is ~1/37,005 of English data and ranks 67 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | **None found**                                                                              |
| Wikidata labels        | 1,721,362 Wikidata items have a label in Swahili. (Wikidata codes (labels): sw (1,721,362)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 457 sentence pairs with English across 1 corpora; largest: [Tatoeba](https://opus.nlpl.eu/Tatoeba) (457).                                                                                                                                                                                                                                                                                                                    |
| Bible translations (eBible corpus)                                                       | **Yes** — 3 translations: full Bible ([swhonen](https://ebible.org/details.php?id=swhonen), by-sa 4.0); full Bible ([swhulb](https://ebible.org/details.php?id=swhulb), by-sa 4.0); New Testament ([swh1850](https://ebible.org/details.php?id=swh1850), Public Domain).                                                                                                                                                     |
| Tatoeba                                                                                  | 4,583 sentences, 4,351 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/swh/none)).                                                                                                                                                                                                                                                                                                        |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_sw) ar → sw: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_sw) en → sw: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__zh_sw) zh → sw: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sw) en → sw: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.947 (P 0.940, R 0.969, FPR 6.34e-04) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.942).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.940 |    0.969 | 0.947 | 0.001 | ✓                |
| GlotLID      |       0.961 |    0.928 | 0.942 | 0.000 | ✓                |
| OpenLID-v2   |       0.835 |    0.987 | 0.865 | 0.006 | ✓                |
| fasttext     |       0.800 |    0.991 | 0.851 | 0.005 | ✓                |
| pyfranc      |       0.847 |    0.835 | 0.836 | 0.002 | ✓                |
| funlangid    |       0.836 |    0.808 | 0.804 | 0.001 | ✓                |
| commonlingua |       0.767 |    0.885 | 0.780 | 0.005 | ✓                |
| AfroLID      |       0.568 |    0.969 | 0.707 | 0.053 | ✓                |
| py3langid    |       0.589 |    0.993 | 0.699 | 0.019 | ✓                |
| cld3         |       0.451 |    0.966 | 0.572 | 0.042 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  58 |       0.604 |    1.000 | 0.753 |
| Tatoeba   | 300 |       0.985 |    0.897 | 0.939 |
| CommonLID | 300 |       1.000 |    0.933 | 0.966 |
| Wikipedia | 300 |       0.997 |    0.973 | 0.985 |
| NTREX     | 300 |       1.000 |    0.983 | 0.992 |
| SmolSent  | 300 |       0.997 |    0.993 | 0.995 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Swahili to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Swahili *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Swahili and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Swahili has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Swahili?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Swahili (and whether the model is exclusively tagged for Swahili or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **510** text-generation models are explicitly tagged for Swahili (191 original uploads, 319 fine-tunes/quantisations/merges).
- **73** are tagged *only* for Swahili.
- Including tags inherited from base models: **954**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       44 | ████                 |
|   2023 |       37 | ███                  |
|   2024 |       94 | ████████             |
|   2025 |      108 | ██████████           |
|   2026 |      227 | ████████████████████ |

### Largest models tagged for Swahili

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Swahili

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [Alfaxad/gemma2-27b-swahili-it](https://huggingface.co/Alfaxad/gemma2-27b-swahili-it) | 27.2B        |                    1 |   2025 | google/gemma-2-27b |
| [Alfaxad/gemma2-9b-swahili-it](https://huggingface.co/Alfaxad/gemma2-9b-swahili-it)   | 9.2B         |                    1 |   2025 | google/gemma-2-9b  |
| [lightonai/Qwen3-8B-SW](https://huggingface.co/lightonai/Qwen3-8B-SW)                 | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base |
| [GodsonNtungi/swahilillama3-8b](https://huggingface.co/GodsonNtungi/swahilillama3-8b) | 8.0B         |                    1 |   2024 | llama-3-8b         |
| [lightblue/kurage-sw](https://huggingface.co/lightblue/kurage-sw)                     | 7.6B         |                    1 |   2024 | —                  |

_96 tagged models have unknown parameter counts and are not ranked by size._

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

**21** benchmark datasets in the survey include Swahili (plus 6 labelled with the macrolanguage `swa`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                             |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual) (as `swa`)        | 6,000          | Template-based                                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                   | 1,098          | Native (written by native speakers)                      |
| 3. Commonsense reasoning               | COPA                           | [Owos/xcopa](https://huggingface.co/datasets/Owos/xcopa) (as `swa`)                                 | 500            | Machine translation (Google)                             |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa) (as `swa`)                              | 500            | Human translation                                        |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `swa`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                  |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `swa`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze) (as `swa`)                    | 1,511          | Human translation (professional)                         |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                         |
| 4. Reading comprehension               | QA – extractive RC             | KenSwQuAD                                                                                           | —              | Native                                                   |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         | 500            | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 438            | Native (national exams)                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                         |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    | 302            | Native                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)           |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 434            | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sw_KE)                           | en → sw_KE                        | 998 segments           | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sw_TZ)                           | en → sw_TZ                        | 998 segments           | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_sw) (training data)   | ar → sw                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_sw) (training data)   | en → sw                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__zh_sw) (training data)   | zh → sw                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sw) (training data) | en → sw                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Swahili datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Swahili? Does it make sense to train one?
  - ~1.35 GB English-equivalent text ≈ 0.34B tokens, enough for a compute-optimal model of ~16.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Swahili-only model is 27.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 323 of ~18,498 papers (1.75%) (rank 21 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Swahili

Here are up to ten papers published in 2026 that mention Swahili. None of the 323 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                      | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                          | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| Calibrating Beyond English: Language Diversity for Better Quantized Multilingual LLMs                                      | [2026.eacl-long.223](https://aclanthology.org/2026.eacl-long.223/)             |
| MERLIN: Multi-Stage Curriculum Alignment for Multilingual Encoder-LLM Integration in Cross-Lingual Reasoning               | [2026.eacl-long.277](https://aclanthology.org/2026.eacl-long.277/)             |
| Localizing Cross-Lingual Generalization in Parameter Space                                                                 | [2026.emnlp-main.2625](https://aclanthology.org/2026.emnlp-main.2625/)         |
| KnowledgeBerg: Evaluating Systematic Knowledge Coverage and Compositional Reasoning in Large Language Models               | [2026.findings-acl.548](https://aclanthology.org/2026.findings-acl.548/)       |
| Science Across Languages: Assessing LLM Multilingual Translation of Scientific Papers                                      | [2026.findings-eacl.204](https://aclanthology.org/2026.findings-eacl.204/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation             | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Cross-Lingual Bias in Large Language Models: A Comparative Analysis of English and Swahili                                 | [2026.mellm-1.17](https://aclanthology.org/2026.mellm-1.17/)                   |
| CYUT at SemEval-2026 Task 3: Multi-Task Dimensional Aspect Sentiment Regression with Polar Multi-Zone Labeling in VA Space | [2026.semeval-1.23](https://aclanthology.org/2026.semeval-1.23/)               |
| TUCNLP at SemEval-2026 Task 11: Neuro-Symbolic Content Stripping for Debiased Syllogistic Reasoning                        | [2026.semeval-1.423](https://aclanthology.org/2026.semeval-1.423/)             |

{% endraw %}
