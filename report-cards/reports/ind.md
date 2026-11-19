---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ind.html
---
{% raw %}
# So you want to work on Indonesian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ind` · macrolanguage `msa`

**Language family:** **Austronesian** › Malayo-Polynesian › Malayo-Chamic › … › Standard Malay-Indonesian ([Glottolog](https://glottolog.org/resource/languoid/id/indo1316))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 180.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Indonesia

**Status:** Official language


## What does Indonesian look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/indonesian.htm):

> Semua orang dilahirkan merdeka dan mempunyai martabat dan hak-hak yang sama. Mereka dikaruniai akal dan hati nurani dan hendaknya bergaul satu sama lain dalam semangat persaudaraan.
> A recording of this text by Ali Aulia Ghozali

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_in.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ind/) has 7 videos of Indonesian speakers. Watch [See all](https://wikitongues.org/videos/?language=ind).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 803,751 articles in id.wikipedia; 4,808 active users. This is ~1/9 of English data and ranks 19 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                          |
| Common Crawl           | 24,023,990 pages per crawl on average, which is 1.1142% of the crawl (2026). This is ~1/37 of English data and ranks 13 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                               |
| FineWeb                | 152.21 GB (ind_Latn 152.21 GB), equivalent to ≈129.13 GB of English after byte-premium scaling; 159.63 GB removed by filtering. This is ~1/351 of English data and ranks 12 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 7.82 GB (ind_Latn 7.82 GB) (rank 27 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 7,628 sentences / 166,635 tokens in total: [UD_Indonesian-CSUI](https://github.com/UniversalDependencies/UD_Indonesian-CSUI) (1,030 sentences), [UD_Indonesian-GSD](https://github.com/UniversalDependencies/UD_Indonesian-GSD) (5,598 sentences), [UD_Indonesian-PUD](https://github.com/UniversalDependencies/UD_Indonesian-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 3,877 lemmas, 27,714 inflected forms ([unimorph/ind](https://github.com/unimorph/ind))                                                                                                                                                                                                                                                                                                                                                      |
| Wikidata labels        | 4,005,574 Wikidata items have a label in Indonesian. (Wikidata codes (labels): id (4,005,574))                                                                                                                                                                                                                                                                                                                                              |
| Wordnets               | [Wordnet Bahasa (Indonesian)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-id-1.4.tar.xz): 38,085 synsets, 41,478 words, 106,688 senses; licence: https://opensource.org/licenses/MIT/; [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD.                                                                                                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 244,581,152 sentence pairs with English across 25 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (73,834,757), [NLLB](https://opus.nlpl.eu/NLLB) (70,545,705), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (70,545,705), [CCAligned](https://opus.nlpl.eu/CCAligned) (15,700,345), [ParaCrawl-Bonus](https://opus.nlpl.eu/ParaCrawl-Bonus) (7,133,466). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: New Testament + parts of the Old Testament ([ind](https://ebible.org/details.php?id=ind), by-sa 4.0); New Testament ([indags](https://ebible.org/details.php?id=indags), by-sa 4.0).                                                                                                                                                               |
| Tatoeba                                                                                  | 28,427 sentences, 22,166 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ind/none)).                                                                                                                                                                                                                                                      |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                          |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_id) en → id: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_id) en → id: size not listed                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.919 (P 0.876, R 0.970, FPR 1.32e-03) averaged over 7 dataset(s). Runner-up: OpenLID-v2 (F1 0.871).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.876 |    0.970 | 0.919 | 0.001 | ✓                |
| OpenLID-v2   |       0.854 |    0.901 | 0.871 | 0.002 | ✓                |
| fasttext     |       0.762 |    0.934 | 0.825 | 0.003 | ✓                |
| cld2         |       0.780 |    0.860 | 0.811 | 0.003 | ✓                |
| py3langid    |       0.686 |    0.837 | 0.745 | 0.005 | ✓                |
| cld3         |       0.691 |    0.710 | 0.691 | 0.006 | ✓                |
| commonlingua |       0.673 |    0.666 | 0.662 | 0.004 | ✓                |
| pyfranc      |       0.645 |    0.594 | 0.613 | 0.004 | ✓                |
| funlangid    |       0.594 |    0.591 | 0.577 | 0.005 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.710 |    0.953 | 0.814 |
| CommonLID | 300 |       0.874 |    0.927 | 0.900 |
| NTREX     | 300 |       0.850 |    0.983 | 0.912 |
| FLORES    | 300 |       0.874 |    0.993 | 0.930 |
| UDHR-LID  |  60 |       0.919 |    0.950 | 0.934 |
| Wikipedia | 300 |       0.908 |    0.990 | 0.947 |
| SmolSent  | 300 |       0.997 |    0.993 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Indonesian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Indonesian *and* from closely related languages that might be confused with it. Likely confusions to include: Malay (`zsm`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Indonesian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Indonesian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Indonesian (and whether the model is exclusively tagged for Indonesian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,767** text-generation models are explicitly tagged for Indonesian (524 original uploads, 1,243 fine-tunes/quantisations/merges).
- **312** are tagged *only* for Indonesian.
- Including tags inherited from base models: **2,892**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       50 | █                    |
|   2023 |       87 | ██                   |
|   2024 |      303 | ███████              |
|   2025 |      441 | ██████████           |
|   2026 |      886 | ████████████████████ |

### Largest models tagged for Indonesian

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                        |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   | 1.9T         |                  143 |   2025 | —                                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       | 856.0B       |                  143 |   2025 | —                                    |
| [Langitzt/Vector-1-lite](https://huggingface.co/Langitzt/Vector-1-lite)                                                     | 753.9B       |                    3 |   2026 | —                                    |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                     | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019      |
| [from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit](https://huggingface.co/from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit) | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E |

### Largest models tagged *only* for Indonesian

| model                                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [komixenon/GoToCompany-Llama-Sahabat-AI-v2-70B-IT-BNB4](https://huggingface.co/komixenon/GoToCompany-Llama-Sahabat-AI-v2-70B-IT-BNB4) | 72.7B        |                    1 |   2025 | GoToCompany/Llama-Sahabat-AI-v2-70B-IT |
| [TheCoderScientist/GarudaCoder-27B-ID-lora](https://huggingface.co/TheCoderScientist/GarudaCoder-27B-ID-lora)                         | 27.0B        |                    1 |   2026 | unsloth/Qwen3.8-27B-unsloth-bnb-4bit   |
| [Lobus22/Lidya-Natalia-1.5-20B](https://huggingface.co/Lobus22/Lidya-Natalia-1.5-20B)                                                 | 20.0B        |                    1 |   2026 | openai/gpt-oss-20b                     |
| [indonlp/cendol-llama2-13b-merged-chat](https://huggingface.co/indonlp/cendol-llama2-13b-merged-chat)                                 | 13.0B        |                    1 |   2023 | —                                      |
| [microsoft/LLaMA-2-13b-GTL-Delta](https://huggingface.co/microsoft/LLaMA-2-13b-GTL-Delta)                                             | 13.0B        |                    1 |   2024 | —                                      |

_231 tagged models have unknown parameter counts and are not ranked by size._

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

**37** benchmark datasets in the survey include Indonesian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 10 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 10 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">4 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">3 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                                                       |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 6              | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                          | [LINDSEA (SEA-HELM)](https://github.com/aisingapore/BHASA)                                          | 380            | Hand-written (expert)                                                              |
| 1. Linguistic knowledge                | BLiMP                          | [MALINDO BLiMP](https://github.com/matbahasa/MALINDO_BLiMP)                                         | 189            | Existing material (linguistics literature)                                         |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                   | 1,140          | Native (written by native speakers)                                                |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                   | 341            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)                     |
| 3. Commonsense reasoning               | COPA                           | [COPAL-ID (colloquial)](https://huggingface.co/datasets/haryoaw/COPAL)                              | 559            | Native (paraphrased from standard)                                                 |
| 3. Commonsense reasoning               | COPA                           | [COPAL-ID](https://huggingface.co/datasets/haryoaw/COPAL)                                           | 559            | Native                                                                             |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                                  |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,314          | Machine translation (GPT-3.5-turbo)                                                |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                                            |
| 3. Commonsense reasoning               | StoryCloze                     | [IndoCloze](https://github.com/fajri91/IndoCloze)                                                   | 1,135          | Native                                                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                                         |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                               | 1,511          | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                                   |
| 4. Reading comprehension               | QA – extractive RC             | IDK-MRC                                                                                             | —              | Native                                                                             |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndoMMLU                                                                                            | 14,981         | Native (school exams)                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                                           |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                                     |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)                           |

### Standard machine translation test sets

Indonesian has been part of the WMT translation task in **2** years (2025, 2026).

| Test set                                                                                            | Direction(s)                      | Size                                | Human reference             |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn)              | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-id_ID)                           | en → id_ID                        | 998 segments                        | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)                            | English → Indonesian              | 87 documents (36,770 source words)  | no (automatic metrics only) |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)                            | English → Indonesian              | 198 documents (28,523 source words) | no (automatic metrics only) |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_id) (training data)   | en → id                           | size not listed                     | ✅                          |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_id) (training data) | en → id                           | size not listed                     | ✅                          |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Indonesian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Indonesian? Does it make sense to train one?
  - ~129.13 GB English-equivalent text ≈ 32.28B tokens, enough for a compute-optimal model of ~1.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Indonesian-only model is 72.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 314 of ~18,498 papers (1.70%) (rank 24 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Indonesian

Here are up to ten papers published in 2026 that mention Indonesian. None of the 314 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                     | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Re:CAP - Auditing Retrieval Coverage in Production RAG Pipelines                                          | [2026.emnlp-industry.150](https://aclanthology.org/2026.emnlp-industry.150/)   |
| ParsHate: A Benchmark Dataset for Hate and Target Detection in Persian                                    | [2026.emnlp-main.1406](https://aclanthology.org/2026.emnlp-main.1406/)         |
| Training free Cross-Modal Alignment for Multilingual Image Retrieval                                      | [2026.findings-aacl.203](https://aclanthology.org/2026.findings-aacl.203/)     |
| What Do Neural Speech Models Know About Phonology? Evidence from Structured Phoneme Confusions            | [2026.findings-acl.1288](https://aclanthology.org/2026.findings-acl.1288/)     |
| Testing Low-Resource Language Support in LLMs Using Language Proficiency Exams: the Case of Luxembourgish | [2026.findings-eacl.128](https://aclanthology.org/2026.findings-eacl.128/)     |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                 | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| OpenSeal: Good, Fast, and Cheap Construction of an Open-Source Southeast Asian LLM via Parallel Data      | [2026.findings-emnlp.2205](https://aclanthology.org/2026.findings-emnlp.2205/) |
| Evaluating the Interplay of Information Status and Information Content in a Multilingual Parallel Corpus  | [2026.sigtyp-main.3](https://aclanthology.org/2026.sigtyp-main.3/)             |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                 | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |
| The Curse of Multilinguality in Lexical Normalization                                                     | [2026.wnut-1.22](https://aclanthology.org/2026.wnut-1.22/)                     |

{% endraw %}
