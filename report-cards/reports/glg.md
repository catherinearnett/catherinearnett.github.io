---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/glg.html
---
{% raw %}
# So you want to work on Galician?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `glg`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Galician Romance ([Glottolog](https://glottolog.org/resource/languoid/id/gali1258))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Latn`

**Speakers:** about 3.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Spain

**Status:** Regional official language


## What does Galician look and sound like?

**Written (Galician)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/galician.htm):

> Tódolos seres humanos nacen libres e iguais en dignidade e
> dereitos e, dotados como están de razón e conciencia,
> díbense comportar fraternalmente uns cos outros.
> A recording of this text by Omar Carrillo

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_gl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/glg/) has 3 videos of Galician speakers. Watch [Artur speaking Galician](https://wikitongues.org/videos/artur_20150101_glg/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 248,056 articles in gl.wikipedia; 441 active users. This is ~1/30 of English data and ranks 38 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 719,220 pages per crawl on average, which is 0.0333% of the crawl (2026). This is ~1/1,240 of English data and ranks 42 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                           |
| FineWeb                | 3.14 GB (glg_Latn 3.14 GB), equivalent to ≈2.97 GB of English after byte-premium scaling; 47.57 GB removed by filtering. This is ~1/17,004 of English data and ranks 59 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 2.02 GB (glg_Latn 2.02 GB) (rank 60 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                           |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 5,993 sentences / 171,322 tokens in total: [UD_Galician-CTG](https://github.com/UniversalDependencies/UD_Galician-CTG) (3,993 sentences), [UD_Galician-PUD](https://github.com/UniversalDependencies/UD_Galician-PUD) (1,000 sentences), [UD_Galician-TreeGal](https://github.com/UniversalDependencies/UD_Galician-TreeGal) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                        |
| Wordnets               | [Multilingual Central Repository (Galician)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-gl-1.4.tar.xz): 19,312 synsets, 23,410 words, 27,138 senses; licence: https://creativecommons.org/licenses/by/3.0/.                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.957 (P 0.993, R 0.926, FPR 4.36e-05) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.947).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.993 |    0.926 | 0.957 | 0.000 | ✓                |
| OpenLID-v2   |       0.928 |    0.967 | 0.947 | 0.001 | ✓                |
| fasttext     |       0.846 |    0.969 | 0.896 | 0.001 | ✓                |
| cld2         |       0.890 |    0.874 | 0.877 | 0.001 | ✓                |
| py3langid    |       0.783 |    0.969 | 0.859 | 0.003 | ✓                |
| commonlingua |       0.836 |    0.852 | 0.843 | 0.002 | ✓                |
| pyfranc      |       0.752 |    0.778 | 0.761 | 0.003 | ✓                |
| cld3         |       0.626 |    0.931 | 0.737 | 0.007 | ✓                |
| funlangid    |       0.761 |    0.703 | 0.721 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.979 |    0.770 | 0.862 |
| NTREX     | 300 |       1.000 |    0.940 | 0.969 |
| Wikipedia | 300 |       0.986 |    0.957 | 0.971 |
| UDHR-LID  |  58 |       1.000 |    0.966 | 0.982 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Galician to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Galician *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Galician and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Galician has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Galician?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Galician (and whether the model is exclusively tagged for Galician or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **300** text-generation models are explicitly tagged for Galician (78 original uploads, 222 fine-tunes/quantisations/merges).
- **39** are tagged *only* for Galician.
- Including tags inherited from base models: **609**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |       13 | ██                   |
|   2024 |       54 | ████████             |
|   2025 |       91 | █████████████        |
|   2026 |      135 | ████████████████████ |

### Largest models tagged for Galician

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                         | 1.9T         |                  143 |   2025 | —                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                             | 856.0B       |                  143 |   2025 | —                             |
| [itzune/Latxa-Llama-3.1-70B-Instruct-v2-GGUF](https://huggingface.co/itzune/Latxa-Llama-3.1-70B-Instruct-v2-GGUF) | 70.6B        |                    6 |   2026 | meta-llama/Llama-3.1-70B      |
| [montevive/ALIA-40b-fc-2605-NVFP4-GGUF](https://huggingface.co/montevive/ALIA-40b-fc-2605-NVFP4-GGUF)             | 40.4B        |                    5 |   2026 | BSC-LT/ALIA-40b               |
| [alamios/ALIA-40b-instruct-2512-Q4_K_M-GGUF](https://huggingface.co/alamios/ALIA-40b-instruct-2512-Q4_K_M-GGUF)   | 40.4B        |                    5 |   2026 | BSC-LT/ALIA-40b-instruct-2512 |

### Largest models tagged *only* for Galician

| model                                                                                         | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [HiTZ/gl_Qwen3-14B-Base](https://huggingface.co/HiTZ/gl_Qwen3-14B-Base)                       | 14.8B        |                    1 |   2025 | Qwen/Qwen3-14B-Base     |
| [HiTZ/gl_Qwen3-8B-Base](https://huggingface.co/HiTZ/gl_Qwen3-8B-Base)                         | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base      |
| [HiTZ/gl_Llama-3.1-8B](https://huggingface.co/HiTZ/gl_Llama-3.1-8B)                           | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |
| [irlab-udc/cabuxa-7b](https://huggingface.co/irlab-udc/cabuxa-7b)                             | 7.0B         |                    1 |   2023 | huggyllama/llama-7b     |
| [alphaedge-ai/Qwen3.5-4B-glg-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-glg-32768) | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |

_48 tagged models have unknown parameter counts and are not ranked by size._

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

**14** benchmark datasets in the survey include Galician.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                    | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 753            | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms  | [SemEval-2022 Task 2 (idiomaticity)](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity) | 776            | Native                                         |
| 3. Commonsense reasoning               | COPA                          | [Owos/xcopa](https://huggingface.co/datasets/Owos/xcopa)                                                   | 500            | Machine translation (Google)                   |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning               | StoryCloze                    | [XStoryCloze_gl](https://huggingface.co/datasets/proxectonos/xstorycloze_gl)                               | 1,511          | Translation (method not checked)               |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele_gl](https://huggingface.co/datasets/proxectonos/belebele_gl)                                     | 900            | Translation (method not checked)               |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [OpenBookQA_gl](https://huggingface.co/datasets/proxectonos/openbookqa_gl)                                 | —              | Translation                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [TruthfulQA_gl](https://huggingface.co/datasets/proxectonos/truthfulqa_gl)                                 | —              | Translation                                    |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 1,019          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Galician datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Galician? Does it make sense to train one?
  - ~2.97 GB English-equivalent text ≈ 0.74B tokens, enough for a compute-optimal model of ~37.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Galician-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 101 of ~18,498 papers (0.55%) (rank 59 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Galician

Here are up to ten papers published in 2026 that mention Galician. None of the 101 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Apertus: Democratizing Open and Compliant LLMs for Global Language Environments                                       | [2026.acl-long.2172](https://aclanthology.org/2026.acl-long.2172/)             |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)         |
| Why are all LLMs Obsessed with Japanese Culture? On the Hidden Cultural and Regional Biases of LLMs                   | [2026.findings-emnlp.1307](https://aclanthology.org/2026.findings-emnlp.1307/) |
| ACAData: Parallel Dataset of Academic Data for Machine Translation                                                    | [2026.lrec-1.671](https://aclanthology.org/2026.lrec-1.671/)                   |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation                  | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)                   |
| UniBO at MWE-2026 PARSEME 2.0 Subtask 2: A Cross-lingual Approach to Multiword Expression Paraphrasing                | [2026.mwe-1.28](https://aclanthology.org/2026.mwe-1.28/)                       |
| ITUNLP at MWE-2026 AdMIRe 2: A Zero-Shot LLM Pipeline for Multimodal Idiom Understanding and Ranking                  | [2026.mwe-1.30](https://aclanthology.org/2026.mwe-1.30/)                       |
| The PROPOR Ecosystem: Structure, Roles, and Evolution of Portuguese-Language NLP                                      | [2026.propor-1.34](https://aclanthology.org/2026.propor-1.34/)                 |
| SpeechLM for Automatic Speech Recognition in Low-resource Languages                                                   | [2026.speakable-1.14](https://aclanthology.org/2026.speakable-1.14/)           |
| Syntax is the Key to Semantics: Combining Universal Dependencies and Abstract Meaning Representation                  | [2026.udw-1.27](https://aclanthology.org/2026.udw-1.27/)                       |

{% endraw %}
