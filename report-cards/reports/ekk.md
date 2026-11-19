---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ekk.html
---
{% raw %}
# So you want to work on Estonian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ekk` · macrolanguage `est`

**Language family:** **Uralic** › Finnic › Coastal Finnic › … › Central Finnic ([Glottolog](https://glottolog.org/resource/languoid/id/esto1258))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 854,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `est`, so includes other varieties

**Official / recognised in:** Estonia

**Status:** Official language


## What does Estonian look and sound like?

**Written (Estonian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/estonian.htm):

> Kõik inimesed sünnivad vabadena ja võrdsetena oma
> väärikuselt ja õigustelt. Neile on antud mõistus
> ja südametunnistus ja nende suhtumist üksteisesse peab kandma
> vendluse vaim.
> A recording of this text by Ülle Hahndorf

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_et.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ekk/) has 1 video of Estonian speakers. Watch [Liisi speaking Standard Estonian](https://wikitongues.org/videos/liisi_20150804_ekk/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 262,759 articles in et.wikipedia; 992 active users. ⚠️ NB: recorded under the macrolanguage code `est`, which can include other varieties of Estonian.                                                                                            |
| Common Crawl           | 3,066,731 pages per crawl on average, which is 0.1423% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `est`, which can include other varieties of Estonian.                                                                    |
| FineWeb                | 19.75 GB (ekk_Latn 19.75 GB), equivalent to ≈19.88 GB of English after byte-premium scaling; 18.71 GB removed by filtering. This is ~1/2,704 of English data and ranks 36 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 62.5 MB (ekk_Latn 62.0 MB) (rank 132 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                           |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 38,120 sentences / 528,370 tokens in total: [UD_Estonian-EDT](https://github.com/UniversalDependencies/UD_Estonian-EDT) (30,930 sentences), [UD_Estonian-EWT](https://github.com/UniversalDependencies/UD_Estonian-EWT) (7,190 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `est`, so this may cover other varieties as well as Estonian. |
| UniMorph               | 886 lemmas, 38,215 inflected forms ([unimorph/est](https://github.com/unimorph/est)) ⚠️ Listed under the macrolanguage code `est`, so this may cover other varieties as well as Estonian.                                                                                                                                                                                                                                             |
| Wikidata labels        | 4,948,916 Wikidata items have a label in Estonian. (Wikidata codes (labels): et (4,948,916))                                                                                                                                                                                                                                                                                                                                          |
| Wordnets               | [Estonian Wordnet (EstWN)](http://www.cl.ut.ee/ressursid/teksaurus/) (size not listed); licence: CC – BY – NC.                                                                                                                                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 142,942,108 sentence pairs with English across 81 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (22,007,049), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (22,007,049), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (20,224,893), [HPLT](https://opus.nlpl.eu/HPLT) (15,520,792), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (15,520,792). ⚠️ Listed under the macrolanguage code `est`, so this may cover other varieties as well as Estonian. |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                                                                  |
| Tatoeba                                                                                  | 6,539 sentences, 5,356 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/est/none)). ⚠️ Listed under the macrolanguage code `est`, so this may cover other varieties as well as Estonian.                                                                                                                                                                                                                                   |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.978, R 0.978, FPR 1.93e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.918).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.978 |    0.978 | 0.978 | 0.000 | ✓                |
| cld2         |       0.938 |    0.913 | 0.918 | 0.001 | ✓                |
| fasttext     |       0.792 |    0.982 | 0.839 | 0.005 | ✓                |
| commonlingua |       0.809 |    0.876 | 0.833 | 0.002 | ✓                |
| pyfranc      |       0.931 |    0.761 | 0.827 | 0.001 | ✓                |
| py3langid    |       0.764 |    0.966 | 0.817 | 0.006 | ✓                |
| OpenLID-v2   |       0.750 |    0.968 | 0.804 | 0.006 | ✓                |
| funlangid    |       0.917 |    0.725 | 0.793 | 0.001 | ✓                |
| cld3         |       0.697 |    0.922 | 0.763 | 0.008 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.972 |    0.913 | 0.942 |
| Tatoeba   | 300 |       0.963 |    0.967 | 0.965 |
| Wikipedia | 300 |       0.955 |    0.990 | 0.972 |
| UDHR-LID  |  60 |       0.984 |    1.000 | 0.992 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Estonian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Estonian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Estonian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Estonian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Estonian (and whether the model is exclusively tagged for Estonian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **428** text-generation models are explicitly tagged for Estonian (115 original uploads, 313 fine-tunes/quantisations/merges).
- **38** are tagged *only* for Estonian.
- Including tags inherited from base models: **876**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | █                    |
|   2023 |       14 | ██                   |
|   2024 |       80 | █████████            |
|   2025 |      147 | █████████████████    |
|   2026 |      174 | ████████████████████ |

### Largest models tagged for Estonian

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [tartuNLP/Llama-3.1-EstLLM-70B-0826](https://huggingface.co/tartuNLP/Llama-3.1-EstLLM-70B-0826)       | 70.6B        |                    2 |   2026 | meta-llama/Llama-3.1-70B               |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Estonian

| model                                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-ekk_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-ekk_latn)     | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-ekk_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-ekk_latn) | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [tartuNLP/llammas-prelim](https://huggingface.co/tartuNLP/llammas-prelim)                     | 6.7B         |                    1 |   2023 | —                         |
| [tartuNLP/Llammas-base-AEG](https://huggingface.co/tartuNLP/Llammas-base-AEG)                 | 6.7B         |                    1 |   2024 | meta-llama/Llama-2-7b-hf  |
| [alphaedge-ai/Qwen3.5-4B-est-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-est-32768) | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |

_58 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Estonian (plus 7 labelled with the macrolanguage `est`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                     | # test items   | construction                                               |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `est`)                             | 2,575          | Treebank-based (automatic, UD + UniMorph)                  |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)     | [EstAnaphora (Estonian pronominal coreference)](https://github.com/EstSyntax/EstAnaphora)                   | 7,250          | Native (manually annotated corpus)                         |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [Estonian WinoGrande](https://huggingface.co/datasets/tartuNLP/winogrande_et)                               | 1,767          | Human translation (revised by professional) + localization |
| 3. Commonsense reasoning               | COPA                          | [EstCOPA](https://huggingface.co/datasets/tartuNLP/EstCOPA) (as `est`)                                      | 500            | MT + human post-editing                                    |
| 3. Commonsense reasoning               | COPA                          | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa) (as `est`)                                      | 500            | Human translation                                          |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx) (as `est`)             | —              | Machine translation (DeepL)                                |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `est`)                                            | 9,088          | Machine translation (GPT-4o, auto-checked)                 |
| 3. Commonsense reasoning               | HellaSwag                     | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks) (as `est`) | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline) |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)         | 100            | Native                                                     |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                | 103            | MT + human post-editing                                    |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `est`)                                           | 1,332          | Machine translation (GPT-4o, auto-checked)                 |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                               | 900            | Human translation (professional)                           |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                  | 5,000          | Synthetic (LLM-generated) on native Wikipedia              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                    | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)             | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                             | —              | Native (local exams)                                       |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                   | 1,997          | Human translation (professional, from English)             |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                        | 1,359          | Native (crowdsourced Tatoeba sentence pairs)               |

