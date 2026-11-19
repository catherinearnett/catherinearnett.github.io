---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/srp.html
---
{% raw %}
# So you want to work on Serbian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `srp` · macrolanguage `hbs`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Eastern Herzegovinian Shtokavian. Glottolog treats Serbian Standard as a variety of Serbian-Croatian-Bosnian ([Glottolog](https://glottolog.org/resource/languoid/id/serb1264))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl` and `Latn`

**Speakers:** about 14.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Bosnia and Herzegovina, Kosovo, Serbia

**Status:** Official language


## What does Serbian look and sound like?

**Written (Serbian in the Cyrillic)**, sample text from [Omniglot](https://www.omniglot.com/writing/serbian.htm):

> Сва људска бића рађају се слободна и једнака у достојанству и правима. Она су обдарена разумом и свешћу и треба једни према другима да поступају у духу братства.

**Written (Serbian in the Latin alphabet)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/serbian.htm):

> Sva ljudska bića rađaju se slobodna i jednaka u dostojanstvu
> i pravima. Ona su obdarena razumom i svešću i treba jedni prema
> drugima da postupaju u duhu bratstva.
> A recording of this text by Robert Todorić

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_sr.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/srp/) has 4 videos of Serbian speakers. Watch [Slobodan speaking Serbian](https://wikitongues.org/videos/slobodan_20140729_srp/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 710,638 articles in sr.wikipedia; 1,491 active users. This is ~1/11 of English data and ranks 21 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                      |
| Common Crawl           | 5,491,412 pages per crawl on average, which is 0.2549% of the crawl (2026). This is ~1/162 of English data and ranks 27 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                                            |
| FineWeb                | 10.49 GB (srp_Cyrl 9.37 GB; srp_Latn 1.12 GB), equivalent to ≈7.93 GB of English after byte-premium scaling; 8.22 GB removed by filtering. This is ~1/5,093 of English data and ranks 41 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 3.39 GB (srp_Cyrl 2.34 GB; srp_Latn 1.05 GB) (rank 51 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

**By writing system:**

| Writing system    | FineWeb                         | FineWeb, English-equivalent   | Goldfish   | Goldfish, English-equivalent   |
|:------------------|:--------------------------------|:------------------------------|:-----------|:-------------------------------|
| Cyrillic (`Cyrl`) | 9.37 GB (+7.26 GB filtered out) | 6.58 GB                       | 2.34 GB    | 1.64 GB                        |
| Latin (`Latn`)    | 1.12 GB (+0.95 GB filtered out) | 1.35 GB                       | 1.05 GB    | 1.28 GB                        |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 6,131 sentences / 143,354 tokens in total: [UD_Serbian-ParCoLab](https://github.com/UniversalDependencies/UD_Serbian-ParCoLab) (1,747 sentences), [UD_Serbian-SET](https://github.com/UniversalDependencies/UD_Serbian-SET) (4,384 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                       |
| Wikidata labels        | 1,441,350 Wikidata items have a label in Serbian. (Wikidata codes (labels): sr-el (1,441,350), sr (1,314,862), sr-ec (371,497))                                                                                                                                                                                                      |
| Wordnets               | [BalkaNet](http://www.dblab.upatras.gr/balkanet/) (size not listed); [Serbian Wordnet (SrpWN)](http://korpus.matf.bg.ac.rs/SrpWN/) (size not listed); licence: CC_BY-NC.                                                                                                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                           |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 136,554,518 sentence pairs with English across 29 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (56,609,882), [NLLB](https://opus.nlpl.eu/NLLB) (26,510,872), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (26,510,872), [HPLT](https://opus.nlpl.eu/HPLT) (8,495,542), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (8,495,542). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([srp1865](https://ebible.org/details.php?id=srp1865), Public Domain).                                                                                                                                                                                                                                            |
| Tatoeba                                                                                  | 52,105 sentences, 32,918 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/srp/none)).                                                                                                                                                                                                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                  |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                                                                                                                                                                                                                   |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=118), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.794 (P 0.773, R 0.847, FPR 2.40e-03) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.774).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.773 |    0.847 | 0.794 | 0.002 | ✓                |
| OpenLID-v2   |       0.833 |    0.748 | 0.774 | 0.002 | ✓                |
| fasttext     |       0.824 |    0.749 | 0.769 | 0.002 | ✓                |
| py3langid    |       0.742 |    0.792 | 0.749 | 0.004 | ✓                |
| commonlingua |       0.667 |    0.794 | 0.722 | 0.004 | ✓                |
| cld2         |       0.655 |    0.814 | 0.719 | 0.005 | ✓                |
| cld3         |       0.740 |    0.731 | 0.708 | 0.005 | ✓                |
| funlangid    |       0.788 |    0.602 | 0.667 | 0.002 | ✓                |
| pyfranc      |       0.486 |    0.499 | 0.490 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 118 |       0.527 |    0.653 | 0.583 |
| Tatoeba   | 300 |       0.517 |    0.937 | 0.667 |
| NTREX     | 300 |       0.860 |    0.653 | 0.742 |
| FLORES    | 300 |       0.968 |    1.000 | 0.984 |
| Wikipedia | 300 |       0.993 |    0.990 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Serbian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Serbian *and* from closely related languages that might be confused with it. Likely confusions to include: Bosnian (`bos`), Montenegrin (`cnr`), Croatian (`hrv`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Serbian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Serbian has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Serbian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Serbian (and whether the model is exclusively tagged for Serbian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **540** text-generation models are explicitly tagged for Serbian (115 original uploads, 425 fine-tunes/quantisations/merges).
- **46** are tagged *only* for Serbian.
- Including tags inherited from base models: **908**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       20 | ██                   |
|   2024 |       69 | ██████               |
|   2025 |      211 | ██████████████████   |
|   2026 |      232 | ████████████████████ |

### Largest models tagged for Serbian

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                            |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 856.0B       |                  143 |   2025 | —                            |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 753.3B       |                   10 |   2026 | —                            |
| [AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8) | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8         |
| [AIAgens/GLM-5.3-Flash-UNCENSORED-W4A16](https://huggingface.co/AIAgens/GLM-5.3-Flash-UNCENSORED-W4A16)   | 321.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-Flash-W4A16 |

### Largest models tagged *only* for Serbian

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------|
| [IvanCvetanovic/Slava-Qwen3-14B-Serbian](https://huggingface.co/IvanCvetanovic/Slava-Qwen3-14B-Serbian)   | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                   |
| [te-sla/serbian-emotion-qwen3.5-9b](https://huggingface.co/te-sla/serbian-emotion-qwen3.5-9b)             | 9.4B         |                    1 |   2026 | unsloth/Qwen3.5-9B                    |
| [datatab/Yugo55A-4bit](https://huggingface.co/datatab/Yugo55A-4bit)                                       | 7.5B         |                    1 |   2024 | mistralai/Mistral-7B-v0.1             |
| [datatab/Yugo55-GPT-v4-4bit](https://huggingface.co/datatab/Yugo55-GPT-v4-4bit)                           | 7.5B         |                    1 |   2024 | datatab/YugoGPT-Alpaca-v1-epoch1-good |
| [MarkoRadojcic/YugoGPT-Florida_Q4_0.GGUF](https://huggingface.co/MarkoRadojcic/YugoGPT-Florida_Q4_0.GGUF) | 7.2B         |                    1 |   2025 | datatab/YugoGPT-Florida               |

_74 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Serbian (plus 1 labelled with the macrolanguage `hbs`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 8 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 8 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                   |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 24             | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                                         | 3,286          | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing)       | —              | Automatically derived from UD treebanks        |
| 3. Commonsense reasoning               | COPA                           | [COPA-SR](https://huggingface.co/datasets/classla/COPA-SR)                                                              | 500            | Human translation                              |
| 3. Commonsense reasoning               | COPA                           | [COPA-SR_lat](https://huggingface.co/datasets/classla/COPA-SR_lat)                                                      | 500            | Human translation (transliterated)             |
| 3. Commonsense reasoning               | COPA                           | [DIALECT-COPA (COPA-SR-TOR)](https://github.com/clarinsi/dialect-copa)                                                  | 500            | Human translation                              |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,449          | Machine translation (GPT-3.5-turbo)            |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (4 varieties/pairs) | 400            | Native                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (4 varieties/pairs)        | 412            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                          | 1,637          | Native (high-school exams)                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Machine translation (Google Translate)         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  | 100            | Native (community-written, peer-verified)      |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                                           | 3,994          | Human translation (professional, from English) |

### Standard machine translation test sets

Serbian has been part of the WMT translation task in **1** year (2025).

| Test set                                                                  | Direction(s)                                              | Size                               | Human reference         |
|:--------------------------------------------------------------------------|:----------------------------------------------------------|:-----------------------------------|:------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)                                 | 2,009 sentences (Cyrl)             | ✅                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)                         | 1,358 sentences (Cyrl)             | ✅                      |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sr_RS) | en → sr_RS                                                | 998 segments                       | ✅                      |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Serbian; English → Serbian (no human reference) | 87 documents (36,770 source words) | partly (see directions) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Serbian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Serbian? Does it make sense to train one?
  - ~7.93 GB English-equivalent text ≈ 1.98B tokens, enough for a compute-optimal model of ~99.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Serbian-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 115 of ~18,498 papers (0.62%) (rank 52 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Serbian

Here are up to ten papers published in 2026 that mention Serbian. None of the 115 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                           | paper                                                            |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Adam’s Law: Textual Frequency Law on Large Language Models                                                      | [2026.acl-long.188](https://aclanthology.org/2026.acl-long.188/) |
| The Degree of Language Diacriticity and Its Effect on Tasks                                                     | [2026.cawl-1.1](https://aclanthology.org/2026.cawl-1.1/)         |
| State of the Art in Text Classification for South Slavic Languages: Fine-Tuning or Prompting?                   | [2026.llms4ssh-1.1](https://aclanthology.org/2026.llms4ssh-1.1/) |
| Who Benchmarks the Benchmarks? A Case Study of LLM Evaluation in Icelandic                                      | [2026.lrec-1.369](https://aclanthology.org/2026.lrec-1.369/)     |
| ROG: A Multi-Layer Manually Annotated Corpus of Spoken Slovenian                                                | [2026.lrec-1.449](https://aclanthology.org/2026.lrec-1.449/)     |
| A Parallel Cross-Lingual Benchmark for Multimodal Idiomaticity Understanding                                    | [2026.lrec-1.741](https://aclanthology.org/2026.lrec-1.741/)     |
| Where Are Language-Specific Features Represented in Multilingual LLMs? Everywhere                               | [2026.mrl-1.27](https://aclanthology.org/2026.mrl-1.27/)         |
| Edition 2.0 of the PARSEME shared task on multilingual identification and paraphrasing of multiword expressions | [2026.mwe-1.33](https://aclanthology.org/2026.mwe-1.33/)         |
| OPENER: A Frugal Open-World NER Pipeline for the Legal Domain                                                   | [2026.nllp-1.40](https://aclanthology.org/2026.nllp-1.40/)       |
| Towards Universal Dependencies for L2 Learners of Modern Greek: Annotation and Challenges                       | [2026.udw-1.8](https://aclanthology.org/2026.udw-1.8/)           |

{% endraw %}
