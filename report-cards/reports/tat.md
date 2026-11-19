---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tat.html
---
{% raw %}
# So you want to work on Tatar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tat`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › Bashkiric ([Glottolog](https://glottolog.org/resource/languoid/id/tata1255))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Cyrl` and `Latn`

**Speakers:** about 2.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Tatar look and sound like?

**Written:** Omniglot has [a page on Tatar](https://www.omniglot.com/writing/tatar.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tat/) has 3 videos of Tatar speakers. Watch [Chingis speaking Tatar](https://wikitongues.org/videos/chingis_20180409_tat/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 709,305 articles in tt.wikipedia; 101 active users. This is ~1/11 of English data and ranks 23 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                        |
| Common Crawl           | 166,163 pages per crawl on average, which is 0.0077% of the crawl (2026). This is ~1/5,365 of English data and ranks 59 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                            |
| FineWeb                | 0.56 GB (tat_Cyrl 0.52 GB; tat_Latn 44.0 MB), equivalent to ≈0.32 GB of English after byte-premium scaling; 1.94 GB removed by filtering. This is ~1/94,773 of English data and ranks 80 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 2.27 GB (tat_Cyrl 2.27 GB) (rank 57 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                |

**By writing system:**

| Writing system    | FineWeb                         | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:--------------------------------|:------------------------------|:-------------|:-------------------------------|
| Cyrillic (`Cyrl`) | 0.52 GB (+1.92 GB filtered out) | 0.28 GB                       | 2.27 GB      | 1.23 GB                        |
| Latin (`Latn`)    | 44.1 MB (+20.6 MB filtered out) | 35.3 MB                       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                          |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 148 sentences / 2,280 tokens in total: [UD_Tatar-NMCTT](https://github.com/UniversalDependencies/UD_Tatar-NMCTT) (148 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,283 lemmas, 7,832 inflected forms ([unimorph/tat](https://github.com/unimorph/tat))                                                                                                                                |
| Wikidata labels        | 843,016 Wikidata items have a label in Tatar. (Wikidata codes (labels): tt (843,016))                                                                                                                                |
| Wordnets               | **None found**                                                                                                                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 10,832,993 sentence pairs with English across 11 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (10,495,969), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (126,003), [Tanzil](https://opus.nlpl.eu/Tanzil) (123,374), [XLEnt](https://opus.nlpl.eu/XLEnt) (33,305), [WikiMatrix](https://opus.nlpl.eu/WikiMatrix) (32,154). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                              |
| Tatoeba                                                                                  | 102,481 sentences, 12,681 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/tat/none)).                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                     |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.963 (P 0.953, R 0.975, FPR 7.37e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.894).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.953 |    0.975 | 0.963 | 0.001 | ✓                |
| cld2         |       0.842 |    0.959 | 0.894 | 0.003 | ✓                |
| commonlingua |       0.836 |    0.852 | 0.821 | 0.002 | ✓                |
| funlangid    |       0.803 |    0.677 | 0.722 | 0.002 | ✓                |
| py3langid    |       0.630 |    0.816 | 0.692 | 0.006 | ✓                |
| fasttext     |       0.594 |    0.856 | 0.672 | 0.006 | ✓                |
| pyfranc      |       0.584 |    0.719 | 0.631 | 0.007 | ✓                |
| OpenLID-v2   |       0.509 |    0.862 | 0.592 | 0.013 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.839 |    0.940 | 0.887 |
| Tatoeba   | 300 |       0.880 |    0.973 | 0.924 |
| Wikipedia | 300 |       0.996 |    0.940 | 0.967 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tatar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tatar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tatar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tatar has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tatar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tatar (and whether the model is exclusively tagged for Tatar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **139** text-generation models are explicitly tagged for Tatar (18 original uploads, 121 fine-tunes/quantisations/merges).
- **86** are tagged *only* for Tatar.
- Including tags inherited from base models: **149**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        4 | █                    |
|   2024 |        8 | ██                   |
|   2025 |       25 | █████                |
|   2026 |      101 | ████████████████████ |

### Largest models tagged for Tatar

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —                         |
| [raahemnabeel/ornith-1.5-122b](https://huggingface.co/raahemnabeel/ornith-1.5-122b)                           | 122.0B       |                    1 |   2026 | ornith-ai/Ornith-1.5-122B |
| [raahemnabeel/qwen3-5-122b-a10b](https://huggingface.co/raahemnabeel/qwen3-5-122b-a10b)                       | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B    |
| [jashansinghTT/gpt-oss-120b-blackhole-fast](https://huggingface.co/jashansinghTT/gpt-oss-120b-blackhole-fast) | 120.0B       |                    1 |   2026 | openai/gpt-oss-120b       |

### Largest models tagged *only* for Tatar

| model                                                                                                                               | parameters   |   # languages tagged |   year | derivative of                           |
|:------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------|
| [raahemnabeel/ornith-1.5-122b](https://huggingface.co/raahemnabeel/ornith-1.5-122b)                                                 | 122.0B       |                    1 |   2026 | ornith-ai/Ornith-1.5-122B               |
| [raahemnabeel/qwen3-5-122b-a10b](https://huggingface.co/raahemnabeel/qwen3-5-122b-a10b)                                             | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B                  |
| [jashansinghTT/gpt-oss-120b-blackhole-fast](https://huggingface.co/jashansinghTT/gpt-oss-120b-blackhole-fast)                       | 120.0B       |                    1 |   2026 | openai/gpt-oss-120b                     |
| [ndaly/Mistral-Small-4-119B-2603](https://huggingface.co/ndaly/Mistral-Small-4-119B-2603)                                           | 119.0B       |                    1 |   2026 | mistralai/Mistral-Small-4-119B-2603     |
| [jashansinghTT/kimi-linear-48b-a3b-instruct-blackhole](https://huggingface.co/jashansinghTT/kimi-linear-48b-a3b-instruct-blackhole) | 48.0B        |                    1 |   2026 | moonshotai/Kimi-Linear-48B-A3B-Instruct |

_26 tagged models have unknown parameter counts and are not ranked by size._

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

**7** benchmark datasets in the survey include Tatar.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                    | dataset                                                                              |   # test items | construction                                   |
|:------------------------------|:------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                   | [TatBLiMP](https://huggingface.co/datasets/ilchats/TatBLiMP)                         |          1,248 | Corpus-extracted + automatic perturbation      |
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                       |            700 | Native (school/entrance exams)                 |
| Machine translation           |                         | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation           |                         | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          1,451 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tatar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tatar? Does it make sense to train one?
  - ~1.23 GB English-equivalent text ≈ 0.31B tokens, enough for a compute-optimal model of ~15.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tatar-only model is 122.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 57 of ~18,498 papers (0.31%) (rank 79 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tatar

Here are up to ten papers published in 2026 that mention Tatar. None of the 57 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                     | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                                                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                                        | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Bootstrapping NLP for Sakha: Named Entity Recognition and Sentiment Analysis in an Extremely Low-Resource Setting                                         | [2026.lrec-1.259](https://aclanthology.org/2026.lrec-1.259/)               |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                                                      | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)               |
| ICT-NLP at SemEval-2026 Task 3: Less Is More — Multilingual Encoder with Joint Training and Adaptive Ensemble for Dimensional Aspect Sentiment Regression | [2026.semeval-1.131](https://aclanthology.org/2026.semeval-1.131/)         |
| kevinyu66 at SemEval-2026 Task 3: A Retrieval-Augmented LLM System for Aspect–Opinion Triplet Extraction                                                  | [2026.semeval-1.16](https://aclanthology.org/2026.semeval-1.16/)           |
| AILS-NTUA at SemEval-2026 Task 3: Efficient Dimensional Aspect-Based Sentiment Analysis                                                                   | [2026.semeval-1.163](https://aclanthology.org/2026.semeval-1.163/)         |
| TeamLasse at SemEval-2026 Task 3: A Hybrid Generative-Discriminative Framework for Dimensional Aspect-Based Sentiment Analysis                            | [2026.semeval-1.273](https://aclanthology.org/2026.semeval-1.273/)         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                                                 | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                     |
| Dictionary-Based Speculative Decoding for Non-Latin-Script Languages                                                                                      | [2026.unlp-1.15](https://aclanthology.org/2026.unlp-1.15/)                 |

{% endraw %}
