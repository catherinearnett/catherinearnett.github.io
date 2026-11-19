---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/plt.html
---
{% raw %}
# So you want to work on Malagasy?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `plt` · macrolanguage `mlg`

**Language family:** **Austronesian** › Malayo-Polynesian › Basap-Greater Barito › … › Central-Eastern Malagasic ([Glottolog](https://glottolog.org/resource/languoid/id/plat1254))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 26.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `mlg`, so includes other varieties

**Official / recognised in:** Madagascar

**Status:** Official language


## What does Malagasy look and sound like?

**Written (Malagasy)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/malagasy.htm):

> Teraka afaka sy mitovy zo sy fahamendrehana ny olombelona rehetra. Samy
> manan-tsaina sy fieritreretana ka tokony hifampitondra ampirahalahiana.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_malagasy.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/plt/) has 4 videos of Malagasy speakers. Watch [Haingo speaking Plateau Malagasy](https://wikitongues.org/videos/haingo_20180904_plt/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 104,282 articles in mg.wikipedia; 67 active users. ⚠️ NB: recorded under the macrolanguage code `mlg`, which can include other varieties of Malagasy.                                                                                           |
| Common Crawl           | 95,715 pages per crawl on average, which is 0.0045% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `mlg`, which can include other varieties of Malagasy.                                                                     |
| FineWeb                | 0.39 GB (plt_Latn 0.39 GB), equivalent to ≈0.34 GB of English after byte-premium scaling; 0.29 GB removed by filtering. This is ~1/138,005 of English data and ranks 86 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.44 GB (plt_Latn 0.44 GB) (rank 97 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                         |
| UniMorph               | 159 lemmas, 644 inflected forms ([unimorph/mlg](https://github.com/unimorph/mlg)) ⚠️ Listed under the macrolanguage code `mlg`, so this may cover other varieties as well as Malagasy. |
| Wikidata labels        | 1,333,196 Wikidata items have a label in Malagasy. (Wikidata codes (labels): mg (1,333,196))                                                                                           |
| Wordnets               | **None found**                                                                                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 61,919 sentence pairs with English across 1 corpora; largest: [bible-uedin](https://opus.nlpl.eu/bible-uedin) (61,919).                                                                                                                                                                                             |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                         |
| Tatoeba                                                                                  | 74 sentences, 60 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mlg/none)). ⚠️ Listed under the macrolanguage code `mlg`, so this may cover other varieties as well as Malagasy.                                                                                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_mg) en → mg: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_mg) en → mg: size not listed ⚠️ Listed under the macrolanguage code `mlg`, so this may cover other varieties as well as Malagasy. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=74), UDHR-LID (n=53), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.970 (P 0.979, R 0.962, FPR 7.33e-05) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.968).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.979 |    0.962 | 0.970 | 0.000 | ✓                |
| GlotLID      |       0.995 |    0.945 | 0.968 | 0.000 | ✓                |
| py3langid    |       0.959 |    0.965 | 0.962 | 0.000 | ✓                |
| fasttext     |       0.951 |    0.978 | 0.962 | 0.000 | ✓                |
| cld2         |       0.988 |    0.927 | 0.954 | 0.000 | ✓                |
| pyfranc      |       0.908 |    0.938 | 0.919 | 0.001 | ✓                |
| commonlingua |       0.857 |    0.861 | 0.854 | 0.001 | ✓                |
| cld3         |       0.789 |    0.951 | 0.852 | 0.003 | ✓                |
| funlangid    |       0.939 |    0.757 | 0.836 | 0.000 | ✓                |
| AfroLID      |       0.944 |    0.711 | 0.810 | 0.002 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  74 |       0.893 |    0.905 | 0.899 |
| CommonLID | 300 |       1.000 |    0.913 | 0.955 |
| Wikipedia | 300 |       0.996 |    0.917 | 0.955 |
| UDHR-LID  |  53 |       0.964 |    1.000 | 0.981 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Malagasy to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Malagasy *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Malagasy and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Malagasy has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Malagasy?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Malagasy (and whether the model is exclusively tagged for Malagasy or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **148** text-generation models are explicitly tagged for Malagasy (48 original uploads, 100 fine-tunes/quantisations/merges).
- **19** are tagged *only* for Malagasy.
- Including tags inherited from base models: **325**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |        5 | █                    |
|   2024 |       18 | ████                 |
|   2025 |       34 | ████████             |
|   2026 |       83 | ████████████████████ |

### Largest models tagged for Malagasy

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of       |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —                   |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B) | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B    |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 14.8B        |                   21 |   2026 | Qwen/Qwen3-14B-Base |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                 | 13.9B        |                   92 |   2024 | —                   |

### Largest models tagged *only* for Malagasy

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [Lo-Renz-O/Mistral-7B-CPT-Malagasy-v2-bnb-4bit](https://huggingface.co/Lo-Renz-O/Mistral-7B-CPT-Malagasy-v2-bnb-4bit) | 7.5B         |                    1 |   2025 | mistralai/Mistral-7B-v0.3     |
| [alphaedge-ai/gemma-3-4b-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mlg-32768)                   | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-plt](https://huggingface.co/ptrdvn/kakugo-3B-plt)                                                   | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-mlg-32768)                   | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-mlg-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-mlg-32768)               | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_37 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Malagasy.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                          | dataset                                                                                             |   # test items | construction                                   |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                         |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        |            103 | MT + human post-editing                        |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       |            900 | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               |         14,042 | Machine translation (Google Translate)         |
| Machine translation           |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           |          1,997 | Human translation (professional, from English) |
| Machine translation           |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                |             51 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_mg) (training data)   | en → mg                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_mg) (training data) | en → mg                           | size not listed        | ✅                |

_⚠️ Listed under the macrolanguage code `mlg`, so this may cover other varieties as well as Malagasy._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Malagasy datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Malagasy? Does it make sense to train one?
  - ~0.38 GB English-equivalent text ≈ 0.10B tokens, enough for a compute-optimal model of ~4.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Malagasy-only model is 7.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,498 papers (0.09%) (rank 133 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Plateau Malagasy | Malagasy

Here are up to ten papers published in 2026 that mention Malagasy. None of the 16 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages         | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)               |
| AfriMTEB and AfriE5: Benchmarking and Adapting Text Embedding Models for African Languages                     | [2026.eacl-long.171](https://aclanthology.org/2026.eacl-long.171/)             |
| Multilinguality after Quantization: Low-Bits, Calibration Languages, Mixed-Precisions, and Cross-Linguality    | [2026.findings-aacl.9](https://aclanthology.org/2026.findings-aacl.9/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                            | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                         | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                               | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/)   |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                     | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                               | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   |

{% endraw %}
