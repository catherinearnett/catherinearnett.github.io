---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lit.html
---
{% raw %}
# So you want to work on Lithuanian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lit`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › Eastern Baltic ([Glottolog](https://glottolog.org/resource/languoid/id/lith1251))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 2.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Lithuania

**Status:** Official language


## What does Lithuanian look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/lithuanian.htm):

> Visi žmonės gimsta laisvi ir lygūs savo orumu ir teisėmis.
> Jiems suteiktas protas ir sąžinė ir jie turi elgtis vienas kito
> atžvilgiu kaip broliai.
> Listen to Augustinas Žemaitis reading this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/lit/) has 2 videos of Lithuanian speakers. Watch [Pau speaking French, Lithuanian, Italian, English, Spanish, Catalan](https://wikitongues.org/videos/pau_20170509_fra-lit-ita-eng-spa-cat/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 227,207 articles in lt.wikipedia; 650 active users. This is ~1/33 of English data and ranks 42 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 3,752,289 pages per crawl on average, which is 0.1741% of the crawl (2026). This is ~1/238 of English data and ranks 32 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 27.71 GB (lit_Latn 27.71 GB), equivalent to ≈26.90 GB of English after byte-premium scaling; 25.60 GB removed by filtering. This is ~1/1,928 of English data and ranks 29 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 3.98 GB (lit_Latn 3.98 GB) (rank 47 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 3,333 sentences / 61,971 tokens in total: [UD_Lithuanian-ALKSNIS](https://github.com/UniversalDependencies/UD_Lithuanian-ALKSNIS) (3,070 sentences), [UD_Lithuanian-HSE](https://github.com/UniversalDependencies/UD_Lithuanian-HSE) (263 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,458 lemmas, 34,130 inflected forms ([unimorph/lit](https://github.com/unimorph/lit))                                                                                                                                                                                                                                                      |
| Wikidata labels        | 1,300,057 Wikidata items have a label in Lithuanian. (Wikidata codes (labels): lt (1,300,057))                                                                                                                                                                                                                                              |
| Wordnets               | [Lithuanian  WordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-lt-1.4.tar.xz): 9,462 synsets, 11,428 words, 16,032 senses; licence: https://creativecommons.org/licenses/by-sa/3.0/.                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 145,217,859 sentence pairs with English across 60 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (23,298,470), [NLLB](https://opus.nlpl.eu/NLLB) (23,298,470), [HPLT](https://opus.nlpl.eu/HPLT) (21,328,192), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (21,328,192), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (13,192,237). |
| Bible translations (eBible corpus)                                                       | **Portions only** — 1 translation: portions ([lit](https://ebible.org/details.php?id=lit), by-sa 4.0).                                                                                                                                                                                                                                          |
| Tatoeba                                                                                  | 159,539 sentences, 8,671 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/lit/none)).                                                                                                                                                                                                                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                            |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                             |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.982, R 0.993, FPR 1.18e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.983).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.982 |    0.993 | 0.987 | 0.000 | ✓                |
| cld2         |       0.992 |    0.975 | 0.983 | 0.000 | ✓                |
| py3langid    |       0.963 |    0.988 | 0.975 | 0.000 | ✓                |
| fasttext     |       0.907 |    0.996 | 0.946 | 0.001 | ✓                |
| OpenLID-v2   |       0.894 |    0.992 | 0.936 | 0.001 | ✓                |
| commonlingua |       0.957 |    0.860 | 0.894 | 0.000 | ✓                |
| pyfranc      |       0.881 |    0.825 | 0.848 | 0.001 | ✓                |
| funlangid    |       0.947 |    0.763 | 0.827 | 0.000 | ✓                |
| cld3         |       0.709 |    0.968 | 0.797 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.964 |    0.970 | 0.967 |
| Wikipedia | 300 |       0.961 |    0.997 | 0.979 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lithuanian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lithuanian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lithuanian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Lithuanian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lithuanian (and whether the model is exclusively tagged for Lithuanian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **398** text-generation models are explicitly tagged for Lithuanian (105 original uploads, 293 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Lithuanian.
- Including tags inherited from base models: **838**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       10 | █                    |
|   2024 |       74 | ████████             |
|   2025 |      122 | █████████████        |
|   2026 |      183 | ████████████████████ |

### Largest models tagged for Lithuanian

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)         | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                   | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [PsycheFoundation/consilience-40b-7Y9v38s5](https://huggingface.co/PsycheFoundation/consilience-40b-7Y9v38s5) | 40.2B        |                   37 |   2025 | —                                      |

### Largest models tagged *only* for Lithuanian

| model                                                                                                                                           | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [VytautoDidziojoUniversitetas/LT-ABS-abstractive-Gemma3-12b](https://huggingface.co/VytautoDidziojoUniversitetas/LT-ABS-abstractive-Gemma3-12b) | 12.0B        |                    1 |   2026 | google/gemma-3-12b-it     |
| [DGurgurov/llama-3.1-8b-lit_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-lit_latn)                                                       | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-lit_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-lit_latn)                                                   | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [alphaedge-ai/Qwen3.5-4B-lit-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-lit-32768)                                                   | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [sauliusp1313/elaba_gemma3.4b](https://huggingface.co/sauliusp1313/elaba_gemma3.4b)                                                             | 3.9B         |                    1 |   2026 | unsloth/gemma-3-4b-it     |

_57 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Lithuanian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | construction                                               |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 46             | Treebank-based (automatic)                                 |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 1,180          | Treebank-based (automatic, UD + UniMorph)                  |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [lt_winogrande](https://huggingface.co/datasets/neurotechnology/lt_winogrande)                      | —              | Machine translation (GPT-4)                                |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                 |
| 3. Commonsense reasoning               | HellaSwag                     | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline) |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                     |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                    |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                 |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                           |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 593            | Native (high-school exams)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                       |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)             |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,585          | Native (crowdsourced Tatoeba sentence pairs)               |

### Standard machine translation test sets

Lithuanian has been part of the WMT translation task in **2** years (2019, 2025).

| Test set                                                                  | Direction(s)                               | Size                               | Human reference             |
|:--------------------------------------------------------------------------|:-------------------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)                  | 2,009 sentences (Latn)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)          | 1,358 sentences (Latn)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-lt_LT) | en → lt_LT                                 | 998 segments                       | ✅                          |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                      | English → Lithuanian; Lithuanian → English | 998 segments / 1,000 segments      | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Lithuanian                       | 87 documents (36,770 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lithuanian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lithuanian? Does it make sense to train one?
  - ~26.90 GB English-equivalent text ≈ 6.73B tokens, enough for a compute-optimal model of ~336.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Lithuanian-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 85 of ~18,498 papers (0.46%) (rank 64 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Lithuanian

Here are up to ten papers published in 2026 that mention Lithuanian. None of the 85 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                | paper                                                                      |
|:---------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| How to Improve LLMs’ Performance on Specific Languages: A Perspective on LLM-Derived Language Similarity             | [2026.acl-long.691](https://aclanthology.org/2026.acl-long.691/)           |
| CRITICS: Critical Science Without Borders by Translation of Scientific Knowledge                                     | [2026.eamt-2.23](https://aclanthology.org/2026.eamt-2.23/)                 |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                  | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/) |
| WikiLingDiv: a dataset for quantifying digital linguistic diversity using Wikipedia page views                       | [2026.latechclfl-1.19](https://aclanthology.org/2026.latechclfl-1.19/)     |
| Pretraining and Benchmarking Modern Encoders for Latvian                                                             | [2026.loreslm-1.40](https://aclanthology.org/2026.loreslm-1.40/)           |
| Assessing the Political Fairness of Multilingual LLMs: A Case Study Based on a 21-Way Multiparallel EuroParl Dataset | [2026.lrec-1.17](https://aclanthology.org/2026.lrec-1.17/)                 |
| SloPal: A 60-Million-Word Slovak Parliamentary Corpus with Aligned Speech and Fine-Tuned ASR Models                  | [2026.lrec-1.282](https://aclanthology.org/2026.lrec-1.282/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                           | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                     | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)               |
| Evaluating the Interplay of Information Status and Information Content in a Multilingual Parallel Corpus             | [2026.sigtyp-main.3](https://aclanthology.org/2026.sigtyp-main.3/)         |

{% endraw %}
