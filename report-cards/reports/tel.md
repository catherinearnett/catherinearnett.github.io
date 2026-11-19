---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tel.html
---
{% raw %}
# So you want to work on Telugu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tel`

**Language family:** **Dravidian** › South Dravidian › South Dravidian II › Teluguic ([Glottolog](https://glottolog.org/resource/languoid/id/telu1262))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Telu`

**Speakers:** about 101.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, South Africa

**Status:** Regional official language; Official language


## What does Telugu look and sound like?

**Written:** Omniglot has [a page on Telugu](https://www.omniglot.com/writing/telugu.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tel/) has 5 videos of Telugu speakers. Watch [Naren speaking Telugu](https://wikitongues.org/videos/naren_20190106_tel/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 130,448 articles in te.wikipedia; 318 active users. This is ~1/58 of English data and ranks 52 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                        |
| Common Crawl           | 450,946 pages per crawl on average, which is 0.0209% of the crawl (2026). This is ~1/1,977 of English data and ranks 47 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                            |
| FineWeb                | 4.04 GB (tel_Telu 3.99 GB; tel_Latn 47.0 MB), equivalent to ≈1.56 GB of English after byte-premium scaling; 6.21 GB removed by filtering. This is ~1/13,233 of English data and ranks 54 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 5.84 GB (tel_Telu 5.84 GB) (rank 33 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                                |

**By writing system:**

| Writing system   | FineWeb                         | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:--------------------------------|:------------------------------|:-------------|:-------------------------------|
| Telugu (`Telu`)  | 3.99 GB (+6.02 GB filtered out) | 1.52 GB                       | 5.84 GB      | 2.23 GB                        |
| Latin (`Latn`)   | 47.4 MB (+0.19 GB filtered out) | 36.8 MB                       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                 |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,328 sentences / 6,465 tokens in total: [UD_Telugu-MTG](https://github.com/UniversalDependencies/UD_Telugu-MTG) (1,328 sentences). It has POS tags, dependency syntax, morphological features. |
| UniMorph               | 127 lemmas, 1,548 inflected forms ([unimorph/tel](https://github.com/unimorph/tel))                                                                                                                         |
| Wikidata labels        | 643,871 Wikidata items have a label in Telugu. (Wikidata codes (labels): te (643,871))                                                                                                                      |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 55,907,602 sentence pairs with English across 20 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (46,376,267), [Samanantar](https://opus.nlpl.eu/Samanantar) (4,946,036), [Anuvaad](https://opus.nlpl.eu/Anuvaad) (1,578,731), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (1,355,728), [CCAligned](https://opus.nlpl.eu/CCAligned) (581,652). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([tel2017](https://ebible.org/details.php?id=tel2017), by-sa 4.0).                                                                                                                                                                                                                                                     |
| Tatoeba                                                                                  | 318 sentences, 314 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/tel/none)).                                                                                                                                                                                                                                          |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Telu script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script); 1,358 sentences (Telu script) — paired with English                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_te) en → te: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_te) en → te: size not listed                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.999 (P 0.999, R 0.999, FPR 1.49e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.999).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.999 | 0.999 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| cld2         |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| py3langid    |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.996 | 0.998 | 0.000 | ✓                |
| commonlingua |       0.998 |    0.996 | 0.997 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.986 | 0.993 | 0.000 | ✗                |
| cld3         |       0.999 |    0.986 | 0.992 | 0.000 | ✓                |
| funlangid    |       0.970 |    0.916 | 0.941 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.997 |    0.997 | 0.997 |
| Wikipedia | 300 |       1.000 |    0.997 | 0.998 |
| Tatoeba   | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Telugu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Telugu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Telugu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Telugu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Telugu (and whether the model is exclusively tagged for Telugu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **701** text-generation models are explicitly tagged for Telugu (243 original uploads, 458 fine-tunes/quantisations/merges).
- **114** are tagged *only* for Telugu.
- Including tags inherited from base models: **1,067**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       42 | ██                   |
|   2023 |       33 | ██                   |
|   2024 |       99 | ██████               |
|   2025 |      189 | ███████████          |
|   2026 |      338 | ████████████████████ |

### Largest models tagged for Telugu

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                 | 176.2B       |                   37 |   2026 | —                                      |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                                 | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Telugu

| model                                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Qwen3-14B-Base-te-madlad-mean-cv](https://huggingface.co/atsuki-yamaguchi/Qwen3-14B-Base-te-madlad-mean-cv)                                     | 14.9B        |                    1 |   2025 | Qwen/Qwen3-14B-Base     |
| [bharadwajswarna/Zephyr-Gemma-7B-Telugu](https://huggingface.co/bharadwajswarna/Zephyr-Gemma-7B-Telugu)                                                           | 8.5B         |                    1 |   2024 | —                       |
| [saucam/Navrasa-2.0-Rudra-7b-dare-ties](https://huggingface.co/saucam/Navrasa-2.0-Rudra-7b-dare-ties)                                                             | 8.5B         |                    1 |   2024 | google/gemma-7b         |
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-te-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-te-madlad-mean-slerp0305-emb) | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [jayasuryajsk/Llama-3-8b-Telugu-Romanized](https://huggingface.co/jayasuryajsk/Llama-3-8b-Telugu-Romanized)                                                       | 8.0B         |                    1 |   2024 | —                       |

_95 tagged models have unknown parameter counts and are not ranked by size._

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

**29** benchmark datasets in the survey include Telugu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 5 datasets; Knowledge &amp; QA: 8 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 5 datasets; Knowledge &amp; QA: 8 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                                  | —              | Native (curated by native speakers; generated contexts + MCQs)   |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated)              | —              | Machine translation (method not stated)                          |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 8,724          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                                   | 1,511          | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | TeQuAD                                                                                                                  | 82,000         | Translation (SQuAD → Telugu)                                     |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                                | 10,489         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension               | QA – extractive RC             | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)                                   | 1,734          | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                           | —              | Machine translation (from MMLU-Pro)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                                  | 7,304          | Native (Indian exams; some translated)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                                       | 1,087          | Native (TyDi questions)                                          |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 262            | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Telu) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Telu) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-te_IN)                           | en → te_IN                        | 998 segments           | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_te) (training data)   | en → te                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_te) (training data) | en → te                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Telugu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Telugu? Does it make sense to train one?
  - ~2.23 GB English-equivalent text ≈ 0.56B tokens, enough for a compute-optimal model of ~27.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Telugu-only model is 14.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 256 of ~18,498 papers (1.38%) (rank 29 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Telugu

Here are up to ten papers published in 2026 that mention Telugu. None of the 256 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                   | paper                                                                              |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| The Reasoning Lingua Franca: A Double-Edged Sword for Multilingual AI                                                   | [2026.eacl-short.25](https://aclanthology.org/2026.eacl-short.25/)                 |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                             | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)             |
| VLURes: Benchmarking Long-Text Grounding and Cross-Lingual Robustness in Vision Language Models                         | [2026.findings-acl.1367](https://aclanthology.org/2026.findings-acl.1367/)         |
| Better as Generators Than Classifiers: Leveraging LLMs and Synthetic Data for Low-Resource Multilingual Classification  | [2026.findings-eacl.148](https://aclanthology.org/2026.findings-eacl.148/)         |
| XLGoBench: Detecting cross-lingual skill gaps with algorithmic tasks                                                    | [2026.findings-emnlp.2139](https://aclanthology.org/2026.findings-emnlp.2139/)     |
| Mind the Gap... or Not? How Translation Errors and Evaluation Details Skew Multilingual Results                         | [2026.gem-main.22](https://aclanthology.org/2026.gem-main.22/)                     |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                              | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)                     |
| Contextualizing Toxicity: An Annotation Framework for Unveiling Pragmatics in Conversations of Online Discussion Forums | [2026.lrec-1.314](https://aclanthology.org/2026.lrec-1.314/)                       |
| Algebraic Classification of Reduplicative Processes                                                                     | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)                   |
| Annotating Indian Regional Biases using Large Language Models: Evaluation and Analysis                                  | [2026.starsem-conference.16](https://aclanthology.org/2026.starsem-conference.16/) |

{% endraw %}
