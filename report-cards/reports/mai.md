---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mai.html
---
{% raw %}
# So you want to work on Maithili?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mai`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Magadhan ([Glottolog](https://glottolog.org/resource/languoid/id/mait1250))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 4 (Educational))

**Writing systems:** `Deva`

**Speakers:** about 20.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India

**Status:** Regional official language


## What does Maithili look and sound like?

**Written:** Omniglot has [a page on Maithili](https://www.omniglot.com/writing/maithili.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mai/) has 3 videos of Maithili speakers. Watch [Keshav speaking Maithili](https://wikitongues.org/videos/keshav_20180702_mai/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,372 articles in mai.wikipedia; 44 active users. This is ~1/525 of English data and ranks 91 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                          |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                           |
| FineWeb                | 47.6 MB (mai_Deva 48.0 MB), equivalent to ≈19.9 MB of English after byte-premium scaling; 0.10 GB removed by filtering. This is ~1/1,121,569 of English data and ranks 124 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 0.10 GB (mai_Deva 0.10 GB) (rank 122 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                               |
|:-----------------------|:------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                            |
| UniMorph               | **None found**                                                                            |
| Wikidata labels        | 272,482 Wikidata items have a label in Maithili. (Wikidata codes (labels): mai (272,482)) |
| Wordnets               | **None found**                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                               |
|:-----------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 4,525,171 sentence pairs with English across 6 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (4,438,382), [GNOME](https://opus.nlpl.eu/GNOME) (43,273), [KDE4](https://opus.nlpl.eu/KDE4) (38,029), [translatewiki](https://opus.nlpl.eu/translatewiki) (5,291), [wikimedia](https://opus.nlpl.eu/wikimedia) (188). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                               |
| Tatoeba                                                                                  | 8 sentences, 8 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mai/none)).                                                                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Deva script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Deva script) — paired with English                                                                                                                                                                                                                                                                       |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_mai) en → mai: size not listed                                                                                                                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.985 (P 1.000, R 0.971, FPR 0.00e+00) averaged over 3 dataset(s). Runner-up: OpenLID-v2 (F1 0.973).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.971 | 0.985 | 0.000 | ✓                |
| OpenLID-v2   |       0.963 |    0.983 | 0.973 | 0.000 | ✓                |
| fasttext     |       0.974 |    0.970 | 0.972 | 0.000 | ✓                |
| commonlingua |       0.950 |    0.816 | 0.878 | 0.000 | ✓                |
| funlangid    |       0.953 |    0.675 | 0.786 | 0.000 | ✓                |
| pyfranc      |       0.912 |    0.668 | 0.757 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.930 | 0.964 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Maithili to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Maithili *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Maithili and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Maithili has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Maithili?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Maithili (and whether the model is exclusively tagged for Maithili or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **72** text-generation models are explicitly tagged for Maithili (50 original uploads, 22 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Maithili.
- Including tags inherited from base models: **111**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        3 | █                    |
|   2025 |        6 | ██                   |
|   2026 |       61 | ████████████████████ |

### Largest models tagged for Maithili

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |
| [chinmaykumar-vyas/sarvam-105b](https://huggingface.co/chinmaykumar-vyas/sarvam-105b)       | 106.0B       |                   23 |   2026 | —                    |
| [justkapoor/sarvam-105b](https://huggingface.co/justkapoor/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Maithili

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [dheeyantra/dhee-nxtgen-qwen3-maithili-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-maithili-v2) | 1.7B         |                    1 |   2025 | —               |

_6 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Maithili.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 1 dataset; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 3. Commonsense reasoning | COPA               | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                     |            500 | Human translation                             |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              8 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)                      | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                            | multi-way (all languages)         | 2,009 sentences (Deva) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                        | ↔ English (and 8 pivot languages) | 1,358 sentences (Deva) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_mai) (training data) | en → mai                          | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Maithili datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Maithili? Does it make sense to train one?
  - ~43.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~538.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Maithili-only model is 1.7B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 37 of ~18,498 papers (0.20%) (rank 105 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Maithili

Here are up to ten papers published in 2026 that mention Maithili. None of the 37 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                             | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| MaiBERT: A Pre-training Corpus and Language Model for Low-Resourced Maithili Language                          | [2026.loreslm-1.38](https://aclanthology.org/2026.loreslm-1.38/)               |
| UrHiOdSynth: A Multilingual Synthetic Corpus for Speech-to-Speech Translation in Low-Resource Indic Languages  | [2026.loreslm-1.50](https://aclanthology.org/2026.loreslm-1.50/)               |
| Same-Language Subtitles for Low-resource Languages: A Case of Bundelkhandi                                     | [2026.lrec-1.246](https://aclanthology.org/2026.lrec-1.246/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| FiNERVINER: Fine-grained Named Entity Recognition for Vulnerable Languages of India’s North Eastern Region     | [2026.lrec-1.607](https://aclanthology.org/2026.lrec-1.607/)                   |
| NepTam: A Nepali-Tamang Parallel Corpus and Baseline Machine Translation Experiments                           | [2026.lrec-1.696](https://aclanthology.org/2026.lrec-1.696/)                   |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies          | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               |

{% endraw %}
