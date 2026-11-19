---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/heb.html
---
{% raw %}
# So you want to work on Hebrew?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `heb`

**Language family:** **Afro-Asiatic** › Semitic › West Semitic › … › Hebrewic ([Glottolog](https://glottolog.org/resource/languoid/id/hebr1245))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Hebr`

**Speakers:** about 9.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Israel, South Africa

**Status:** Official language


## What does Hebrew look and sound like?

**Written:** Omniglot has [a page on Hebrew](https://www.omniglot.com/writing/hebrew.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/heb/) has 7 videos of Hebrew speakers. Watch [See all](https://wikitongues.org/videos/?language=heb).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 408,229 articles in he.wikipedia; 6,504 active users. This is ~1/18 of English data and ranks 30 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 5,486,293 pages per crawl on average, which is 0.2544% of the crawl (2026). This is ~1/162 of English data and ranks 28 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 24.90 GB (heb_Hebr 24.90 GB), equivalent to ≈18.37 GB of English after byte-premium scaling; 36.03 GB removed by filtering. This is ~1/2,145 of English data and ranks 31 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 8.75 GB (heb_Hebr 8.75 GB) (rank 21 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 14,361 sentences / 273,830 tokens in total: [UD_Hebrew-HTB](https://github.com/UniversalDependencies/UD_Hebrew-HTB) (6,143 sentences), [UD_Hebrew-IAHLTknesset](https://github.com/UniversalDependencies/UD_Hebrew-IAHLTknesset) (2,883 sentences), [UD_Hebrew-IAHLTwiki](https://github.com/UniversalDependencies/UD_Hebrew-IAHLTwiki) (5,039 sentences), [UD_Hebrew-PostRab](https://github.com/UniversalDependencies/UD_Hebrew-PostRab) (296 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,176 lemmas, 33,177 inflected forms ([unimorph/heb](https://github.com/unimorph/heb))                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Wordnets               | [Hebrew Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-he-1.4.tar.xz): 5,448 synsets, 5,379 words, 6,872 senses; licence: wordnet; [MultiWordNet](http://multiwordnet.fbk.eu/english/home.php) (size not listed); licence: CC-BY 3.0.                                                                                                                                                                                                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                        |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                            |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([heb](https://ebible.org/details.php?id=heb), Public Domain). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                         |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Hebr script) — the same sentences in 200+ languages                               |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Hebr script) — paired with English                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.993 (P 0.992, R 0.994, FPR 1.43e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.986).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.992 |    0.994 | 0.993 | 0.000 | ✓                |
| OpenLID-v2   |       0.976 |    0.997 | 0.986 | 0.001 | ✓                |
| fasttext     |       0.976 |    0.997 | 0.986 | 0.001 | ✓                |
| commonlingua |       0.990 |    0.968 | 0.979 | 0.000 | ✓                |
| cld3         |       0.976 |    0.977 | 0.976 | 0.001 | ✓                |
| pyfranc      |       0.976 |    0.974 | 0.975 | 0.001 | ✓                |
| cld2         |       0.993 |    0.951 | 0.971 | 0.000 | ✓                |
| funlangid    |       0.982 |    0.931 | 0.954 | 0.000 | ✓                |
| py3langid    |       0.905 |    0.989 | 0.938 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.954 |    0.967 | 0.960 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| Wikipedia | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hebrew to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hebrew *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hebrew and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hebrew?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hebrew (and whether the model is exclusively tagged for Hebrew or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **790** text-generation models are explicitly tagged for Hebrew (307 original uploads, 483 fine-tunes/quantisations/merges).
- **66** are tagged *only* for Hebrew.
- Including tags inherited from base models: **1,531**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       17 | █                    |
|   2023 |       24 | ██                   |
|   2024 |      161 | ██████████           |
|   2025 |      279 | ██████████████████   |
|   2026 |      309 | ████████████████████ |

### Largest models tagged for Hebrew

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                               |
| [liskcell/qunie-6.2](https://huggingface.co/liskcell/qunie-6.2)                                         | 1.1T         |                    2 |   2026 | —                               |
| [liskcell/LPT-6.1-Thinking](https://huggingface.co/liskcell/LPT-6.1-Thinking)                           | 1.0T         |                    2 |   2026 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |

### Largest models tagged *only* for Hebrew

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of          |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------|
| [liskcell/Qunie-V7-mini](https://huggingface.co/liskcell/Qunie-V7-mini)                             | 7.5B         |                    1 |   2026 | liskCell/Qunie-V7-mini |
| [618AI/dictalm2-it-qa-fine-tune](https://huggingface.co/618AI/dictalm2-it-qa-fine-tune)             | 7.3B         |                    1 |   2024 | dicta-il/dictalm2.0    |
| [alphaedge-ai/Qwen3.5-4B-heb-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-heb-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B             |
| [alphaedge-ai/gemma-3-4b-it-heb-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-heb-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it   |
| [Norod78/hebrew_lyrics-gemma2_2b](https://huggingface.co/Norod78/hebrew_lyrics-gemma2_2b)           | 2.6B         |                    1 |   2025 | google/gemma-2-2b      |

_90 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Hebrew.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 5 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 5 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 4 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">5 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                          |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 96             | Treebank-based (automatic)                            |
| 1. Linguistic knowledge                | BLiMP                          | [CLAMS](https://github.com/aaronmueller/clams)                                                      | 40,800         | Template-based (Marvin & Linzen grammars, translated) |
| 1. Linguistic knowledge                | BLiMP                          | [Colorless green (Gulordava et al.)](https://github.com/facebookresearch/colorlessgreenRNNs)        | 373            | Treebank-extracted (+ nonce variants)                 |
| 1. Linguistic knowledge                | BLiMP                          | [HeCLiMP](https://github.com/NLU-BGU/tafberta)                                                      | 13,988         | Template-based                                        |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,330          | Treebank-based (automatic, UD + UniMorph)             |
| 2. Pragmatics, discourse & coreference | WSC                            | [Hebrew Winograd Schemas](https://www.cs.ubc.ca/~vshwartz/resources/winograd_he.html)               | 139            | Translation (method not stated)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                               |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)            |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                      |
| 4. Reading comprehension               | QA – extractive RC             | HeQ                                                                                                 | —              | Native                                                |
| 4. Reading comprehension               | QA – extractive RC             | ParaShoot                                                                                           | —              | Native                                                |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                     |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                              |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)        |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 10,915         | Native (crowdsourced Tatoeba sentence pairs)          |

### Standard machine translation test sets

Hebrew has been part of the WMT translation task in **1** year (2023).

| Test set                                                                  | Direction(s)                       | Size                            | Human reference   |
|:--------------------------------------------------------------------------|:-----------------------------------|:--------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)          | 2,009 sentences (Hebr)          | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)  | 1,358 sentences (Hebr)          | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-he_IL) | en → he_IL                         | 998 segments                    | ✅                |
| [WMT23 general task](https://www2.statmt.org/wmt23/)                      | English → Hebrew; Hebrew → English | 2,074 segments / 1,910 segments | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hebrew datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hebrew? Does it make sense to train one?
  - ~18.37 GB English-equivalent text ≈ 4.59B tokens, enough for a compute-optimal model of ~229.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hebrew-only model is 7.5B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 213 of ~18,498 papers (1.15%) (rank 32 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Hebrew

Here are up to ten papers published in 2026 that mention Hebrew. None of the 213 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                  | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| New Terms, New Toxicity: Consensus-based Chinese Neologism Toxicity Detection via Search-Augmented LLMs                | [2026.acl-long.1602](https://aclanthology.org/2026.acl-long.1602/)             |
| Translation from the Information Bottleneck Perspective: an Efficiency Analysis of Spatial Prepositions in Bitexts     | [2026.cmcl-1.20](https://aclanthology.org/2026.cmcl-1.20/)                     |
| NaijaS2ST: A Multi-Accent Benchmark for Speech-to-Speech Translation in Low-Resource Nigerian Languages                | [2026.emnlp-main.665](https://aclanthology.org/2026.emnlp-main.665/)           |
| HSS-Synth: Humanities and Social Sciences Data Synthesis for LLMs                                                      | [2026.findings-acl.1880](https://aclanthology.org/2026.findings-acl.1880/)     |
| Better as Generators Than Classifiers: Leveraging LLMs and Synthetic Data for Low-Resource Multilingual Classification | [2026.findings-eacl.148](https://aclanthology.org/2026.findings-eacl.148/)     |
| Loci Similes: A Benchmark for Extracting Intertextualities in Latin Literature                                         | [2026.findings-emnlp.1224](https://aclanthology.org/2026.findings-emnlp.1224/) |
| ROG: A Multi-Layer Manually Annotated Corpus of Spoken Slovenian                                                       | [2026.lrec-1.449](https://aclanthology.org/2026.lrec-1.449/)                   |
| Preserving Endangered Linguistic Heritage: Developing a Corpus for the Study of Contact-induced Changes in Corfioto    | [2026.lrec-1.76](https://aclanthology.org/2026.lrec-1.76/)                     |
| Beyond Aggregate Loss: Training Dynamics and Language-Specific Scaling Laws for Multilingual Language Models           | [2026.mrl-1.23](https://aclanthology.org/2026.mrl-1.23/)                       |
| What LID Systems Say About Dialectal Variation. The Case of Yiddish, Quechua and Mande                                 | [2026.speakable-1.11](https://aclanthology.org/2026.speakable-1.11/)           |

{% endraw %}
