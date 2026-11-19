---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ces.html
---
{% raw %}
# So you want to work on Czech?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ces`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Czech-Slovak ([Glottolog](https://glottolog.org/resource/languoid/id/czec1258))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 13.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Czech Republic

**Status:** Official language


## What does Czech look and sound like?

**Written (Czech)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/czech.htm):

> Všichni lidé se rodí svobodní a sobě rovní co do důstojnosti a práv. Jsou nadáni rozumem a svědomím a mají spolu jednat v duchu bratrství.
> A recording of this text by Vaclav Dekanovsky

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_cz.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ces/) has 6 videos of Czech speakers. Watch [Dr. Karel Oliva speaking Czech, English, Bulgarian, Italian, Standard German, Russian](https://wikitongues.org/videos/dr-kareloliva_20160330_ces-eng-bul-ita-deu-rus/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 601,212 articles in cs.wikipedia; 4,549 active users. This is ~1/13 of English data and ranks 26 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 24,730,182 pages per crawl on average, which is 1.1474% of the crawl (2026). This is ~1/36 of English data and ranks 12 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                               |
| FineWeb                | 109.98 GB (ces_Latn 109.98 GB), equivalent to ≈106.17 GB of English after byte-premium scaling; 161.70 GB removed by filtering. This is ~1/486 of English data and ranks 15 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 8.25 GB (ces_Latn 8.25 GB) (rank 24 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 7 treebanks, 255,426 sentences / 4,162,615 tokens in total: [UD_Czech-CAC](https://github.com/UniversalDependencies/UD_Czech-CAC) (24,709 sentences), [UD_Czech-CLTT](https://github.com/UniversalDependencies/UD_Czech-CLTT) (1,121 sentences), [UD_Czech-CzeSL](https://github.com/UniversalDependencies/UD_Czech-CzeSL) (1,642 sentences), [UD_Czech-FicTree](https://github.com/UniversalDependencies/UD_Czech-FicTree) (12,760 sentences), [UD_Czech-PDTC](https://github.com/UniversalDependencies/UD_Czech-PDTC) (213,897 sentences), [UD_Czech-PUD](https://github.com/UniversalDependencies/UD_Czech-PUD) (1,000 sentences), [UD_Czech-Poetry](https://github.com/UniversalDependencies/UD_Czech-Poetry) (297 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 5,125 lemmas, 134,527 inflected forms ([unimorph/ces](https://github.com/unimorph/ces))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Wordnets               | [BalkaNet](http://www.dblab.upatras.gr/balkanet/) (size not listed); [Czech WordNet](https://ufal-point.mff.cuni.cz/xmlui/handle/11858/00-097C-0000-0001-4880-3) (size not listed); licence: OLD VERSION: CC-BY-NC-SA.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                |
|:-----------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                    |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([ces1613](https://ebible.org/details.php?id=ces1613), Public Domain); New Testament ([cesnkb](https://ebible.org/details.php?id=cesnkb), by-nd 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                       |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                        |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.980, R 0.977, FPR 1.95e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.959).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.977 | 0.978 | 0.000 | ✓                |
| cld2         |       0.964 |    0.954 | 0.959 | 0.000 | ✓                |
| OpenLID-v2   |       0.881 |    0.967 | 0.916 | 0.001 | ✓                |
| py3langid    |       0.879 |    0.968 | 0.915 | 0.002 | ✓                |
| commonlingua |       0.912 |    0.879 | 0.895 | 0.001 | ✓                |
| fasttext     |       0.825 |    0.978 | 0.886 | 0.002 | ✓                |
| pyfranc      |       0.959 |    0.721 | 0.811 | 0.000 | ✓                |
| cld3         |       0.737 |    0.932 | 0.809 | 0.005 | ✓                |
| funlangid    |       0.791 |    0.633 | 0.699 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.898 |    0.970 | 0.933 |
| CommonLID | 300 |       0.990 |    0.943 | 0.966 |
| Wikipedia | 300 |       0.993 |    0.947 | 0.969 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Czech to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Czech *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Czech and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Czech?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Czech (and whether the model is exclusively tagged for Czech or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,262** text-generation models are explicitly tagged for Czech (300 original uploads, 962 fine-tunes/quantisations/merges).
- **78** are tagged *only* for Czech.
- Including tags inherited from base models: **2,339**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       12 | █                    |
|   2023 |       33 | █                    |
|   2024 |      212 | ███████              |
|   2025 |      423 | ███████████████      |
|   2026 |      582 | ████████████████████ |

### Largest models tagged for Czech

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 856.0B       |                  143 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                         | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                           | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16) | 123.6B       |                   20 |   2026 | —                                      |

### Largest models tagged *only* for Czech

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [OJBLCZ/Qwen3.8-27B-Czech-4bit](https://huggingface.co/OJBLCZ/Qwen3.8-27B-Czech-4bit)                         | 26.9B        |                    1 |   2026 | oriyonay/Qwen3.8-27B-bnb-4bit |
| [vishinvents/OpenEuroLLM-Czech-Ollama-GGUF](https://huggingface.co/vishinvents/OpenEuroLLM-Czech-Ollama-GGUF) | 12.2B        |                    1 |   2026 | —                             |
| [Neptune1722/CheXagent-nf4-quantized](https://huggingface.co/Neptune1722/CheXagent-nf4-quantized)             | 8.6B         |                    1 |   2024 | —                             |
| [StanfordAIMI/CheXagent-8b](https://huggingface.co/StanfordAIMI/CheXagent-8b)                                 | 8.4B         |                    1 |   2023 | —                             |
| [ssmits/Falcon2-8B-Czech](https://huggingface.co/ssmits/Falcon2-8B-Czech)                                     | 8.1B         |                    1 |   2024 | tiiuae/falcon-11B             |

_97 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Czech.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 5 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 5 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 6 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">3 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                   |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 1,213          | Treebank-based (automatic)                     |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 4,256          | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks        |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                                  | 2,600          | Machine translation (DeepL) + sample check     |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                                   | 6,261          | Machine translation (DeepL) + sample check     |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                              | —              | Machine translation (DeepL)                    |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | MT + community post-editing                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CUS-QA](https://huggingface.co/datasets/ufal/cus-qa)                                                             | 1,536          | Native (regional knowledge)                    |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                       |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 18,434         | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

Czech has been part of the WMT translation task in **20** years (2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024, 2025, 2026).

| Test set                                                                  | Direction(s)                                                                                | Size                                                                                                            | Human reference         |
|:--------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------|:------------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)                                                                   | 2,009 sentences (Latn)                                                                                          | ✅                      |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages)                                                           | 1,358 sentences (Latn)                                                                                          | ✅                      |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-cs_CZ) | en → cs_CZ                                                                                  | 998 segments                                                                                                    | ✅                      |
| [WMT07 general task](https://www.statmt.org/wmt07/shared-task.html)       | Czech → English; English → Czech                                                            | size not listed                                                                                                 | ✅                      |
| [WMT08 general task](https://www2.statmt.org/wmt08/)                      | Czech → English; English → Czech                                                            | 2,051 segments                                                                                                  | ✅                      |
| [WMT09 general task](https://www2.statmt.org/wmt09/)                      | Czech → English; English → Czech                                                            | 3,027 segments                                                                                                  | ✅                      |
| [WMT10 general task](https://www2.statmt.org/wmt10/)                      | Czech → English; English → Czech                                                            | 2,489 segments                                                                                                  | ✅                      |
| [WMT11 general task](https://www2.statmt.org/wmt11/)                      | Czech → English; English → Czech                                                            | 3,003 segments                                                                                                  | ✅                      |
| [WMT12 general task](https://www2.statmt.org/wmt12/)                      | Czech → English; English → Czech                                                            | 3,003 segments                                                                                                  | ✅                      |
| [WMT13 general task](https://www2.statmt.org/wmt13/)                      | Czech → English; English → Czech                                                            | 3,000 segments                                                                                                  | ✅                      |
| [WMT14 general task](https://www2.statmt.org/wmt14/)                      | Czech → English; English → Czech                                                            | 3,003 segments                                                                                                  | ✅                      |
| [WMT15 general task](https://www2.statmt.org/wmt15/)                      | Czech → English; English → Czech                                                            | 2,656 segments                                                                                                  | ✅                      |
| [WMT16 general task](https://www2.statmt.org/wmt16/)                      | Czech → English; English → Czech                                                            | 2,999 segments                                                                                                  | ✅                      |
| [WMT17 general task](https://www2.statmt.org/wmt17/)                      | Czech → English; English → Czech                                                            | 3,005 segments                                                                                                  | ✅                      |
| [WMT18 general task](https://www2.statmt.org/wmt18/)                      | Czech → English; English → Czech                                                            | 2,983 segments                                                                                                  | ✅                      |
| [WMT19 general task](https://www2.statmt.org/wmt19/)                      | Czech → German; German → Czech; English → Czech                                             | 1,997 segments                                                                                                  | ✅                      |
| [WMT20 general task](https://www2.statmt.org/wmt20/)                      | Czech → English; English → Czech                                                            | 664 segments / 1,418 segments                                                                                   | ✅                      |
| [WMT21 general task](https://www2.statmt.org/wmt21/)                      | Czech → English; English → Czech                                                            | 1,000 segments / 1,002 segments                                                                                 | ✅                      |
| [WMT22 general task](https://www2.statmt.org/wmt22/)                      | Czech → English; Czech → Ukrainian; English → Czech; Ukrainian → Czech                      | 1,448 segments / 1,930 segments / 2,037 segments / 2,812 segments                                               | ✅                      |
| [WMT23 general task](https://www2.statmt.org/wmt23/)                      | Czech → Ukrainian; English → Czech                                                          | 2,017 segments / 2,074 segments                                                                                 | ✅                      |
| [WMT24 general task](https://www2.statmt.org/wmt24/)                      | Czech → Ukrainian; English → Czech                                                          | 2,316 segments / 997 segments                                                                                   | ✅                      |
| [WMT25 general task](https://github.com/wmt-conference/wmt25-general-mt)  | Czech → German; Czech → Ukrainian; English → Czech                                          | 256 documents (43,796 source words) / 230 documents (36,136 source words) / 113 documents (46,067 source words) | ✅                      |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt)  | Czech → German; Czech → Ukrainian (no human reference); Czech → Vietnamese; English → Czech | 315 documents (41,529 source words) / 198 documents (28,523 source words)                                       | partly (see directions) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Czech datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Czech? Does it make sense to train one?
  - ~106.17 GB English-equivalent text ≈ 26.54B tokens, enough for a compute-optimal model of ~1.3B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Czech-only model is 26.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 455 of ~18,498 papers (2.46%) (rank 14 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Czech

Here are up to ten papers published in 2026 that mention Czech. None of the 455 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                            | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| IGenBench: Benchmarking the Reliability of Text-to-Infographic Generation                                                        | [2026.acl-long.1713](https://aclanthology.org/2026.acl-long.1713/)             |
| CorPipe at CRAC 2026: Empty Nodes and Cross-Lingual Transfer in Multilingual Coreference Resolution                              | [2026.codi-1.27](https://aclanthology.org/2026.codi-1.27/)                     |
| Generative Models Enhanced by Sequence Labelling and Aspect-Code Switching Improve Cross-lingual Aspect-Based Sentiment Analysis | [2026.emnlp-main.1531](https://aclanthology.org/2026.emnlp-main.1531/)         |
| Assessment of Generative Named Entity Recognition in the Era of Large Language Models                                            | [2026.findings-emnlp.1706](https://aclanthology.org/2026.findings-emnlp.1706/) |
| Large Language Models for Citation Function Classification                                                                       | [2026.lrec-1.191](https://aclanthology.org/2026.lrec-1.191/)                   |
| The MultiplEYE Text Corpus: Towards a Diverse and Ever-Expanding Multilingual Text Corpus                                        | [2026.lrec-1.534](https://aclanthology.org/2026.lrec-1.534/)                   |
| Proffiliadur: Welsh Language Text Profiling Toolkit                                                                              | [2026.lrec-1.88](https://aclanthology.org/2026.lrec-1.88/)                     |
| Fluency and Faithfulness in Human and Machine Literary Translation                                                               | [2026.nlp4dh-1.17](https://aclanthology.org/2026.nlp4dh-1.17/)                 |
| Overview of the SIGTURK 2026 Shared Task: Terminology-Aware Machine Translation for English–Turkish Scientific Texts             | [2026.sigturk-1.20](https://aclanthology.org/2026.sigturk-1.20/)               |
| CUNI-UFAL at WMT26 Multilingual Instruction Shared Task                                                                          | [2026.wmt-main.130](https://aclanthology.org/2026.wmt-main.130/)               |

{% endraw %}
