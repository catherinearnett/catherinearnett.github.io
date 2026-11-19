---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/xho.html
---
{% raw %}
# So you want to work on Xhosa?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `xho`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Southern Ndebele-Lowland ([Glottolog](https://glottolog.org/resource/languoid/id/xhos1239))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 10.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa, Zimbabwe

**Status:** Official language


## What does Xhosa look and sound like?

**Written (Xhosa)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/xhosa.htm):

> Bonke abantu bazalwa bekhululekile belingana ngesidima
> nangokweemfanelo. Bonke abantu banesiphiwo sesazela nesizathu
> sokwenza isenzo ongathanda ukuba senziwe kumzalwane wakho.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Some corrections to this page by Michael Peter Füstumum

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Xhosa yet ([its Wikitongues page](https://wikitongues.org/languages/xho/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,604 articles in xh.wikipedia; 23 active users. This is ~1/2,898 of English data and ranks 135 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 19,993 pages per crawl on average, which is 0.0009% of the crawl (2026). This is ~1/44,591 of English data and ranks 89 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 0.29 GB (xho_Latn 0.29 GB), equivalent to ≈0.24 GB of English after byte-premium scaling; 2.82 GB removed by filtering. This is ~1/183,338 of English data and ranks 93 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.60 GB (xho_Latn 0.60 GB) (rank 84 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

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

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=260), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.947 (P 0.949, R 0.946, FPR 4.64e-04) averaged over 7 dataset(s). Runner-up: cld2 (F1 0.885).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.949 |    0.946 | 0.947 | 0.000 | ✓                |
| cld2         |       0.885 |    0.895 | 0.885 | 0.002 | ✓                |
| fasttext     |       0.841 |    0.946 | 0.882 | 0.003 | ✓                |
| OpenLID-v2   |       0.775 |    0.960 | 0.844 | 0.004 | ✓                |
| AfroLID      |       0.835 |    0.855 | 0.841 | 0.009 | ✓                |
| py3langid    |       0.604 |    0.892 | 0.684 | 0.014 | ✓                |
| cld3         |       0.563 |    0.878 | 0.660 | 0.020 | ✓                |
| commonlingua |       0.677 |    0.686 | 0.649 | 0.005 | ✓                |
| funlangid    |       0.734 |    0.609 | 0.634 | 0.003 | ✓                |
| pyfranc      |       0.790 |    0.478 | 0.566 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 260 |       0.918 |    0.862 | 0.889 |
| Wikipedia | 300 |       0.911 |    0.883 | 0.897 |
| NTREX     | 300 |       0.948 |    0.963 | 0.955 |
| CommonLID | 300 |       0.993 |    0.943 | 0.968 |
| SmolSent  | 300 |       0.940 |    0.997 | 0.968 |
| UDHR-LID  |  58 |       0.951 |    1.000 | 0.975 |
| FLORES    | 300 |       0.983 |    0.977 | 0.980 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Xhosa to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Xhosa *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Xhosa and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Xhosa has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/xho/) video of Xhosa yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Xhosa?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Xhosa (and whether the model is exclusively tagged for Xhosa or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **266** text-generation models are explicitly tagged for Xhosa (116 original uploads, 150 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Xhosa.
- Including tags inherited from base models: **565**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████              |
|   2023 |       25 | █████                |
|   2024 |       43 | ████████             |
|   2025 |       59 | ███████████          |
|   2026 |      103 | ████████████████████ |

### Largest models tagged for Xhosa

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Xhosa

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-xho-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-xho-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-xho](https://huggingface.co/ptrdvn/kakugo-3B-xho)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-xho-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-xho-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-xho-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-xho-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_45 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Xhosa.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 1 dataset; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 1 dataset; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                             |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 3,955          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                    |
| Machine translation                    |                               | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    |                               | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    |                               | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    |                               | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 180            | Native (crowdsourced Tatoeba sentence pairs)                        |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Xhosa datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Xhosa? Does it make sense to train one?
  - ~0.50 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Xhosa-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 42 of ~18,498 papers (0.23%) (rank 100 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Xhosa

Here are up to ten papers published in 2026 that mention Xhosa. None of the 42 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                        | paper                                                                          | mentioned in   |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| LLM as a Meta-Judge: Synthetic Data for NLP Evaluation Metric Validation                                                     | [2026.acl-srw.125](https://aclanthology.org/2026.acl-srw.125/)                 | body only      |
| Calibrating Beyond English: Language Diversity for Better Quantized Multilingual LLMs                                        | [2026.eacl-long.223](https://aclanthology.org/2026.eacl-long.223/)             | body only      |
| MERLIN: Multi-Stage Curriculum Alignment for Multilingual Encoder-LLM Integration in Cross-Lingual Reasoning                 | [2026.eacl-long.277](https://aclanthology.org/2026.eacl-long.277/)             | body only      |
| TIPA: Typologically Informed Parameter Aggregation                                                                           | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     | body only      |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation               | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) | body only      |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                       | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) | body only      |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                 | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   | body only      |
| Searching for a Unified Approach to Morpheme Segmentation: Benchmarking Supervised and LLM Architectures Across 20 Languages | [2026.findings-emnlp.715](https://aclanthology.org/2026.findings-emnlp.715/)   | body only      |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                             | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                   | body only      |
| Evaluating Open-Source LLMs for Text Summarization and Named Entity Recognition in Long, Unstructured Text                   | [2026.nlp4dh-1.35](https://aclanthology.org/2026.nlp4dh-1.35/)                 | body only      |

{% endraw %}
