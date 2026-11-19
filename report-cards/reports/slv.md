---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/slv.html
---
{% raw %}
# So you want to work on Slovene?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `slv`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Western South Slavic ([Glottolog](https://glottolog.org/resource/languoid/id/slov1268))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 2.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Austria, Italy, Slovenia

**Status:** Regional official language; Official language


## What does Slovene look and sound like?

**Written (Slovenian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/slovene.htm):

> Vsi ljudje se rodijo svobodni in imajo enako dostojanstvo in enake pravice.
> Obdarjeni so z razumom in vestjo in bi morali ravnati drug z drugim kakor bratje.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_slovenian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/slv/) has 1 video of Slovene speakers. Watch [Matic speaking Slovene](https://wikitongues.org/videos/matic_20151010_slv/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 199,510 articles in sl.wikipedia; 632 active users. This is ~1/38 of English data and ranks 44 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 3,147,200 pages per crawl on average, which is 0.1461% of the crawl (2026). This is ~1/283 of English data and ranks 33 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 20.70 GB (slv_Latn 20.70 GB), equivalent to ≈21.29 GB of English after byte-premium scaling; 20.04 GB removed by filtering. This is ~1/2,581 of English data and ranks 33 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 1.52 GB (slv_Latn 1.52 GB) (rank 67 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 19,556 sentences / 365,490 tokens in total: [UD_Slovenian-SSJ](https://github.com/UniversalDependencies/UD_Slovenian-SSJ) (13,435 sentences), [UD_Slovenian-SST](https://github.com/UniversalDependencies/UD_Slovenian-SST) (6,121 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 2,535 lemmas, 60,110 inflected forms ([unimorph/slv](https://github.com/unimorph/slv))                                                                                                                                                                                                                                               |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                       |
| Wordnets               | [sloWNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-sl-1.4.tar.xz): 42,583 synsets, 40,340 words, 70,945 senses; licence: https://creativecommons.org/licenses/by-sa/3.0/.                                                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.967 (P 0.955, R 0.981, FPR 3.66e-04) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.932).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.955 |    0.981 | 0.967 | 0.000 | ✓                |
| fasttext     |       0.892 |    0.979 | 0.932 | 0.001 | ✓                |
| cld2         |       0.990 |    0.840 | 0.901 | 0.000 | ✓                |
| py3langid    |       0.814 |    0.953 | 0.872 | 0.002 | ✓                |
| cld3         |       0.803 |    0.913 | 0.850 | 0.003 | ✓                |
| OpenLID-v2   |       0.775 |    0.964 | 0.839 | 0.003 | ✓                |
| commonlingua |       0.877 |    0.806 | 0.837 | 0.001 | ✓                |
| funlangid    |       0.724 |    0.732 | 0.720 | 0.003 | ✓                |
| pyfranc      |       0.830 |    0.641 | 0.715 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.844 |    0.920 | 0.880 |
| Wikipedia | 300 |       0.964 |    0.990 | 0.977 |
| NTREX     | 300 |       0.987 |    0.993 | 0.990 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Slovene to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Slovene *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Slovene and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Slovene?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Slovene (and whether the model is exclusively tagged for Slovene or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **497** text-generation models are explicitly tagged for Slovene (125 original uploads, 372 fine-tunes/quantisations/merges).
- **34** are tagged *only* for Slovene.
- Including tags inherited from base models: **957**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       18 | ██                   |
|   2024 |       96 | █████████            |
|   2025 |      157 | ██████████████       |
|   2026 |      217 | ████████████████████ |

### Largest models tagged for Slovene

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [CRD716/ggml-LLaMa-65B-quantized](https://huggingface.co/CRD716/ggml-LLaMa-65B-quantized)             | 65.0B        |                   20 |   2023 | —                                      |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Slovene

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [Pucciami/vaccination-media-5c-qwen3-32b-lora](https://huggingface.co/Pucciami/vaccination-media-5c-qwen3-32b-lora)   | 32.0B        |                    1 |   2026 | Qwen/Qwen3-32B            |
| [DGurgurov/llama-3.1-8b-slv_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-slv_latn)                             | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-slv_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-slv_latn)                         | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [Pucciami/vaccination-media-5c-apertus-8b-lora](https://huggingface.co/Pucciami/vaccination-media-5c-apertus-8b-lora) | 8.0B         |                    1 |   2026 | swiss-ai/Apertus-8B-2509  |
| [alphaedge-ai/Qwen3.5-4B-slv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-slv-32768)                         | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |

_52 tagged models have unknown parameter counts and are not ranked by size._

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

**20** benchmark datasets in the survey include Slovene.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                                 | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 168            | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 4,483          | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | WSC                           | [Slovene SuperGLUE WSC](http://hdl.handle.net/11356/1380)                                                               | 146            | Human translation                              |
| 3. Commonsense reasoning               | COPA                          | [COPA-SL](http://hdl.handle.net/11356/1380)                                                                             | 500            | Human translation                              |
| 3. Commonsense reasoning               | COPA                          | [DIALECT-COPA (COPA-SL-CER)](https://github.com/clarinsi/dialect-copa)                                                  | 500            | Human translation                              |
| 3. Commonsense reasoning               | HellaSwag                     | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                                    | —              | Machine translation (DeepL)                    |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (3 varieties/pairs) | 300            | Native                                         |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (3 varieties/pairs)        | 309            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                                | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                               | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                    |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 2,495          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sl_SI) | en → sl_SI                        | 998 segments           | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Slovene datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Slovene? Does it make sense to train one?
  - ~21.29 GB English-equivalent text ≈ 5.32B tokens, enough for a compute-optimal model of ~266.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Slovene-only model is 32.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,498 papers (0.31%) (rank 79 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Slovene

Here are up to ten papers published in 2026 that mention Slovene. None of the 57 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                              | paper                                                            |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| A Lightweight N-gram Approach to Abbreviation Expansion in Large Corpora                                                           | [2026.cawl-1.10](https://aclanthology.org/2026.cawl-1.10/)       |
| Environmental, Social and Governance Sentiment Analysis on Slovene News: A Novel Dataset and Models                                | [2026.fnp-1.5](https://aclanthology.org/2026.fnp-1.5/)           |
| Modeling the Human Lexicon under Temperature Variations: Linguistic Factors, Diversity and Typicality in LLM Word Associations     | [2026.lrec-1.179](https://aclanthology.org/2026.lrec-1.179/)     |
| PARSEME 2.0 Multilingual Corpus of Multiword Expressions                                                                           | [2026.lrec-1.378](https://aclanthology.org/2026.lrec-1.378/)     |
| A Large-Scale Instruction-Tuning Dataset and Models for Slovenian Vision-Language Tasks                                            | [2026.lrec-1.740](https://aclanthology.org/2026.lrec-1.740/)     |
| SemiAdapt: Semi-Supervised and Efficient LoRA-Based Domain Adaptation for Low-Resource Irish Machine Translation with Transformers | [2026.lrec-1.801](https://aclanthology.org/2026.lrec-1.801/)     |
| MorfFlex: Handling Rich Morphology                                                                                                 | [2026.lrec-1.899](https://aclanthology.org/2026.lrec-1.899/)     |
| Edition 2.0 of the PARSEME shared task on multilingual identification and paraphrasing of multiword expressions                    | [2026.mwe-1.33](https://aclanthology.org/2026.mwe-1.33/)         |
| What Persists across Web Crawls? Genre and News Topic Variation in South Slavic Web Corpora                                        | [2026.wac-1.5](https://aclanthology.org/2026.wac-1.5/)           |
| One Model, Five Tasks, Two RTX 3090 GPUs: The HSE System for the Sorbian Track of WMT26 Multitask LLMs with Limited Resources      | [2026.wmt-main.209](https://aclanthology.org/2026.wmt-main.209/) |

{% endraw %}
