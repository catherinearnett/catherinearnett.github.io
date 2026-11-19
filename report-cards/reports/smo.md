---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/smo.html
---
{% raw %}
# So you want to work on Samoan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `smo`

**Language family:** **Austronesian** › Malayo-Polynesian › Eastern Malayo-Polynesian › … › Samoan-Tokelauan ([Glottolog](https://glottolog.org/resource/languoid/id/samo1305))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 253,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Samoa, United States

**Status:** Official language; Regional official language


## What does Samoan look and sound like?

**Written (Samoan)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/samoan.htm):

> O tagata soifua uma ua saoloto lo latou fananau mai, ma e tutusa o
> latou tulaga aloaia faapea a latou aia tatau. Ua faaeeina atu i a latou
> le mafaufau lelei ma le loto fuatiaifo ma e tatau ona faatino le agaga
> faauso i le va o le tasi i le isi.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/smo/) has 3 videos of Samoan speakers. Watch [Sooalo speaking Samoan](https://wikitongues.org/videos/sooalo_20161025_smo/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,208 articles in sm.wikipedia; 14 active users. This is ~1/6,247 of English data and ranks 150 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 16,562 pages per crawl on average, which is 0.0008% of the crawl (2026). This is ~1/53,828 of English data and ranks 94 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 0.16 GB (smo_Latn 0.16 GB), equivalent to ≈0.14 GB of English after byte-premium scaling; 0.17 GB removed by filtering. This is ~1/329,622 of English data and ranks 101 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.41 GB (smo_Latn 0.41 GB) (rank 98 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=78), UDHR-LID (n=63), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.971 (P 0.982, R 0.961, FPR 4.10e-05) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.900).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.982 |    0.961 | 0.971 | 0.000 | ✓                |
| pyfranc      |       0.887 |    0.917 | 0.900 | 0.001 | ✓                |
| funlangid    |       0.885 |    0.912 | 0.898 | 0.001 | ✓                |
| cld2         |       0.898 |    0.892 | 0.893 | 0.000 | ✓                |
| commonlingua |       0.820 |    0.849 | 0.832 | 0.001 | ✓                |
| cld3         |       0.703 |    0.940 | 0.799 | 0.004 | ✓                |
| fasttext     |       0.690 |    0.959 | 0.794 | 0.003 | ✓                |
| OpenLID-v2   |       0.626 |    0.982 | 0.748 | 0.005 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  78 |       0.919 |    0.872 | 0.895 |
| Wikipedia | 300 |       0.993 |    0.947 | 0.969 |
| NTREX     | 300 |       1.000 |    0.987 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  63 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Samoan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Samoan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Samoan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Samoan has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Samoan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Samoan (and whether the model is exclusively tagged for Samoan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **111** text-generation models are explicitly tagged for Samoan (24 original uploads, 87 fine-tunes/quantisations/merges).
- **29** are tagged *only* for Samoan.
- Including tags inherited from base models: **141**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | ██                   |
|   2023 |        5 | █                    |
|   2024 |        7 | ██                   |
|   2025 |        9 | ██                   |
|   2026 |       83 | ████████████████████ |

### Largest models tagged for Samoan

| model                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                     | 1.9T         |                  143 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                         | 856.0B       |                  143 |   2025 | —                                  |
| [Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8](https://huggingface.co/Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8) | 159.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731 |
| [JasonW2025/Hy3-295B-A21B-R2fc](https://huggingface.co/JasonW2025/Hy3-295B-A21B-R2fc)                                                         | 94.7B        |                    2 |   2026 | tencent/Hy3-295B-A21B              |
| [s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF)                                       | 35.5B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B           |

### Largest models tagged *only* for Samoan

| model                                                                                                                                               | parameters   |   # languages tagged |   year | derivative of                                           |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------------------|
| [Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8](https://huggingface.co/Jon-Nielsen/DeepSeek-V4-Flash-0731-Abliterated-MXFP4-INT8)       | 159.2B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4-Flash-0731                      |
| [s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF](https://huggingface.co/s-batman/Ornith-1.0-35B-NVFP4-MTP-GGUF)                                             | 35.5B        |                    1 |   2026 | ornith-ai/Ornith-1.0-35B                                |
| [jajmangold/Ornith-1.0-35B-fni8](https://huggingface.co/jajmangold/Ornith-1.0-35B-fni8)                                                             | 35.0B        |                    1 |   2026 | deepreinforce-ai/Ornith-1.0-35B                         |
| [jajmangold/Qwen3-30B-A3B-fni8](https://huggingface.co/jajmangold/Qwen3-30B-A3B-fni8)                                                               | 30.0B        |                    1 |   2026 | Qwen/Qwen3-30B-A3B-Base                                 |
| [nuiun/Ternary-Bonsai-2-27B-Heretic-NInfer-RTX3080-16G-Bundle](https://huggingface.co/nuiun/Ternary-Bonsai-2-27B-Heretic-NInfer-RTX3080-16G-Bundle) | 27.0B        |                    1 |   2026 | emiltsoi/Ternary-Bonsai-2-27B-Uncensored-Heretic-NInfer |

_15 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Samoan.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          1,278 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             78 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)              | Size                   | Human reference   |
|:------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Samoan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Samoan? Does it make sense to train one?
  - ~0.35 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Samoan-only model is 159.2B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,498 papers (0.05%) (rank 149 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Samoan

Here are up to ten papers published in 2026 that mention Samoan. None of the 10 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Toward a Coarse-Labeled Spoken Language Identification Dataset for Central Alaskan Yup’ik and Samoan from US Broadcast Archives | [2026.americasnlp-6.18](https://aclanthology.org/2026.americasnlp-6.18/)       |
| Low-Resource Methods for Hawaiian Machine Translation                                                                           | [2026.computel-1.11](https://aclanthology.org/2026.computel-1.11/)             |
| Uncovering Currency Bias and Syntax Gap in Text Embedding Models                                                                | [2026.findings-acl.2118](https://aclanthology.org/2026.findings-acl.2118/)     |
| TIPA: Typologically Informed Parameter Aggregation                                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                      | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                         | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                  | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| The Linguist’s Lie Detector: Linguistic Knowledge in Large Language Models                                                      | [2026.nslp-1.23](https://aclanthology.org/2026.nslp-1.23/)                     |
| Algebraic Classification of Reduplicative Processes                                                                             | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               |

{% endraw %}