### Standard machine translation test sets

Estonian has been part of the WMT translation task in **1** year (2026).

| Test set                                                                  | Direction(s)                      | Size                                | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn)              | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-et_EE) | en → et_EE                        | 998 segments                        | ✅                |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)  | English → Estonian                | 198 documents (28,523 source words) | ✅                |

_⚠️ Listed under the macrolanguage code `est`, so this may cover other varieties as well as Estonian._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Estonian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Estonian? Does it make sense to train one?
  - ~19.88 GB English-equivalent text ≈ 4.97B tokens, enough for a compute-optimal model of ~248.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Estonian-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 131 of ~18,498 papers (0.71%) (rank 47 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Standard Estonian | Estonian

Here are up to ten papers published in 2026 that mention Estonian. None of the 131 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                             | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Neural Text-to-Speech for Myaamia: Speech Synthesis for an Indigenous Algonquian Language                                         | [2026.americasnlp-6.1](https://aclanthology.org/2026.americasnlp-6.1/)         |
| Efficient Low-Resource Language Models Using Tokenizer Transfer                                                                   | [2026.eacl-srw.49](https://aclanthology.org/2026.eacl-srw.49/)                 |
| Automatic translation in public services: A survey of the Finnish public sector                                                   | [2026.eamt-1.45](https://aclanthology.org/2026.eamt-1.45/)                     |
| Presentation of the Project CLingS: Cross-lingual information retrieval for scientific datasets in less-resourced languages       | [2026.eamt-2.6](https://aclanthology.org/2026.eamt-2.6/)                       |
| Gold vs. Translation: Are We Measuring Language, Knowledge, or Locality in Translated Benchmarks?                                 | [2026.emnlp-main.32](https://aclanthology.org/2026.emnlp-main.32/)             |
| Dialects of Translationese Shape Language Model Learning                                                                          | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                      | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                        | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Prompt-Based Stance Control in German: An Evaluation of LLMs for Experimental Research on Attitude Change                         | [2026.lrec-1.644](https://aclanthology.org/2026.lrec-1.644/)                   |
| How Well Do Commodity Text-to-Speech Systems Evade Acoustic Perturbation Detection? A Multi-Engine Evaluation Across 21 Languages | [2026.nlpaics-1.18](https://aclanthology.org/2026.nlpaics-1.18/)               |

{% endraw %}
