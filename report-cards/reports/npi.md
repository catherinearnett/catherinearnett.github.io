---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/npi.html
---
{% raw %}
# So you want to work on Nepali?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `npi` · macrolanguage `nep`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Eastern Pahari ([Glottolog](https://glottolog.org/resource/languoid/id/nepa1254))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Deva`

**Speakers:** about 21.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `nep`, so includes other varieties

**Official / recognised in:** India, Nepal

**Status:** Regional official language; Official language


## What does Nepali look and sound like?

**Written (Nepali)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/nepali.htm):

> सबै व्यक्तिहरू जन्मजात स्वतन्त्र हुन्, ती सबैको समान अधिकार र महत्त्व छ । निजहरूमा विचार शक्ति र सद्विचार भएकोले निजहरूले आपस्तमा भ्रातृत्वको भावनाबाट व्यवहार गर्नुपर्छ ।

*Transliteration:* Sabai vyaktiharū janmajāta svatantra hun, tī sabaiko samāna adhikāra ra mahattva cha. Nijaharūmā vicāra śakti ra sadvicāra bhaekole nijaharūle āpastamā bhrātṛtvako bhāvanābāṭa vyavahāra garnuparcha. A recording of this text by Sarthak Sharma

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Details provided by Arvind Iyengar and Arnav Darnal.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ne.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/npi/) has 7 videos of Nepali speakers. Watch [See all](https://wikitongues.org/videos/?language=npi).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                         |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 30,073 articles in ne.wikipedia; 138 active users. ⚠️ NB: recorded under the macrolanguage code `nep`, which can include other varieties of Nepali.                                                                                                            |
| Common Crawl           | 1,231,877 pages per crawl on average, which is 0.0571% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `nep`, which can include other varieties of Nepali.                                                                                   |
| FineWeb                | 6.76 GB (npi_Deva 6.75 GB; npi_Latn 4.0 MB), equivalent to ≈2.79 GB of English after byte-premium scaling; 3.77 GB removed by filtering. This is ~1/7,905 of English data and ranks 47 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                                   |

**By writing system:**

| Writing system      | FineWeb                         | FineWeb, English-equivalent   |
|:--------------------|:--------------------------------|:------------------------------|
| Devanagari (`Deva`) | 6.75 GB (+3.75 GB filtered out) | 2.79 GB                       |
| Latin (`Latn`)      | 4.5 MB (+22.9 MB filtered out)  | 4.1 MB                        |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 69 sentences / 801 tokens in total: [UD_Nepali-BK](https://github.com/UniversalDependencies/UD_Nepali-BK) (69 sentences). It has POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `nep`, so this may cover other varieties as well as Nepali. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                  |
| Wikidata labels        | 312,583 Wikidata items have a label in Nepali. (Wikidata codes (labels): ne (312,583))                                                                                                                                                                                                                          |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD; [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY; nan (size not listed).                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 415 sentence pairs with English across 1 corpora; largest: [Tatoeba](https://opus.nlpl.eu/Tatoeba) (415).                                                                                                      |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([npiulb](https://ebible.org/details.php?id=npiulb), by-sa 4.0).                                                                                                           |
| Tatoeba                                                                                  | 4,506 sentences, 3,644 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/npi/none)).                                                                                          |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Deva script) — the same sentences in 200+ languages                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Deva script) — paired with English                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ne) en → ne: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ne) en → ne: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=55), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.971 (P 0.967, R 0.977, FPR 2.63e-04) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.963).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.967 |    0.977 | 0.971 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.932 | 0.963 | 0.000 | ✓                |
| fasttext     |       0.885 |    0.975 | 0.926 | 0.001 | ✓                |
| cld2         |       0.866 |    0.970 | 0.906 | 0.001 | ✓                |
| pyfranc      |       0.934 |    0.855 | 0.889 | 0.001 | ✓                |
| funlangid    |       0.992 |    0.809 | 0.886 | 0.000 | ✓                |
| commonlingua |       0.895 |    0.823 | 0.833 | 0.001 | ✓                |
| py3langid    |       0.709 |    0.971 | 0.801 | 0.004 | ✓                |
| cld3         |       0.319 |    0.976 | 0.466 | 0.027 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.885 |    1.000 | 0.939 |
| Wikipedia | 300 |       0.979 |    0.923 | 0.950 |
| Tatoeba   | 300 |       0.990 |    0.960 | 0.975 |
| UDHR-LID  |  55 |       0.982 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Nepali to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Nepali *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Nepali and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Nepali has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Nepali?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Nepali (and whether the model is exclusively tagged for Nepali or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **533** text-generation models are explicitly tagged for Nepali (195 original uploads, 338 fine-tunes/quantisations/merges).
- **51** are tagged *only* for Nepali.
- Including tags inherited from base models: **875**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       37 | ███                  |
|   2023 |       34 | ███                  |
|   2024 |       54 | █████                |
|   2025 |      195 | ██████████████████   |
|   2026 |      213 | ████████████████████ |

### Largest models tagged for Nepali

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Nepali

| model                                                                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [shivam9980/NEPALI-LLM](https://huggingface.co/shivam9980/NEPALI-LLM)                                                         | 10.3B        |                    1 |   2024 | google/gemma-2-9b         |
| [divaspoudel/poetry-nepali-ft-9b](https://huggingface.co/divaspoudel/poetry-nepali-ft-9b)                                     | 9.2B         |                    1 |   2026 | unsloth/gemma-2-9b-it     |
| [DGurgurov/llama-3.1-8b-npi_deva](https://huggingface.co/DGurgurov/llama-3.1-8b-npi_deva)                                     | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-npi_deva](https://huggingface.co/DGurgurov/aya-expanse-8b-npi_deva)                                 | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [iamsubingyawali/gemma-3-4b-nepali-news-pretrained](https://huggingface.co/iamsubingyawali/gemma-3-4b-nepali-news-pretrained) | 4.3B         |                    1 |   2025 | google/gemma-3-4b-pt      |

_78 tagged models have unknown parameter counts and are not ranked by size._

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

**19** benchmark datasets in the survey include Nepali (plus 1 labelled with the macrolanguage `nep`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | construction                                             |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                   |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | Nepali WinoGrande (NLUE)                                                                                       | 8,140          | MT (Gemini-2.5-flash) + manual correction                |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA) (as `nep`)                                    | 500            | Human translation                                        |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                       | 9,318          | Machine translation (GPT-3.5-turbo)                      |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                   |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                  |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (2 varieties/pairs)                              | 1,800          | Human translation (professional)                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Machine translation (Google Translate)                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                         | —              | Machine translation (GPT-3.5, Okapi)                     |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)           |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 116            | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Deva) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Deva) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ne) (training data)   | en → ne                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ne) (training data) | en → ne                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Nepali datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Nepali? Does it make sense to train one?
  - ~2.79 GB English-equivalent text ≈ 0.70B tokens, enough for a compute-optimal model of ~34.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Nepali-only model is 10.3B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 168 of ~18,498 papers (0.91%) (rank 39 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nepali

Here are up to ten papers published in 2026 that mention Nepali. None of the 168 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                     | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                                                                              | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/)         |
| MUTANT: A Recipe for Multilingual Tokenizer Design                                                                                                        | [2026.acl-long.2146](https://aclanthology.org/2026.acl-long.2146/)         |
| Seeing the Unseen: Visual Similarity for Pixel Language Model Adaptation                                                                                  | [2026.emnlp-main.1509](https://aclanthology.org/2026.emnlp-main.1509/)     |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                                     | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)     |
| POLAR: A Benchmark for Multilingual, Multicultural, and Multi-Event Online Polarization                                                                   | [2026.findings-acl.1433](https://aclanthology.org/2026.findings-acl.1433/) |
| Can Linguistically Related Languages Guide LLM Translation in Low-Resource Settings?                                                                      | [2026.loresmt-1.14](https://aclanthology.org/2026.loresmt-1.14/)           |
| Estonian WinoGrande Dataset: Comparative Analysis of LLM Performance on Human and Machine Translation                                                     | [2026.lrec-1.549](https://aclanthology.org/2026.lrec-1.549/)               |
| NepPlural: A Human-Anchored Benchmark for Persona Annotation in Nepali Migration Discourse                                                                | [2026.plurvallm-1.15](https://aclanthology.org/2026.plurvallm-1.15/)       |
| OZemi at SemEval-2026 Task 9: A Cross-Lingual Approach to Online Text Polarization Classification Using Multilingual Models and Adaptive Loss Formulation | [2026.semeval-1.27](https://aclanthology.org/2026.semeval-1.27/)           |
| SemEval-2026 Task 9: Detecting Multilingual, Multicultural and Multievent Online Polarization                                                             | [2026.semeval-1.453](https://aclanthology.org/2026.semeval-1.453/)         |

{% endraw %}
