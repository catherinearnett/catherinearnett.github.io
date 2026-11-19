---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sin.html
---
{% raw %}
# So you want to work on Sinhala?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sin`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Sinhalaic ([Glottolog](https://glottolog.org/resource/languoid/id/sinh1246))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Sinh`

**Speakers:** about 14.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Sri Lanka

**Status:** Official and national language


## What does Sinhala look and sound like?

**Written:** Omniglot has [a page on Sinhala](https://www.omniglot.com/writing/sinhala.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/sin/) has 4 videos of Sinhala speakers. Watch [Shehan speaking Sinhala](https://wikitongues.org/videos/shehan_20200819_sin/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 25,833 articles in si.wikipedia; 130 active users. This is ~1/292 of English data and ranks 79 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 203,392 pages per crawl on average, which is 0.0094% of the crawl (2026). This is ~1/4,383 of English data and ranks 56 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 2.03 GB (sin_Sinh 2.03 GB), equivalent to ≈0.83 GB of English after byte-premium scaling; 1.53 GB removed by filtering. This is ~1/26,279 of English data and ranks 64 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 5.10 GB (sin_Sinh 5.10 GB) (rank 40 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 169 sentences / 1,549 tokens in total: [UD_Sinhala-Appuwa](https://github.com/UniversalDependencies/UD_Sinhala-Appuwa) (69 sentences), [UD_Sinhala-STB](https://github.com/UniversalDependencies/UD_Sinhala-STB) (100 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                          |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                          |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD; [Sinhala Wordnet](http://www.wordnet.lk/) (size not listed); licence: not available yet.                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                    |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                        |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                    |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                     |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Sinh script) — the same sentences in 200+ languages                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Sinh script) — paired with English                                                                                                                                                            |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_si) en → si: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_si) en → si: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=75), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.995 (P 0.999, R 0.990, FPR 6.41e-06) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.994).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.990 | 0.995 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.989 | 0.994 | 0.000 | ✓                |
| cld2         |       0.999 |    0.987 | 0.993 | 0.000 | ✓                |
| commonlingua |       0.999 |    0.983 | 0.991 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.983 | 0.991 | 0.000 | ✓                |
| cld3         |       0.998 |    0.975 | 0.986 | 0.000 | ✓                |
| fasttext     |       0.999 |    0.970 | 0.984 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.932 | 0.962 | 0.000 | ✗                |
| funlangid    |       0.999 |    0.869 | 0.917 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.950 | 0.973 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   |  75 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sinhala to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sinhala *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sinhala and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Sinhala has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Sinhala?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sinhala (and whether the model is exclusively tagged for Sinhala or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **200** text-generation models are explicitly tagged for Sinhala (56 original uploads, 144 fine-tunes/quantisations/merges).
- **86** are tagged *only* for Sinhala.
- Including tags inherited from base models: **226**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | ███                  |
|   2023 |       11 | ███                  |
|   2024 |       48 | ██████████████       |
|   2025 |       62 | ██████████████████   |
|   2026 |       69 | ████████████████████ |

### Largest models tagged for Sinhala

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of       |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   | 1.9T         |                  143 |   2025 | —                   |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       | 856.0B       |                  143 |   2025 | —                   |
| [dgsr2809/GraveTextAI](https://huggingface.co/dgsr2809/GraveTextAI)                                                         | 70.6B        |                   20 |   2025 | —                   |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base |
| [AIDSC/mt0-xxl](https://huggingface.co/AIDSC/mt0-xxl)                                                                       | 13.9B        |                   92 |   2024 | —                   |

### Largest models tagged *only* for Sinhala

| model                                                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [lm-spell/gemma-2-9b-it-ft-ssc](https://huggingface.co/lm-spell/gemma-2-9b-it-ft-ssc)                                                                                         | 9.0B         |                    1 |   2025 | google/gemma-2-9b                           |
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-si-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-si-madlad-mean-slerp0305-emb)             | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B                     |
| [Chamaka8/Serendip-LLM-CPT-SFT-v2](https://huggingface.co/Chamaka8/Serendip-LLM-CPT-SFT-v2)                                                                                   | 8.0B         |                    1 |   2026 | Chamaka8/serendib-llm-cpt-llama3-8b         |
| [lm-spell/llama-3.1-8b-it-ft-ssc](https://huggingface.co/lm-spell/llama-3.1-8b-it-ft-ssc)                                                                                     | 8.0B         |                    1 |   2025 | unsloth/meta-llama-3.1-8b-instruct-bnb-4bit |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-si-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-si-madlad-mean-slerp0305-emb-special) | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B                             |

_42 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Sinhala.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                                                 |   # test items | construction                                   |
|:------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) |            200 | Native                                         |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        |            206 | MT + human post-editing                        |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele) (2 varieties/pairs)                                       |          1,800 | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                                   |         14,042 | MT + community post-editing                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  |            100 | Native (community-written, peer-verified)      |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               |          1,997 | Human translation (professional, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    |             47 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Sinh) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Sinh) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_si) (training data)   | en → si                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_si) (training data) | en → si                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sinhala datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sinhala? Does it make sense to train one?
  - ~2.09 GB English-equivalent text ≈ 0.52B tokens, enough for a compute-optimal model of ~26.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sinhala-only model is 9.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 74 of ~18,498 papers (0.40%) (rank 70 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Sinhala

Here are up to ten papers published in 2026 that mention Sinhala. None of the 74 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                        | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Leveraging CoHere Multilingual Embeddings and Inverted Softmax Retrieval for Automatic Parallel Sentence Alignment in Low-Resource Languages | [2026.africanlp-main.4](https://aclanthology.org/2026.africanlp-main.4/)       |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models                        | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)         |
| XQ-MEval: A Dataset with Cross-lingual Parallel Quality for Benchmarking Translation Metrics                                                 | [2026.findings-acl.1846](https://aclanthology.org/2026.findings-acl.1846/)     |
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model                                       | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| Confident but Wrong: A Constrained Decoding Diagnostic for Low-Resource Automatic Post-Editing                                               | [2026.findings-emnlp.1079](https://aclanthology.org/2026.findings-emnlp.1079/) |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                                 | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)               |
| OasisSimp: An Open-source Asian-English Sentence Simplification Dataset                                                                      | [2026.lrec-1.483](https://aclanthology.org/2026.lrec-1.483/)                   |
| SiDiaC-v.2.0: Sinhala Diachronic Corpus Version 2.0                                                                                          | [2026.lrec-1.537](https://aclanthology.org/2026.lrec-1.537/)                   |
| Do LLMs Judge Distantly Supervised Named Entity Labels Well? Constructing the JudgeWEL Dataset                                               | [2026.lrec-1.612](https://aclanthology.org/2026.lrec-1.612/)                   |
| PlurVA-LLM-2026 Shared Task Track-2: PluriGuide—Principle Distillation and Identifier-Bound Demonstrations for Pluralistic Value Alignment   | [2026.plurvallm-1.7](https://aclanthology.org/2026.plurvallm-1.7/)             |

{% endraw %}
