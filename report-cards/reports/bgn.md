---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bgn.html
---
{% raw %}
# So you want to work on Balochi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bgn` · macrolanguage `bal`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Southern-Western Balochi ([Glottolog](https://glottolog.org/resource/languoid/id/west2368))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Speakers:** about 2.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Afghanistan

**Status:** Regional official language


## What does Balochi look and sound like?

**Written:** no Omniglot page found for Balochi.

**Spoken:** no Wikitongues video of Balochi yet ([its Wikitongues page](https://wikitongues.org/languages/bgn/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                           |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                       |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                        |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bal) en → bal: 3,994 lexicon entries ⚠️ Listed under the macrolanguage code `bal`, so this may cover other varieties as well as Balochi. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **1 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID.
- **Eval datasets (1):** Tatoeba (n=192)
- **Best model:** GlotLID — F1 0.827 (P 0.993, R 0.708, FPR 2.76e-05) averaged over 1 dataset(s). Runner-up: AfroLID (F1 0.000).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.993 |    0.708 | 0.827 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Balochi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Balochi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Balochi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Balochi has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/bgn/) video of Balochi yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Balochi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Balochi (and whether the model is exclusively tagged for Balochi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8** text-generation models are explicitly tagged for Balochi (3 original uploads, 5 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Balochi.
- Including tags inherited from base models: **9**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        2 | ███████              |
|   2025 |        0 |                      |
|   2026 |        6 | ████████████████████ |

### Largest models tagged for Balochi

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3)                     | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it      |
| [nassimjp/LFM2.5-2.6B-Pashto-Zi-b](https://huggingface.co/nassimjp/LFM2.5-2.6B-Pashto-Zi-b)                 | 2.7B         |                    5 |   2026 | LiquidAI/LFM2.5-2.6B-Base |
| [nassimjp/Qwen3.5-2B-Base-Pashto-Plus](https://huggingface.co/nassimjp/Qwen3.5-2B-Base-Pashto-Plus)         | 1.9B         |                    6 |   2026 | Qwen/Qwen3.5-2B-Base      |
| [umairjamali/balochi-qwen-2.5-7b-instruct](https://huggingface.co/umairjamali/balochi-qwen-2.5-7b-instruct) | 40.4M        |                    1 |   2026 | Qwen/Qwen2.5-7B           |

### Largest models tagged *only* for Balochi

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [umairjamali/balochi-qwen-2.5-7b-instruct](https://huggingface.co/umairjamali/balochi-qwen-2.5-7b-instruct) | 40.4M        |                    1 |   2026 | Qwen/Qwen2.5-7B |

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Balochi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level               | task   | dataset                                                                              |   # test items | construction                                 |
|:--------------------|:-------|:-------------------------------------------------------------------------------------|---------------:|:---------------------------------------------|
| Machine translation |        | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             48 | Native (crowdsourced Tatoeba sentence pairs) |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)   | Size                  | Human reference   |
|:---------------------------------------------------------------------------------------------------|:---------------|:----------------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_bal) (training data) | en → bal       | 3,994 lexicon entries | ✅                |

_⚠️ Listed under the macrolanguage code `bal`, so this may cover other varieties as well as Balochi._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Balochi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Balochi? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Balochi-only model is 40.4M, aim no higher than
  *2. Pragmatics, discourse & coreference* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,498 papers (0.04%) (rank 172 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Western Balochi | Balochi

Here are up to ten papers published in 2026 that mention Balochi. None of the 7 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                     | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Framing Political Bias in Multilingual LLMs Across Pakistani Languages                                    | [2026.acl-long.1689](https://aclanthology.org/2026.acl-long.1689/)             |
| Fairness Evaluation and Inference Level Mitigation in LLMs                                                | [2026.findings-acl.1452](https://aclanthology.org/2026.findings-acl.1452/)     |
| Computationally Invisible: Charting the NLP Landscape of Iranic Languages                                 | [2026.findings-emnlp.2362](https://aclanthology.org/2026.findings-emnlp.2362/) |
| From Press to Pixels: Evolving Urdu Text Recognition                                                      | [2026.lrec-1.235](https://aclanthology.org/2026.lrec-1.235/)                   |
| Common Voice for Pakistan: Developing an Open Speech Corpus for Low-Resource Pakistani Languages          | [2026.lrec-1.265](https://aclanthology.org/2026.lrec-1.265/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Progressing beyond Art Masterpieces or Touristic Clichés: how to assess your LLMs for cultural alignment? | [2026.resourceful-4.13](https://aclanthology.org/2026.resourceful-4.13/)       |

{% endraw %}
