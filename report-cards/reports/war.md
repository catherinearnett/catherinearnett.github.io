---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/war.html
---
{% raw %}
# So you want to work on Waray?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `war`

**Language family:** **Austronesian** › Malayo-Polynesian › Greater Central Philippine › … › Samar-Waray ([Glottolog](https://glottolog.org/resource/languoid/id/wara1300))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 3.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Waray look and sound like?

**Written:** no Omniglot page found for Waray.

**Spoken:** no Wikitongues video of Waray yet ([its Wikitongues page](https://wikitongues.org/languages/war/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,267,056 articles in war.wikipedia; 70 active users. This is ~1/6 of English data and ranks 14 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                  |
| Common Crawl           | 37,157 pages per crawl on average, which is 0.0017% of the crawl (2026). This is ~1/23,993 of English data and ranks 82 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                       |
| FineWeb                | 1.8 MB (war_Latn 0), equivalent to ≈1.6 MB of English after byte-premium scaling; 0.66 GB removed by filtering. This is ~1/30,024,762 of English data and ranks 186 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.22 GB (war_Latn 0.22 GB) (rank 105 of the 166 languages in the set that have any; 166 have none)                                                                                                                                          |

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
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_war) en → war: size not listed                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.936 (P 0.979, R 0.902, FPR 1.19e-04) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.890).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.979 |    0.902 | 0.936 | 0.000 | ✓                |
| fasttext     |       0.836 |    0.962 | 0.890 | 0.002 | ✓                |
| OpenLID-v2   |       0.817 |    0.966 | 0.878 | 0.002 | ✓                |
| funlangid    |       0.942 |    0.784 | 0.836 | 0.000 | ✓                |
| commonlingua |       0.780 |    0.823 | 0.789 | 0.002 | ✓                |
| pyfranc      |       0.792 |    0.793 | 0.782 | 0.002 | ✓                |
| cld2         |       0.811 |    0.791 | 0.762 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.978 |    0.743 | 0.845 |
| Wikipedia | 300 |       0.940 |    0.887 | 0.913 |
| UDHR-LID  |  60 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    0.993 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Waray to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Waray *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Waray and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Waray has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/war/) video of Waray yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Waray?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Waray (and whether the model is exclusively tagged for Waray or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **40** text-generation models are explicitly tagged for Waray (7 original uploads, 33 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Waray.
- Including tags inherited from base models: **45**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        4 | ████                 |
|   2025 |       16 | ██████████████████   |
|   2026 |       18 | ████████████████████ |

### Largest models tagged for Waray

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                     | 8.6B         |                  189 |   2023 | —                   |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                     | 8.6B         |                  189 |   2023 | —                   |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                                                       | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base  |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                                                       | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base  |

### Largest models tagged *only* for Waray

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/Qwen3.5-4B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-war-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-war-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-war-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-war-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-war-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-war-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |
| [alphaedge-ai/gemma-3-1b-it-war-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-war-32768) | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Waray.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)              |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          1,512 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)                      | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                            | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                        | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_war) (training data) | en → war                          | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Waray datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Waray? Does it make sense to train one?
  - ~0.20 GB English-equivalent text ≈ 0.05B tokens, enough for a compute-optimal model of ~2.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Waray-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Waray

Here are up to ten papers published in 2026 that mention Waray. None of the 8 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| How Good is Your Wikipedia? Auditing Data Quality for Low-resource and Multilingual NLP                                                       | [2026.acl-long.1373](https://aclanthology.org/2026.acl-long.1373/)         |
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets                                                         | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)                     |
| Tokenization Sets the Measurement Scale for Cross-Lingual Diagnostics                                                                         | [2026.oracle-main.24](https://aclanthology.org/2026.oracle-main.24/)       |

{% endraw %}
