---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/som.html
---
{% raw %}
# So you want to work on Somali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `som`

**Language family:** **Afro-Asiatic** › Cushitic › East Cushitic › … › Eastern Omo-Tana ([Glottolog](https://glottolog.org/resource/languoid/id/soma1255))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 18.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Ethiopia, Somalia

**Status:** Official language


## What does Somali look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/somali.htm):

> Aadanaha dhammaantiis wuxuu dhashaa isagoo xor ah kana siman xagga sharafta iyo xuquuqada Waxaa Alle (Ilaah) siiyay aqoon iyo wacyi, waana in qof la arkaa qofka kale ula dhaqmaa si walaaltinimo ah.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) [top]

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_so.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/som/) has 3 videos of Somali speakers. Watch [Sedday speaking English, Somali, Swahili](https://wikitongues.org/videos/sedday_20150217_eng-som-swh/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,177 articles in so.wikipedia; 95 active users. This is ~1/532 of English data and ranks 94 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 120,016 pages per crawl on average, which is 0.0056% of the crawl (2026). This is ~1/7,428 of English data and ranks 62 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 1.01 GB (som_Latn 1.01 GB), equivalent to ≈0.71 GB of English after byte-premium scaling; 1.79 GB removed by filtering. This is ~1/52,955 of English data and ranks 71 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 1.71 GB (som_Latn 1.71 GB) (rank 64 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

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

| Resource                                                                                 | What exists                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                        |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([som](https://ebible.org/details.php?id=som), by-nc-nd 4.0).                                                                                                              |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_so) en → so: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_so) en → so: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=164), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.980 (P 0.985, R 0.975, FPR 9.57e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.976).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.985 |    0.975 | 0.980 | 0.000 | ✓                |
| GlotLID      |       0.977 |    0.978 | 0.976 | 0.000 | ✓                |
| pyfranc      |       0.945 |    0.922 | 0.930 | 0.000 | ✓                |
| funlangid    |       0.967 |    0.886 | 0.916 | 0.000 | ✓                |
| fasttext     |       0.817 |    0.974 | 0.870 | 0.003 | ✓                |
| commonlingua |       0.768 |    0.901 | 0.815 | 0.003 | ✓                |
| OpenLID-v2   |       0.737 |    0.995 | 0.814 | 0.007 | ✓                |
| py3langid    |       0.636 |    0.990 | 0.740 | 0.014 | ✓                |
| cld3         |       0.335 |    0.972 | 0.477 | 0.053 | ✓                |
| AfroLID      |       0.237 |    0.920 | 0.338 | 0.176 | ✓                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 164 |       0.936 |    0.890 | 0.912 |
| Wikipedia | 300 |       0.993 |    0.960 | 0.976 |
| UDHR-LID  |  57 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Somali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Somali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Somali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Somali has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Somali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Somali (and whether the model is exclusively tagged for Somali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Somali (52 original uploads, 75 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Somali.
- Including tags inherited from base models: **189**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ██                   |
|   2023 |        5 | ██                   |
|   2024 |       21 | ███████              |
|   2025 |       36 | ████████████         |
|   2026 |       58 | ████████████████████ |

### Largest models tagged for Somali

| model                                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                         |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                       | 1.9T         |                  143 |   2025 | —                                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                           | 856.0B       |                  143 |   2025 | —                                     |
| [frankmorales2020/mixtral-8x22b-instruct-v0.1-topo-cbp-GGUF](https://huggingface.co/frankmorales2020/mixtral-8x22b-instruct-v0.1-topo-cbp-GGUF) | 140.6B       |                    2 |   2026 | mistralai/Mixtral-8x22B-Instruct-v0.1 |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                                                           | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B                      |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)                                                                 | 14.8B        |                   21 |   2026 | Qwen/Qwen3-14B-Base                   |

### Largest models tagged *only* for Somali

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-som-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-som-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [boore1/SOMA-S1](https://huggingface.co/boore1/SOMA-S1)                                                 | 126.2M       |                    1 |   2026 | —                    |
| [alphaedge-ai/gemma-3-270m-it-som-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-som-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |
| [tacab/somali-agriculture](https://huggingface.co/tacab/somali-agriculture)                             | 7.1M         |                    1 |   2025 | —                    |

_34 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Somali.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                              |   # test items | construction                                             |
|:------------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                |         14,042 | Machine translation (Google Translate)                   |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English)           |
| Machine translation           |                               | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              |          2,100 | Human translation (professional/volunteer, from English) |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              5 | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_so) (training data)   | en → so                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_so) (training data) | en → so                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Somali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Somali? Does it make sense to train one?
  - ~1.20 GB English-equivalent text ≈ 0.30B tokens, enough for a compute-optimal model of ~15.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Somali-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 65 of ~18,498 papers (0.35%) (rank 75 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Somali

Here are up to ten papers published in 2026 that mention Somali. None of the 65 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     | body only      |
| ConRAS: Contrastive In-context Learning Framework for Retrieval-Augmented Summarization                                                       | [2026.findings-eacl.255](https://aclanthology.org/2026.findings-eacl.255/)     | body only      |
| SEC: Selective Embedding Correction for Cross-Lingual Transfer in Low-Resource Languages                                                      | [2026.findings-emnlp.1033](https://aclanthology.org/2026.findings-emnlp.1033/) | body only      |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) | body only      |
| Before the First Token: Jailbreak Detection with Attention Probes                                                                             | [2026.findings-emnlp.2242](https://aclanthology.org/2026.findings-emnlp.2242/) | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   | body only      |
| Comparing Approaches to Automatic Summarization in Less-Resourced Languages                                                                   | [2026.lrec-1.270](https://aclanthology.org/2026.lrec-1.270/)                   | body only      |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   | body only      |
| Beyond Majority Voting: Agreement-Based Clustering to Model Annotator Perspectives in Subjective NLP Tasks                                    | [2026.tacl-1.61](https://aclanthology.org/2026.tacl-1.61/)                     | body only      |
| AmharicStoryQA: A Multicultural Story Question Answering Benchmark in Amharic                                                                 | [2026.winlp-main.3](https://aclanthology.org/2026.winlp-main.3/)               | body only      |

{% endraw %}
