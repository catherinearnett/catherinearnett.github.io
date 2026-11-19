---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ceb.html
---
{% raw %}
# So you want to work on Cebuano?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ceb`

**Language family:** **Austronesian** › Malayo-Polynesian › Greater Central Philippine › … › Bisayan ([Glottolog](https://glottolog.org/resource/languoid/id/cebu1242))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 28.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Cebuano look and sound like?

**Written (Cebuano)**, sample text from [Omniglot](https://www.omniglot.com/writing/cebuano.htm):

> Ang tanang katawhan gipakatawo nga may kagawasan ug managsama sa kabililhon. Sila gigasahan sa salabutan ug tanlag og mag-ilhanay isip managsoon sa usa'g-usa diha sa diwa sa ospiritu.
> A recording of this text by Jicko Racines
> Another recording of this text by Josh Montarde

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_cebuano2.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ceb/) has 1 video of Cebuano speakers. Watch [Presi speaking Bisaian](https://wikitongues.org/videos/presi_20140316_ceb/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,116,261 articles in ceb.wikipedia; 245 active users. This is about the same amount as English and ranks 2 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                          |
| Common Crawl           | 40,610 pages per crawl on average, which is 0.0019% of the crawl (2026). This is ~1/21,953 of English data and ranks 79 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 0.28 GB (ceb_Latn 0.28 GB), equivalent to ≈0.25 GB of English after byte-premium scaling; 0.65 GB removed by filtering. This is ~1/189,680 of English data and ranks 95 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.67 GB (ceb_Latn 0.67 GB) (rank 82 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                          |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 208 sentences / 1,412 tokens in total: [UD_Cebuano-GJA](https://github.com/UniversalDependencies/UD_Cebuano-GJA) (208 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 97 lemmas, 618 inflected forms ([unimorph/ceb](https://github.com/unimorph/ceb))                                                                                                                                     |
| Wikidata labels        | 8,320,870 Wikidata items have a label in Cebuano. (Wikidata codes (labels): ceb (8,320,870))                                                                                                                         |
| Wordnets               | **None found**                                                                                                                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 16,040,734 sentence pairs with English across 10 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (14,768,997), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (962,549), [XLEnt](https://opus.nlpl.eu/XLEnt) (207,637), [bible-uedin](https://opus.nlpl.eu/bible-uedin) (62,172), [WikiMatrix](https://opus.nlpl.eu/WikiMatrix) (29,062). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([cebulb](https://ebible.org/details.php?id=cebulb), by-sa 4.0).                                                                                                                                                                                                                                     |
| Tatoeba                                                                                  | 1,893 sentences, 789 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ceb/none)).                                                                                                                                                                                                                      |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                     |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.954 (P 0.963, R 0.948, FPR 2.35e-04) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.781).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.948 | 0.954 | 0.000 | ✓                |
| fasttext     |       0.688 |    0.959 | 0.781 | 0.004 | ✓                |
| OpenLID-v2   |       0.679 |    0.968 | 0.776 | 0.005 | ✓                |
| commonlingua |       0.708 |    0.761 | 0.717 | 0.003 | ✓                |
| funlangid    |       0.859 |    0.623 | 0.711 | 0.001 | ✓                |
| cld2         |       0.704 |    0.737 | 0.690 | 0.003 | ✓                |
| pyfranc      |       0.749 |    0.664 | 0.688 | 0.002 | ✓                |
| cld3         |       0.432 |    0.872 | 0.566 | 0.013 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.913 |    0.800 | 0.853 |
| Wikipedia | 300 |       0.958 |    0.990 | 0.974 |
| UDHR-LID  |  59 |       0.983 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Cebuano to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Cebuano *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Cebuano and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Cebuano has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Cebuano?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Cebuano (and whether the model is exclusively tagged for Cebuano or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **81** text-generation models are explicitly tagged for Cebuano (24 original uploads, 57 fine-tunes/quantisations/merges).
- **21** are tagged *only* for Cebuano.
- Including tags inherited from base models: **114**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █████                |
|   2023 |        4 | ███                  |
|   2024 |       15 | ███████████          |
|   2025 |       28 | ████████████████████ |
|   2026 |       27 | ███████████████████  |

### Largest models tagged for Cebuano

| model                                                                             | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                 | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B     |
| [KYUNGYONG/Kyro-n1-14B-4bit](https://huggingface.co/KYUNGYONG/Kyro-n1-14B-4bit)   | 14.8B        |                   29 |   2025 | open-neo/Kyro-n1-14B |
| [aayanmishra-ml/Athena-3-14B](https://huggingface.co/aayanmishra-ml/Athena-3-14B) | 14.0B        |                   29 |   2024 | Qwen/Qwen2.5-14B     |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                             | 13.9B        |                   92 |   2024 | —                    |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                   | 13.9B        |                   92 |   2022 | —                    |

### Largest models tagged *only* for Cebuano

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-ceb-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-ceb-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-ceb-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-ceb](https://huggingface.co/ptrdvn/kakugo-3B-ceb)                                 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-ceb-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-ceb-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-ceb-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Cebuano.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                                      |   # test items | construction                                  |
|:-------------------------|:------------------------------|:---------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                        |          9,088 | Machine translation (GPT-4o, auto-checked)    |
| 3. Commonsense reasoning | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) |            103 | MT + human post-editing                       |
| 3. Commonsense reasoning | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                       |          1,332 | Machine translation (GPT-4o, auto-checked)    |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                |            900 | Human translation (professional)              |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                   |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)         |            424 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Cebuano datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Cebuano? Does it make sense to train one?
  - ~0.60 GB English-equivalent text ≈ 0.15B tokens, enough for a compute-optimal model of ~7.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Cebuano-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 28 of ~18,498 papers (0.15%) (rank 115 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Cebuano

Here are up to ten papers published in 2026 that mention Cebuano. None of the 28 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                               | paper                                                                        |
|:----------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| DeepSEA: A Multilingual Evaluation Benchmark for Southeast Asia                                     | [2026.emnlp-main.1](https://aclanthology.org/2026.emnlp-main.1/)             |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)   |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                    | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?          | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)               |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                 | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP          | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)                 |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings      | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                 |
| Whisper-Style Speech Encoders Align Semantically Beyond Phonetic Cues                               | [2026.mrl-1.32](https://aclanthology.org/2026.mrl-1.32/)                     |
| Pag-refuse: Safety Alignment Transfers Unevenly to Tagalog and Taglish                              | [2026.mrl-1.41](https://aclanthology.org/2026.mrl-1.41/)                     |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                               | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)         |

{% endraw %}
