---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pes.html
---
{% raw %}
# So you want to work on Persian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pes` · macrolanguage `fas`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Farsic ([Glottolog](https://glottolog.org/resource/languoid/id/west2369))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Arab`

**Speakers:** about 89.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `fas`, so includes other varieties · 52.8 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q3513637#P1098), 2019)

**Official / recognised in:** Iran

**Status:** Official language


## What does Persian look and sound like?

**Written:** no Omniglot page found for Persian.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/pes/) has 6 videos of Persian speakers. Watch [Daniel speaking Farsi](https://wikitongues.org/videos/daniel_20180207_pes/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,101,428 articles in fa.wikipedia; 8,324 active users. ⚠️ NB: counted under the macrolanguage code `fas`, so this number is shared with Dari (`prs`) and overstates Persian.                      |
| Common Crawl           | 10,945,849 pages per crawl on average, which is 0.5082% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `fas`, so this number is shared with Dari (`prs`) and overstates Persian. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                     |
| Goldfish training data | 12.52 GB (pes_Arab 12.52 GB) (rank 5 of 166 in the set)                                                                                                                                            |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 35,104 sentences / 645,790 tokens in total: [UD_Persian-PerDT](https://github.com/UniversalDependencies/UD_Persian-PerDT) (29,107 sentences), [UD_Persian-Seraji](https://github.com/UniversalDependencies/UD_Persian-Seraji) (5,997 sentences). All have POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `fas`, so this may cover other varieties as well as Persian. |
| UniMorph               | 273 lemmas, 37,128 inflected forms ([unimorph/fas](https://github.com/unimorph/fas)) ⚠️ Listed under the macrolanguage code `fas`, so this may cover other varieties as well as Persian.                                                                                                                                                                                                                                                   |
| Wikidata labels        | 2,789,245 Wikidata items have a label in Persian. (Wikidata codes (labels): fa (2,789,245))                                                                                                                                                                                                                                                                                                                                                |
| Wordnets               | FarsNet (size not listed); licence: OPEN FOR ACADEMIC USE; PersiaNet (size not listed); Persian Wordnet (size not listed); licence: OPEN.                                                                                                                                                                                                                                                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                              |
|:-----------------------------------|:---------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                  |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([pesOPV](https://ebible.org/details.php?id=pesOPV), Public Domain). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.823 (P 0.733, R 0.998, FPR 3.41e-03) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.814).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.733 |    0.998 | 0.823 | 0.003 | ✓                |
| fasttext     |       0.728 |    0.978 | 0.814 | 0.004 | ✓                |
| OpenLID-v2   |       0.747 |    0.903 | 0.807 | 0.003 | ✓                |
| cld2         |       0.717 |    0.983 | 0.804 | 0.005 | ✓                |
| commonlingua |       0.721 |    0.967 | 0.799 | 0.004 | ✓                |
| py3langid    |       0.699 |    0.993 | 0.797 | 0.006 | ✓                |
| funlangid    |       0.737 |    0.545 | 0.585 | 0.002 | ✓                |
| cld3         |       0.440 |    0.978 | 0.575 | 0.020 | ✓                |
| pyfranc      |       0.477 |    0.410 | 0.413 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| FLORES    | 300 |       0.477 |    1.000 | 0.646 |
| NTREX     | 300 |       0.499 |    1.000 | 0.666 |
| UDHR-LID  |  58 |       0.509 |    1.000 | 0.674 |
| Wikipedia | 300 |       0.943 |    0.997 | 0.969 |
| CommonLID | 300 |       0.987 |    0.993 | 0.990 |
| Tatoeba   | 300 |       0.984 |    0.997 | 0.990 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Persian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Persian *and* from closely related languages that might be confused with it. Likely confusions to include: Dari (`prs`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Persian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Persian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Persian (and whether the model is exclusively tagged for Persian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,650** text-generation models are explicitly tagged for Persian (369 original uploads, 1,281 fine-tunes/quantisations/merges).
- **360** are tagged *only* for Persian.
- Including tags inherited from base models: **2,046**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       16 | █                    |
|   2023 |       33 | █                    |
|   2024 |      197 | ████                 |
|   2025 |      436 | █████████            |
|   2026 |      968 | ████████████████████ |

### Largest models tagged for Persian

| model                                                                                                                     | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                 | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                     | 856.0B       |                  143 |   2025 | —               |
| [mindlab-research/Macaron-V1-Preview-744B-Merged](https://huggingface.co/mindlab-research/Macaron-V1-Preview-744B-Merged) | 753.9B       |                    4 |   2026 | zai-org/GLM-5.1 |
| [mindlab-research/Macaron-V1-Venti](https://huggingface.co/mindlab-research/Macaron-V1-Venti)                             | 753.3B       |                    4 |   2026 | —               |
| [mindlab-research/Macaron-V1.1](https://huggingface.co/mindlab-research/Macaron-V1.1)                                     | 753.3B       |                    2 |   2026 | —               |

### Largest models tagged *only* for Persian

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------|
| [bartowski/QuixiAI_Ina-v11.1-GGUF](https://huggingface.co/bartowski/QuixiAI_Ina-v11.1-GGUF)                   | 70.6B        |                    1 |   2025 | NeverSleep/Lumimaid-v0.2-70B |
| [anonymousAAK/impersona](https://huggingface.co/anonymousAAK/impersona)                                       | 40.2B        |                    1 |   2026 | —                            |
| [GemMaroc/Qwen2.5-32B-Instruct-darija-gguf](https://huggingface.co/GemMaroc/Qwen2.5-32B-Instruct-darija-gguf) | 32.8B        |                    1 |   2025 | Qwen/Qwen2.5-32B             |
| [projectmiko/miko-persona-31b-w4a16](https://huggingface.co/projectmiko/miko-persona-31b-w4a16)               | 31.5B        |                    1 |   2026 | unsloth/gemma-4-31B-it       |
| [debaterhub/Bohr-LoRA-v1-Qwen3-30B](https://huggingface.co/debaterhub/Bohr-LoRA-v1-Qwen3-30B)                 | 30.0B        |                    1 |   2025 | Qwen/Qwen3-30B-A3B-Base      |

_271 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Persian (plus 4 labelled with the macrolanguage `fas`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [6]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [3]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [4]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [4]   \
  /____________________|_____________________\
 /         ✅ Machine translation [8]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | construction                                                        |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data) (as `fas`)                                           | 449            | Treebank-based (automatic)                                          |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `fas`)                                | 2,553          | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                         | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                              |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)      | Mehr corpus (Persian pronoun resolution)                                                                       | —              | Native (annotated coreference corpus)                               |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | Persian WinoGrande (MELAC)                                                                                     | 1,129          | Translation + localization (LLM-assisted, 3 human reviewers)        |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `fas`)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `fas`)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | PQuAD                                                                                                          | —              | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | Khayyam Challenge (PersianMMLU)                                                                                | 20,192         | Native (exams)                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | MT + community post-editing                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                        | 500            | Native (cultural; native-speaker answers)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                         | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                            |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                        | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 3,762          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Negation, Presupposition & scalar implicature, WNLI, WSC
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Persian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Persian? Does it make sense to train one?
  - ~7.84 GB English-equivalent text ≈ 1.96B tokens, enough for a compute-optimal model of ~97.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Persian-only model is 70.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 285 of ~18,498 papers (1.54%) (rank 28 of 278 in the set); English is mentioned in 8,465.
- Search terms: Iranian Persian | Persian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 285):

| title                                                                                                                                                     | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AdabNER: Arabic Digital Archive Books with Nested Entity Recognition                                                                                      | [2026.acl-long.1541](https://aclanthology.org/2026.acl-long.1541/)             |
| Multilingual Idioms in Sentences and Conversations Across High-, Medium-, and Low-Resource Languages                                                      | [2026.acl-long.564](https://aclanthology.org/2026.acl-long.564/)               |
| Query Decomposition for RAG: Balancing Exploration-Exploitation                                                                                           | [2026.eacl-long.322](https://aclanthology.org/2026.eacl-long.322/)             |
| ChemCLIR-Bench: Benchmarking Cross-Lingual Information Retrieval in Multilingual Chemical Patents                                                         | [2026.emnlp-industry.175](https://aclanthology.org/2026.emnlp-industry.175/)   |
| CEAID: Benchmark of Multilingual Machine-Generated Text Detection Methods for Central European Languages                                                  | [2026.findings-acl.1458](https://aclanthology.org/2026.findings-acl.1458/)     |
| Translation Circuit Discovery and Targeted Optimization for Low-Resource Multilingual Translation                                                         | [2026.findings-emnlp.1348](https://aclanthology.org/2026.findings-emnlp.1348/) |
| Simple Additions, Substantial Gains: Expanding Scripts, Languages, and Lineage Coverage in URIEL+                                                         | [2026.lrec-1.863](https://aclanthology.org/2026.lrec-1.863/)                   |
| Wisdom in Unity: The Role of Multilingual Training in Figurative Language Identification in Proverbs                                                      | [2026.mrl-1.12](https://aclanthology.org/2026.mrl-1.12/)                       |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                                                    | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)           |
| Sagarmatha at SemEval-2026 Task 9: Heterogeneous Ensembling and Hierarchical Task Conditioning for Multilingual Latent Distributional Divergence Modeling | [2026.semeval-1.382](https://aclanthology.org/2026.semeval-1.382/)             |

{% endraw %}
