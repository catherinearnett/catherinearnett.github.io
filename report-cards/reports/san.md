---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/san.html
---
{% raw %}
# So you want to work on Sanskrit?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `san`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › Indo-Aryan ([Glottolog](https://glottolog.org/resource/languoid/id/sans1269))

**Endangerment:** ⚫ extinct (level 6 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 10 (Extinct))

**Writing systems:** `Deva` and `Latn`

**Speakers:** about 17,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, South Africa

**Status:** Regional official language; Official language


## What does Sanskrit look and sound like?

**Written (Sanskrit)**, sample text from [Omniglot](https://www.omniglot.com/writing/sanskrit.htm):

> Translated into Sanskrit by Arvind Iyengar

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/san/) has 2 videos of Sanskrit speakers. Watch [Sushyanth and Anonymous speaking Sanskrit](https://wikitongues.org/videos/sushyanth-anonymous_20210523_san/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                             |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 12,587 articles in sa.wikipedia; 82 active users. This is ~1/600 of English data and ranks 97 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                           |
| Common Crawl           | 80,639 pages per crawl on average, which is 0.0037% of the crawl (2026). This is ~1/11,056 of English data and ranks 67 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                              |
| FineWeb                | 0.11 GB (san_Deva 90.0 MB; san_Latn 25.0 MB), equivalent to ≈61.3 MB of English after byte-premium scaling; 0.78 GB removed by filtering. This is ~1/465,494 of English data and ranks 111 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.35 GB (san_Deva 0.35 GB) (rank 104 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                 |

**By writing system:**

| Writing system      | FineWeb                         | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|:--------------------------------|:------------------------------|:-------------|:-------------------------------|
| Devanagari (`Deva`) | 89.6 MB (+0.32 GB filtered out) | 35.2 MB                       | 0.35 GB      | 0.14 GB                        |
| Latin (`Latn`)      | 25.1 MB (+0.47 GB filtered out) | 26.0 MB                       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 27,412 sentences / 207,914 tokens in total: [UD_Sanskrit-UFAL](https://github.com/UniversalDependencies/UD_Sanskrit-UFAL) (230 sentences), [UD_Sanskrit-Vedic](https://github.com/UniversalDependencies/UD_Sanskrit-Vedic) (27,182 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 917 lemmas, 33,847 inflected forms ([unimorph/san](https://github.com/unimorph/san))                                                                                                                                                                                                                                                 |
| Wikidata labels        | 469,249 Wikidata items have a label in Sanskrit. (Wikidata codes (labels): sa (469,249))                                                                                                                                                                                                                                             |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY; [Sanskrit Wordnet](http://www.cfilt.iitb.ac.in/wordnet/webswn/english_version.php) (size not listed); licence: GNU FDL; [ilts-utkal.org](http://ilts-utkal.org/) (size not listed).                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 3,104,495 sentence pairs with English across 5 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (3,095,396), [translatewiki](https://opus.nlpl.eu/translatewiki) (6,523), [wikimedia](https://opus.nlpl.eu/wikimedia) (2,262), [QED](https://opus.nlpl.eu/QED) (164), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (150).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Bible translations (eBible corpus)                                                       | **Yes** — 20 translations: New Testament ([sanasm](https://ebible.org/details.php?id=sanasm), by-sa 4.0); New Testament ([santib](https://ebible.org/details.php?id=santib), by-sa 4.0); New Testament ([santha](https://ebible.org/details.php?id=santha), by-sa 4.0); New Testament ([santel](https://ebible.org/details.php?id=santel), by-sa 4.0); New Testament ([santam](https://ebible.org/details.php?id=santam), by-sa 4.0); New Testament ([sansin](https://ebible.org/details.php?id=sansin), by-sa 4.0); New Testament ([sanpun](https://ebible.org/details.php?id=sanpun), by-sa 4.0); New Testament ([sanori](https://ebible.org/details.php?id=sanori), by-sa 4.0); New Testament ([sanmal](https://ebible.org/details.php?id=sanmal), by-sa 4.0); New Testament ([sankhm](https://ebible.org/details.php?id=sankhm), by-sa 4.0); New Testament ([sanitr](https://ebible.org/details.php?id=sanitr), by-sa 4.0); New Testament ([saniso](https://ebible.org/details.php?id=saniso), by-sa 4.0); New Testament ([sanias](https://ebible.org/details.php?id=sanias), by-sa 4.0); New Testament ([sanhk](https://ebible.org/details.php?id=sanhk), by-sa 4.0); New Testament ([sanguj](https://ebible.org/details.php?id=sanguj), by-sa 4.0); New Testament ([sandev](https://ebible.org/details.php?id=sandev), by-sa 4.0); New Testament ([sanbur](https://ebible.org/details.php?id=sanbur), by-sa 4.0); New Testament ([sanben](https://ebible.org/details.php?id=sanben), by-sa 4.0); New Testament ([sanurd](https://ebible.org/details.php?id=sanurd), by-sa 4.0); New Testament ([sanvel](https://ebible.org/details.php?id=sanvel), by-sa 4.0). |
| Tatoeba                                                                                  | 167 sentences, 134 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/san/none)).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Deva script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sa) en → sa: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sa) en → sa: size not listed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=167), UDHR-LID (n=106), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.968 (P 0.992, R 0.947, FPR 4.44e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.907).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.947 | 0.968 | 0.000 | ✓                |
| OpenLID-v2   |       0.977 |    0.867 | 0.907 | 0.000 | ✓                |
| py3langid    |       0.965 |    0.847 | 0.891 | 0.000 | ✓                |
| fasttext     |       0.984 |    0.788 | 0.865 | 0.000 | ✓                |
| cld2         |       0.933 |    0.793 | 0.851 | 0.001 | ✓                |
| commonlingua |       0.928 |    0.748 | 0.812 | 0.001 | ✓                |
| pyfranc      |       0.909 |    0.721 | 0.790 | 0.001 | ✓                |
| funlangid    |       0.872 |    0.694 | 0.760 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.979 |    0.790 | 0.875 |
| CommonLID | 300 |       0.996 |    0.947 | 0.971 |
| Tatoeba   | 167 |       0.988 |    0.970 | 0.979 |
| UDHR-LID  | 106 |       0.991 |    0.991 | 0.991 |
| FLORES    | 300 |       1.000 |    0.987 | 0.993 |
| SmolSent  | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sanskrit to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sanskrit *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sanskrit and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Sanskrit?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sanskrit (and whether the model is exclusively tagged for Sanskrit or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **205** text-generation models are explicitly tagged for Sanskrit (102 original uploads, 103 fine-tunes/quantisations/merges).
- **35** are tagged *only* for Sanskrit.
- Including tags inherited from base models: **263**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █                    |
|   2024 |        8 | █                    |
|   2025 |       59 | █████████            |
|   2026 |      135 | ████████████████████ |

### Largest models tagged for Sanskrit

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 856.0B       |                  143 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Sanskrit

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of               |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------|
| [saucam/Rudra-7b](https://huggingface.co/saucam/Rudra-7b)                                                                   | 8.5B         |                    1 |   2024 | —                           |
| [diabolic6045/Sanskrit-Qwen2.5-VL-7B-Instruct-OCR](https://huggingface.co/diabolic6045/Sanskrit-Qwen2.5-VL-7B-Instruct-OCR) | 8.3B         |                    1 |   2025 | Qwen/Qwen2.5-VL-7B-Instruct |
| [swarup3204/llama-3.1-8B-it-anvaya-ift-10perm](https://huggingface.co/swarup3204/llama-3.1-8B-it-anvaya-ift-10perm)         | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B     |
| [diabolic6045/Sanskrit-Qwen2.5-7B-base](https://huggingface.co/diabolic6045/Sanskrit-Qwen2.5-7B-base)                       | 7.6B         |                    1 |   2025 | Qwen/Qwen2.5-7B             |
| [snskrt/gemma-3-4b-it-sanskrit-ocr](https://huggingface.co/snskrt/gemma-3-4b-it-sanskrit-ocr)                               | 4.3B         |                    1 |   2025 | google/gemma-3-4b-it        |

_53 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Sanskrit.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |          4,442 | Treebank-based (automatic, UD + UniMorph)     |
| 3. Commonsense reasoning | COPA               | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                     |            500 | Human translation                             |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            144 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)              | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages) | 2,009 sentences (Deva) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_sa) (training data)   | en → sa                   | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_sa) (training data) | en → sa                   | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sanskrit datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sanskrit? Does it make sense to train one?
  - ~0.14 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sanskrit-only model is 8.5B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 106 of ~18,498 papers (0.57%) (rank 57 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Sanskrit

Here are up to ten papers published in 2026 that mention Sanskrit. None of the 106 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                | paper                                                                              |
|:---------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| ThaiEditBench: A Mechanism-Typed, Length-Stratified Benchmark for Thai Orthographic Error Correction                 | [2026.aacl-short.17](https://aclanthology.org/2026.aacl-short.17/)                 |
| Paramanu: Compact and Competitive Monolingual Language Models for Low-Resource Morphologically Rich Indian Languages | [2026.acl-long.1922](https://aclanthology.org/2026.acl-long.1922/)                 |
| Digitizing Nepal’s Written Heritage: A Comprehensive HTR Pipeline for Old Nepali Manuscripts                         | [2026.acl-long.671](https://aclanthology.org/2026.acl-long.671/)                   |
| LIMP: Linguistically-Informed Multi-Strategy Prompting for Telugu Multi-Turn Dialogue Generation                     | [2026.dravidianlangtech-1.5](https://aclanthology.org/2026.dravidianlangtech-1.5/) |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                          | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)             |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                  | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)                       |
| Paradigms over Surface Cues: Inflection Class Drives Hindi Gender Assignment in Expert-Annotated Noun Paradigms      | [2026.mrl-1.9](https://aclanthology.org/2026.mrl-1.9/)                             |
| Integrating Cultural Wisdom and Digital Technologies for Children’s Moral and Emotional Development                  | [2026.wildre-1.15](https://aclanthology.org/2026.wildre-1.15/)                     |
| Konkani Wordnet Resources                                                                                            | [2026.wildre-1.6](https://aclanthology.org/2026.wildre-1.6/)                       |
| StalePO: Anchored Token-Level Preference Optimization using Legacy Post-Edits in Machine Translation                 | [2026.wmt-main.8](https://aclanthology.org/2026.wmt-main.8/)                       |

{% endraw %}
