---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kaz.html
---
{% raw %}
# So you want to work on Kazakh?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kaz`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › South Kipchak ([Glottolog](https://glottolog.org/resource/languoid/id/kaza1248))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 14.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Kazakhstan

**Status:** Official language


## What does Kazakh look and sound like?

**Written (the Arabic alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/kazakh.htm):

> بارلىق ادامدار تۋمىسىنان ازات جانە قادىر‐قاسىييەتى مەن كۇقىقتارى تەڭ بولىپ دۇنىييەگە كەلەدى. ادامدارعا اقىل‐پاراسات، ار‐وجدان بەرىلگەن، سوندىقتان ولار بىر‐بىرىمەن تۋىستىق، باۋىرمالدىق قارىم‐قاتىناس جاساۋلارى ٴتىيىس.

**Written (the Latin alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/kazakh.htm):

> Barlıq adamdar twmısınan azat jäne
> qadir-qasïyeti men quqıqtarı teñ bolıp
> dünïyege keledi. Adamdarğa aqıl-parasat,
> ar-ojdan berilgen, sondıqtan olar bir-birimen twıstıq,
> bawırmaldıq qarım-qatınas jasawları tïis.

**Written (the Cyrillic alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/kazakh.htm):

> Барлық адамдар тумысынан азат және қадір-қасиеті мен кұқықтары тең болып дүниеге келеді. Адамдарға ақыл-парасат, ар-ождан берілген, сондықтан олар бір-бірімен туыстық, бауырмалдық қарым-қатынас жасаулары тиіс.
> Transliteration
> Barlıq adamdar tumısınan azat jäne qadir qasyeti men kûqıqtarı teŋ bolıp dünyege keledi. Adamdarġa aqıl
> parasat, ar ojdan berilgen, sondıqtan olar bir birimen tuıstıq, …

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Improvements supplied by 이윤호

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_kazakh.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kaz/) has 4 videos of Kazakh speakers. Watch [Yernur speaking Kazakh](https://wikitongues.org/videos/yernur_20180502_kaz/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                        |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 245,945 articles in kk.wikipedia; 505 active users. This is ~1/31 of English data and ranks 39 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                     |
| Common Crawl           | 860,796 pages per crawl on average, which is 0.0400% of the crawl (2026). This is ~1/1,036 of English data and ranks 38 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                         |
| FineWeb                | 6.86 GB (kaz_Cyrl 6.86 GB), equivalent to ≈3.89 GB of English after byte-premium scaling; 6.46 GB removed by filtering. This is ~1/7,783 of English data and ranks 44 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 3.47 GB (kaz_Cyrl 3.47 GB) (rank 50 of the 166 languages in the set that have any; 166 have none)                                                                                                                                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,078 sentences / 10,495 tokens in total: [UD_Kazakh-KTB](https://github.com/UniversalDependencies/UD_Kazakh-KTB) (1,078 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 26 lemmas, 357 inflected forms ([unimorph/kaz](https://github.com/unimorph/kaz))                                                                                                                                        |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                          |
| Wordnets               | **None found**                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.988 (P 0.987, R 0.990, FPR 7.59e-05) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.890).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.987 |    0.990 | 0.988 | 0.000 | ✓                |
| cld2         |       0.839 |    0.981 | 0.890 | 0.002 | ✓                |
| pyfranc      |       0.836 |    0.922 | 0.875 | 0.003 | ✓                |
| commonlingua |       0.844 |    0.965 | 0.874 | 0.002 | ✓                |
| funlangid    |       0.848 |    0.877 | 0.861 | 0.002 | ✓                |
| py3langid    |       0.775 |    0.987 | 0.838 | 0.005 | ✓                |
| fasttext     |       0.734 |    0.992 | 0.811 | 0.005 | ✓                |
| OpenLID-v2   |       0.699 |    0.991 | 0.788 | 0.005 | ✓                |
| cld3         |       0.418 |    0.981 | 0.576 | 0.017 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.966 |    0.957 | 0.961 |
| UDHR-LID  |  58 |       0.967 |    1.000 | 0.983 |
| Wikipedia | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kazakh to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kazakh *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kazakh and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kazakh has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Kazakh?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kazakh (and whether the model is exclusively tagged for Kazakh or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **323** text-generation models are explicitly tagged for Kazakh (113 original uploads, 210 fine-tunes/quantisations/merges).
- **99** are tagged *only* for Kazakh.
- Including tags inherited from base models: **380**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       13 | █                    |
|   2024 |       28 | ███                  |
|   2025 |       79 | ████████             |
|   2026 |      195 | ████████████████████ |

### Largest models tagged for Kazakh

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [issai/LLama-3.1-KazLLM-1.0-70B](https://huggingface.co/issai/LLama-3.1-KazLLM-1.0-70B)                 | 70.6B        |                    4 |   2024 | —                               |
| [issai/LLama-3.1-KazLLM-1.0-70B-AWQ4](https://huggingface.co/issai/LLama-3.1-KazLLM-1.0-70B-AWQ4)       | 70.6B        |                    4 |   2024 | —                               |

### Largest models tagged *only* for Kazakh

| model                                                                                         | parameters   |   # languages tagged |   year | derivative of              |
|:----------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------|
| [TilQazyna/llama-kaz-instruct-8B-1](https://huggingface.co/TilQazyna/llama-kaz-instruct-8B-1) | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |
| [Gen2B/Irbis-7b-Instruct_lora](https://huggingface.co/Gen2B/Irbis-7b-Instruct_lora)           | 7.0B         |                    1 |   2024 | —                          |
| [AmanMussa/llama2-kazakh-7b](https://huggingface.co/AmanMussa/llama2-kazakh-7b)               | 6.7B         |                    1 |   2023 | —                          |
| [pkupie/gemma-3-4b-kk-cpt](https://huggingface.co/pkupie/gemma-3-4b-kk-cpt)                   | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt       |
| [alphaedge-ai/Qwen3.5-4B-kaz-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-kaz-32768) | 4.0B         |                    1 |   2026 | Qwen3.5-4B                 |

_55 tagged models have unknown parameter counts and are not ranked by size._

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

**15** benchmark datasets in the survey include Kazakh.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 3 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 3 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | construction                                                   |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 173            | Treebank-based (automatic, UD + UniMorph)                      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms  | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs) |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                         |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                     |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                               |
| 4. Reading comprehension               | QA – extractive RC            | [KazCulture](https://huggingface.co/datasets/issai/KazCulture)                                      | 16,137         | Native (human-crafted)                                         |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | KazMMLU                                                                                             | —              | Native                                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                                 |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                 |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 434            | Native (crowdsourced Tatoeba sentence pairs)                   |

### Standard machine translation test sets

Kazakh has been part of the WMT translation task in **2** years (2019, 2026).

| Test set                                                                 | Direction(s)                       | Size                                | Human reference             |
|:-------------------------------------------------------------------------|:-----------------------------------|:------------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)  | multi-way (all languages)          | 2,009 sentences (Cyrl)              | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)              | ↔ English (and 8 pivot languages)  | 1,358 sentences (Cyrl)              | ✅                          |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                     | English → Kazakh; Kazakh → English | 998 segments / 1,000 segments       | ✅                          |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt) | English → Kazakh                   | 198 documents (28,523 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kazakh datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kazakh? Does it make sense to train one?
  - ~3.89 GB English-equivalent text ≈ 0.97B tokens, enough for a compute-optimal model of ~48.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kazakh-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 130 of ~18,498 papers (0.70%) (rank 48 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Kazakh

Here are up to ten papers published in 2026 that mention Kazakh. None of the 130 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                               | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Efficient Low-Resource Language Adaptation via Multi-Source Dynamic Logit Fusion                                    | [2026.acl-long.207](https://aclanthology.org/2026.acl-long.207/)           |
| LLM Reasoning for Machine Translation: Synthetic Data Generation over Thinking Tokens                               | [2026.emnlp-main.1302](https://aclanthology.org/2026.emnlp-main.1302/)     |
| A Survey on Representing Linguistic Style: Challenges and Opportunities                                             | [2026.emnlp-main.295](https://aclanthology.org/2026.emnlp-main.295/)       |
| Are Language Models Script-Aware?                                                                                   | [2026.findings-aacl.12](https://aclanthology.org/2026.findings-aacl.12/)   |
| MathMist: A Parallel Multilingual Benchmark Dataset for Mathematical Problem Solving and Reasoning                  | [2026.findings-eacl.131](https://aclanthology.org/2026.findings-eacl.131/) |
| Qomhrá: A Bilingual Irish and English Large Language Model                                                          | [2026.loreslm-1.18](https://aclanthology.org/2026.loreslm-1.18/)           |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)           |
| IdiomRanker-X at MWE-2026 AdMIRe 2: Multilingual Idiom-Image Alignment via Low-Rank Adaptation of Cross-Encoders    | [2026.mwe-1.16](https://aclanthology.org/2026.mwe-1.16/)                   |
| ITUNLP at MWE-2026 AdMIRe 2: A Zero-Shot LLM Pipeline for Multimodal Idiom Understanding and Ranking                | [2026.mwe-1.30](https://aclanthology.org/2026.mwe-1.30/)                   |
| Lost in Speech: Trilingual Spoken Hallucination Detection Across Audio and Transcripts                              | [2026.salma-1.6](https://aclanthology.org/2026.salma-1.6/)                 |

{% endraw %}
