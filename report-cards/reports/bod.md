---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bod.html
---
{% raw %}
# So you want to work on Tibetan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bod`

**Language family:** **Sino-Tibetan** › Bodic › Bodish › … › Central Tibetan ([Glottolog](https://glottolog.org/resource/languoid/id/tibe1272))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Writing systems:** `Tibt`

**Speakers:** about 3.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** People's Republic of China

**Status:** Regional official language


## What does Tibetan look and sound like?

**Written:** Omniglot has [a page on Tibetan](https://www.omniglot.com/writing/tibetan.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bod/) has 1 video of Tibetan speakers. Watch [Tenzin speaking Central Tibetan](https://wikitongues.org/videos/tenzin_20160717_bod/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 8,111 articles in bo.wikipedia; 32 active users. This is ~1/930 of English data and ranks 107 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 28,193 pages per crawl on average, which is 0.0013% of the crawl (2026). This is ~1/31,622 of English data and ranks 86 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 0.42 GB (bod_Tibt 0.42 GB), equivalent to ≈0.16 GB of English after byte-premium scaling; 0.11 GB removed by filtering. This is ~1/126,125 of English data and ranks 81 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.47 GB (bod_Tibt 0.47 GB) (rank 92 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                           |
|:-----------------------|:--------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                        |
| UniMorph               | 1,335 lemmas, 5,067 inflected forms ([unimorph/bod](https://github.com/unimorph/bod)) |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._        |
| Wordnets               | **None found**                                                                        |

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

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=53), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.955 (P 0.973, R 0.937, FPR 1.65e-04) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.891).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.973 |    0.937 | 0.955 | 0.000 | ✓                |
| commonlingua |       0.895 |    0.895 | 0.891 | 0.001 | ✓                |
| pyfranc      |       0.886 |    0.793 | 0.829 | 0.001 | ✓                |
| OpenLID-v2   |       0.974 |    0.720 | 0.826 | 0.000 | ✓                |
| fasttext     |       0.745 |    0.995 | 0.816 | 0.002 | ✓                |
| funlangid    |       0.769 |    0.523 | 0.604 | 0.001 | ✓                |
| cld2         |       0.167 |    0.006 | 0.012 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.846 |    0.827 | 0.836 |
| NTREX     | 300 |       0.990 |    0.950 | 0.969 |
| Tatoeba   |  53 |       1.000 |    0.943 | 0.971 |
| UDHR-LID  |  60 |       1.000 |    0.950 | 0.974 |
| SmolSent  | 300 |       1.000 |    0.970 | 0.985 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tibetan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tibetan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tibetan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tibetan has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tibetan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tibetan (and whether the model is exclusively tagged for Tibetan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127** text-generation models are explicitly tagged for Tibetan (58 original uploads, 69 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Tibetan.
- Including tags inherited from base models: **163**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        2 | █                    |
|   2024 |        8 | ██                   |
|   2025 |       10 | ██                   |
|   2026 |      106 | ████████████████████ |

### Largest models tagged for Tibetan

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 856.0B       |                  143 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Tibetan

| model                                                                                           | parameters   |   # languages tagged |   year | derivative of                  |
|:------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------|
| [TenzinGayche/Monlam_Melong_preview](https://huggingface.co/TenzinGayche/Monlam_Melong_preview) | 9.2B         |                    1 |   2024 | buddhist-nlp/gemma2-mitra-base |
| [YoLo2000/TiLamb-7B](https://huggingface.co/YoLo2000/TiLamb-7B)                                 | 7.0B         |                    1 |   2024 | —                              |
| [pkupie/gemma-3-4b-bo-cpt](https://huggingface.co/pkupie/gemma-3-4b-bo-cpt)                     | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt           |
| [ptrdvn/kakugo-3B-bod](https://huggingface.co/ptrdvn/kakugo-3B-bod)                             | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro  |
| [pkupie/Qwen2.5-3B-bo-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-bo-cpt)                     | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                |

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

**8** benchmark datasets in the survey include Tibetan.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      |                               | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      |                               | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      |                               | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      |                               | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                       | —              | Human translation (professional, from English)                   |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 38             | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tibetan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tibetan? Does it make sense to train one?
  - ~0.18 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~2.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tibetan-only model is 9.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 153 of ~18,498 papers (0.83%) (rank 43 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Standard Tibetan | Tibetan

Here are up to ten papers published in 2026 that mention Tibetan. None of the 153 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                        | paper                                                                      | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| Where the Cat Sat: A Multilingual Framework for Spatial Language Understanding                               | [2026.acl-long.1633](https://aclanthology.org/2026.acl-long.1633/)         | body only      |
| Findings of the Second Workshop on Challenges in Processing South Asian Languages (CHiPSAL 2026)             | [2026.chipsal-1.1](https://aclanthology.org/2026.chipsal-1.1/)             | body only      |
| A Morphological Transducer for the Limbu Language                                                            | [2026.chipsal-1.4](https://aclanthology.org/2026.chipsal-1.4/)             | body only      |
| Large-scale Multilingual News Image Captioning with LLMs                                                     | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)     | body only      |
| IndicParam: Benchmark to evaluate LLMs on low-resource Indic Languages                                       | [2026.emnlp-main.250](https://aclanthology.org/2026.emnlp-main.250/)       | body only      |
| Cultural Awareness is Represented but Not Decoded: Tracing Mythological Knowledge across 18 Open-Source LLMs | [2026.findings-aacl.227](https://aclanthology.org/2026.findings-aacl.227/) | body only      |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                   | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)             | body only      |
| Insights from Romanized Manipuri Social Media Text: A Transliteration Corpus and Variation Analysis          | [2026.lrec-1.147](https://aclanthology.org/2026.lrec-1.147/)               | body only      |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                    | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)               | body only      |
| Benchmarking Multilingual LLM Translation Accuracy for Fuzhounese                                            | [2026.sigul-1.20](https://aclanthology.org/2026.sigul-1.20/)               | body only      |

{% endraw %}
