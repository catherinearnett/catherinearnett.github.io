---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gaz.html
---
{% raw %}
# So you want to work on Oromo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gaz` · macrolanguage `orm`

**Language family:** **Afro-Asiatic** › Cushitic › East Cushitic › … › Nuclear Oromo ([Glottolog](https://glottolog.org/resource/languoid/id/west2721))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 38.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `orm`, so includes other varieties

**Official / recognised in:** Ethiopia

**Status:** Official language


## What does Oromo look and sound like?

**Written:** Omniglot has [a page on Oromo](https://www.omniglot.com/writing/oromo.htm) but no sample text.

**Spoken:** no Wikitongues video of Oromo yet ([its Wikitongues page](https://wikitongues.org/languages/gaz/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,970 articles in om.wikipedia; 28 active users. ⚠️ NB: recorded under the macrolanguage code `orm`, which can include other varieties of Oromo.                                                                                                 |
| Common Crawl           | 15,021 pages per crawl on average, which is 0.0007% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `orm`, which can include other varieties of Oromo.                                                                         |
| FineWeb                | 58.6 MB (gaz_Latn 60.0 MB), equivalent to ≈44.0 MB of English after byte-premium scaling; 0.17 GB removed by filtering. This is ~1/911,458 of English data and ranks 113 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.11 GB (gaz_Latn 0.11 GB) (rank 118 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                       |
| UniMorph               | 92 lemmas, 2,046 inflected forms ([unimorph/orm](https://github.com/unimorph/orm)) ⚠️ Listed under the macrolanguage code `orm`, so this may cover other varieties as well as Oromo. |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                       |
| Wordnets               | **None found**                                                                                                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                                                                                                 |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                                                                                                             |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                                                                                              |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                                                                                    |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                                                                                                                     |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_om) en → om: size not listed; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_om) en → om: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_om) en → om: size not listed ⚠️ Listed under the macrolanguage code `orm`, so this may cover other varieties as well as Oromo. |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=10), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** cld2 — F1 0.944 (P 0.938, R 0.952, FPR 1.26e-04) averaged over 7 dataset(s). Runner-up: GlotLID (F1 0.924).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| cld2         |       0.938 |    0.952 | 0.944 | 0.000 | ✓                |
| GlotLID      |       0.913 |    0.944 | 0.924 | 0.000 | ✓                |
| pyfranc      |       0.810 |    0.880 | 0.829 | 0.001 | ✓                |
| fasttext     |       0.761 |    0.973 | 0.813 | 0.003 | ✓                |
| funlangid    |       0.872 |    0.719 | 0.780 | 0.000 | ✓                |
| OpenLID-v2   |       0.703 |    0.991 | 0.770 | 0.005 | ✓                |
| commonlingua |       0.717 |    0.851 | 0.745 | 0.003 | ✓                |
| py3langid    |       0.651 |    0.990 | 0.720 | 0.009 | ✓                |
| AfroLID      |       0.242 |    0.937 | 0.360 | 0.155 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (cld2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  10 |       0.667 |    0.800 | 0.727 |
| Wikipedia | 300 |       1.000 |    0.903 | 0.949 |
| UDHR-LID  |  60 |       0.909 |    1.000 | 0.952 |
| CommonLID | 300 |       1.000 |    0.973 | 0.986 |
| NTREX     | 300 |       0.993 |    0.990 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| SmolSent  | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Oromo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Oromo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Oromo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Oromo has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/gaz/) video of Oromo yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Oromo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Oromo (and whether the model is exclusively tagged for Oromo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **84** text-generation models are explicitly tagged for Oromo (42 original uploads, 42 fine-tunes/quantisations/merges).
- **8** are tagged *only* for Oromo.
- Including tags inherited from base models: **129**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | █                    |
|   2024 |       18 | █████████            |
|   2025 |       22 | ██████████           |
|   2026 |       42 | ████████████████████ |

### Largest models tagged for Oromo

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of         |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —                     |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —                     |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B) | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B      |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)       | 14.8B        |                   21 |   2026 | Qwen/Qwen3-14B-Base   |
| [McGill-NLP/AfriqueGemma-12B](https://huggingface.co/McGill-NLP/AfriqueGemma-12B)     | 12.2B        |                   21 |   2026 | google/gemma-3-12b-pt |

### Models tagged *only* for Oromo

None of these has a known parameter count, so here is a random sample of 5 of the 8 model families:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/gaz_latn_10mb](https://huggingface.co/goldfish-models/gaz_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/gaz_latn_5mb](https://huggingface.co/goldfish-models/gaz_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/gaz_latn_full](https://huggingface.co/goldfish-models/gaz_latn_full) |                    1 |   2024 | —               |
| [goldfish-models/orm_latn_5mb](https://huggingface.co/goldfish-models/orm_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/orm_latn_full](https://huggingface.co/goldfish-models/orm_latn_full) |                    1 |   2024 | —               |

_32 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Oromo.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                |   # test items | construction                                             |
|:------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------|---------------:|:---------------------------------------------------------|
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                          |            900 | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)             |          4,458 | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)            |            500 | Human translation (professional)                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles) |            100 | Native (community-written, peer-verified)                |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                              |          1,997 | Human translation (professional, from English)           |
| Machine translation           |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                |          2,100 | Human translation (professional/volunteer, from English) |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_om) (training data)   | en → om                           | size not listed        | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_om) (training data)   | en → om                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_om) (training data) | en → om                           | size not listed        | ✅                |

_⚠️ Listed under the macrolanguage code `orm`, so this may cover other varieties as well as Oromo._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Oromo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Oromo? Does it make sense to train one?
  - ~80.7 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~1.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 39 of ~18,498 papers (0.21%) (rank 103 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: West Central Oromo | Oromo

Here are up to ten papers published in 2026 that mention Oromo. None of the 39 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                        | paper                                                                        | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|:---------------|
| Sample-Size Scaling of the African Languages NLI Evaluation                                                  | [2026.africanlp-main.22](https://aclanthology.org/2026.africanlp-main.22/)   | body only      |
| Large-scale Multilingual News Image Captioning with LLMs                                                     | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)       | body only      |
| AfrIFact: Cultural Information Retrieval, Evidence Extraction And Fact Checking for African Languages        | [2026.emnlp-main.133](https://aclanthology.org/2026.emnlp-main.133/)         | body only      |
| Active Learning with Non-Uniform Costs for African Natural Language Processing                               | [2026.findings-eacl.349](https://aclanthology.org/2026.findings-eacl.349/)   | body only      |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) | body only      |
| Yeswa-Stories: A Three-Way Parallel Dataset of Female African Figures in Low-Web Data Languages              | [2026.gitt-1.7](https://aclanthology.org/2026.gitt-1.7/)                     | body only      |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                   | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)               | body only      |
| Mining Naturally Romanized Seed Corpora without Romanizations                                                | [2026.lrec-1.234](https://aclanthology.org/2026.lrec-1.234/)                 | body only      |
| Enhancing Multi-Label Emotion Analysis and Corresponding Intensities for Ethiopian Languages                 | [2026.lrec-1.639](https://aclanthology.org/2026.lrec-1.639/)                 | body only      |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                             | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)                 | body only      |

{% endraw %}
