---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hrv.html
---
{% raw %}
# So you want to work on Croatian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hrv` · macrolanguage `hbs` (also listed as: Burgenland Croatian)

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Eastern Herzegovinian Shtokavian. Glottolog treats Croatian Standard as a variety of Serbian-Croatian-Bosnian ([Glottolog](https://glottolog.org/resource/languoid/id/croa1245))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (40% certain))

**Writing systems:** `Latn`

**Speakers:** about 6.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Austria, Bosnia and Herzegovina, Croatia

**Status:** Regional official language; Official language


## What does Croatian look and sound like?

**Written (Croatian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/croatian.htm):

> Sva ljudska bića rađaju se slobodna i jednaka u
> dostojanstvu i pravima. Ona su obdarena razumom i sviješću
> i trebaju jedna prema drugima postupati u duhu bratstva.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_hr.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hrv/) has 3 videos of Croatian speakers. Watch [Nela speaking Croatian](https://wikitongues.org/videos/nela_20180726_hrv/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 236,370 articles in hr.wikipedia; 1,007 active users. This is ~1/32 of English data and ranks 41 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 4,662,570 pages per crawl on average, which is 0.2163% of the crawl (2026). This is ~1/191 of English data and ranks 30 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                             |
| FineWeb                | 17.60 GB (hrv_Latn 17.59 GB), equivalent to ≈17.78 GB of English after byte-premium scaling; 51.73 GB removed by filtering. This is ~1/3,036 of English data and ranks 37 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 7.20 GB (hrv_Latn 7.20 GB) (rank 32 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                  |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 9,010 sentences / 199,409 tokens in total: [UD_Croatian-SET](https://github.com/UniversalDependencies/UD_Croatian-SET) (9,010 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                               |
| Wikidata labels        | 1,965,490 Wikidata items have a label in Croatian. (Wikidata codes (labels): hr (1,965,490))                                                                                                                                 |
| Wordnets               | [Croatian Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-hr-1.4.tar.xz): 23,120 synsets, 29,089 words, 47,900 senses; licence: https://creativecommons.org/licenses/by/3.0/.                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 187,496,976 sentence pairs with English across 89 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (57,609,799), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (26,377,878), [HPLT](https://opus.nlpl.eu/HPLT) (26,377,878), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (18,797,643), [NLLB](https://opus.nlpl.eu/NLLB) (18,797,643). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([hrv](https://ebible.org/details.php?id=hrv), Public Domain).                                                                                                                                                                                                                                                      |
| Tatoeba                                                                                  | 6,582 sentences, 3,321 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/hrv/none)).                                                                                                                                                                                                                                   |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                     |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.705 (P 0.637, R 0.819, FPR 2.87e-03) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.669).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.637 |    0.819 | 0.705 | 0.003 | ✓                |
| OpenLID-v2   |       0.575 |    0.834 | 0.669 | 0.006 | ✓                |
| fasttext     |       0.500 |    0.878 | 0.628 | 0.008 | ✓                |
| cld2         |       0.531 |    0.627 | 0.574 | 0.005 | ✓                |
| py3langid    |       0.499 |    0.695 | 0.574 | 0.007 | ✓                |
| commonlingua |       0.496 |    0.577 | 0.528 | 0.005 | ✓                |
| cld3         |       0.445 |    0.605 | 0.506 | 0.009 | ✓                |
| funlangid    |       0.401 |    0.530 | 0.450 | 0.007 | ✓                |
| pyfranc      |       0.484 |    0.360 | 0.405 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.577 |    0.487 | 0.528 |
| UDHR-LID  |  58 |       0.479 |    0.983 | 0.644 |
| NTREX     | 300 |       0.651 |    0.840 | 0.734 |
| FLORES    | 300 |       0.713 |    0.860 | 0.779 |
| Wikipedia | 300 |       0.764 |    0.927 | 0.837 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Croatian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Croatian *and* from closely related languages that might be confused with it. Likely confusions to include: Bosnian (`bos`), Montenegrin (`cnr`), Serbian (`srp`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Croatian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Croatian has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Croatian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Croatian (and whether the model is exclusively tagged for Croatian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **441** text-generation models are explicitly tagged for Croatian (114 original uploads, 327 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Croatian.
- Including tags inherited from base models: **890**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        2 | █                    |
|   2023 |       15 | █                    |
|   2024 |       87 | █████████            |
|   2025 |      133 | █████████████        |
|   2026 |      204 | ████████████████████ |

### Largest models tagged for Croatian

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [CRD716/ggml-LLaMa-65B-quantized](https://huggingface.co/CRD716/ggml-LLaMa-65B-quantized)             | 65.0B        |                   20 |   2023 | —                                      |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Croatian

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [Shome/croguana-RC2](https://huggingface.co/Shome/croguana-RC2)                                     | 7.2B         |                    1 |   2025 | gordicaleksa/YugoGPT |
| [alphaedge-ai/Qwen3.5-4B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-hrv-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-hrv-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-hrv-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-hrv-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-hrv-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |

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

**17** benchmark datasets in the survey include Croatian (plus 1 labelled with the macrolanguage `hbs`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | construction                                   |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 71             | Treebank-based (automatic)                     |
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                     | 3,286          | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning      | COPA                          | [COPA-HR](http://hdl.handle.net/11356/1404)                                                         | 500            | Human translation                              |
| 3. Commonsense reasoning      | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning      | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,471          | Machine translation (GPT-3.5-turbo)            |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning      | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,879          | Native (high-school exams)                     |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)           |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 10,498         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Croatian has been part of the WMT translation task in **1** year (2022).

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-hr_HR) | en → hr_HR                        | 998 segments           | ✅                |
| [WMT22 general task](https://www2.statmt.org/wmt22/)                      | English → Croatian                | 1,671 segments         | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Croatian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Croatian? Does it make sense to train one?
  - ~17.78 GB English-equivalent text ≈ 4.44B tokens, enough for a compute-optimal model of ~222.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Croatian-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 129 of ~18,498 papers (0.70%) (rank 49 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Croatian

Here are up to ten papers published in 2026 that mention Croatian. None of the 129 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                       | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Different types of syntactic agreement recruit the same units within large language models                                                  | [2026.acl-long.7](https://aclanthology.org/2026.acl-long.7/)                   |
| One Workflow Does Not Fit All Relations: A System Description for the AKBC 2026 LM-KBC Shared Task                                          | [2026.akbc-1.41](https://aclanthology.org/2026.akbc-1.41/)                     |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                                                    | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)           |
| Sequence Repetition Enhances Token Embeddings and Improves Sequence Labeling with Decoder-only Language Models                              | [2026.findings-eacl.339](https://aclanthology.org/2026.findings-eacl.339/)     |
| What Makes Blood Thicker than Water: Related Word Discrimination in Romance Languages from a Multi-dimensional Perspective                  | [2026.findings-emnlp.1916](https://aclanthology.org/2026.findings-emnlp.1916/) |
| From Oral History to Structured Data: The MalachNER Dataset                                                                                 | [2026.htres-2.7](https://aclanthology.org/2026.htres-2.7/)                     |
| Exploring Social Bias in Slovenia: The EEC-SL Dataset                                                                                       | [2026.lrec-1.318](https://aclanthology.org/2026.lrec-1.318/)                   |
| Pluralistic Annotation of Cultural Weaponization on Wikipedia: A Multi-Annotator Case Study across Ukraine and Armenia                      | [2026.pandora-1.5](https://aclanthology.org/2026.pandora-1.5/)                 |
| Supercharging Agenda Setting Research: The ParlaCAP Dataset of 28 European Parliaments and a Scalable Multilingual LLM-Based Classification | [2026.politicalnlp-1.11](https://aclanthology.org/2026.politicalnlp-1.11/)     |
| OpenLID-v3: Improving the Precision of Closely Related Language Identification – An Experience Report                                       | [2026.vardial-1.23](https://aclanthology.org/2026.vardial-1.23/)               |

{% endraw %}
