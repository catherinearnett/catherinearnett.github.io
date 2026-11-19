---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kir.html
---
{% raw %}
# So you want to work on Kyrgyz?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kir`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › East Kipchak ([Glottolog](https://glottolog.org/resource/languoid/id/kirg1245))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 3.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Kyrgyzstan

**Status:** Official language


## What does Kyrgyz look and sound like?

**Written:** Omniglot has [a page on Kyrgyz](https://www.omniglot.com/writing/kirghiz.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kir/) has 2 videos of Kyrgyz speakers. Watch [Azim speaking Kyrgyz](https://wikitongues.org/videos/azim_20180512_kir/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 76,665 articles in ky.wikipedia; 276 active users. This is ~1/98 of English data and ranks 61 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 251,577 pages per crawl on average, which is 0.0117% of the crawl (2026). This is ~1/3,544 of English data and ranks 52 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 1.48 GB (kir_Cyrl 1.48 GB), equivalent to ≈0.75 GB of English after byte-premium scaling; 0.94 GB removed by filtering. This is ~1/36,039 of English data and ranks 66 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 2.59 GB (kir_Cyrl 2.59 GB) (rank 56 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                               |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 2,703 sentences / 25,342 tokens in total: [UD_Kyrgyz-KTMU](https://github.com/UniversalDependencies/UD_Kyrgyz-KTMU) (2,530 sentences), [UD_Kyrgyz-TueCL](https://github.com/UniversalDependencies/UD_Kyrgyz-TueCL) (173 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 98 lemmas, 5,544 inflected forms ([unimorph/kir](https://github.com/unimorph/kir))                                                                                                                                                                                                                                        |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                            |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.981, R 0.995, FPR 1.67e-04) averaged over 5 dataset(s). Runner-up: commonlingua (F1 0.854).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.981 |    0.995 | 0.987 | 0.000 | ✓                |
| commonlingua |       0.847 |    0.865 | 0.854 | 0.002 | ✓                |
| cld2         |       0.759 |    0.967 | 0.845 | 0.003 | ✓                |
| funlangid    |       0.784 |    0.814 | 0.798 | 0.003 | ✓                |
| pyfranc      |       0.646 |    0.871 | 0.715 | 0.009 | ✓                |
| fasttext     |       0.534 |    0.990 | 0.668 | 0.009 | ✓                |
| OpenLID-v2   |       0.427 |    0.995 | 0.549 | 0.017 | ✓                |
| py3langid    |       0.384 |    0.979 | 0.495 | 0.026 | ✓                |
| cld3         |       0.231 |    0.979 | 0.360 | 0.045 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.913 |    0.983 | 0.947 |
| Wikipedia | 300 |       0.990 |    0.990 | 0.990 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kyrgyz to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kyrgyz *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kyrgyz and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kyrgyz has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Kyrgyz?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kyrgyz (and whether the model is exclusively tagged for Kyrgyz or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **135** text-generation models are explicitly tagged for Kyrgyz (52 original uploads, 83 fine-tunes/quantisations/merges).
- **17** are tagged *only* for Kyrgyz.
- Including tags inherited from base models: **165**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ███                  |
|   2023 |        6 | ██                   |
|   2024 |       16 | █████                |
|   2025 |       62 | ████████████████████ |
|   2026 |       43 | ██████████████       |

### Largest models tagged for Kyrgyz

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                                                 | 13.9B        |                   92 |   2024 | —                    |
| [bigscience/mt0-xxl](https://huggingface.co/bigscience/mt0-xxl)                                                       | 13.9B        |                   92 |   2022 | —                    |

### Largest models tagged *only* for Kyrgyz

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-kir-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-kir-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-kir-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-kir-Q8_0-GGUF) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [metinovadilet/miti-2.3b-base-v1](https://huggingface.co/metinovadilet/miti-2.3b-base-v1)               | 2.3B         |                    1 |   2025 | —                             |
| [alphaedge-ai/gemma-3-1b-it-kir-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-kir-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [ZSuranbaev/orfo](https://huggingface.co/ZSuranbaev/orfo)                                               | 556.3M       |                    1 |   2026 | google/mt5-small              |

_35 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Kyrgyz.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 185            | Treebank-based (automatic, UD + UniMorph)      |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [winogrande_kg (KyrgyzLLM-Bench)](https://huggingface.co/collections/TTimur/kyrgyzllm-bench)        | —              | MT + post-editing                              |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)         |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 123            | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kyrgyz datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kyrgyz? Does it make sense to train one?
  - ~1.32 GB English-equivalent text ≈ 0.33B tokens, enough for a compute-optimal model of ~16.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kyrgyz-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,498 papers (0.23%) (rank 96 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Kyrgyz

Here are up to ten papers published in 2026 that mention Kyrgyz. None of the 43 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                  | paper                                                                  |
|:---------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Mitigating Catastrophic Forgetting in Target Language Adaptation of LLMs via Source-Shielded Updates                                   | [2026.acl-long.865](https://aclanthology.org/2026.acl-long.865/)       |
| Large-scale Multilingual News Image Captioning with LLMs                                                                               | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/) |
| Do LLMs Cross Alphabets? A Cross-Script Audit of LLMs Across Four Kazakh Latin Proposals                                               | [2026.emnlp-main.1479](https://aclanthology.org/2026.emnlp-main.1479/) |
| No One-Size-Fits-All: Building Systems For Translation to Bashkir, Kazakh, Kyrgyz, Tatar and Chuvash Using Synthetic And Original Data | [2026.loresmt-1.17](https://aclanthology.org/2026.loresmt-1.17/)       |
| Data-Centric Approach at the LoResMT 2026 Turkic Translation Challenge: Russian-Kyrgyz                                                 | [2026.loresmt-1.22](https://aclanthology.org/2026.loresmt-1.22/)       |
| LoResMT 2026 Shared Task System Description                                                                                            | [2026.loresmt-1.23](https://aclanthology.org/2026.loresmt-1.23/)       |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                             | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)           |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                                       | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)           |
| Omnivorous Agreement, like Uyghur Backness Harmony, is a Challenge for Tier-Based Strict Locality                                      | [2026.scil-main.13](https://aclanthology.org/2026.scil-main.13/)       |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                                                 | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)       |

{% endraw %}
