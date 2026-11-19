---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/arb.html
---
{% raw %}
# So you want to work on Arabic?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `arb` · macrolanguage `ara`

**Language family:** **Afro-Asiatic** › Semitic › West Semitic › … › Arabic ([Glottolog](https://glottolog.org/resource/languoid/id/stan1318))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Arab`

**Speakers:** about 378.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `ara`, so includes other varieties

**Official / recognised in:** Algeria, Bahrain, Chad, Comoros, Djibouti, Egypt, Eritrea, Iraq, Jordan, Kuwait, Lebanon, Libya, Mauritania, Morocco, Oman, Palestine, Qatar, Saudi Arabia, Somalia, South Africa, Sudan, Syria, Tunisia, United Arab Emirates, Yemen

**Status:** Official language; De facto official language; Official and national language


## What does Arabic look and sound like?

**Written:** Omniglot has [a page on Arabic](https://www.omniglot.com/writing/arabic.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/arb/) has 5 videos of Arabic speakers. Watch [Souleymane speaking Nanerigé Sénoufo, French, Standard Arabic, Mandinka](https://wikitongues.org/videos/souleymane_20151201_sen-fra-arb-mnk/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                         |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,339,150 articles in ar.wikipedia; 5,501 active users. ⚠️ NB: recorded under the macrolanguage code `ara`, which can include other varieties of Arabic.                                                                                                       |
| Common Crawl           | 14,185,767 pages per crawl on average, which is 0.6580% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `ara`, which can include other varieties of Arabic.                                                                                  |
| FineWeb                | 106.04 GB (arb_Arab 106.04 GB; arb_Latn 0), equivalent to ≈72.38 GB of English after byte-premium scaling; 119.94 GB removed by filtering. This is ~1/504 of English data and ranks 16 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 11.62 GB (arb_Arab 11.62 GB) (rank 7 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                             |

**By writing system:**

| Writing system   | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Arabic (`Arab`)  | 106.04 GB | — (no byte premium yet)       | 11.62 GB     | 7.93 GB                        |
| Latin (`Latn`)   | 0         | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 28,402 sentences / 892,098 tokens in total: [UD_Arabic-NYUAD](https://github.com/UniversalDependencies/UD_Arabic-NYUAD) (19,738 sentences), [UD_Arabic-PADT](https://github.com/UniversalDependencies/UD_Arabic-PADT) (7,664 sentences), [UD_Arabic-PUD](https://github.com/UniversalDependencies/UD_Arabic-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `ara`, so this may cover other varieties as well as Arabic. |
| UniMorph               | 4,134 lemmas, 140,003 inflected forms ([unimorph/ara](https://github.com/unimorph/ara)) ⚠️ Listed under the macrolanguage code `ara`, so this may cover other varieties as well as Arabic.                                                                                                                                                                                                                                                                                                                                   |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Wordnets               | [Arabic WordNet (AWN v2)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-arb-1.4.tar.xz): 9,916 synsets, 18,003 words, 37,342 senses; licence: https://creativecommons.org/licenses/by-sa/3.0/.                                                                                                                                                                                                                                                                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([arb-vd](https://ebible.org/details.php?id=arb-vd)); full Bible ([arbnav](https://ebible.org/details.php?id=arbnav), by-sa 4.0).                                                                                                                                                                                                                                                                                                                                                                                      |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Arab script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ar-MA) en → ar-MA: 3,989 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_am) ar → am: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_sw) ar → sw: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ar-MA) en → ar-MA: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ar-MA) en → ar-MA: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.871 (P 0.815, R 0.971, FPR 2.95e-03) averaged over 6 dataset(s). Runner-up: commonlingua (F1 0.785).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.815 |    0.971 | 0.871 | 0.003 | ✓                |
| commonlingua |       0.746 |    0.857 | 0.785 | 0.004 | ✓                |
| py3langid    |       0.705 |    0.911 | 0.779 | 0.006 | ✓                |
| cld2         |       0.724 |    0.864 | 0.766 | 0.006 | ✓                |
| pyfranc      |       0.679 |    0.875 | 0.748 | 0.007 | ✓                |
| funlangid    |       0.716 |    0.806 | 0.748 | 0.004 | ✓                |
| OpenLID-v2   |       0.828 |    0.702 | 0.740 | 0.002 | ✓                |
| fasttext     |       0.576 |    0.997 | 0.716 | 0.008 | ✓                |
| cld3         |       0.582 |    0.897 | 0.695 | 0.011 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| NTREX     | 300 |       0.584 |    0.997 | 0.736 |
| FLORES    | 300 |       0.593 |    1.000 | 0.744 |
| CommonLID | 300 |       0.744 |    0.980 | 0.846 |
| Tatoeba   | 300 |       0.996 |    0.853 | 0.919 |
| Wikipedia | 300 |       0.971 |    0.993 | 0.982 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Arabic to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Arabic *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Arabic and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Arabic?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Arabic (and whether the model is exclusively tagged for Arabic or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,434** text-generation models are explicitly tagged for Arabic (940 original uploads, 3,494 fine-tunes/quantisations/merges).
- **434** are tagged *only* for Arabic.
- Including tags inherited from base models: **11,659**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       57 | █                    |
|   2023 |       93 | █                    |
|   2024 |      690 | ██████               |
|   2025 |     1291 | ███████████          |
|   2026 |     2303 | ████████████████████ |

### Largest models tagged for Arabic

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 856.0B       |                  143 |   2025 | —                                 |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 753.3B       |                   10 |   2026 | —                                 |
| [AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8) | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8              |

### Largest models tagged *only* for Arabic

| model                                                                                                                   | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [UnstableLlama/Laguna-S-2.1-Heretic](https://huggingface.co/UnstableLlama/Laguna-S-2.1-Heretic)                         | 117.6B       |                    1 |   2026 | poolside/Laguna-S-2.1 |
| [BiMediX/BiMediX-Ara](https://huggingface.co/BiMediX/BiMediX-Ara)                                                       | 46.6B        |                    1 |   2024 | —                     |
| [OS-Software/Ornith-1.5-35B-A3B-heretic-ja](https://huggingface.co/OS-Software/Ornith-1.5-35B-A3B-heretic-ja)           | 35.1B        |                    1 |   2026 | —                     |
| [lafintiger/Ornith-1.5-35B-A3B-heretic-ja-tiiny](https://huggingface.co/lafintiger/Ornith-1.5-35B-A3B-heretic-ja-tiiny) | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B  |
| [OS-Software/Ornith-1.5-35B-A3B-heretic-ja-GGUF](https://huggingface.co/OS-Software/Ornith-1.5-35B-A3B-heretic-ja-GGUF) | 34.7B        |                    1 |   2026 | —                     |

_415 tagged models have unknown parameter counts and are not ranked by size._

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

**43** benchmark datasets in the survey include Arabic.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 6 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 14 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 6 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 14 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">14 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">9 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">6 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | construction                                                   |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | Alrajhi et al. (Arabic)                                                                                    | 3,000          | Not reported                                                   |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 1,215          | Treebank-based (automatic, UD + UniMorph)                      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | Jawaher                                                                                                    | —              | Native (multidialectal proverbs)                               |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                      | —              | Native idioms; meanings MT from English + native review        |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom) (4 varieties/pairs)                 | —              | Native (curated by native speakers; generated contexts + MCQs) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)              | 2,181          | Native (Reddit/Twitter, native-speaker annotation)             |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [AraDiCE-WinoGrande](https://huggingface.co/datasets/QCRI/AraDiCE-WinoGrande) (3 varieties/pairs)          | 3,801          | MT + human post-editing                                        |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [EgyptianWinoGrande (Nile-Chat)](https://hf.co/datasets/MBZUAI-Paris/EgyptianWinoGrande)                   | —              | Machine translation (Claude)                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 9,176          | Machine translation (GPT-3.5-turbo)                            |
| 3. Commonsense reasoning               | PIQA                           | [AraDiCE-PIQA](https://huggingface.co/datasets/QCRI/AraDiCE-PIQA)                                          | 1,838          | MT + human post-editing                                        |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                        |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                     |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                      | 1,511          | Human translation (professional)                               |
| 3. Commonsense reasoning               | Temporal reasoning             | Arabic temporal commonsense (MC-TACO translation)                                                          | —              | Machine translation (Google) + native proofreading             |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                           | 10,400         | Template-generated with native-curated carrier phrases         |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (7 varieties/pairs)                          | 6,300          | Human translation (professional)                               |
| 4. Reading comprehension               | QA – extractive RC             | [ARCD](https://huggingface.co/datasets/hsseinmz/arcd)                                                      | 1,395          | Native                                                         |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | AraSTEM                                                                                                    | 11,637         | Native                                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ArabicMMLU](https://huggingface.co/datasets/MBZUAI/ArabicMMLU)                                            | 14,575         | Native (school exams)                                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                             | 562            | Native (high-school exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                      | 14,042         | Human translation (professional)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                             | 14,042         | Human translation (professional)                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                 | —              | Native (local exams/publications)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                    | 500            | Native (cultural; native-speaker answers)                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) (6 varieties/pairs) | 600            | Native (community-written, peer-verified)                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                   | 10,000         | Human translation                                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                            | 250            | Native (locally sourced)                                       |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                          | 1,270          | Native (TyDi questions)                                        |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                 |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                    | 2,100          | Human translation (professional/volunteer, from English)       |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 13,290         | Native (crowdsourced Tatoeba sentence pairs)                   |

### Standard machine translation test sets

| Test set                                                                                               | Direction(s)              | Size                   | Human reference   |
|:-------------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                | multi-way (all languages) | 2,009 sentences (Arab) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-ar_SA)                              | en → ar_SA                | 998 segments           | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ar-MA) (training data)   | en → ar-MA                | 3,989 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_am) (training data)      | ar → am                   | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ar_sw) (training data)      | ar → sw                   | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_ar-MA) (training data)   | en → ar-MA                | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_ar-MA) (training data) | en → ar-MA                | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Arabic datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Arabic? Does it make sense to train one?
  - ~72.38 GB English-equivalent text ≈ 18.10B tokens, enough for a compute-optimal model of ~904.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Arabic-only model is 117.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,556 of ~18,498 papers (8.41%) (rank 4 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Modern Standard Arabic | Arabic

Here are up to ten papers published in 2026 that mention Arabic. None of the 1,556 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                            | paper                                                                                      | mentioned in   |
|:-----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------|:---------------|
| AKARROUCH at DialectSentEval 2026: A Generate-and-Rerank Approach for Arabic Dialect Sentiment Swapping          | [2026.arabicnlp-sharedtasks.174](https://aclanthology.org/2026.arabicnlp-sharedtasks.174/) | body only      |
| Tarjih at StanceEval-2026: Argument-Guided Arabic Stance Detection                                               | [2026.arabicnlp-sharedtasks.69](https://aclanthology.org/2026.arabicnlp-sharedtasks.69/)   | body only      |
| Lightweight Multilingual Coreference Resolution without LLMs @CRAC2026                                           | [2026.codi-1.26](https://aclanthology.org/2026.codi-1.26/)                                 | body only      |
| Do Political Opinions Transfer Between Western Languages? An Analysis of Unaligned and Aligned Multilingual LLMs | [2026.eacl-long.14](https://aclanthology.org/2026.eacl-long.14/)                           | body only      |
| Artificial intelligence language technologies in multilingual healthcare: Grand challenges ahead                 | [2026.eamt-1.48](https://aclanthology.org/2026.eamt-1.48/)                                 | body only      |
| MultiSynt/MT: Trillion-Token Multi-Parallel Pretraining Data Translated Across 36 Languages                      | [2026.emnlp-main.2185](https://aclanthology.org/2026.emnlp-main.2185/)                     | body only      |
| A Survey of Incorporating Gaze Data into Natural Language Processing Models and Applications                     | [2026.gaze4nlp-1.10](https://aclanthology.org/2026.gaze4nlp-1.10/)                         | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                               | body only      |
| Using Valency Inheritance in Building a Valency Lexicon                                                          | [2026.lrec-1.900](https://aclanthology.org/2026.lrec-1.900/)                               | body only      |
| Hate Speech as a Conflict-Period Marker: Evidence from Arabic Telegram in Sudan                                  | [2026.nlp4pi-1.20](https://aclanthology.org/2026.nlp4pi-1.20/)                             | body only      |

{% endraw %}
