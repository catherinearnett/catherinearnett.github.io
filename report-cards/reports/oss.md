---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/oss.html
---
{% raw %}
# So you want to work on Ossetian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `oss`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Modern Ossetic ([Glottolog](https://glottolog.org/resource/languoid/id/iron1242))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Cyrl`

**Speakers:** about 558,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Ossetian look and sound like?

**Written:** Omniglot has [a page on Ossetian](https://www.omniglot.com/writing/ossetian.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/oss/) has 2 videos of Ossetian speakers. Watch [Alana speaking Two dialects of Ossetian, Iron and Digorsky (Digor), the language of Northern Ossetia-Alania](https://wikitongues.org/videos/alana_20170705_oss/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                             |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 21,763 articles in os.wikipedia; 28 active users. This is ~1/347 of English data and ranks 85 of the 168 languages in the set with any data in Wikipedia; 164 have none.           |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                           |
| FineWeb                | 88.4 MB (oss_Cyrl 90.0 MB); 34.6 MB removed by filtering. This is ~1/604,463 of English data and ranks 110 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 83.0 MB (oss_Cyrl 83.0 MB) (rank 124 of the 166 languages in the set that have any; 166 have none)                                                                                 |

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

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_os) en → os: size not listed                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=300), UDHR-LID (n=44), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.993 (P 0.996, R 0.990, FPR 3.18e-05) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.958).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.990 | 0.993 | 0.000 | ✓                |
| fasttext     |       0.942 |    0.974 | 0.958 | 0.001 | ✓                |
| funlangid    |       0.929 |    0.787 | 0.847 | 0.001 | ✓                |
| pyfranc      |       0.921 |    0.743 | 0.813 | 0.001 | ✓                |
| commonlingua |       0.959 |    0.636 | 0.642 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.993 |    0.977 | 0.985 |
| Wikipedia | 300 |       0.993 |    0.993 | 0.993 |
| UDHR-LID  |  44 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ossetian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Ossetian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ossetian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Ossetian has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Ossetian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ossetian (and whether the model is exclusively tagged for Ossetian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **38** text-generation models are explicitly tagged for Ossetian (18 original uploads, 20 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Ossetian.
- Including tags inherited from base models: **42**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        4 | ████                 |
|   2024 |        5 | █████                |
|   2025 |        7 | ███████              |
|   2026 |       21 | ████████████████████ |

### Largest models tagged for Ossetian

| model                                                                                                                         | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                     | 1.9T         |                  143 |   2025 | —                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                         | 856.0B       |                  143 |   2025 | —                             |
| [nightmedia/Qwen3-32B-Element3-qx64-hi-mlx](https://huggingface.co/nightmedia/Qwen3-32B-Element3-qx64-hi-mlx)                 | 32.8B        |                    3 |   2026 | nightmedia/Qwen3-32B-Element3 |
| [nightmedia/Qwen3-32B-Element5-Heretic-qx86-hi-mlx](https://huggingface.co/nightmedia/Qwen3-32B-Element5-Heretic-qx86-hi-mlx) | 32.8B        |                    3 |   2026 | nightmedia/Qwen3-32B-Element5 |
| [NxcodeOfficial/NxCode-SafeCoder-30B](https://huggingface.co/NxcodeOfficial/NxCode-SafeCoder-30B)                             | 30.5B        |                    2 |   2025 | —                             |

### Models tagged *only* for Ossetian

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [ctaxnagomi/DGUI-OSEngine](https://huggingface.co/ctaxnagomi/DGUI-OSEngine)           |                    1 |   2025 | —               |
| [goldfish-models/oss_cyrl_10mb](https://huggingface.co/goldfish-models/oss_cyrl_10mb) |                    1 |   2024 | —               |
| [goldfish-models/oss_cyrl_5mb](https://huggingface.co/goldfish-models/oss_cyrl_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/oss_cyrl_full](https://huggingface.co/goldfish-models/oss_cyrl_full) |                    1 |   2024 | —               |

_11 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Ossetian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             58 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                          | Direction(s)   | Size            | Human reference   |
|:--------------------------------------------------------------------------------------------------|:---------------|:----------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_os) (training data) | en → os        | size not listed | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ossetian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ossetian? Does it make sense to train one?
  - ~42.3 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~528.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,498 papers (0.02%) (rank 199 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Iron Ossetic | Ossetian

Here are up to ten papers published in 2026 that mention Ossetian. None of the 4 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                     | paper                                                                          |
|:--------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| TIPA: Typologically Informed Parameter Aggregation                        | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Computationally Invisible: Charting the NLP Landscape of Iranic Languages | [2026.findings-emnlp.2362](https://aclanthology.org/2026.findings-emnlp.2362/) |
| Goldfish: Monolingual Language Models for 350 Languages                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| MultiWikiQA: A Reading Comprehension Benchmark in 300+ Languages          | [2026.lrec-1.499](https://aclanthology.org/2026.lrec-1.499/)                   |

{% endraw %}
