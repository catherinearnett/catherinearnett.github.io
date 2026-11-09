---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ckb.html
---
{% raw %}
# So you want to work on Kurdish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ckb` · macrolanguage `kur`

**Writing systems:** `Arab`

**Official / recognised in:** Iraq

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 85,215 articles in ckb.wikipedia (rank 59 of 161 in the set) — ~1/89 of English; 163 active users                                                                                                                      |
| Common Crawl 2026      | 142,651 pages per crawl on average, which is 0.0066% of the crawl. ⚠️ NB: this is counted using `kur` (macrolanguage code), so this number is shared with other varieties and overstates Kurdish.                      |
| FineWeb                | 0.83 GB (ckb_Arab (0.83)); which is equivalent to ≈0.50 GB English data after byte-premium scaling; 0.35 GB removed by filtering. This is ~1/64,271 of English data and ranks 75 of 248 official languages in FineWeb. |
| Goldfish training data | 1.59 GB (ckb_arab) (rank 65 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.998, R 0.987, FPR 4.49e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.981).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.998 |    0.987 | 0.992 | 0.000 | ✓                |
| fasttext     |       0.970 |    0.993 | 0.981 | 0.001 | ✓                |
| OpenLID-v2   |       0.971 |    0.991 | 0.980 | 0.001 | ✓                |
| commonlingua |       0.970 |    0.971 | 0.969 | 0.001 | ✓                |
| funlangid    |       0.882 |    0.931 | 0.901 | 0.002 | ✓                |
| cld2         |       0.977 |    0.677 | 0.795 | 0.000 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.003 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       1.000 |    0.950 | 0.974 |
| Wikipedia | 300 |       1.000 |    0.987 | 0.993 |
| SmolSent  | 300 |       0.990 |    0.997 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kurdish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kurdish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kurdish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Kurdish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kurdish (and whether the model is exclusively tagged for Kurdish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **25** text-generation models are explicitly tagged for Kurdish (11 original uploads, 14 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Kurdish.
- Including tags inherited from base models: **25**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        4 | ███████              |
|   2025 |        7 | ████████████         |
|   2026 |       12 | ████████████████████ |

### Most popular models tagged for Kurdish

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                  |
| [QuantFactory/lb-reranker-0.5B-v1.0-GGUF](https://huggingface.co/QuantFactory/lb-reranker-0.5B-v1.0-GGUF)                                 | 8,634                  | 986                   | 630.2M       |                   88 |   2025 | Qwen/Qwen2.5-0.5B  |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                                   | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                  |

### Most popular models tagged *only* for Kurdish

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of    |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------|
| [goldfish-models/ckb_arab_full](https://huggingface.co/goldfish-models/ckb_arab_full)                       |                    738 |                    24 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/ckb_arab_5mb](https://huggingface.co/goldfish-models/ckb_arab_5mb)                         |                    451 |                    15 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/ckb_arab_10mb](https://huggingface.co/goldfish-models/ckb_arab_10mb)                       |                    449 |                    12 | unknown      |                    1 |   2024 | —                |
| [goldfish-models/ckb_arab_100mb](https://huggingface.co/goldfish-models/ckb_arab_100mb)                     |                    446 |                    13 | unknown      |                    1 |   2024 | —                |
| [akam-ot/kurdish-spellchecker-sorani-byt5](https://huggingface.co/akam-ot/kurdish-spellchecker-sorani-byt5) |                    241 |                    13 | 582.8M       |                    1 |   2026 | google/byt5-base |

### Largest models tagged for Kurdish

| model                                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------|
| [PawanKrd/RastNus-Base-12B](https://huggingface.co/PawanKrd/RastNus-Base-12B)                                                             | 114                    | 27                    | 12.0B        |                    1 |   2026 | google/gemma-4-12b |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 6,611                  | 1,111                 | 9.0B         |                   97 |   2026 | unsloth/Qwen3.5-9B |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 3,464                  | 746                   | 9.0B         |                   97 |   2026 | Qwen/Qwen3.5-9B    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                                   | 1,443                  | 59                    | 8.6B         |                  185 |   2023 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 11,812                 | 600                   | 8.6B         |                  185 |   2023 | —                  |

### Largest models tagged *only* for Kurdish

| model                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [PawanKrd/RastNus-Base-12B](https://huggingface.co/PawanKrd/RastNus-Base-12B)                               |                    114 |                    27 | 12.0B        |                    1 |   2026 | google/gemma-4-12b            |
| [ptrdvn/kakugo-3B-ckb](https://huggingface.co/ptrdvn/kakugo-3B-ckb)                                         |                    180 |                    42 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [akam-ot/kurdish-spellchecker-sorani-byt5](https://huggingface.co/akam-ot/kurdish-spellchecker-sorani-byt5) |                    241 |                    13 | 582.8M       |                    1 |   2026 | google/byt5-base              |

_10 tagged models have unknown parameter counts and are not ranked by size._

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

**14** benchmark datasets in the survey include Kurdish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [1]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /        ✅ Machine translation [11]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 750            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kurdish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kurdish? Does it make sense to train one?
  - ~0.96 GB English-equivalent text ≈ 0.24B tokens, enough for a compute-optimal model of ~12.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kurdish-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 69 of ~18,460 papers (0.37%) (rank 69 of 252 in the set); English is mentioned in 8,441.
- Search terms: Central Kurdish (Sorani) | Central Kurdish | Kurdish | Sorani

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 69):

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                     | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                     |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                                  | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                 |
| Common Voice for Pakistan: Developing an Open Speech Corpus for Low-Resource Pakistani Languages                                              | [2026.lrec-1.265](https://aclanthology.org/2026.lrec-1.265/)                 |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                 |
| Whisper-Style Speech Encoders Align Semantically Beyond Phonetic Cues                                                                         | [2026.mrl-1.32](https://aclanthology.org/2026.mrl-1.32/)                     |
| Doing More with Less: Determining Optimal Pre-training Model for Irish Automatic Speech Recognition through Multi-step Fine-tuning            | [2026.speakable-1.18](https://aclanthology.org/2026.speakable-1.18/)         |
| Predicting Convincingness in Political Speech: How Emotional Tone Shapes Persuasive Strength                                                  | [2026.wassa-1.4](https://aclanthology.org/2026.wassa-1.4/)                   |
| TUM-Heilbronn: WMT26 Multilingual Instruction Shared Task                                                                                     | [2026.wmt-main.128](https://aclanthology.org/2026.wmt-main.128/)             |
| Probe Before you Answer! Answerability Probing for Abstention in Cross-Lingual Context-Based Question Answering                               | [2026.wmt-main.129](https://aclanthology.org/2026.wmt-main.129/)             |

{% endraw %}
