---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nld.html
---
{% raw %}
# So you want to work on Dutch?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nld`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Global Dutch ([Glottolog](https://glottolog.org/resource/languoid/id/dutc1256))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 32.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Belgium, Kingdom of the Netherlands, Suriname

**Status:** Official language


## What does Dutch look and sound like?

**Written (Standard Dutch)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/dutch.htm):

> Alle mensen worden vrij en gelijk in waardigheid en rechten geboren. Zij zijn begiftigd met verstand en geweten, en behoren zich jegens elkander in een geest van broederschap te gedragen.
> A recording of this text

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_nl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/nld/) has 7 videos of Dutch speakers. Watch [See all](https://wikitongues.org/videos/?language=nld).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,231,210 articles in nl.wikipedia; 8,144 active users. This is ~1/3 of English data and ranks 6 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 38,521,061 pages per crawl on average, which is 1.7874% of the crawl (2026). This is ~1/23 of English data and ranks 10 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                               |
| FineWeb                | 190.07 GB (nld_Latn 190.07 GB), equivalent to ≈180.74 GB of English after byte-premium scaling; 243.42 GB removed by filtering. This is ~1/281 of English data and ranks 11 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.02 GB (nld_Latn 9.02 GB) (rank 18 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 30,723 sentences / 505,678 tokens in total: [UD_Dutch-Alpino](https://github.com/UniversalDependencies/UD_Dutch-Alpino) (13,603 sentences), [UD_Dutch-LassySmall](https://github.com/UniversalDependencies/UD_Dutch-LassySmall) (17,120 sentences). All have POS tags, dependency syntax, lemmas and morphological features.                                                                                                                                                                                                                                                                   |
| UniMorph               | 4,993 lemmas, 55,467 inflected forms ([unimorph/nld](https://github.com/unimorph/nld))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Wordnets               | [Open Dutch WordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-nl-1.4.tar.xz): 30,177 synsets, 43,667 words, 60,259 senses; licence: https://creativecommons.org/licenses/by-sa/4.0/; [Combinatorial and Relational Network as Toolkit for Dutch Language Technology (Cornetto)](http://www2.let.vu.nl/oz/cltl/cornetto/) (size not listed); licence: RESTRICTED (Browse Online Free); [Dutch Open Source WordNet](http://wordpress.let.vupr.nl/odwn/) (size not listed); licence: OPEN; [EuroWordNet Dutch](http://www.illc.uva.nl/EuroWordNet/) (size not listed); licence: RESTRICTED. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                    |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([nld1939](https://ebible.org/details.php?id=nld1939), Public Domain). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                        |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.964, R 0.993, FPR 3.28e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.926).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.964 |    0.993 | 0.978 | 0.000 | ✓                |
| cld2         |       0.932 |    0.928 | 0.926 | 0.001 | ✓                |
| cld3         |       0.866 |    0.959 | 0.908 | 0.002 | ✓                |
| py3langid    |       0.850 |    0.983 | 0.904 | 0.002 | ✓                |
| commonlingua |       0.885 |    0.888 | 0.885 | 0.001 | ✓                |
| funlangid    |       0.885 |    0.869 | 0.876 | 0.001 | ✓                |
| pyfranc      |       0.892 |    0.851 | 0.869 | 0.001 | ✓                |
| fasttext     |       0.743 |    0.991 | 0.835 | 0.004 | ✓                |
| OpenLID-v2   |       0.749 |    0.967 | 0.831 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.927 |    0.980 | 0.953 |
| Wikipedia | 300 |       0.940 |    0.997 | 0.968 |
| CommonLID | 300 |       0.958 |    0.983 | 0.970 |
| UDHR-LID  |  58 |       0.967 |    1.000 | 0.983 |
| NTREX     | 300 |       0.997 |    0.997 | 0.997 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dutch to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dutch *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dutch and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Dutch?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dutch (and whether the model is exclusively tagged for Dutch or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,568** text-generation models are explicitly tagged for Dutch (373 original uploads, 1,195 fine-tunes/quantisations/merges).
- **139** are tagged *only* for Dutch.
- Including tags inherited from base models: **3,431**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       16 | █                    |
|   2023 |       48 | █                    |
|   2024 |      322 | █████████            |
|   2025 |      495 | ██████████████       |
|   2026 |      687 | ████████████████████ |

### Largest models tagged for Dutch

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                                     |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 1.9T         |                  143 |   2025 | —                                                 |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 856.0B       |                  143 |   2025 | —                                                 |
| [FriendliAI/Mistral-Large-3-675B-Instruct-2512-BF16](https://huggingface.co/FriendliAI/Mistral-Large-3-675B-Instruct-2512-BF16) | 676.0B       |                   11 |   2025 | mistralai/Mistral-Large-3-675B-Instruct-2512-BF16 |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                         | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019                   |
| [ai21labs/AI21-Jamba-Large-1.5](https://huggingface.co/ai21labs/AI21-Jamba-Large-1.5)                                           | 398.6B       |                    9 |   2024 | —                                                 |

### Largest models tagged *only* for Dutch

| model                                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                              |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------------|
| [BramVanroy/falcon-40b-ft-alpaca-dolly-dutch](https://huggingface.co/BramVanroy/falcon-40b-ft-alpaca-dolly-dutch)                           | 41.3B        |                    1 |   2023 | tiiuae/falcon-40b                          |
| [MichielBuisman/granite-4.0-h-small-dutch-calibrated-gguf](https://huggingface.co/MichielBuisman/granite-4.0-h-small-dutch-calibrated-gguf) | 32.2B        |                    1 |   2026 | ibm-granite/granite-4.0-h-small            |
| [MeerDevelopment/gemma-4-31B-it-nl-lora](https://huggingface.co/MeerDevelopment/gemma-4-31B-it-nl-lora)                                     | 31.0B        |                    1 |   2026 | google/gemma-4-31B-it                      |
| [robinsmits/open_llama_13b_alpaca_clean_dutch_qlora](https://huggingface.co/robinsmits/open_llama_13b_alpaca_clean_dutch_qlora)             | 13.0B        |                    1 |   2023 | openlm-research/open_llama_13b             |
| [robinsmits/polylm_13b_ft_alpaca_clean_dutch](https://huggingface.co/robinsmits/polylm_13b_ft_alpaca_clean_dutch)                           | 13.0B        |                    1 |   2023 | DAMO-NLP-MT/polylm-13b-fine-grained-shards |

_98 tagged models have unknown parameter counts and are not ranked by size._

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

**31** benchmark datasets in the survey include Dutch.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 6 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 9 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 6 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 7 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 9 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">9 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">6 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                           |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation              |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMP-NL](https://data.ru.nl/collections/ru/cls/blimp-nl_dsc_550)                                  | 8,400          | Template-based                                         |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 1,771          | Treebank-based (automatic)                             |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,331          | Treebank-based (automatic, UD + UniMorph)              |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                    | 5,153          | Translation (method not stated)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)        | 5,153          | Translation (method not stated)                        |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)       | 1,000          | Native (Reddit/Twitter, native-speaker annotation)     |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)      | [DPR (Dutch Pronoun Resolution, DUMB)](https://github.com/wietsedv/dumb)                            | 1,216          | Native (SemEval-2010 coref recast)                     |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                            |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)             |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,265          | Machine translation (GPT-3.5-turbo)                    |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)             |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                       |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                               |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)         |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 17,138         | Native (crowdsourced Tatoeba sentence pairs)           |

### Standard machine translation test sets

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-nl_NL) | en → nl_NL                        | 998 segments           | ✅                |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dutch datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dutch? Does it make sense to train one?
  - ~180.74 GB English-equivalent text ≈ 45.19B tokens, enough for a compute-optimal model of ~2.3B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Dutch-only model is 41.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 588 of ~18,498 papers (3.18%) (rank 12 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Dutch

Here are up to ten papers published in 2026 that mention Dutch. None of the 588 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                    | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| ALIGN: Word Association Learning for Cultural Alignment in Large Language Models                                                         | [2026.acl-long.130](https://aclanthology.org/2026.acl-long.130/)       |
| Augustinian BabyLM: What Ostensive Definition Can and Cannot Teach a Small Language Model                                                | [2026.babylm-main.13](https://aclanthology.org/2026.babylm-main.13/)   |
| MIMO: Multilingual Information Retrieval via Monolingual Objectives                                                                      | [2026.emnlp-main.156](https://aclanthology.org/2026.emnlp-main.156/)   |
| The Masked Advantage: Uncovering Local-Language Access to Cultural Knowledge in LLMs                                                     | [2026.emnlp-main.1754](https://aclanthology.org/2026.emnlp-main.1754/) |
| Right Diagnoses, Decorative Reasoning: A Perturbation Audit of Medical Chain-of-Thought                                                  | [2026.emnlp-main.334](https://aclanthology.org/2026.emnlp-main.334/)   |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                                      | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)           |
| Towards an Interoperable Corpus of Austrian Historical Newspapers: The case of PressMint-AT                                              | [2026.pressmint-1.7](https://aclanthology.org/2026.pressmint-1.7/)     |
| SemEval-2026 Task 4: Narrative Story Similarity and Narrative Representation Learning                                                    | [2026.semeval-1.429](https://aclanthology.org/2026.semeval-1.429/)     |
| A Morphology-Aware Evaluation of Turkish Syntax in Large Language Models                                                                 | [2026.sigturk-1.9](https://aclanthology.org/2026.sigturk-1.9/)         |
| ICB-UMA at #SMM4H–HeaRD 2026: Hybrid Clinical Entity Projection for MultiClinAI: Adaptive Candidate Windows, XGBoost, and LLM Refinement | [2026.smm4h-1.21](https://aclanthology.org/2026.smm4h-1.21/)           |

{% endraw %}
