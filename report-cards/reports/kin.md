---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kin.html
---
{% raw %}
# So you want to work on Kinyarwanda?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kin`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › West Highlands Kivu ([Glottolog](https://glottolog.org/resource/languoid/id/kiny1244))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 12.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Rwanda

**Status:** Official language


## What does Kinyarwanda look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/kinyarwanda.htm):

> Abantu bose bavuka aliko bakwiye agaciro no kwubahwa kimwe. Bose bavukana
> ubwenge n'umutima, bagomba kugilirana kivandimwe.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kin/) has 4 videos of Kinyarwanda speakers. Watch [Daisy speaking Kinyarwanda](https://wikitongues.org/videos/daisy_20160102_kin/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,729 articles in rw.wikipedia; 67 active users. This is ~1/703 of English data and ranks 101 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 59,405 pages per crawl on average, which is 0.0028% of the crawl (2026). This is ~1/15,007 of English data and ranks 74 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                           |
| FineWeb                | 0.37 GB (kin_Latn 0.37 GB), equivalent to ≈0.33 GB of English after byte-premium scaling; 2.26 GB removed by filtering. This is ~1/144,501 of English data and ranks 88 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.97 GB (kin_Latn 0.97 GB) (rank 75 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | **None found**                                                                              |
| Wikidata labels        | 487,808 Wikidata items have a label in Kinyarwanda. (Wikidata codes (labels): rw (487,808)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 10,395,923 sentence pairs with English across 8 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (10,080,672), [GNOME](https://opus.nlpl.eu/GNOME) (232,909), [KDE4](https://opus.nlpl.eu/KDE4) (39,214), [wikimedia](https://opus.nlpl.eu/wikimedia) (38,338), [tico-19](https://opus.nlpl.eu/tico-19) (3,071). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                         |
| Tatoeba                                                                                  | 31 sentences, 21 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/kin/none)).                                                                                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_rw) en → rw: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_rw) en → rw: size not listed                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=31), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** fasttext — F1 0.813 (P 0.786, R 0.863, FPR 1.17e-03) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.799).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| fasttext     |       0.786 |    0.863 | 0.813 | 0.001 | ✓                |
| GlotLID      |       0.728 |    0.949 | 0.799 | 0.002 | ✓                |
| cld2         |       0.611 |    0.928 | 0.711 | 0.007 | ✓                |
| commonlingua |       0.626 |    0.803 | 0.687 | 0.004 | ✓                |
| OpenLID-v2   |       0.748 |    0.598 | 0.639 | 0.001 | ✓                |
| pyfranc      |       0.703 |    0.595 | 0.634 | 0.002 | ✓                |
| funlangid    |       0.568 |    0.669 | 0.604 | 0.004 | ✓                |
| py3langid    |       0.461 |    0.981 | 0.585 | 0.016 | ✓                |
| AfroLID      |       0.387 |    0.888 | 0.523 | 0.057 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (fasttext) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  31 |       0.227 |    0.548 | 0.321 |
| UDHR-LID  |  59 |       0.761 |    0.864 | 0.810 |
| Wikipedia | 300 |       0.821 |    0.853 | 0.837 |
| SmolSent  | 300 |       0.926 |    0.963 | 0.944 |
| FLORES    | 300 |       0.987 |    0.977 | 0.982 |
| NTREX     | 300 |       0.997 |    0.970 | 0.983 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kinyarwanda to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kinyarwanda *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kinyarwanda and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kinyarwanda has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Kinyarwanda?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kinyarwanda (and whether the model is exclusively tagged for Kinyarwanda or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **171** text-generation models are explicitly tagged for Kinyarwanda (77 original uploads, 94 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Kinyarwanda.
- Including tags inherited from base models: **334**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ██████████           |
|   2023 |       24 | █████████            |
|   2024 |       25 | █████████            |
|   2025 |       37 | █████████████        |
|   2026 |       56 | ████████████████████ |

### Largest models tagged for Kinyarwanda

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Kinyarwanda

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [NiyonshutiDavid/uruti-advisory-model-best](https://huggingface.co/NiyonshutiDavid/uruti-advisory-model-best) | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B               |
| [ptrdvn/kakugo-3B-kin](https://huggingface.co/ptrdvn/kakugo-3B-kin)                                           | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

_30 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Kinyarwanda.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             |   # test items | construction                                             |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                                   |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        |            103 | MT + human post-editing                                  |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       |            900 | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          5,000 | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                         |            500 | Human translation (professional)                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [AfriQA](https://github.com/masakhane-io/afriqa)                                                    |            347 | Native                                                   |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           |          1,997 | Human translation (professional, from English)           |
| Machine translation           |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             |          2,100 | Human translation (professional/volunteer, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                |             17 | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_rw) (training data)   | en → rw                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_rw) (training data) | en → rw                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kinyarwanda datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kinyarwanda? Does it make sense to train one?
  - ~0.85 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kinyarwanda-only model is 7.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 52 of ~18,498 papers (0.28%) (rank 87 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Kinyarwanda

Here are up to ten papers published in 2026 that mention Kinyarwanda. None of the 52 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mitigating Tokenization-Induced Distance Distortion in Long-Context Multilingual Machine Translation                             | [2026.acl-long.1696](https://aclanthology.org/2026.acl-long.1696/)             |
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                        | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| SALT-31: A Machine Translation Benchmark Dataset for 31 Ugandan Languages                                                        | [2026.africanlp-main.21](https://aclanthology.org/2026.africanlp-main.21/)     |
| The Geometry of Low-Resource Language Representations                                                                            | [2026.emnlp-main.2097](https://aclanthology.org/2026.emnlp-main.2097/)         |
| Bridging the Culture Gap: A Framework for LLM-Driven Socio-Cultural Localization of Math Word Problems in Low-Resource Languages | [2026.findings-acl.42](https://aclanthology.org/2026.findings-acl.42/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                                        | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                                    | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| Amulwe Kimün: A Community-Grounded Demo, Resource, and ASR Baseline for Mapuzugun                                                | [2026.lrec-1.266](https://aclanthology.org/2026.lrec-1.266/)                   |

{% endraw %}
