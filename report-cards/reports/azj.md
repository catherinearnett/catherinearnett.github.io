---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/azj.html
---
{% raw %}
# So you want to work on Azerbaijani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `azj` · macrolanguage `aze`

**Writing systems:** `Latn`

**Official / recognised in:** Azerbaijan, Russia

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                   |
| Common Crawl 2026      | 1,304,787 pages per crawl on average, which is 0.0606% of the crawl. ⚠️ NB: this is counted using `aze` (macrolanguage code), so this number is shared with other varieties and overstates Azerbaijani.                                    |
| FineWeb                | 11.31 GB (azj_Cyrl (0.01); azj_Latn (11.30)); which is equivalent to ≈10.50 GB English data after byte-premium scaling; 22.86 GB removed by filtering. This is ~1/4,722 of English data and ranks 39 of 248 official languages in FineWeb. |
| Goldfish training data | 0.17 GB (azj_latn) (rank 111 of 166 in the set)                                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.980 (P 0.974, R 0.986, FPR 2.28e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.885).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.974 |    0.986 | 0.980 | 0.000 | ✓                |
| OpenLID-v2   |       0.863 |    0.910 | 0.885 | 0.002 | ✓                |
| py3langid    |       0.863 |    0.898 | 0.878 | 0.003 | ✓                |
| cld2         |       0.866 |    0.887 | 0.875 | 0.001 | ✓                |
| commonlingua |       0.893 |    0.856 | 0.873 | 0.001 | ✓                |
| pyfranc      |       0.879 |    0.816 | 0.843 | 0.001 | ✓                |
| fasttext     |       0.783 |    0.908 | 0.837 | 0.003 | ✓                |
| funlangid    |       0.874 |    0.783 | 0.820 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.893 |    0.943 | 0.917 |
| Wikipedia | 300 |       0.980 |    0.987 | 0.983 |
| CommonLID | 300 |       0.990 |    0.983 | 0.987 |
| UDHR-LID  | 114 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Azerbaijani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Azerbaijani *and* from closely related languages that might be confused with it. Likely confusions to include: Turkmen (`azb`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Azerbaijani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Azerbaijani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Azerbaijani (and whether the model is exclusively tagged for Azerbaijani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **201** text-generation models are explicitly tagged for Azerbaijani (85 original uploads, 116 fine-tunes/quantisations/merges).
- **49** are tagged *only* for Azerbaijani.
- Including tags inherited from base models: **250**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |       12 | ███                  |
|   2024 |       36 | ██████████           |
|   2025 |       70 | ███████████████████  |
|   2026 |       75 | ████████████████████ |

### Most popular models tagged for Azerbaijani

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |

### Most popular models tagged *only* for Azerbaijani

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [LocalDoc/azerbaijani_spell_corrector](https://huggingface.co/LocalDoc/azerbaijani_spell_corrector)                   |                    964 |                    15 | 300.2M       |                    1 |   2024 | google/mt5-small      |
| [learningmachineaz/cirtdan-azerbaijani-chatbot](https://huggingface.co/learningmachineaz/cirtdan-azerbaijani-chatbot) |                    780 |                    19 | 1.2B         |                    1 |   2023 | —                     |
| [allmalab/gpt2-aze](https://huggingface.co/allmalab/gpt2-aze)                                                         |                    649 |                     0 | 135.0M       |                    1 |   2024 | openai-community/gpt2 |
| [aghasalim/siba-meristem-native-0.5b-base](https://huggingface.co/aghasalim/siba-meristem-native-0.5b-base)           |                    644 |                   340 | 539.0M       |                    1 |   2026 | —                     |
| [khazarai/Nizami-1.7B](https://huggingface.co/khazarai/Nizami-1.7B)                                                   |                    574 |                    35 | 1.7B         |                    1 |   2026 | unsloth/Qwen3-1.7B    |

### Largest models tagged for Azerbaijani

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) |                    875 |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [16th-research-lab-ai/actum-az-31b](https://huggingface.co/16th-research-lab-ai/actum-az-31b)                         |                      3 |                     0 | 31.3B        |                    3 |   2026 | —                    |
| [vrashad/gpt-oss-20b-medical-az](https://huggingface.co/vrashad/gpt-oss-20b-medical-az)                               |                    186 |                    18 | 20.0B        |                    1 |   2025 | openai/gpt-oss-20b   |

### Largest models tagged *only* for Azerbaijani

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [vrashad/gpt-oss-20b-medical-az](https://huggingface.co/vrashad/gpt-oss-20b-medical-az)             |                    186 |                    18 | 20.0B        |                    1 |   2025 | openai/gpt-oss-20b   |
| [lmnglzd/az-spellfix-qwen35-9b-short](https://huggingface.co/lmnglzd/az-spellfix-qwen35-9b-short)   |                      0 |                     0 | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B      |
| [omar07ibrahim/unt-8b](https://huggingface.co/omar07ibrahim/unt-8b)                                 |                    205 |                     3 | 8.0B         |                    1 |   2025 | —                    |
| [alphaedge-ai/Qwen3.5-4B-aze-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-aze-32768)       |                     49 |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-aze-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-aze-32768) |                     46 |                     8 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |

_67 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Azerbaijani (plus 2 labelled with the macrolanguage `aze`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [3]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [4]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `aze`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `aze`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                                   |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                        |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,659          | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Azerbaijani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Azerbaijani? Does it make sense to train one?
  - ~10.50 GB English-equivalent text ≈ 2.63B tokens, enough for a compute-optimal model of ~131.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Azerbaijani-only model is 20.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 63 of ~18,460 papers (0.34%) (rank 75 of 252 in the set); English is mentioned in 8,441.
- Search terms: North Azerbaijani | Azerbaijani

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 63):

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Sign-Language Datasets at Scale: A Comprehensive Survey on Resources, Benchmarks, and Annotation Standards                                    | [2026.acl-long.1928](https://aclanthology.org/2026.acl-long.1928/)           |
| Language Family Matters: Evaluating LLM-based ASR Across Linguistic Boundaries                                                                | [2026.eacl-short.36](https://aclanthology.org/2026.eacl-short.36/)           |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                                  | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                 |
| MultiInpaintCOCO: Fine-Grained Visual Understanding in Multiple Languages                                                                     | [2026.mrl-1.45](https://aclanthology.org/2026.mrl-1.45/)                     |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                                                        | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)             |
| wangkongqiang at SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                                | [2026.semeval-1.36](https://aclanthology.org/2026.semeval-1.36/)             |
| SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                                                 | [2026.semeval-1.455](https://aclanthology.org/2026.semeval-1.455/)           |
| Bukva: Russian Sign Language Alphabet                                                                                                         | [2026.wslp-1.15](https://aclanthology.org/2026.wslp-1.15/)                   |

{% endraw %}
