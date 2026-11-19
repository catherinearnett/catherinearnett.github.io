---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/div.html
---
{% raw %}
# So you want to work on Dhivehi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `div`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Dhivehi-Sinhala ([Glottolog](https://glottolog.org/resource/languoid/id/dhiv1236))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Thaa`

**Speakers:** about 385,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Maldives

**Status:** Official and national language


## What does Dhivehi look and sound like?

**Written:** no Omniglot page found for Dhivehi.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/div/) has 1 video of Dhivehi speakers. Watch [Mohammed speaking Addu dialect](https://wikitongues.org/videos/mohammed_20210413_div/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,235 articles in dv.wikipedia; 15 active users. This is ~1/2,333 of English data and ranks 127 of the 168 languages in the set with any data in Wikipedia; 164 have none.                            |
| Common Crawl           | 52,919 pages per crawl on average, which is 0.0025% of the crawl (2026). This is ~1/16,847 of English data and ranks 76 of the 115 languages in the set with any data in Common Crawl; 217 have none. |
| FineWeb                | 0.38 GB (div_Thaa 0.38 GB); 0.28 GB removed by filtering. This is ~1/139,551 of English data and ranks 87 of the 261 languages in the set with any data in FineWeb; 71 have none.                     |
| Goldfish training data | 1.33 GB (div_Thaa 1.33 GB) (rank 69 of the 171 languages in the set that have any; 161 have none)                                                                                                     |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | **None found**                                                                          |
| Wikidata labels        | 524,348 Wikidata items have a label in Dhivehi. (Wikidata codes (labels): dv (524,348)) |
| Wordnets               | **None found**                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 95,809 sentence pairs with English across 6 corpora; largest: [Tanzil](https://opus.nlpl.eu/Tanzil) (93,540), [QED](https://opus.nlpl.eu/QED) (1,052), [translatewiki](https://opus.nlpl.eu/translatewiki) (902), [wikimedia](https://opus.nlpl.eu/wikimedia) (258), [GNOME](https://opus.nlpl.eu/GNOME) (53). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                    |
| Tatoeba                                                                                  | 58 sentences, 56 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/div/none)).                                                                                                                                                                                                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                              |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Thaa script) — paired with English                                                                                                                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_dv) en → dv: 3,973 lexicon entries                                                                                                                                                                                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid.
- **Eval datasets (4):** NTREX (n=300), Tatoeba (n=58), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** commonlingua — F1 0.995 (P 0.999, R 0.991, FPR 5.11e-06) averaged over 4 dataset(s). Runner-up: GlotLID (F1 0.995).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| commonlingua |       0.999 |    0.991 | 0.995 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.990 | 0.995 | 0.000 | ✓                |
| cld2         |       0.999 |    0.990 | 0.994 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.985 | 0.992 | 0.000 | ✗                |
| funlangid    |       1.000 |    0.967 | 0.983 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (commonlingua) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.963 | 0.980 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   |  58 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dhivehi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dhivehi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dhivehi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Dhivehi has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Dhivehi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dhivehi (and whether the model is exclusively tagged for Dhivehi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **38** text-generation models are explicitly tagged for Dhivehi (12 original uploads, 26 fine-tunes/quantisations/merges).
- **14** are tagged *only* for Dhivehi.
- Including tags inherited from base models: **41**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        5 | █████                |
|   2025 |       11 | ███████████          |
|   2026 |       20 | ████████████████████ |

### Largest models tagged for Dhivehi

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                       |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                       |
| [mohamedrayyan/dhivehi-news-lora-qwen3-30b](https://huggingface.co/mohamedrayyan/dhivehi-news-lora-qwen3-30b) | 30.0B        |                    1 |   2026 | Qwen/Qwen3-30B-A3B-Base |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                       | 8.6B         |                  189 |   2023 | —                       |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                       | 8.6B         |                  189 |   2023 | —                       |

### Largest models tagged *only* for Dhivehi

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------|
| [mohamedrayyan/dhivehi-news-lora-qwen3-30b](https://huggingface.co/mohamedrayyan/dhivehi-news-lora-qwen3-30b) | 30.0B        |                    1 |   2026 | Qwen/Qwen3-30B-A3B-Base      |
| [naturecodeproject/dhivehi](https://huggingface.co/naturecodeproject/dhivehi)                                 | 7.6B         |                    1 |   2026 | Qwen/Qwen3-8B-Base           |
| [Serialtechlab/dhivehi-orpheus-tts](https://huggingface.co/Serialtechlab/dhivehi-orpheus-tts)                 | 3.3B         |                    1 |   2026 | unsloth/orpheus-3b-0.1-ft    |
| [hilarl/naturecode-dhivehi-270m](https://huggingface.co/hilarl/naturecode-dhivehi-270m)                       | 270.0M       |                    1 |   2026 | google/functiongemma-270m-it |
| [alakxender/gemma-3-270m-dhivehi-ctx](https://huggingface.co/alakxender/gemma-3-270m-dhivehi-ctx)             | 268.1M       |                    1 |   2025 | google/gemma-3-270m          |

_14 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Dhivehi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |              4 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                          | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                       | ↔ English (and 8 pivot languages) | 1,358 sentences (Thaa) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_dv) (training data) | en → dv                           | 3,973 lexicon entries  | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dhivehi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dhivehi? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Dhivehi-only model is 30.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 5 of ~18,498 papers (0.03%) (rank 190 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Maldivian | Dhivehi

Here are up to ten papers published in 2026 that mention Dhivehi. None of the 5 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                          | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| IndicJR: A Judge-Free Benchmark of Jailbreak Robustness in South Asian Languages                               | [2026.eacl-industry.50](https://aclanthology.org/2026.eacl-industry.50/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                             | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| IndicSafe: A Benchmark for Evaluating Multilingual LLM Safety in South Asia                                    | [2026.findings-emnlp.2135](https://aclanthology.org/2026.findings-emnlp.2135/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                        | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |

{% endraw %}
