---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ell.html
---
{% raw %}
# So you want to work on Greek?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ell`

**Language family:** **Indo-European** › Classical Indo-European › Graeco-Phrygian › … › Nuclear Modern Greek ([Glottolog](https://glottolog.org/resource/languoid/id/mode1248))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Grek`

**Speakers:** about 12.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Cyprus, Greece, South Africa

**Status:** Official language


## What does Greek look and sound like?

**Written (handwritten Greek)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/greek.htm):

> Font from: http://boboss.gr/2009/12/13/greek-handwriting-font/

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Corrections and notes on pronunciation provided by Δημήτρης Χριστούλιας (Dimitris Christoulias) [top]

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ell/) has 7 videos of Greek speakers. Watch [See all](https://wikitongues.org/videos/?language=ell).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 275,091 articles in el.wikipedia; 2,113 active users. This is ~1/27 of English data and ranks 36 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 11,595,458 pages per crawl on average, which is 0.5380% of the crawl (2026). This is ~1/77 of English data and ranks 19 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 78.61 GB (ell_Grek 78.61 GB), equivalent to ≈39.96 GB of English after byte-premium scaling; 100.72 GB removed by filtering. This is ~1/680 of English data and ranks 23 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 12.84 GB (ell_Grek 12.84 GB) (rank 4 of the 171 languages in the set that have any; 161 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 8 treebanks, 6,204 sentences / 111,412 tokens in total: [UD_Greek-Cretan](https://github.com/UniversalDependencies/UD_Greek-Cretan) (270 sentences), [UD_Greek-Cypriot](https://github.com/UniversalDependencies/UD_Greek-Cypriot) (100 sentences), [UD_Greek-GDT](https://github.com/UniversalDependencies/UD_Greek-GDT) (2,521 sentences), [UD_Greek-GLCII](https://github.com/UniversalDependencies/UD_Greek-GLCII) (671 sentences), [UD_Greek-GUD](https://github.com/UniversalDependencies/UD_Greek-GUD) (1,807 sentences), [UD_Greek-Griko](https://github.com/UniversalDependencies/UD_Greek-Griko) (100 sentences), [UD_Greek-Lesbian](https://github.com/UniversalDependencies/UD_Greek-Lesbian) (625 sentences), [UD_Greek-Messinian](https://github.com/UniversalDependencies/UD_Greek-Messinian) (110 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 11,906 lemmas, 199,757 inflected forms ([unimorph/ell](https://github.com/unimorph/ell))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Wikidata labels        | 1,316,022 Wikidata items have a label in Greek. (Wikidata codes (labels): el (1,316,022))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Wordnets               | [Greek Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-el-1.4.tar.xz): 18,049 synsets, 18,264 words, 24,106 senses; licence: https://opensource.org/licenses/Apache-2.0; [BalkaNet](http://www.dblab.upatras.gr/balkanet/) (size not listed).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 361,538,056 sentence pairs with English across 112 corpora; largest: [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (76,818,359), [HPLT](https://opus.nlpl.eu/HPLT) (55,649,558), [MultiHPLT](https://opus.nlpl.eu/MultiHPLT) (55,649,558), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (49,262,631), [NLLB](https://opus.nlpl.eu/NLLB) (49,262,631). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                              |
| Tatoeba                                                                                  | 43,102 sentences, 30,822 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ell/none)).                                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Grek script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                     |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Grek script) — paired with English                                                                                                                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.997 (P 0.997, R 0.997, FPR 2.76e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.997).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.997 |    0.997 | 0.997 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.996 | 0.997 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.990 | 0.994 | 0.000 | ✗                |
| GlotLID      |       0.997 |    0.989 | 0.993 | 0.000 | ✓                |
| cld2         |       0.956 |    0.997 | 0.974 | 0.000 | ✓                |
| py3langid    |       0.996 |    0.895 | 0.929 | 0.000 | ✓                |
| funlangid    |       0.958 |    0.904 | 0.924 | 0.000 | ✓                |
| commonlingua |       0.995 |    0.866 | 0.913 | 0.000 | ✓                |
| cld3         |       0.832 |    0.993 | 0.902 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.983 |    0.983 | 0.983 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 116 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Greek to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Greek *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Greek and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Greek?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Greek (and whether the model is exclusively tagged for Greek or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **740** text-generation models are explicitly tagged for Greek (239 original uploads, 501 fine-tunes/quantisations/merges).
- **91** are tagged *only* for Greek.
- Including tags inherited from base models: **1,327**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       18 | █                    |
|   2023 |       22 | ██                   |
|   2024 |      215 | ████████████████     |
|   2025 |      213 | ████████████████     |
|   2026 |      272 | ████████████████████ |

### Largest models tagged for Greek

| model                                                                                                               | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)             | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)               | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [Tonic/c4ai-command-a-03-2025-4bit_nf4_double](https://huggingface.co/Tonic/c4ai-command-a-03-2025-4bit_nf4_double) | 114.4B       |                   23 |   2025 | CohereLabs/c4ai-command-a-03-2025      |

### Largest models tagged *only* for Greek

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                                   |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------------------------|
| [MikCil/PREMOVE_llama3.3-70b_float16](https://huggingface.co/MikCil/PREMOVE_llama3.3-70b_float16)     | 70.6B        |                    1 |   2026 | unsloth/llama-3.3-70b-instruct-unsloth-bnb-4bit |
| [Efso/Nemotron-3-Nano-30B-A3B-GR](https://huggingface.co/Efso/Nemotron-3-Nano-30B-A3B-GR)             | 31.6B        |                    1 |   2026 | nvidia/NVIDIA-Nemotron-3-Nano-30B-A3B-BF16      |
| [d-michail/Mitos-Qwen3-14B-Dialogue](https://huggingface.co/d-michail/Mitos-Qwen3-14B-Dialogue)       | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                             |
| [IMISLab/Maistros-8B-Instruct-4bit](https://huggingface.co/IMISLab/Maistros-8B-Instruct-4bit)         | 9.2B         |                    1 |   2026 | mistralai/Ministral-3-8B-Instruct-2512-BF16     |
| [themetron/Krikri-Cypriot-8B-v0.1-GGUF](https://huggingface.co/themetron/Krikri-Cypriot-8B-v0.1-GGUF) | 8.2B         |                    1 |   2026 | ilsp/Llama-Krikri-8B-Base                       |

_75 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Greek.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">3 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                               |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 87             | Treebank-based (automatic)                                 |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 1,096          | Treebank-based (automatic, UD + UniMorph)                  |
| 1. Linguistic knowledge       | BLiMP                          | [el-BLiMP](https://github.com/eirisel/el-blimp)                                                     | 600            | Mixed (template + LLM-assisted + web-extracted)            |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                 |
| 3. Commonsense reasoning      | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline) |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                     |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                    |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                 |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                           |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia              |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                     |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                       |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                  |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)             |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 13,055         | Native (crowdsourced Tatoeba sentence pairs)               |

### Standard machine translation test sets

Greek has been part of the WMT translation task in **1** year (2025).

| Test set                                                                  | Direction(s)                      | Size                               | Human reference             |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Grek)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Grek)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-el_GR) | en → el_GR                        | 998 segments                       | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Greek                   | 87 documents (36,770 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Greek datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Greek? Does it make sense to train one?
  - ~39.96 GB English-equivalent text ≈ 9.99B tokens, enough for a compute-optimal model of ~499.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Greek-only model is 70.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 426 of ~18,498 papers (2.30%) (rank 17 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Greek

Here are up to ten papers published in 2026 that mention Greek. None of the 426 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mitigating Tokenization-Induced Distance Distortion in Long-Context Multilingual Machine Translation                  | [2026.acl-long.1696](https://aclanthology.org/2026.acl-long.1696/)             |
| Hellenic National Corpus: The Current State                                                                           | [2026.cmlc-1.7](https://aclanthology.org/2026.cmlc-1.7/)                       |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages                         | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/)       |
| Thinking While Speaking: Inference-Time Knowledge Transfer for Responsive and Intelligent Conversational Voice Agents | [2026.findings-emnlp.1371](https://aclanthology.org/2026.findings-emnlp.1371/) |
| ConvDeck: Conversational Paper-to-Slide Generation via Stage-Specific User Feedback                                   | [2026.findings-emnlp.541](https://aclanthology.org/2026.findings-emnlp.541/)   |
| Universal NER v2: Towards a Massively Multilingual Named Entity Recognition Benchmark                                 | [2026.lrec-1.525](https://aclanthology.org/2026.lrec-1.525/)                   |
| WikIPA: Integrating WikiPron and Lingua Libre for Multilingual IPA Transcription                                      | [2026.lrec-1.668](https://aclanthology.org/2026.lrec-1.668/)                   |
| Building a Corpus and Database for Rare and Undeciphered Scripts                                                      | [2026.lt4hala-1.17](https://aclanthology.org/2026.lt4hala-1.17/)               |
| When Retrieval Hurts: Evidence Utilization, Script Fidelity, and Knowledge Conflicts in Multilingual RAG              | [2026.mellm-1.9](https://aclanthology.org/2026.mellm-1.9/)                     |
| Decoding News Narratives: A Critical Analysis of Large Language Models in Framing Detection                           | [2026.politicalnlp-1.2](https://aclanthology.org/2026.politicalnlp-1.2/)       |

{% endraw %}
