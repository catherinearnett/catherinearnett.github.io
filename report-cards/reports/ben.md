---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ben.html
---
{% raw %}
# So you want to work on Bengali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ben`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Gauda-Banga ([Glottolog](https://glottolog.org/resource/languoid/id/beng1280))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Beng`

**Speakers:** about 279.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Bangladesh, India

**Status:** Official and national language; Regional official language


## What does Bengali look and sound like?

**Written:** Omniglot has [a page on Bengali](https://www.omniglot.com/writing/bengali.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ben/) has 7 videos of Bengali speakers. Watch [See all](https://wikitongues.org/videos/?language=ben).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 192,418 articles in bn.wikipedia; 1,740 active users. This is ~1/39 of English data and ranks 45 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                 |
| Common Crawl           | 2,365,388 pages per crawl on average, which is 0.1097% of the crawl (2026). This is ~1/377 of English data and ranks 34 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                                                                                                                                       |
| FineWeb                | 24.02 GB (ben_Beng 23.99 GB; ben_Latn 30.0 MB), equivalent to ≈9.87 GB of English after byte-premium scaling (⚠️ only 100% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 17.61 GB removed by filtering. This is ~1/2,224 of English data and ranks 32 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 4.50 GB (ben_Beng 4.50 GB) (rank 41 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                           |

**By writing system:**

| Writing system   | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Bengali (`Beng`) | 23.99 GB  | 9.87 GB                       | 4.50 GB      | 1.85 GB                        |
| Latin (`Latn`)   | 30.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                         |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 56 sentences / 320 tokens in total: [UD_Bengali-BRU](https://github.com/UniversalDependencies/UD_Bengali-BRU) (56 sentences). It has POS tags, dependency syntax, lemmas and morphological features.    |
| UniMorph               | 136 lemmas, 4,443 inflected forms ([unimorph/ben](https://github.com/unimorph/ben))                                                                                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                      |
| Wordnets               | [Bengali WordNet](http://www.isical.ac.in/~lru/wordnetnew/) (size not listed); licence: CC By 3.0; [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                 |
|:-----------------------------------|:--------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                     |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([ben2017](https://ebible.org/details.php?id=ben2017)). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** fasttext — F1 0.989 (P 0.986, R 0.992, FPR 1.71e-04) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.989).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| fasttext     |       0.986 |    0.992 | 0.989 | 0.000 | ✓                |
| GlotLID      |       0.987 |    0.991 | 0.989 | 0.000 | ✓                |
| OpenLID-v2   |       0.989 |    0.989 | 0.989 | 0.000 | ✓                |
| cld2         |       0.995 |    0.943 | 0.966 | 0.000 | ✓                |
| py3langid    |       0.933 |    0.984 | 0.954 | 0.001 | ✓                |
| commonlingua |       0.921 |    0.955 | 0.933 | 0.001 | ✓                |
| cld3         |       0.668 |    0.984 | 0.773 | 0.010 | ✓                |
| pyfranc      |       0.667 |    0.971 | 0.769 | 0.009 | ✗                |
| funlangid    |       0.874 |    0.628 | 0.727 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (fasttext) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.949 |    0.997 | 0.972 |
| CommonLID | 300 |       0.980 |    0.973 | 0.977 |
| Wikipedia | 300 |       0.990 |    0.980 | 0.985 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bengali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bengali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bengali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bengali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bengali (and whether the model is exclusively tagged for Bengali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,014** text-generation models are explicitly tagged for Bengali (308 original uploads, 706 fine-tunes/quantisations/merges).
- **115** are tagged *only* for Bengali.
- Including tags inherited from base models: **1,442**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       47 | ██                   |
|   2023 |       51 | ██                   |
|   2024 |      116 | █████                |
|   2025 |      333 | ██████████████       |
|   2026 |      467 | ████████████████████ |

### Largest models tagged for Bengali

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF) | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)   | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                   | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Bengali

| model                                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of              |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------|
| [1-800-LLMs/OSS20B_BN](https://huggingface.co/1-800-LLMs/OSS20B_BN)                                                                                               | 21.5B        |                    1 |   2025 | openai/gpt-oss-20b         |
| [atsuki-yamaguchi/Qwen3-14B-Base-bn-madlad-mean-cv](https://huggingface.co/atsuki-yamaguchi/Qwen3-14B-Base-bn-madlad-mean-cv)                                     | 14.9B        |                    1 |   2025 | Qwen/Qwen3-14B-Base        |
| [KillerShoaib/gemma-2-9b-bangla-16bit](https://huggingface.co/KillerShoaib/gemma-2-9b-bangla-16bit)                                                               | 9.0B         |                    1 |   2024 | google/gemma-2-9b          |
| [KillerShoaib/llama-3-8b-bangla-4bit](https://huggingface.co/KillerShoaib/llama-3-8b-bangla-4bit)                                                                 | 8.2B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-bn-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-bn-madlad-mean-slerp0305-emb) | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B    |

_140 tagged models have unknown parameter counts and are not ranked by size._

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

**31** benchmark datasets in the survey include Bengali.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 10 datasets; Machine translation: 8 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 10 datasets; Machine translation: 8 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                                |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:----------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 21             | Treebank-based (automatic, UD + UniMorph)                                   |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                                       | 340            | Native proverbs; contexts written in English, MT, then corrected by natives |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual)          | 240            | Native                                                                      |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        | 500            | Human translation                                                           |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                                  |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,242          | Machine translation (GPT-3.5-turbo)                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                                      |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                                     |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                                  |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (2 varieties/pairs)                                       | 1,800          | Human translation (professional)                                            |
| 4. Reading comprehension               | QA – extractive RC             | BanglaRQA                                                                                                               | —              | Native                                                                      |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                                | 10,835         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii            |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                           | —              | Machine translation (from MMLU-Pro)                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Human translation (professional)                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                                  | 6,638          | Native (Indian exams; some translated)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                          | 14,042         | Human translation (professional)                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) (2 varieties/pairs)              | 200            | Native (community-written, peer-verified)                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                                    |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                                       | 266            | Native (TyDi questions)                                                     |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (2 varieties/pairs)                                         | 1,708          | Human translation via English pivot                                         |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                                 | 1,012          | Human translation (professional, from English Wikimedia sources)            |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)                              |
| Machine translation                    |                                | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                           | —              | Human translation (professional) of LLM-generated English documents         |
| Machine translation                    |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                          | —              | Human translation (professional, from English)                              |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)                    |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 2,500          | Native (crowdsourced Tatoeba sentence pairs)                                |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                               | 998            | Human translation (professional) + post-edits                               |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bengali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bengali? Does it make sense to train one?
  - ~9.87 GB English-equivalent text ≈ 2.47B tokens, enough for a compute-optimal model of ~123.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bengali-only model is 21.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 427 of ~18,498 papers (2.31%) (rank 16 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bengali

Here are up to ten papers published in 2026 that mention Bengali. None of the 427 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                      | paper                                                                          | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| Structure-Guided Entity Resolution: Fine-Tuning LLMs for Robust Name Matching in Complex Linguistic Contexts                               | [2026.acl-industry.101](https://aclanthology.org/2026.acl-industry.101/)       | body only      |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                  | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                       | body only      |
| Indic-CodecFake meets SATYAM: Towards Detecting Neural Audio Codec Synthesized Speech Deepfakes in Indic Languages                         | [2026.findings-acl.2159](https://aclanthology.org/2026.findings-acl.2159/)     | body only      |
| A Comprehensive Evaluation of Multilingual Chain-of-Thought Reasoning: Performance, Consistency, and Faithfulness Across Languages         | [2026.findings-eacl.276](https://aclanthology.org/2026.findings-eacl.276/)     | body only      |
| Code-Switching Reveals Language Anchoring in Multilingual LLMs                                                                             | [2026.findings-emnlp.1719](https://aclanthology.org/2026.findings-emnlp.1719/) | body only      |
| Can NLP Tackle Hate Speech in the Real World? Stakeholder-Informed Feedback and Survey on Counterspeech                                    | [2026.lrec-1.655](https://aclanthology.org/2026.lrec-1.655/)                   | body only      |
| MLingualFC: Evaluating Jailbreak Vulnerabilities in Multilingual Vision-Language Models                                                    | [2026.mellm-1.22](https://aclanthology.org/2026.mellm-1.22/)                   | body only      |
| AIvengers at SemEval-2026 Task 9: Utilizing Language Specific Encoders for Multilingual Text Classification                                | [2026.semeval-1.108](https://aclanthology.org/2026.semeval-1.108/)             | body only      |
| PolAR Bears at SemEval-2026 Task 9: Parameter-Efficient Fine-Tuning and Cross-Lingual Augmentation for Multilingual Polarization Detection | [2026.semeval-1.279](https://aclanthology.org/2026.semeval-1.279/)             | body only      |
| Data-Efficient Adaptation of Multilingual LLMs to Ukrainian                                                                                | [2026.unlp-1.14](https://aclanthology.org/2026.unlp-1.14/)                     | body only      |

{% endraw %}
