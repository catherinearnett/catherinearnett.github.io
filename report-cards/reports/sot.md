---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sot.html
---
{% raw %}
# So you want to work on Sesotho?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sot` (also listed as: Sotho)

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Sesotho-Lozi ([Glottolog](https://glottolog.org/resource/languoid/id/sout2807))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 7.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Lesotho, South Africa, Zimbabwe

**Status:** Official language


## What does Sesotho look and sound like?

**Written (Southern Sotho)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/sesotho.htm):

> Batho bohle ba tswetswe ba lokolohile mme ba lekana ka botho le ditokelo.
> Ba tswetswe le monahano le letswalo mme ba tlamehile ho phedisana le ba
> bang ka moya wa boena.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Sesotho yet ([its Wikitongues page](https://wikitongues.org/languages/sot/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,252 articles in st.wikipedia; 26 active users. This is ~1/3,351 of English data and ranks 138 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 15,365 pages per crawl on average, which is 0.0007% of the crawl (2026). This is ~1/58,022 of English data and ranks 95 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 0.15 GB (sot_Latn 0.15 GB), equivalent to ≈0.13 GB of English after byte-premium scaling; 0.21 GB removed by filtering. This is ~1/356,614 of English data and ranks 103 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.42 GB (sot_Latn 0.42 GB) (rank 96 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                  |
| UniMorph               | 26 lemmas, 494 inflected forms ([unimorph/sot](https://github.com/unimorph/sot))                                                                                                |
| Wikidata labels        | 477,110 Wikidata items have a label in Sesotho. (Wikidata codes (labels): st (477,110))                                                                                         |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,387,163 sentence pairs with English across 7 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (1,377,570), [wikimedia](https://opus.nlpl.eu/wikimedia) (8,368), [CCAligned](https://opus.nlpl.eu/CCAligned) (905), [translatewiki](https://opus.nlpl.eu/translatewiki) (288), [GNOME](https://opus.nlpl.eu/GNOME) (21). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                  |
| Tatoeba                                                                                  | 12 sentences, 12 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/sot/none)).                                                                                                                                                                                                              |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_st) en → st: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_st) en → st: size not listed                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), SmolSent (n=300), Tatoeba (n=12), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.954 (P 0.999, R 0.918, FPR 1.35e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.882).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.918 | 0.954 | 0.000 | ✓                |
| OpenLID-v2   |       0.973 |    0.834 | 0.882 | 0.000 | ✓                |
| cld2         |       0.858 |    0.880 | 0.866 | 0.001 | ✓                |
| commonlingua |       0.788 |    0.859 | 0.812 | 0.001 | ✓                |
| pyfranc      |       0.778 |    0.853 | 0.796 | 0.001 | ✓                |
| funlangid    |       0.773 |    0.728 | 0.726 | 0.001 | ✓                |
| fasttext     |       0.810 |    0.702 | 0.708 | 0.001 | ✓                |
| py3langid    |       0.497 |    0.939 | 0.602 | 0.011 | ✓                |
| cld3         |       0.344 |    0.894 | 0.471 | 0.033 | ✓                |
| AfroLID      |       0.778 |    0.123 | 0.163 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  12 |       1.000 |    0.750 | 0.857 |
| Wikipedia | 300 |       0.996 |    0.817 | 0.897 |
| FLORES    | 300 |       1.000 |    0.967 | 0.983 |
| CommonLID | 300 |       0.997 |    0.980 | 0.988 |
| SmolSent  | 300 |       1.000 |    0.993 | 0.997 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sesotho to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sesotho *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sesotho and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Sesotho has no UD treebank yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/sot/) video of Sesotho yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Sesotho?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sesotho (and whether the model is exclusively tagged for Sesotho or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **207** text-generation models are explicitly tagged for Sesotho (95 original uploads, 112 fine-tunes/quantisations/merges).
- **12** are tagged *only* for Sesotho.
- Including tags inherited from base models: **430**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | █████████            |
|   2023 |       24 | ██████               |
|   2024 |       28 | ███████              |
|   2025 |       38 | █████████            |
|   2026 |       81 | ████████████████████ |

### Largest models tagged for Sesotho

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [Wwayu/GLM-4.7-PRISM-mlx-2Bit](https://huggingface.co/Wwayu/GLM-4.7-PRISM-mlx-2Bit)   | 352.8B       |                    3 |   2025 | zai-org/GLM-4.7 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |

### Largest models tagged *only* for Sesotho

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sot-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-sot](https://huggingface.co/ptrdvn/kakugo-3B-sot)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sot-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-sot-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sot-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |
| [56m/Dumb-1.1-Rc-1](https://huggingface.co/56m/Dumb-1.1-Rc-1)                                           | 18.9M        |                    1 |   2026 | —                             |

_24 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Sesotho.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                  |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                             |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)              |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 1,270          | Synthetic (LLM-generated) on native Wikipedia |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)              |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_st) (training data)   | en → st                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_st) (training data) | en → st                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sesotho datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sesotho? Does it make sense to train one?
  - ~0.36 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sesotho-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 27 of ~18,498 papers (0.15%) (rank 116 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Southern Sotho | Sesotho

Here are up to ten papers published in 2026 that mention Sesotho. None of the 27 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)         |
| Sample-Size Scaling of the African Languages NLI Evaluation                                                                                   | [2026.africanlp-main.22](https://aclanthology.org/2026.africanlp-main.22/) |
| The Geometry of Low-Resource Language Representations                                                                                         | [2026.emnlp-main.2097](https://aclanthology.org/2026.emnlp-main.2097/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Multi-Hall-SA: A Cross-lingual Benchmark for Multi-Type Hallucination Detection in Low-Resource South African Languages                       | [2026.findings-eacl.330](https://aclanthology.org/2026.findings-eacl.330/) |
| Learning from Scarcity: Building and Benchmarking Speech Technology for Sukuma.                                                               | [2026.loreslm-1.25](https://aclanthology.org/2026.loreslm-1.25/)           |
| MzansiText and MzansiLM: An Open Corpus and Decoder-Only Language Model for South African Languages                                           | [2026.lrec-1.109](https://aclanthology.org/2026.lrec-1.109/)               |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Code-Switching in End-to-End Automatic Speech Recognition: A Systematic Literature Review                                                     | [2026.lrec-1.768](https://aclanthology.org/2026.lrec-1.768/)               |
| Extension of Linguistic Resources for South African Languages: Part-of-Speech Annotated Domain-Specific Data                                  | [2026.rail-1.2](https://aclanthology.org/2026.rail-1.2/)                   |

{% endraw %}
