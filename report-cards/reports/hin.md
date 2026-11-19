---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hin.html
---
{% raw %}
# So you want to work on Hindi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hin`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Hindustani ([Glottolog](https://glottolog.org/resource/languoid/id/hind1269))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Deva`

**Speakers:** about 581.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Fiji, India, South Africa

**Status:** Official language


## What does Hindi look and sound like?

**Written:** Omniglot has [a page on Hindi](https://www.omniglot.com/writing/hindi.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hin/) has 7 videos of Hindi speakers. Watch [See all](https://wikitongues.org/videos/?language=hin).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 172,305 articles in hi.wikipedia; 933 active users. This is ~1/44 of English data and ranks 49 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                   |
| Common Crawl           | 4,714,422 pages per crawl on average, which is 0.2187% of the crawl (2026). This is ~1/189 of English data and ranks 29 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                                                                                                                                       |
| FineWeb                | 34.56 GB (hin_Deva 34.36 GB; hin_Latn 0.20 GB), equivalent to ≈14.50 GB of English after byte-premium scaling (⚠️ only 99% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 21.71 GB removed by filtering. This is ~1/1,546 of English data and ranks 28 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 7.59 GB (hin_Deva 7.59 GB) (rank 29 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                           |

**By writing system:**

| Writing system      | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Devanagari (`Deva`) | 34.36 GB  | 14.50 GB                      | 7.59 GB      | 3.20 GB                        |
| Latin (`Latn`)      | 0.20 GB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 17,649 sentences / 375,533 tokens in total: [UD_Hindi-HDTB](https://github.com/UniversalDependencies/UD_Hindi-HDTB) (16,649 sentences), [UD_Hindi-PUD](https://github.com/UniversalDependencies/UD_Hindi-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features.                                                                                      |
| UniMorph               | 258 lemmas, 54,438 inflected forms ([unimorph/hin](https://github.com/unimorph/hin))                                                                                                                                                                                                                                                                                                                        |
| Wikidata labels        | 1,263,182 Wikidata items have a label in Hindi. (Wikidata codes (labels): hi (1,263,182))                                                                                                                                                                                                                                                                                                                   |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD; [Hindi WordNet](http://www.cfilt.iitb.ac.in/wordnet/webhwn/) (size not listed); licence: GNU FDL; [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY; [Malayalam WordNet](http://malayalamwordnet.cusat.ac.in/) (size not listed); licence: BROWSE ONLINE. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                          |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 84,043,743 sentence pairs with English across 31 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (33,193,629), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (15,127,900), [Samanantar](https://opus.nlpl.eu/Samanantar) (10,125,707), [CCAligned](https://opus.nlpl.eu/CCAligned) (8,181,587), [Anuvaad](https://opus.nlpl.eu/Anuvaad) (5,029,374). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: full Bible ([hin2017](https://ebible.org/details.php?id=hin2017), by-sa 4.0).                                                                                                                                                                                                                                               |
| Tatoeba                                                                                  | 16,479 sentences, 13,290 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/hin/none)).                                                                                                                                                                                                                              |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Deva script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Deva script); 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                   |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_hi) en → hi: 3,984 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_hi) en → hi: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_hi) en → hi: size not listed                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.953 (P 0.920, R 0.991, FPR 7.61e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.868).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.920 |    0.991 | 0.953 | 0.001 | ✓                |
| fasttext     |       0.806 |    0.989 | 0.868 | 0.003 | ✓                |
| OpenLID-v2   |       0.807 |    0.941 | 0.847 | 0.003 | ✓                |
| cld2         |       0.772 |    0.986 | 0.845 | 0.004 | ✓                |
| funlangid    |       0.894 |    0.773 | 0.823 | 0.001 | ✓                |
| commonlingua |       0.762 |    0.934 | 0.817 | 0.003 | ✓                |
| pyfranc      |       0.769 |    0.857 | 0.797 | 0.004 | ✓                |
| py3langid    |       0.685 |    0.978 | 0.762 | 0.009 | ✓                |
| cld3         |       0.329 |    0.972 | 0.466 | 0.035 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.852 |    1.000 | 0.920 |
| Wikipedia | 300 |       0.881 |    0.983 | 0.929 |
| CommonLID | 300 |       0.896 |    0.973 | 0.933 |
| UDHR-LID  |  60 |       0.923 |    1.000 | 0.960 |
| Tatoeba   | 300 |       0.977 |    0.987 | 0.982 |
| NTREX     | 300 |       0.990 |    1.000 | 0.995 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hindi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hindi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hindi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hindi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hindi (and whether the model is exclusively tagged for Hindi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,787** text-generation models are explicitly tagged for Hindi (1,201 original uploads, 3,586 fine-tunes/quantisations/merges).
- **130** are tagged *only* for Hindi.
- Including tags inherited from base models: **23,764**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       47 | █                    |
|   2023 |       66 | █                    |
|   2024 |     1413 | ████████████████     |
|   2025 |     1533 | ██████████████████   |
|   2026 |     1728 | ████████████████████ |

### Largest models tagged for Hindi

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 856.0B       |                  143 |   2025 | —                    |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)         | 753.3B       |                   10 |   2026 | —                    |
| [AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/AleaiactaEst1/GLM-5.3-CYBERSECURITY-FP8) | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8 |
| [newzyerror/fluidity-vapour-4.1](https://huggingface.co/newzyerror/fluidity-vapour-4.1)                   | 753.3B       |                    4 |   2026 | fluidity-vapour-4.1  |

### Largest models tagged *only* for Hindi

| model                                                                                                                                     | parameters   |   # languages tagged |   year | derivative of               |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------|
| [Aaravomega/sarvam-30b-GGUF-IQ2_S-surgical](https://huggingface.co/Aaravomega/sarvam-30b-GGUF-IQ2_S-surgical)                             | 32.2B        |                    1 |   2026 | sarvamai/sarvam-30b         |
| [snupilab/laplace-v37-qwen3-14b-hindsight-ep1.00](https://huggingface.co/snupilab/laplace-v37-qwen3-14b-hindsight-ep1.00)                 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base         |
| [pranavajay/hindi-8b](https://huggingface.co/pranavajay/hindi-8b)                                                                         | 10.7B        |                    1 |   2024 | —                           |
| [snupilab/laplace-v37-qwen3-8b-hindsight-smoothed-ep1.34](https://huggingface.co/snupilab/laplace-v37-qwen3-8b-hindsight-smoothed-ep1.34) | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base          |
| [MotherEarth/MotherEarth-1.0-8B](https://huggingface.co/MotherEarth/MotherEarth-1.0-8B)                                                   | 8.0B         |                    1 |   2024 | MotherEarth/MotherEarth_1.0 |

_325 tagged models have unknown parameter counts and are not ranked by size._

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

**38** benchmark datasets in the survey include Hindi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 4 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 8 datasets; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 4 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 8 datasets; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">9 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">4 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">4 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                                 | # test items   | construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | Jain & Vaidya (Hindi)                                                                                                   | 224            | Not reported                                                     |
| 1. Linguistic knowledge                | BLiMP                          | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual)                                       | 6,000          | Template-based                                                   |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                               | 107            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                                    | 1,447          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MABL (Multilingual Fig-QA)](https://huggingface.co/datasets/cmu-lti/multi-figqa)                                       | 1,000          | Native (written by native speakers)                              |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                           | 786            | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual)          | 240            | Native                                                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated)              | —              | Machine translation (method not stated)                          |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                                   | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                                | 9,416          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | HellaSwag                      | [hellaswag-hi](https://huggingface.co/datasets/ai4bharat/hellaswag-hi)                                                  | 10,042         | Translation (method not checked)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) | 200            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        | 206            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                                  | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                                   | 1,511          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                                        | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (2 varieties/pairs)                                       | 1,800          | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                                | 15,514         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [chaii](https://www.kaggle.com/c/chaii-hindi-and-tamil-question-answering)                                              | 746            | Native                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                                           | —              | Machine translation (from MMLU-Pro)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                         | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                                  | 14,837         | Native (Indian exams; some translated)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                           | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                          | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                                  | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                         | 250            | Native (locally sourced)                                         |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                                 | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    | 5,000          | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

Hindi has been part of the WMT translation task in **4** years (2014, 2021, 2024, 2025).

| Test set                                                                                            | Direction(s)                      | Size                               | Human reference             |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Deva)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Deva)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-hi_IN)                           | en → hi_IN                        | 998 segments                       | ✅                          |
| [WMT14 general task](https://www2.statmt.org/wmt14/)                                                | English → Hindi; Hindi → English  | 2,507 segments                     | ✅                          |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                                                | Bengali → Hindi; Hindi → Bengali  | 503 segments / 509 segments        | ✅                          |
| [WMT24 general task](https://www2.statmt.org/wmt24/)                                                | English → Hindi                   | 997 segments                       | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)                            | English → Hindi                   | 87 documents (36,770 source words) | no (automatic metrics only) |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_hi) (training data)   | en → hi                           | 3,984 lexicon entries              | ✅                          |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_hi) (training data)   | en → hi                           | size not listed                    | ✅                          |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_hi) (training data) | en → hi                           | size not listed                    | ✅                          |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hindi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hindi? Does it make sense to train one?
  - ~14.50 GB English-equivalent text ≈ 3.62B tokens, enough for a compute-optimal model of ~181.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hindi-only model is 32.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 775 of ~18,498 papers (4.19%) (rank 10 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Hindi

Here are up to ten papers published in 2026 that mention Hindi. None of the 775 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                              | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| When Does Knowledge Distillation Hurt? Reliability-Aware Distillation for Low-Resource Language Summarization                      | [2026.aacl-short.4](https://aclanthology.org/2026.aacl-short.4/)               |
| Multi-Modal-Minds@CHiPSAL 2026: A Comparative Study of Textual, Visual and Multimodal Architecture for Nepali Meme Moderation      | [2026.chipsal-1.26](https://aclanthology.org/2026.chipsal-1.26/)               |
| Reaching multilingual communities: a survey mapping MT use in the West Midlands (UK) third and public sector organisations         | [2026.eamt-1.38](https://aclanthology.org/2026.eamt-1.38/)                     |
| Pak3H: Evaluating the Cost of Cultural Mismatch in LLM Alignment with a Human-Contextualized Urdu Benchmark                        | [2026.emnlp-main.883](https://aclanthology.org/2026.emnlp-main.883/)           |
| Using large language models to provide effective embeddings for native language identification                                     | [2026.findings-emnlp.1251](https://aclanthology.org/2026.findings-emnlp.1251/) |
| ARJUN: A Parameter-Efficient Multi-Objective Pre-Training Framework for Language Models                                            | [2026.findings-emnlp.1877](https://aclanthology.org/2026.findings-emnlp.1877/) |
| Democratic ICAI: Debating Our Way to Steering Principles from Preferences                                                          | [2026.findings-emnlp.2355](https://aclanthology.org/2026.findings-emnlp.2355/) |
| Does Safety Reasoning Travel? A Multilingual Measurement of Prompt-Injection Attacks and Runtime Monitors in Tool-Using LLM Agents | [2026.oracle-main.13](https://aclanthology.org/2026.oracle-main.13/)           |
| The Shabd Portal – Searchable Lexical Resources for Indian Languages by Government of India                                        | [2026.wildre-1.8](https://aclanthology.org/2026.wildre-1.8/)                   |
| BVSLP at WMT 2026: An Empirical Study of Multilingual Transfer for Low-Resource Arabic-Centric Translation                         | [2026.wmt-main.168](https://aclanthology.org/2026.wmt-main.168/)               |

{% endraw %}
