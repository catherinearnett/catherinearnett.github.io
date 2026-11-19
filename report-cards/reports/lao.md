---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lao.html
---
{% raw %}
# So you want to work on Lao?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lao`

**Language family:** **Tai-Kadai** › Kam-Tai › Daic-Beic › … › Lao-Thai ([Glottolog](https://glottolog.org/resource/languoid/id/laoo1244))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Laoo`

**Speakers:** about 5.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Laos

**Status:** Official language


## What does Lao look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/lao.htm):

> Transliteration
> Manut thuk khôn kœ̄t māmīkẏat sâk sī, sitthi, sēlī phôp læ khwôm smœ̄ phôp thàw thẏam kân. Thuk thuk khôn mīhēt phôn læ khwômkhit khwôm hian swàn tôw khɔ̄̄ṅ phai khɔ̄ṅ mân, tǣ̀vồ manut thuk thuk khôn khwan paphʉt tàṁ kân khʉ̄ kân kâp pianốy nɔ̄́ṅ kân.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_lao.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/lao/) has 3 videos of Lao speakers. Watch [Maly speaking Lao](https://wikitongues.org/videos/maly_20191108_lao/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 5,651 articles in lo.wikipedia; 59 active users. This is ~1/1,335 of English data and ranks 119 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                     |
| Common Crawl           | 111,108 pages per crawl on average, which is 0.0051% of the crawl (2026). This is ~1/8,024 of English data and ranks 64 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 0.60 GB (lao_Laoo 0.60 GB), equivalent to ≈0.22 GB of English after byte-premium scaling; 0.44 GB removed by filtering. This is ~1/89,341 of English data and ranks 77 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 1.58 GB (lao_Laoo 1.58 GB) (rank 66 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                         |
|:-----------------------|:------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                      |
| UniMorph               | **None found**                                                                      |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._      |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=231), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** commonlingua — F1 0.997 (P 1.000, R 0.994, FPR 0.00e+00) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| commonlingua |       1.000 |    0.994 | 0.997 | 0.000 | ✓                |
| py3langid    |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| cld2         |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.989 | 0.995 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.988 | 0.994 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.982 | 0.991 | 0.000 | ✗                |
| cld3         |       1.000 |    0.951 | 0.974 | 0.000 | ✓                |
| funlangid    |       0.999 |    0.913 | 0.952 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (commonlingua) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.970 | 0.985 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 231 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lao to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lao *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lao and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Lao has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Lao?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lao (and whether the model is exclusively tagged for Lao or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **268** text-generation models are explicitly tagged for Lao (71 original uploads, 197 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Lao.
- Including tags inherited from base models: **523**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       13 | ███                  |
|   2024 |       67 | ██████████████       |
|   2025 |       96 | ████████████████████ |
|   2026 |       85 | ██████████████████   |

### Largest models tagged for Lao

| model                                                                                                                         | parameters   |   # languages tagged |   year | derivative of                                      |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                     | 1.9T         |                  143 |   2025 | —                                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                         | 856.0B       |                  143 |   2025 | —                                                  |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B-Base) | 120.7B       |                   10 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                                                             | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B                                   |
| [aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF](https://huggingface.co/aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF)                 | 70.6B        |                   11 |   2024 | meta-llama/Llama-3.1-70B                           |

### Largest models tagged *only* for Lao

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-lao-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-lao-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-lao-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-lao](https://huggingface.co/ptrdvn/kakugo-3B-lao)                                 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-lao-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-lao-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-lao-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_33 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Lao.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      |                               | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          |            854 | Human translation via English pivot                              |
| Machine translation      |                               | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              |          1,012 | Human translation (professional, from English Wikimedia sources) |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English)                   |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            166 | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lao datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lao? Does it make sense to train one?
  - ~0.58 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Lao-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 56 of ~18,498 papers (0.30%) (rank 82 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Lao
- Because 'Lao' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers published in 2026 that mention Lao. None of the 56 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                | paper                                                                          | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| LaoBench: A Large-Scale Multidimensional Lao Benchmark for Large Language Models                                     | [2026.acl-long.1088](https://aclanthology.org/2026.acl-long.1088/)             | body only      |
| DeepSEA: A Multilingual Evaluation Benchmark for Southeast Asia                                                      | [2026.emnlp-main.1](https://aclanthology.org/2026.emnlp-main.1/)               | body only      |
| TIPA: Typologically Informed Parameter Aggregation                                                                   | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     | body only      |
| Which Language Should a Skeleton Speak? Language Choices in Multilingual Reasoning                                   | [2026.findings-emnlp.1500](https://aclanthology.org/2026.findings-emnlp.1500/) | body only      |
| OpenSeal: Good, Fast, and Cheap Construction of an Open-Source Southeast Asian LLM via Parallel Data                 | [2026.findings-emnlp.2205](https://aclanthology.org/2026.findings-emnlp.2205/) | body only      |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation         | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                              | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   | body only      |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                     | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   | body only      |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                       | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   | body only      |
| One Vector, Thirty-Eight Languages: Benchmark-Derived Anti-Sycophancy Steering Works Worst Where Sycophancy Is Worst | [2026.oracle-main.12](https://aclanthology.org/2026.oracle-main.12/)           | body only      |

{% endraw %}
