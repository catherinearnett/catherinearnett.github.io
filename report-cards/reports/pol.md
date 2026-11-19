---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pol.html
---
{% raw %}
# So you want to work on Polish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pol`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Polish-Silesian ([Glottolog](https://glottolog.org/resource/languoid/id/poli1260))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 41.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Poland

**Status:** Official language


## What does Polish look and sound like?

**Written (Polish)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/polish.htm):

> Wszyscy ludzie rodzą się wolni i równi w swojej godności i prawach. Są obdarzeni rozumem i sumieniem i powinni postępować wobec siebie w duchu braterstwa.
> A recording of this text by Marcin K.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_pl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/pol/) has 7 videos of Polish speakers. Watch [See all](https://wikitongues.org/videos/?language=pol).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,713,709 articles in pl.wikipedia; 9,281 active users. This is ~1/4 of English data and ranks 10 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 43,509,173 pages per crawl on average, which is 2.0187% of the crawl (2026). This is ~1/20 of English data and ranks 9 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                |
| FineWeb                | 225.92 GB (pol_Latn 225.92 GB), equivalent to ≈209.69 GB of English after byte-premium scaling; 273.59 GB removed by filtering. This is ~1/236 of English data and ranks 10 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.44 GB (pol_Latn 9.44 GB) (rank 15 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 42,913 sentences / 555,179 tokens in total: [UD_Polish-LFG](https://github.com/UniversalDependencies/UD_Polish-LFG) (17,246 sentences), [UD_Polish-MPDT](https://github.com/UniversalDependencies/UD_Polish-MPDT) (2,515 sentences), [UD_Polish-PDB](https://github.com/UniversalDependencies/UD_Polish-PDB) (22,152 sentences), [UD_Polish-PUD](https://github.com/UniversalDependencies/UD_Polish-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 10,185 lemmas, 201,024 inflected forms ([unimorph/pol](https://github.com/unimorph/pol))                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Wikidata labels        | 8,748,472 Wikidata items have a label in Polish. (Wikidata codes (labels): pl (8,748,472))                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Wordnets               | [plWordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-pl-1.4.tar.xz): 33,826 synsets, 45,456 words, 52,376 senses; licence: wordnet; PolNet (size not listed); licence: Creative Commons Public License.                                                                                                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 310,316,348 sentence pairs with English across 185 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (75,324,736), [NLLB](https://opus.nlpl.eu/NLLB) (74,070,714), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (74,070,714), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (40,082,839), [CCAligned](https://opus.nlpl.eu/CCAligned) (12,950,300). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([polubg](https://ebible.org/details.php?id=polubg), by-nd 4.0); New Testament ([polsz](https://ebible.org/details.php?id=polsz), by-sa 4.0).                                                                                                                                                                                 |
| Tatoeba                                                                                  | 137,214 sentences, 78,633 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/pol/none)).                                                                                                                                                                                                                                           |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                               |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.975, R 0.999, FPR 1.89e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.952).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.975 |    0.999 | 0.987 | 0.000 | ✓                |
| cld2         |       0.923 |    0.984 | 0.952 | 0.001 | ✓                |
| commonlingua |       0.909 |    0.951 | 0.929 | 0.001 | ✓                |
| pyfranc      |       0.948 |    0.875 | 0.904 | 0.000 | ✓                |
| funlangid    |       0.915 |    0.816 | 0.859 | 0.001 | ✓                |
| OpenLID-v2   |       0.743 |    0.995 | 0.838 | 0.003 | ✓                |
| fasttext     |       0.676 |    0.999 | 0.778 | 0.006 | ✓                |
| py3langid    |       0.663 |    0.997 | 0.776 | 0.006 | ✓                |
| cld3         |       0.606 |    0.991 | 0.728 | 0.010 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.938 |    1.000 | 0.968 |
| Tatoeba   | 300 |       0.949 |    0.997 | 0.972 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |
| NTREX     | 300 |       0.993 |    1.000 | 0.997 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Polish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Polish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Polish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Polish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Polish (and whether the model is exclusively tagged for Polish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2,057** text-generation models are explicitly tagged for Polish (548 original uploads, 1,509 fine-tunes/quantisations/merges).
- **446** are tagged *only* for Polish.
- Including tags inherited from base models: **3,905**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | █                    |
|   2023 |      151 | ███                  |
|   2024 |      342 | ███████              |
|   2025 |      620 | █████████████        |
|   2026 |      931 | ████████████████████ |

### Largest models tagged for Polish

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 856.0B       |                  143 |   2025 | —               |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 751.4B       |                   10 |   2026 | —               |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B)               | 749.4B       |                   10 |   2026 | —               |
| [Vanedap/K-EXAONE-2.0-750B-A37B](https://huggingface.co/Vanedap/K-EXAONE-2.0-750B-A37B)                       | 749.4B       |                   10 |   2026 | —               |

### Largest models tagged *only* for Polish

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [OsaurusAI/Laguna-M.1-JANG_1L](https://huggingface.co/OsaurusAI/Laguna-M.1-JANG_1L)                         | 225.8B       |                    1 |   2026 | poolside/Laguna-M.1   |
| [AtomicChat/Laguna-S-2.1-GGUF](https://huggingface.co/AtomicChat/Laguna-S-2.1-GGUF)                         | 117.6B       |                    1 |   2026 | poolside/Laguna-S-2.1 |
| [CYFRAGOVPL/Llama-PLLuM-70B-chat-2508](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-chat-2508)         | 70.6B        |                    1 |   2025 | —                     |
| [CYFRAGOVPL/Llama-PLLuM-70B-instruct-2508](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-instruct-2508) | 70.6B        |                    1 |   2025 | —                     |
| [CYFRAGOVPL/Llama-PLLuM-70B-chat-2512](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-chat-2512)         | 70.6B        |                    1 |   2025 | —                     |

_175 tagged models have unknown parameter counts and are not ranked by size._

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

**28** benchmark datasets in the survey include Polish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 5 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 13 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 5 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 13 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">13 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                   |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 764            | Treebank-based (automatic)                     |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 3,272          | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                    |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 4. Reading comprehension      | QA – extractive RC             | [PoQuAD](https://huggingface.co/datasets/clarin-pl/poquad)                                          | —              | Native                                         |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | LLMzSzŁ                                                                                             | —              | Native (national exams)                        |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 1,971          | Native (high-school exams)                     |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)         |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | Complex Q&A Corpus                                                                                  | —              | Native (human-annotated)                       |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)      |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [KLEJ-DYK (Polish Wikipedia "Czy wiesz")](https://huggingface.co/datasets/allegro/klej-dyk)         | 1,029          | Native                                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                              |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                       |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [PolQA](https://huggingface.co/datasets/ipipan/polqa)                                               | 1,000          | Native (quiz questions)                        |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 11,713         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Polish has been part of the WMT translation task in **1** year (2020).

| Test set                                                                  | Direction(s)                       | Size                            | Human reference   |
|:--------------------------------------------------------------------------|:-----------------------------------|:--------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)          | 2,009 sentences (Latn)          | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)  | 1,358 sentences (Latn)          | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-pl_PL) | en → pl_PL                         | 998 segments                    | ✅                |
| [WMT20 general task](https://www2.statmt.org/wmt20/)                      | English → Polish; Polish → English | 1,000 segments / 1,001 segments | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Polish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Polish? Does it make sense to train one?
  - ~209.69 GB English-equivalent text ≈ 52.42B tokens, enough for a compute-optimal model of ~2.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Polish-only model is 225.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 438 of ~18,498 papers (2.37%) (rank 15 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Polish

Here are up to ten papers published in 2026 that mention Polish. None of the 438 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                              | paper                                                                          |
|:---------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| SOAPTriage: SOAP-Guided Multi-View Clinical Text Modeling Framework for Automated ESI Prediction   | [2026.acl-long.1608](https://aclanthology.org/2026.acl-long.1608/)             |
| BNLI: A Linguistically-Refined Bengali Dataset for Natural Language Inference                      | [2026.chipsal-1.9](https://aclanthology.org/2026.chipsal-1.9/)                 |
| Reasoning-Aware AIGC Detection via Alignment and Reinforcement                                     | [2026.findings-acl.1043](https://aclanthology.org/2026.findings-acl.1043/)     |
| AI translation of literary texts is ’fine’, but readers still prefer human translations            | [2026.findings-emnlp.2138](https://aclanthology.org/2026.findings-emnlp.2138/) |
| Charting the European LLM Benchmarking Landscape: A New Taxonomy and Registry                      | [2026.llms4ssh-1.22](https://aclanthology.org/2026.llms4ssh-1.22/)             |
| FalAR: A Large-scale Speaker-Annotated European Portuguese Speech Corpus of Parliamentary Sessions | [2026.lrec-1.435](https://aclanthology.org/2026.lrec-1.435/)                   |
| Evaluating the Impact of Source Diversity for RAG in Historical Research                           | [2026.lrec-1.53](https://aclanthology.org/2026.lrec-1.53/)                     |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings     | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| Tracing Morph Origins in Czech: A Computational Approach to Morph-Level Etymology                  | [2026.lt4hala-1.2](https://aclanthology.org/2026.lt4hala-1.2/)                 |
| The Polish PressMint Corpus                                                                        | [2026.pressmint-1.2](https://aclanthology.org/2026.pressmint-1.2/)             |

{% endraw %}
