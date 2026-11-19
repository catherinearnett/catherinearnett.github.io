---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/swe.html
---
{% raw %}
# So you want to work on Swedish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `swe`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › East Swedic ([Glottolog](https://glottolog.org/resource/languoid/id/swed1254))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 13.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Finland, Sweden

**Status:** Official language


## What does Swedish look and sound like?

**Written (Swedish)**, sample text from [Omniglot](https://www.omniglot.com/writing/swedish.htm):

> Alla människor är födda fria och lika i värde och rättigheter. De är utrustade med förnuft och samvete och bör handla gentemot varandra i en anda av broderskap.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_sv.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/swe/) has 7 videos of Swedish speakers. Watch [See all](https://wikitongues.org/videos/?language=swe).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,629,888 articles in sv.wikipedia; 4,777 active users. This is ~1/3 of English data and ranks 5 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 15,372,610 pages per crawl on average, which is 0.7136% of the crawl (2026). This is ~1/58 of English data and ranks 17 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                            |
| FineWeb                | 95.21 GB (swe_Latn 95.21 GB), equivalent to ≈93.25 GB of English after byte-premium scaling; 146.95 GB removed by filtering. This is ~1/561 of English data and ranks 19 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 8.36 GB (swe_Latn 8.37 GB) (rank 22 of the 171 languages in the set that have any; 161 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 6 treebanks, 14,152 sentences / 246,250 tokens in total: [UD_Swedish-LinES](https://github.com/UniversalDependencies/UD_Swedish-LinES) (5,696 sentences), [UD_Swedish-Modern](https://github.com/UniversalDependencies/UD_Swedish-Modern) (735 sentences), [UD_Swedish-Old](https://github.com/UniversalDependencies/UD_Swedish-Old) (40 sentences), [UD_Swedish-PUD](https://github.com/UniversalDependencies/UD_Swedish-PUD) (1,000 sentences), [UD_Swedish-SweLL](https://github.com/UniversalDependencies/UD_Swedish-SweLL) (643 sentences), [UD_Swedish-Talbanken](https://github.com/UniversalDependencies/UD_Swedish-Talbanken) (6,038 sentences). All have POS tags, dependency syntax, morphological features. |
| UniMorph               | 12,520 lemmas, 131,697 inflected forms ([unimorph/swe](https://github.com/unimorph/swe))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Wikidata labels        | 9,662,411 Wikidata items have a label in Swedish. (Wikidata codes (labels): sv (9,662,411))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Wordnets               | [WordNet-SALDO](https://github.com/omwn/omw-data/releases/download/v1.4/omw-sv-1.4.tar.xz): 6,796 synsets, 5,872 words, 6,904 senses; licence: https://creativecommons.org/licenses/by/3.0/; nan (size not listed).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 324,773,569 sentence pairs with English across 96 corpora; largest: [CCMatrix](https://opus.nlpl.eu/CCMatrix) (77,008,059), [NLLB](https://opus.nlpl.eu/NLLB) (77,008,059), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (53,218,418), [ParaCrawl](https://opus.nlpl.eu/ParaCrawl) (49,110,322), [ELRC-4268-NTEU_TierA](https://opus.nlpl.eu/ELRC-4268-NTEU_TierA) (12,737,597). |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament + parts of the Old Testament ([swe](https://ebible.org/details.php?id=swe), by-nc-nd 4.0).                                                                                                                                                                                                                                                       |
| Tatoeba                                                                                  | 56,869 sentences, 38,823 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/swe/none)).                                                                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                     |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.975, R 0.999, FPR 1.89e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.969).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.975 |    0.999 | 0.987 | 0.000 | ✓                |
| py3langid    |       0.949 |    0.992 | 0.969 | 0.001 | ✓                |
| cld2         |       0.991 |    0.924 | 0.956 | 0.000 | ✓                |
| fasttext     |       0.914 |    0.997 | 0.952 | 0.001 | ✓                |
| cld3         |       0.882 |    0.969 | 0.922 | 0.002 | ✓                |
| OpenLID-v2   |       0.846 |    0.995 | 0.909 | 0.002 | ✓                |
| commonlingua |       0.929 |    0.891 | 0.904 | 0.001 | ✓                |
| funlangid    |       0.869 |    0.894 | 0.881 | 0.001 | ✓                |
| pyfranc      |       0.932 |    0.811 | 0.859 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.938 |    1.000 | 0.968 |
| Tatoeba   | 300 |       0.943 |    0.997 | 0.969 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| UDHR-LID  |  61 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Swedish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Swedish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Swedish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Swedish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Swedish (and whether the model is exclusively tagged for Swedish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,115** text-generation models are explicitly tagged for Swedish (263 original uploads, 852 fine-tunes/quantisations/merges).
- **131** are tagged *only* for Swedish.
- Including tags inherited from base models: **2,348**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       17 | █                    |
|   2023 |       38 | ██                   |
|   2024 |      170 | ███████              |
|   2025 |      425 | ██████████████████   |
|   2026 |      465 | ████████████████████ |

### Largest models tagged for Swedish

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 856.0B       |                  143 |   2025 | —               |
| [mindlab-research/Macaron-V1-Coding-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Coding-Venti) | 753.3B       |                    4 |   2026 | —               |
| [batiai/GLM-5.2-GGUF](https://huggingface.co/batiai/GLM-5.2-GGUF)                                           | 753.3B       |                    4 |   2026 | zai-org/GLM-5.2 |
| [Kronumos/Kronumos-Aion](https://huggingface.co/Kronumos/Kronumos-Aion)                                     | 684.5B       |                    2 |   2026 | —               |

### Largest models tagged *only* for Swedish

| model                                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [banyaaiofficial/Qwen3.5-122B-A10B-Tuned-v10](https://huggingface.co/banyaaiofficial/Qwen3.5-122B-A10B-Tuned-v10)                     | 122.0B       |                    1 |   2026 | Qwen/Qwen3.5-122B-A10B          |
| [AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-BF16](https://huggingface.co/AEON-7/Ornith-1.0-35B-AEON-Ultimate-Uncensored-BF16)     | 35.1B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B        |
| [ansulev/Ornith-1.0-35B-AEON-Uncensored](https://huggingface.co/ansulev/Ornith-1.0-35B-AEON-Uncensored)                               | 35.1B        |                    1 |   2026 | deepreinforce-ai/Ornith-1.0-35B |
| [nanoswe/qwen-3.6-35b-a3b-teacher](https://huggingface.co/nanoswe/qwen-3.6-35b-a3b-teacher)                                           | 35.1B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [davidanugraha/Qwen3.5-35B-A3B-SWE-Smith-LoRA-Adapters](https://huggingface.co/davidanugraha/Qwen3.5-35B-A3B-SWE-Smith-LoRA-Adapters) | 35.0B        |                    1 |   2026 | Qwen/Qwen3.5-35B-A3B            |

_105 tagged models have unknown parameter counts and are not ranked by size._

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

**25** benchmark datasets in the survey include Swedish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 4 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">4 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 760            | Corpus-extracted + automatic manipulation        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 59             | Treebank-based (automatic)                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 201            | Treebank-based (automatic, UD + UniMorph)        |
| 1. Linguistic knowledge                | BLiMP                          | [Swe-BLiMP](https://github.com/itsup/swe_blimp)                                                     | 2,500          | Semi-automatic (hand-written seeds + generation) |
| 2. Pragmatics, discourse & coreference | WSC                            | [SweWinograd 2.0 (SuperLim)](https://researchdata.se/en/catalogue/dataset/doi-10-23695-h7rn-az19)   | 140            | Human translation / adaptation (loose)           |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,122          | Machine translation (GPT-3.5-turbo)              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                         |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)   |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 11,452         | Native (crowdsourced Tatoeba sentence pairs)     |

### Standard machine translation test sets

Swedish has been part of the WMT translation task in **1** year (2025).

| Test set                                                                  | Direction(s)                      | Size                               | Human reference             |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------------------|:----------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Latn)             | ✅                          |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)             | ✅                          |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-sv_SE) | en → sv_SE                        | 998 segments                       | ✅                          |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | English → Swedish                 | 87 documents (36,770 source words) | no (automatic metrics only) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Swedish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Swedish? Does it make sense to train one?
  - ~93.25 GB English-equivalent text ≈ 23.31B tokens, enough for a compute-optimal model of ~1.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Swedish-only model is 122.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 321 of ~18,498 papers (1.74%) (rank 22 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Swedish

Here are up to ten papers published in 2026 that mention Swedish. None of the 321 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                       | paper                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Apertus: Democratizing Open and Compliant LLMs for Global Language Environments                                                             | [2026.acl-long.2172](https://aclanthology.org/2026.acl-long.2172/)           |
| Adaptive CAT-embedded MT for low-memory, low-compute end-user devices                                                                       | [2026.eamt-2.14](https://aclanthology.org/2026.eamt-2.14/)                   |
| Reading the News: Adapting Large Language Models to Swedish Journalism Through Continued Pre-Training                                       | [2026.emnlp-industry.255](https://aclanthology.org/2026.emnlp-industry.255/) |
| IREKIER: An Easy Read Corpus for Basque and Spanish                                                                                         | [2026.lrec-1.128](https://aclanthology.org/2026.lrec-1.128/)                 |
| Evaluating Embedding Models on Danish Historical Newspapers: A Corpus and Benchmark Resource                                                | [2026.lrec-1.287](https://aclanthology.org/2026.lrec-1.287/)                 |
| Universal NER v2: Towards a Massively Multilingual Named Entity Recognition Benchmark                                                       | [2026.lrec-1.525](https://aclanthology.org/2026.lrec-1.525/)                 |
| APODICTUS: Automatic Processing of DICTionary Update candidateS                                                                             | [2026.lrec-1.924](https://aclanthology.org/2026.lrec-1.924/)                 |
| BEReshiT: an Ancient Hebrew Model based on DictaBERT                                                                                        | [2026.lt4hala-1.7](https://aclanthology.org/2026.lt4hala-1.7/)               |
| Exploring the syntactic parsing of learner texts in Modern Greek: Variety trumps size, genre trumps grammaticality                          | [2026.nlp4call-1.11](https://aclanthology.org/2026.nlp4call-1.11/)           |
| Supercharging Agenda Setting Research: The ParlaCAP Dataset of 28 European Parliaments and a Scalable Multilingual LLM-Based Classification | [2026.politicalnlp-1.11](https://aclanthology.org/2026.politicalnlp-1.11/)   |

{% endraw %}
