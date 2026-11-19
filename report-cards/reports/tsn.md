---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tsn.html
---
{% raw %}
# So you want to work on Setswana?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tsn` (also listed as: Tswana)

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Central Sotho-Tswana ([Glottolog](https://glottolog.org/resource/languoid/id/tswa1253))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 6.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## What does Setswana look and sound like?

**Written:** no Omniglot page found for Setswana.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tsn/) has 1 video of Setswana speakers. Watch [Donald speaking Tswana](https://wikitongues.org/videos/donald_20181213_tsn/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 6,118 articles in tn.wikipedia; 63 active users. This is ~1/1,233 of English data and ranks 115 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 5,661 pages per crawl on average, which is 0.0003% of the crawl (2026). This is ~1/157,482 of English data and ranks 99 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 11.2 MB (tsn_Latn 10.0 MB), equivalent to ≈9.6 MB of English after byte-premium scaling; 0.64 GB removed by filtering. This is ~1/4,759,097 of English data and ranks 146 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.13 GB (tsn_Latn 0.12 GB) (rank 114 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                  |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 50 sentences / 580 tokens in total: [UD_Tswana-Popapolelo](https://github.com/UniversalDependencies/UD_Tswana-Popapolelo) (50 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                               |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                               |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0).                                              |

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

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=42), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.970 (P 0.970, R 0.970, FPR 1.61e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.911).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.970 |    0.970 | 0.970 | 0.000 | ✓                |
| cld2         |       0.897 |    0.934 | 0.911 | 0.001 | ✓                |
| OpenLID-v2   |       0.856 |    0.979 | 0.909 | 0.001 | ✓                |
| commonlingua |       0.928 |    0.850 | 0.876 | 0.000 | ✓                |
| fasttext     |       0.730 |    0.983 | 0.835 | 0.004 | ✓                |
| pyfranc      |       0.814 |    0.856 | 0.831 | 0.002 | ✓                |
| funlangid    |       0.752 |    0.861 | 0.800 | 0.002 | ✓                |
| AfroLID      |       0.277 |    0.985 | 0.423 | 0.096 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  42 |       0.900 |    0.857 | 0.878 |
| Wikipedia | 300 |       0.986 |    0.970 | 0.978 |
| FLORES    | 300 |       0.974 |    1.000 | 0.987 |
| NTREX     | 300 |       0.980 |    0.997 | 0.988 |
| SmolSent  | 300 |       0.980 |    0.997 | 0.988 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Setswana to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Setswana *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Setswana and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Setswana has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Setswana?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Setswana (and whether the model is exclusively tagged for Setswana or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **162** text-generation models are explicitly tagged for Setswana (90 original uploads, 72 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Setswana.
- Including tags inherited from base models: **308**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████         |
|   2023 |       22 | █████████            |
|   2024 |       27 | ███████████          |
|   2025 |       35 | ██████████████       |
|   2026 |       49 | ████████████████████ |

### Largest models tagged for Setswana

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Models tagged *only* for Setswana

None of these has a known parameter count:

| model                                                                                   |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/tsn_latn_100mb](https://huggingface.co/goldfish-models/tsn_latn_100mb) |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_10mb](https://huggingface.co/goldfish-models/tsn_latn_10mb)   |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_5mb](https://huggingface.co/goldfish-models/tsn_latn_5mb)     |                    1 |   2024 | —               |
| [goldfish-models/tsn_latn_full](https://huggingface.co/goldfish-models/tsn_latn_full)   |                    1 |   2024 | —               |

_36 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Setswana.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 4,744          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation                    |                               | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    |                               | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    |                               | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional, from English)                      |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    |                               | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    |                               | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 30             | Native (crowdsourced Tatoeba sentence pairs)                        |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Setswana datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Setswana? Does it make sense to train one?
  - ~0.11 GB English-equivalent text ≈ 0.03B tokens, enough for a compute-optimal model of ~1.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 29 of ~18,498 papers (0.16%) (rank 113 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Setswana | Tswana

Here are up to ten papers published in 2026 that mention Setswana. None of the 29 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             | body only      |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                                                            | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)             | body only      |
| Pseudo2Real: Task Arithmetic for Pseudo-Label Correction in Automatic Speech Recognition                                                      | [2026.findings-acl.59](https://aclanthology.org/2026.findings-acl.59/)         | body only      |
| When Audit Quality Fails to Predict Downstream Utility: Synthetic-Data Selection for Low-Resource Classification                              | [2026.findings-emnlp.1184](https://aclanthology.org/2026.findings-emnlp.1184/) | body only      |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   | body only      |
| Code-Switching in End-to-End Automatic Speech Recognition: A Systematic Literature Review                                                     | [2026.lrec-1.768](https://aclanthology.org/2026.lrec-1.768/)                   | body only      |
| How Much of Native Language Identification Is Corpus Artifact? A Cross-Corpus Audit of SVMs and LLMs on TOEFL11 and ICLEv3                    | [2026.nlp4call-1.1](https://aclanthology.org/2026.nlp4call-1.1/)               | body only      |
| Extension of Linguistic Resources for South African Languages: Part-of-Speech Annotated Domain-Specific Data                                  | [2026.rail-1.2](https://aclanthology.org/2026.rail-1.2/)                       | body only      |
| Benchmarking Text Embedding Models for South African Languages                                                                                | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       | body only      |

{% endraw %}
