---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/haw.html
---
{% raw %}
# So you want to work on Hawaiian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `haw`

**Language family:** **Austronesian** › Malayo-Polynesian › Eastern Malayo-Polynesian › … › East Polynesian Proximal ([Glottolog](https://glottolog.org/resource/languoid/id/hawa1245))

**Endangerment:** 🔴 moribund (level 4 of 6 on Glottolog’s scale; source: ElCat: Severely Endangered (100% certain))

**Writing systems:** `Latn`

**Speakers:** about 30,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** United States

**Status:** Regional official language


## What does Hawaiian look and sound like?

**Written (Hawaiian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/hawaiian.htm):

> Hānau kū'oko'a 'ia nā kānaka apau loa, a ua kau like ka hanohano a me nā pono kīvila ma luna o kākou pākahi. Ua ku'u mai ka no'ono'o pono a me ka 'ike pono ma luna o kākou, no laila, e aloha kākou kekahi i kekahi.
> A recording of this text by Tamati Taylor

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_hawaiian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/haw/) has 3 videos of Hawaiian speakers. Watch [Awapuhi speaking Niʻihau, ʻŌlelo Niʻihau, ʻŌlelo Matuahine](https://wikitongues.org/videos/awapuhi_20250626_haw/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,901 articles in haw.wikipedia; 23 active users. This is ~1/2,601 of English data and ranks 131 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 17,520 pages per crawl on average, which is 0.0008% of the crawl (2026). This is ~1/50,885 of English data and ranks 91 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 0.13 GB (haw_Latn 0.13 GB), equivalent to ≈0.12 GB of English after byte-premium scaling; 68.0 MB removed by filtering. This is ~1/414,981 of English data and ranks 106 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.33 GB (haw_Latn 0.33 GB) (rank 102 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                    |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([haw1868](https://ebible.org/details.php?id=haw1868), Public Domain). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, cld3, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=166), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.983 (P 1.000, R 0.967, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.904).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.967 | 0.983 | 0.000 | ✓                |
| pyfranc      |       0.956 |    0.866 | 0.904 | 0.000 | ✓                |
| cld2         |       0.962 |    0.851 | 0.892 | 0.000 | ✓                |
| commonlingua |       0.777 |    0.892 | 0.818 | 0.002 | ✓                |
| funlangid    |       0.870 |    0.769 | 0.804 | 0.001 | ✓                |
| cld3         |       0.391 |    0.934 | 0.512 | 0.028 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 166 |       1.000 |    0.916 | 0.956 |
| Wikipedia | 300 |       1.000 |    0.987 | 0.993 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hawaiian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hawaiian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hawaiian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Hawaiian has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Hawaiian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hawaiian (and whether the model is exclusively tagged for Hawaiian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **36** text-generation models are explicitly tagged for Hawaiian (17 original uploads, 19 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Hawaiian.
- Including tags inherited from base models: **50**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ███████████          |
|   2023 |        4 | ██████               |
|   2024 |        6 | █████████            |
|   2025 |        6 | █████████            |
|   2026 |       13 | ████████████████████ |

### Largest models tagged for Hawaiian

| model                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                 | 13.9B        |                   92 |   2024 | —               |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)       | 13.9B        |                   92 |   2022 | —               |
| [bigscience/mt0-xxl-mt](https://huggingface.co/bigscience/mt0-xxl-mt) | 13.9B        |                   92 |   2022 | —               |
| [bigscience/mt0-xxl-p3](https://huggingface.co/bigscience/mt0-xxl-p3) | 13.9B        |                   92 |   2022 | —               |
| [akoksal/muri-101](https://huggingface.co/akoksal/muri-101)           | 12.9B        |                   90 |   2024 | google/mt5-xxl  |

### Largest models tagged *only* for Hawaiian

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-haw-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-haw-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-haw-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-haw-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

_8 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Hawaiian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                             |   # test items | construction                                  |
|:-------------------------|:-------------------|:----------------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | PIQA               | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                        |
| 3. Commonsense reasoning | PIQA               | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        |            103 | MT + human post-editing                       |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          1,903 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                |             93 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Hawaiian isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hawaiian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hawaiian? Does it make sense to train one?
  - ~0.29 GB English-equivalent text ≈ 0.07B tokens, enough for a compute-optimal model of ~3.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hawaiian-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 41 of ~18,498 papers (0.22%) (rank 101 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Hawaiian

Here are up to ten papers published in 2026 that mention Hawaiian. None of the 41 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                                   | paper                                                                        |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Controlling Distributional Bias in Multi-Round LLM Generation via KL-Optimized Fine-Tuning                                                                              | [2026.acl-long.802](https://aclanthology.org/2026.acl-long.802/)             |
| Developing A Hawaiian Corpus Toolkit for Data-Driven Language Learning                                                                                                  | [2026.computel-1.18](https://aclanthology.org/2026.computel-1.18/)           |
| Voice Activation Detection for Transcription of Indigenous Languages                                                                                                    | [2026.computel-1.19](https://aclanthology.org/2026.computel-1.19/)           |
| Kinship Data Benchmark for Multi-hop Reasoning                                                                                                                          | [2026.findings-emnlp.274](https://aclanthology.org/2026.findings-emnlp.274/) |
| Decoupled Analysis-Judging: An Automated Creativity Evaluator Using LLMs in Complex Multi-step Creativity Tasks                                                         | [2026.findings-emnlp.816](https://aclanthology.org/2026.findings-emnlp.816/) |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                                                                                     | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)               |
| Diacritic Restoration for Low-Resource Indigenous Languages: Case Study with Bribri and Cook Islands Māori                                                              | [2026.lrec-1.276](https://aclanthology.org/2026.lrec-1.276/)                 |
| A Modern Online Learning Platform for ʻŌlelo Hawaiʻi Classrooms                                                                                                         | [2026.lrec-1.277](https://aclanthology.org/2026.lrec-1.277/)                 |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                                          | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                 |
| Outlining an Experiment Design of Gamifying Language Learning in Low-Resource Contexts: Kurdish Learning in University, Language Courses, and on Web-Based Applications | [2026.multilll-1.10](https://aclanthology.org/2026.multilll-1.10/)           |

{% endraw %}
