---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/isl.html
---
{% raw %}
# So you want to work on Icelandic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `isl`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Icelandic-Faroese ([Glottolog](https://glottolog.org/resource/languoid/id/icel1247))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 364,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Iceland

**Status:** Official language


## What does Icelandic look and sound like?

**Written (Icelandic)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/icelandic.htm):

> Hver maður er borinn frjáls og jafn öðrum að virðingu og réttindum. Menn eru gæddir vitsmunum og samvisku, og ber þeim að breyta bróðurlega hverjum við annan.
> A recording of this text by Marc Volhardt
> A recording of this text by Alexander Jarl
> A recording of this text by Stefan Steinsson

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_is3.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/isl/) has 3 videos of Icelandic speakers. Watch [Ljóni speaking Icelandic](https://wikitongues.org/videos/ljoni_20160404_isl/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 60,612 articles in is.wikipedia; 266 active users. This is ~1/125 of English data and ranks 68 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 781,785 pages per crawl on average, which is 0.0363% of the crawl (2026). This is ~1/1,140 of English data and ranks 41 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                          |
| FineWeb                | 4.98 GB (isl_Latn 4.98 GB), equivalent to ≈4.31 GB of English after byte-premium scaling; 3.77 GB removed by filtering. This is ~1/10,725 of English data and ranks 51 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 2.65 GB (isl_Latn 2.65 GB) (rank 55 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 53,564 sentences / 1,182,501 tokens in total: [UD_Icelandic-GC](https://github.com/UniversalDependencies/UD_Icelandic-GC) (5,000 sentences), [UD_Icelandic-IcePaHC](https://github.com/UniversalDependencies/UD_Icelandic-IcePaHC) (44,029 sentences), [UD_Icelandic-Modern](https://github.com/UniversalDependencies/UD_Icelandic-Modern) (3,535 sentences), [UD_Icelandic-PUD](https://github.com/UniversalDependencies/UD_Icelandic-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 4,775 lemmas, 76,915 inflected forms ([unimorph/isl](https://github.com/unimorph/isl))                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Wikidata labels        | 1,530,392 Wikidata items have a label in Icelandic. (Wikidata codes (labels): is (1,530,392))                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Wordnets               | [IceWordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-is-1.4.tar.xz): 4,951 synsets, 11,655 words, 16,004 senses; licence: https://creativecommons.org/licenses/by/3.0/; NordicNet (HuWN) (size not listed).                                                                                                                                                                                                                                                                                                                      |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 42,471,980 sentence pairs with English across 49 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (8,723,145), [NLLB](https://opus.nlpl.eu/NLLB) (8,723,145), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (5,491,654), [HPLT](https://opus.nlpl.eu/HPLT) (5,491,654), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (4,057,039). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                       |
| Tatoeba                                                                                  | 13,394 sentences, 10,805 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/isl/none)).                                                                                                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                              |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                               |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_is) en → is: 3,995 lexicon entries; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_is) en → is: size not listed                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.992 (P 0.986, R 0.999, FPR 1.37e-04) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.986 |    0.999 | 0.992 | 0.000 | ✓                |
| GlotLID      |       0.990 |    0.994 | 0.992 | 0.000 | ✓                |
| cld2         |       0.992 |    0.977 | 0.984 | 0.000 | ✓                |
| py3langid    |       0.963 |    0.995 | 0.978 | 0.000 | ✓                |
| commonlingua |       0.928 |    0.912 | 0.919 | 0.001 | ✓                |
| funlangid    |       0.956 |    0.864 | 0.907 | 0.000 | ✓                |
| pyfranc      |       0.887 |    0.892 | 0.889 | 0.001 | ✓                |
| fasttext     |       0.673 |    0.998 | 0.795 | 0.004 | ✓                |
| cld3         |       0.509 |    0.985 | 0.651 | 0.014 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.943 |    0.997 | 0.969 |
| UDHR-LID  |  58 |       0.983 |    1.000 | 0.991 |
| Wikipedia | 300 |       0.993 |    0.997 | 0.995 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Icelandic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Icelandic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Icelandic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Icelandic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Icelandic (and whether the model is exclusively tagged for Icelandic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **334** text-generation models are explicitly tagged for Icelandic (118 original uploads, 216 fine-tunes/quantisations/merges).
- **62** are tagged *only* for Icelandic.
- Including tags inherited from base models: **609**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | ██                   |
|   2023 |       26 | ████                 |
|   2024 |       51 | ███████              |
|   2025 |       98 | █████████████        |
|   2026 |      146 | ████████████████████ |

### Largest models tagged for Icelandic

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [Unbabel/Tower-Plus-72B](https://huggingface.co/Unbabel/Tower-Plus-72B)                               | 72.7B        |                   22 |   2025 | Qwen/Qwen2.5-72B                       |
| [AI-Sweden-Models/gpt-sw3-40b](https://huggingface.co/AI-Sweden-Models/gpt-sw3-40b)                   | 39.9B        |                    5 |   2023 | —                                      |

### Largest models tagged *only* for Icelandic

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [cyboghostginx/gemma-4-31B-it-Adetayo](https://huggingface.co/cyboghostginx/gemma-4-31B-it-Adetayo) | 31.3B        |                    1 |   2026 | google/gemma-4-31b-it   |
| [cyboghostginx/gemma-3-27b-it-Adetayo](https://huggingface.co/cyboghostginx/gemma-3-27b-it-Adetayo) | 27.0B        |                    1 |   2026 | google/gemma-3-27b-it   |
| [Hodfa71/viking-13b-is-saga-delta-dpo](https://huggingface.co/Hodfa71/viking-13b-is-saga-delta-dpo) | 13.0B        |                    1 |   2026 | LumiOpen/Viking-13B     |
| [darkps/ice-AI](https://huggingface.co/darkps/ice-AI)                                               | 8.2B         |                    1 |   2026 | —                       |
| [DGurgurov/llama-3.1-8b-isl_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-isl_latn)           | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |

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

**18** benchmark datasets in the survey include Icelandic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 47             | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,801          | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [Icelandic WinoGrande](https://huggingface.co/datasets/mideind/icelandic-winogrande)                | 1,088          | Human translation + localization               |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC            | [Icelandic Wiki QA](https://huggingface.co/datasets/mideind/icelandic_wiki_qa)                      | 1,900          | Synthetic (GPT-4-turbo) + manual review        |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (Greynir)                  |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,658          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Icelandic has been part of the WMT translation task in **4** years (2021, 2024, 2025, 2026).

| Test set                                                                                            | Direction(s)                             | Size                                | Human reference   |
|:----------------------------------------------------------------------------------------------------|:-----------------------------------------|:------------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)                | 2,009 sentences (Latn)              | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages)        | 1,358 sentences (Latn)              | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-is_IS)                           | en → is_IS                               | 998 segments                        | ✅                |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                                                | English → Icelandic; Icelandic → English | 1,000 segments                      | ✅                |
| [WMT24 general task](https://www2.statmt.org/wmt24/)                                                | English → Icelandic                      | 997 segments                        | ✅                |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)                            | English → Icelandic                      | 87 documents (36,770 source words)  | ✅                |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)                            | English → Icelandic                      | 198 documents (28,523 source words) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_is) (training data)   | en → is                                  | 3,995 lexicon entries               | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_is) (training data) | en → is                                  | size not listed                     | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Icelandic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Icelandic? Does it make sense to train one?
  - ~4.31 GB English-equivalent text ≈ 1.08B tokens, enough for a compute-optimal model of ~53.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Icelandic-only model is 31.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 110 of ~18,498 papers (0.59%) (rank 55 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Icelandic

Here are up to ten papers published in 2026 that mention Icelandic. None of the 110 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Towards Fast and Accurate Modeling for Cross-Lingual Label Projection                                                                         | [2026.acl-long.1817](https://aclanthology.org/2026.acl-long.1817/)           |
| BabyBabelLM: A Multilingual Benchmark of Developmentally Plausible Training Data                                                              | [2026.eacl-long.152](https://aclanthology.org/2026.eacl-long.152/)           |
| Reading the News: Adapting Large Language Models to Swedish Journalism Through Continued Pre-Training                                         | [2026.emnlp-industry.255](https://aclanthology.org/2026.emnlp-industry.255/) |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                         | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)       |
| Learning to Translate by Translating: Stabilizing the Dual Loop via Semantic-Aware Self-Evolution                                             | [2026.findings-acl.723](https://aclanthology.org/2026.findings-acl.723/)     |
| PressMint: Towards Interoperable Corpora of Historical Newspapers                                                                             | [2026.pressmint-1.1](https://aclanthology.org/2026.pressmint-1.1/)           |
| Stage-Aware Cross-Lingual Transfer for Faroese ASR: When and Which Languages Matter                                                           | [2026.speakable-1.17](https://aclanthology.org/2026.speakable-1.17/)         |
| Syntax is the Key to Semantics: Combining Universal Dependencies and Abstract Meaning Representation                                          | [2026.udw-1.27](https://aclanthology.org/2026.udw-1.27/)                     |
| Findings of the WMT26 Shared Task on Automated Translation Quality Evaluation Systems: Compact Open Models are Competitive Quality Evaluators | [2026.wmt-main.49](https://aclanthology.org/2026.wmt-main.49/)               |
| Isolated Sign Language Recognition for Icelandic Sign Language: Experiments in a Low-resource Setting                                         | [2026.wslp-1.9](https://aclanthology.org/2026.wslp-1.9/)                     |

{% endraw %}
