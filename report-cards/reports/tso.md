---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tso.html
---
{% raw %}
# So you want to work on Shangani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tso` (also listed as: Xitsonga)

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Tsongan ([Glottolog](https://glottolog.org/resource/languoid/id/tson1249))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 5.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## What does Shangani look and sound like?

**Written:** no Omniglot page found for Shangani.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tso/) has 5 videos of Shangani speakers. Watch [Amu speaking XiTsonga](https://wikitongues.org/videos/amu_20140729_tso/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,329 articles in ts.wikipedia; 10 active users. This is ~1/5,678 of English data and ranks 147 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 1,659 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/537,376 of English data and ranks 109 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 13.0 MB (tso_Latn 10.0 MB), equivalent to ≈10.7 MB of English after byte-premium scaling; 58.9 MB removed by filtering. This is ~1/4,122,175 of English data and ranks 141 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 93.4 MB (tso_Latn 93.0 MB) (rank 122 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                  |
| UniMorph               | **None found**                                                                                                                                                                  |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                  |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                           |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                               |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                           |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                            |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                   |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                   |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ts) en → ts: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ts) en → ts: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ts) en → ts: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=17), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.952 (P 0.981, R 0.926, FPR 3.96e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.888).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.926 | 0.952 | 0.000 | ✓                |
| cld2         |       0.917 |    0.867 | 0.888 | 0.000 | ✓                |
| AfroLID      |       0.909 |    0.843 | 0.874 | 0.001 | ✓                |
| funlangid    |       0.878 |    0.732 | 0.797 | 0.000 | ✓                |
| pyfranc      |       0.793 |    0.775 | 0.779 | 0.001 | ✓                |
| OpenLID-v2   |       0.622 |    0.974 | 0.745 | 0.009 | ✓                |
| fasttext     |       0.586 |    0.921 | 0.702 | 0.009 | ✓                |
| commonlingua |       0.667 |    0.757 | 0.697 | 0.003 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  17 |       0.938 |    0.882 | 0.909 |
| UDHR-LID  | 114 |       0.990 |    0.868 | 0.925 |
| Wikipedia | 300 |       0.978 |    0.880 | 0.926 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Shangani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Shangani *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Shangani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Shangani has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Shangani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Shangani (and whether the model is exclusively tagged for Shangani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **123** text-generation models are explicitly tagged for Shangani (74 original uploads, 49 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Shangani.
- Including tags inherited from base models: **234**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████████████████████ |
|   2023 |       22 | ███████████████      |
|   2024 |       24 | █████████████████    |
|   2025 |       19 | █████████████        |
|   2026 |       29 | ████████████████████ |

### Largest models tagged for Shangani

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Models tagged *only* for Shangani

None of these has a known parameter count:

| model                                                                                         |   # languages tagged |   year | derivative of   |
|:----------------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [BoggersTheFish/ts-proof-ranker-v4](https://huggingface.co/BoggersTheFish/ts-proof-ranker-v4) |                    1 |   2026 | —               |
| [goldfish-models/tso_latn_10mb](https://huggingface.co/goldfish-models/tso_latn_10mb)         |                    1 |   2024 | —               |
| [goldfish-models/tso_latn_5mb](https://huggingface.co/goldfish-models/tso_latn_5mb)           |                    1 |   2024 | —               |
| [goldfish-models/tso_latn_full](https://huggingface.co/goldfish-models/tso_latn_full)         |                    1 |   2024 | —               |

_20 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Shangani.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                  |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                             |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)              |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 1,583          | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 3              | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ts) (training data)   | en → ts                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ts) (training data)   | en → ts                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ts) (training data) | en → ts                           | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Shangani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Shangani? Does it make sense to train one?
  - ~77.4 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~967.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 19 of ~18,498 papers (0.10%) (rank 124 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Xitsonga | Tsonga

Here are up to ten papers published in 2026 that mention Shangani. None of the 19 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriMTEB and AfriE5: Benchmarking and Adapting Text Embedding Models for African Languages                                       | [2026.eacl-long.171](https://aclanthology.org/2026.eacl-long.171/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                      | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| JPhonABX: Japanese Phonological Discrimination Dataset for Moraic and Accentual Minimal Pairs                                    | [2026.findings-emnlp.1072](https://aclanthology.org/2026.findings-emnlp.1072/) |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                   | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                       | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Benchmarking Text Embedding Models for South African Languages                                                                   | [2026.rail-1.5](https://aclanthology.org/2026.rail-1.5/)                       |
| Measuring the Cost of Variety Conflation in Multilingual MT Evaluation: Adding Mozambican Xichangana, Nyanja and Sena to FLORES+ | [2026.wmt-main.193](https://aclanthology.org/2026.wmt-main.193/)               |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                                                        | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)                 |

{% endraw %}
