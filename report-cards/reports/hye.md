---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hye.html
---
{% raw %}
# So you want to work on Armenian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hye`

**Language family:** **Indo-European** › Classical Indo-European › Armenic › Eastern-Western Armenian ([Glottolog](https://glottolog.org/resource/languoid/id/nucl1235))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Armn`

**Speakers:** about 5.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Armenia

**Status:** Official language


## What does Armenian look and sound like?

**Written:** Omniglot has [a page on Armenian](https://www.omniglot.com/writing/armenian.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hye/) has 4 videos of Armenian speakers. Watch [Irina speaking Armenian](https://wikitongues.org/videos/irina_20190820_hye/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 333,079 articles in hy.wikipedia; 618 active users. This is ~1/23 of English data and ranks 32 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 694,076 pages per crawl on average, which is 0.0322% of the crawl (2026). This is ~1/1,284 of English data and ranks 43 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 2.45 GB (hye_Armn 2.45 GB), equivalent to ≈1.42 GB of English after byte-premium scaling; 8.95 GB removed by filtering. This is ~1/21,847 of English data and ranks 61 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 1.93 GB (hye_Armn 1.93 GB) (rank 61 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 8,050 sentences / 149,683 tokens in total: [UD_Armenian-ArmTDP](https://github.com/UniversalDependencies/UD_Armenian-ArmTDP) (5,527 sentences), [UD_Armenian-BSUT](https://github.com/UniversalDependencies/UD_Armenian-BSUT) (2,523 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 6,989 lemmas, 333,870 inflected forms ([unimorph/hye](https://github.com/unimorph/hye))                                                                                                                                                                                                                                                |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                         |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=71), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.998 (P 0.999, R 0.997, FPR 1.28e-05) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.998).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.996 | 0.998 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.996 | 0.997 | 0.000 | ✓                |
| GlotLID      |       0.999 |    0.994 | 0.996 | 0.000 | ✓                |
| cld2         |       0.996 |    0.996 | 0.996 | 0.000 | ✓                |
| cld3         |       1.000 |    0.987 | 0.994 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.985 | 0.992 | 0.000 | ✗                |
| commonlingua |       0.994 |    0.971 | 0.982 | 0.000 | ✓                |
| funlangid    |       0.999 |    0.923 | 0.955 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.993 |    0.983 | 0.988 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  71 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Armenian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Armenian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Armenian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Armenian has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Armenian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Armenian (and whether the model is exclusively tagged for Armenian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **360** text-generation models are explicitly tagged for Armenian (100 original uploads, 260 fine-tunes/quantisations/merges).
- **156** are tagged *only* for Armenian.
- Including tags inherited from base models: **420**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        9 | █                    |
|   2023 |       11 | █                    |
|   2024 |       16 | █                    |
|   2025 |       81 | ███████              |
|   2026 |      243 | ████████████████████ |

### Largest models tagged for Armenian

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [Vaibhavhome30/Hy4-preview-FP8](https://huggingface.co/Vaibhavhome30/Hy4-preview-FP8) | 803.5B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview-FP8](https://huggingface.co/tencent/Hy4-preview-FP8)             | 803.5B       |                    1 |   2026 | —               |
| [Godwind/Hy4-preview](https://huggingface.co/Godwind/Hy4-preview)                     | 780.0B       |                    1 |   2026 | —               |

### Largest models tagged *only* for Armenian

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [Vaibhavhome30/Hy4-preview-FP8](https://huggingface.co/Vaibhavhome30/Hy4-preview-FP8) | 803.5B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview-FP8](https://huggingface.co/tencent/Hy4-preview-FP8)             | 803.5B       |                    1 |   2026 | —               |
| [Godwind/Hy4-preview](https://huggingface.co/Godwind/Hy4-preview)                     | 780.0B       |                    1 |   2026 | —               |
| [tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview)                     | 780.0B       |                    1 |   2026 | —               |
| [thetechoddbug/Hy4-preview](https://huggingface.co/thetechoddbug/Hy4-preview)         | 780.0B       |                    1 |   2026 | —               |

_56 tagged models have unknown parameter counts and are not ranked by size._

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

**14** benchmark datasets in the survey include Armenian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                                     |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 42             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 1,415          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse         | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 3. Commonsense reasoning               | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 8,632          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| Machine translation                    |                               | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    |                               | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,121          | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Armenian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Armenian? Does it make sense to train one?
  - ~1.42 GB English-equivalent text ≈ 0.35B tokens, enough for a compute-optimal model of ~17.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Armenian-only model is 803.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 75 of ~18,498 papers (0.41%) (rank 69 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Armenian

Here are up to ten papers published in 2026 that mention Armenian. None of the 75 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                        | paper                                                                          | mentioned in   |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| Automatic translation in public services: A survey of the Finnish public sector                                              | [2026.eamt-1.45](https://aclanthology.org/2026.eamt-1.45/)                     | body only      |
| Script Choice in LLMs: Evidence for Late-Layer Commitment                                                                    | [2026.findings-emnlp.1173](https://aclanthology.org/2026.findings-emnlp.1173/) | body only      |
| Searching for a Unified Approach to Morpheme Segmentation: Benchmarking Supervised and LLM Architectures Across 20 Languages | [2026.findings-emnlp.715](https://aclanthology.org/2026.findings-emnlp.715/)   | body only      |
| From Corpus to Concept Scheme: Developing a SKOS Vocabulary for Armenian Epigraphic Heritage                                 | [2026.latechclfl-1.1](https://aclanthology.org/2026.latechclfl-1.1/)           | body only      |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                 | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)               | body only      |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                       | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)           | body only      |
| Population-Grounded Evaluation of Multilingual LLM Alignment with European Societal Values                                   | [2026.pandora-1.6](https://aclanthology.org/2026.pandora-1.6/)                 | body only      |
| Frequency modulates structural choice in Turkish suspended affixation: a latent-process account                              | [2026.scil-main.32](https://aclanthology.org/2026.scil-main.32/)               | body only      |
| Towards Universal Dependencies for L2 Learners of Modern Greek: Annotation and Challenges                                    | [2026.udw-1.8](https://aclanthology.org/2026.udw-1.8/)                         | body only      |
| Yandex at WMT26: Translation Adaptation at 235B and Hard-Label Distillation to 8B                                            | [2026.wmt-main.77](https://aclanthology.org/2026.wmt-main.77/)                 | body only      |

{% endraw %}
