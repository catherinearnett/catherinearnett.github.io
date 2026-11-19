---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kas.html
---
{% raw %}
# So you want to work on Kashmiri?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kas`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Kashmiric ([Glottolog](https://glottolog.org/resource/languoid/id/kash1277))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 4 (Educational))

**Speakers:** about 6.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 6.9 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33552#P1098), 2011)

**Official / recognised in:** India

**Status:** Regional official language


## What does Kashmiri look and sound like?

**Written:** Omniglot has [a page on Kashmiri](https://www.omniglot.com/writing/kashmiri.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kas/) has 1 video of Kashmiri speakers. Watch [Aakriti speaking Kashmiri](https://wikitongues.org/videos/aakriti_20180802_kas/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 11,926 articles in ks.wikipedia; 24 active users. This is ~1/633 of English data and ranks 99 of 168 languages in the set in Wikipedia.                                                                                                                                                                                                                     |
| Common Crawl           | 92 pages per crawl on average, which is 0.0000% of the crawl (2026). This is ~1/9,690,299 of English data and ranks 113 of 113 languages in the set in Common Crawl.                                                                                                                                                                                        |
| FineWeb                | 1.1 MB (kas_Arab 0; kas_Deva 0; kas_Latn 0), equivalent to ≈0.5 MB of English after byte-premium scaling (⚠️ only 95% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 0.19 GB removed by filtering. This is ~1/48,354,845 of English data and ranks 198 of 248 languages in the set in FineWeb. |
| Goldfish training data | 17.9 MB (kas_Deva 18.0 MB) (rank 153 of 166 in the set)                                                                                                                                                                                                                                                                                                     |

**By writing system:**

| Writing system      |   FineWeb | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|----------:|:------------------------------|:-------------|:-------------------------------|
| Devanagari (`Deva`) |         0 | — (no byte premium yet)       | 18.0 MB      | 7.1 MB                         |
| Arabic (`Arab`)     |         0 | — (no byte premium yet)       | not included | —                              |
| Latin (`Latn`)      |         0 | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                              |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 180 sentences / 2,148 tokens in total: [UD_Kashmiri-Zaan](https://github.com/UniversalDependencies/UD_Kashmiri-Zaan) (180 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                           |
| Wikidata labels        | 172,636 Wikidata items have a label in Kashmiri. (Wikidata codes (labels): ks (172,636))                                                                                                                                 |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid.
- **Eval datasets (4):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=280), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.948 (P 0.995, R 0.910, FPR 2.57e-05) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.731).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.910 | 0.948 | 0.000 | ✓                |
| OpenLID-v2   |       0.947 |    0.703 | 0.731 | 0.001 | ✓                |
| funlangid    |       0.787 |    0.648 | 0.696 | 0.001 | ✓                |
| fasttext     |       0.929 |    0.634 | 0.672 | 0.001 | ✓                |
| commonlingua |       0.817 |    0.512 | 0.609 | 0.001 | ✓                |
| cld2         |       0.825 |    0.091 | 0.160 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 280 |       0.986 |    0.729 | 0.838 |
| Wikipedia | 300 |       0.996 |    0.940 | 0.967 |
| SmolSent  | 300 |       1.000 |    0.973 | 0.986 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kashmiri to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kashmiri *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kashmiri and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kashmiri has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Kashmiri?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kashmiri (and whether the model is exclusively tagged for Kashmiri or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **73** text-generation models are explicitly tagged for Kashmiri (49 original uploads, 24 fine-tunes/quantisations/merges).
- **7** are tagged *only* for Kashmiri.
- Including tags inherited from base models: **108**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |        2 | █                    |
|   2025 |        6 | ██                   |
|   2026 |       63 | ████████████████████ |

### Largest models tagged for Kashmiri

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 856.0B       |                  143 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Kashmiri

| model                                                                                                           | parameters   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [Omarrran/ks-byte-lm-spacebyte-transformers](https://huggingface.co/Omarrran/ks-byte-lm-spacebyte-transformers) | 15.8M        |                    1 |   2026 | —               |

_12 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Kashmiri.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /   [0]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [1]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                                     | # test items   | construction                                                     |
|:-------------------------|:--------------------|:--------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                  | 1,571          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (2 varieties/pairs) | 2,024          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol) (2 varieties/pairs)           | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) (2 varieties/pairs)          | —              | Human translation (professional, from English)                   |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kashmiri datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kashmiri? Does it make sense to train one?
  - ~7.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~88.7K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kashmiri-only model is 15.8M, aim no higher than
  *2. Pragmatics, discourse & coreference* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 16 of ~18,498 papers (0.09%) (rank 133 of 278 in the set); English is mentioned in 8,465.
- Search terms: Kashmiri

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 16):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| BhashaSutra: A Task-Centric Unified Survey of Indian NLP Datasets, Corpora, and Resources                                                     | [2026.acl-long.551](https://aclanthology.org/2026.acl-long.551/)               |
| Thesis Proposal: Development of End-to-End Speech Translation Models for Indian Languages                                                     | [2026.eacl-srw.41](https://aclanthology.org/2026.eacl-srw.41/)                 |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Evaluating Cross-lingual Knowledge Consistency in Code-Mixed vis-a-vis Indian Languages using IndicKLAR                                       | [2026.findings-emnlp.1655](https://aclanthology.org/2026.findings-emnlp.1655/) |
| UrHiOdSynth: A Multilingual Synthetic Corpus for Speech-to-Speech Translation in Low-Resource Indic Languages                                 | [2026.loreslm-1.50](https://aclanthology.org/2026.loreslm-1.50/)               |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Cross-Lingual TTS for Indian Languages: A Benchmark and Inference-Time Duration Estimation Strategies                                         | [2026.multilll-1.6](https://aclanthology.org/2026.multilll-1.6/)               |
| Algebraic Classification of Reduplicative Processes                                                                                           | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               |

{% endraw %}
