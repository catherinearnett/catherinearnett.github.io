---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mlt.html
---
{% raw %}
# So you want to work on Maltese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mlt`

**Language family:** **Afro-Asiatic** › Semitic › West Semitic › … › Malta-Tunisian Arabic ([Glottolog](https://glottolog.org/resource/languoid/id/malt1254))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 470,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Malta

**Status:** Official language


## What does Maltese look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/maltese.htm):

> Il-bnedmin kollha jitwieldu ħielsa u ugwali fid-dinjità u d-drittijiet. Huma mogħnija bir-raġuni u bil-kuxjenza u għandhom inġibu ruħhom ma' xulxin bi spirtu ta' aħwa.
> A recording of this text by Sami Kleit

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_maltese.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mlt/) has 2 videos of Maltese speakers. Watch [Keith speaking Maltese](https://wikitongues.org/videos/keith_20200119_mlt/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 8,090 articles in mt.wikipedia; 43 active users. This is ~1/933 of English data and ranks 108 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 68,435 pages per crawl on average, which is 0.0032% of the crawl (2026). This is ~1/13,027 of English data and ranks 72 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                          |
| FineWeb                | 0.74 GB (mlt_Latn 0.74 GB), equivalent to ≈0.68 GB of English after byte-premium scaling; 5.36 GB removed by filtering. This is ~1/72,020 of English data and ranks 77 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 4.32 GB (mlt_Latn 4.32 GB) (rank 43 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 2,074 sentences / 44,162 tokens in total: [UD_Maltese-MUDT](https://github.com/UniversalDependencies/UD_Maltese-MUDT) (2,074 sentences). It has POS tags, dependency syntax, morphological features. |
| UniMorph               | 112 lemmas, 3,584 inflected forms ([unimorph/mlt](https://github.com/unimorph/mlt))                                                                                                                              |
| Wikidata labels        | 714,190 Wikidata items have a label in Maltese. (Wikidata codes (labels): mt (714,190))                                                                                                                          |
| Wordnets               | nan (size not listed).                                                                                                                                                                                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                        |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 31,659,275 sentence pairs with English across 46 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (14,798,113), [DGT](https://opus.nlpl.eu/DGT) (4,196,920), [HPLT](https://opus.nlpl.eu/HPLT) (2,434,798), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (2,434,798), [TildeMODEL](https://opus.nlpl.eu/TildeMODEL) (1,976,073). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                        |
| Tatoeba                                                                                  | 697 sentences, 646 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mlt/none)).                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                               |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.992, R 0.966, FPR 5.52e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.948).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.966 | 0.978 | 0.000 | ✓                |
| cld2         |       0.997 |    0.910 | 0.948 | 0.000 | ✓                |
| fasttext     |       0.939 |    0.955 | 0.942 | 0.000 | ✓                |
| py3langid    |       0.857 |    0.959 | 0.892 | 0.002 | ✓                |
| commonlingua |       0.898 |    0.870 | 0.867 | 0.001 | ✓                |
| pyfranc      |       0.960 |    0.771 | 0.830 | 0.000 | ✓                |
| funlangid    |       0.964 |    0.775 | 0.827 | 0.000 | ✓                |
| OpenLID-v2   |       0.702 |    0.961 | 0.773 | 0.006 | ✓                |
| cld3         |       0.501 |    0.931 | 0.610 | 0.020 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.981 |    0.850 | 0.911 |
| Wikipedia | 300 |       0.977 |    0.983 | 0.980 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Maltese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Maltese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Maltese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Maltese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Maltese (and whether the model is exclusively tagged for Maltese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **285** text-generation models are explicitly tagged for Maltese (65 original uploads, 220 fine-tunes/quantisations/merges).
- **28** are tagged *only* for Maltese.
- Including tags inherited from base models: **663**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        5 | █                    |
|   2024 |       81 | ██████████████       |
|   2025 |       78 | ██████████████       |
|   2026 |      114 | ████████████████████ |

### Largest models tagged for Maltese

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B                   |

### Largest models tagged *only* for Maltese

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-mlt_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-mlt_latn)           | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-mlt_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-mlt_latn)       | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [mayflowergmbh/Wiedervereinigung-7b](https://huggingface.co/mayflowergmbh/Wiedervereinigung-7b)     | 7.2B         |                    1 |   2024 | DRXD1000/Phoenix-7B       |
| [alphaedge-ai/Qwen3.5-4B-mlt-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-mlt-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [alphaedge-ai/gemma-3-4b-it-mlt-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mlt-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it      |

_23 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Maltese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)               |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            251 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Maltese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Maltese? Does it make sense to train one?
  - ~3.97 GB English-equivalent text ≈ 0.99B tokens, enough for a compute-optimal model of ~49.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Maltese-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,498 papers (0.31%) (rank 79 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Maltese

Here are up to ten papers published in 2026 that mention Maltese. None of the 57 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mem-Gallery: Benchmarking Multimodal Long-Term Conversational Memory for MLLM Agents                                                          | [2026.acl-long.1892](https://aclanthology.org/2026.acl-long.1892/)             |
| LEMUR: A Corpus for Robust Fine-Tuning of Multilingual Law Embedding Models for Retrieval                                                     | [2026.eacl-srw.18](https://aclanthology.org/2026.eacl-srw.18/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Dialects of Translationese Shape Language Model Learning                                                                                      | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| Balancing Fluency and Adherence: Hybrid Fallback Term Injection in Low-Resource Terminology Translation                                       | [2026.loresmt-1.6](https://aclanthology.org/2026.loresmt-1.6/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Assessing the Political Fairness of Multilingual LLMs: A Case Study Based on a 21-Way Multiparallel EuroParl Dataset                          | [2026.lrec-1.17](https://aclanthology.org/2026.lrec-1.17/)                     |
| Phonetic-based Ranking for Improved Pseudo-Labeling in Low-Resource ASR                                                                       | [2026.lrec-1.795](https://aclanthology.org/2026.lrec-1.795/)                   |
| Lost in Translation: Structured-Span Corruption in Machine-Translated Multilingual Web Corpora                                                | [2026.wac-1.9](https://aclanthology.org/2026.wac-1.9/)                         |
| North Small Translate: Advanced Cost-Effective Translation (Cohere CAT+)                                                                      | [2026.wmt-main.70](https://aclanthology.org/2026.wmt-main.70/)                 |

{% endraw %}
