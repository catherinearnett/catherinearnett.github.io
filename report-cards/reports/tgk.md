---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tgk.html
---
{% raw %}
# So you want to work on Tajik?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tgk`

**Writing systems:** `Cyrl`

**Official / recognised in:** Tajikistan

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                 |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 119,530 articles in tg.wikipedia (rank 53 of 161 in the set) — ~1/63 of English; 123 active users                                                                                                                      |
| Common Crawl 2026      | 140,960 pages per crawl on average, which is 0.0065% of the crawl. This is ~1/6,325 of English data and ranks 61 of 113 official languages in Common Crawl.                                                            |
| FineWeb                | 1.25 GB (tgk_Cyrl (1.25)); which is equivalent to ≈0.71 GB English data after byte-premium scaling; 0.60 GB removed by filtering. This is ~1/42,885 of English data and ranks 69 of 248 official languages in FineWeb. |
| Goldfish training data | 2.25 GB (tgk_cyrl) (rank 58 of 166 in the set)                                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=82), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.974 (P 0.963, R 0.986, FPR 1.09e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.968).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.986 | 0.974 | 0.000 | ✓                |
| cld2         |       0.961 |    0.976 | 0.968 | 0.000 | ✓                |
| fasttext     |       0.738 |    0.989 | 0.813 | 0.004 | ✓                |
| funlangid    |       0.766 |    0.907 | 0.812 | 0.002 | ✓                |
| py3langid    |       0.726 |    0.970 | 0.807 | 0.003 | ✓                |
| OpenLID-v2   |       0.705 |    0.996 | 0.803 | 0.003 | ✓                |
| commonlingua |       0.743 |    0.910 | 0.789 | 0.003 | ✓                |
| pyfranc      |       0.713 |    0.942 | 0.783 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  82 |       0.918 |    0.951 | 0.934 |
| UDHR-LID  |  57 |       0.905 |    1.000 | 0.950 |
| Wikipedia | 300 |       0.993 |    0.980 | 0.987 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tajik to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tajik *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tajik and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Tajik?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tajik (and whether the model is exclusively tagged for Tajik or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **94** text-generation models are explicitly tagged for Tajik (36 original uploads, 58 fine-tunes/quantisations/merges).
- **25** are tagged *only* for Tajik.
- Including tags inherited from base models: **124**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ████                 |
|   2023 |        6 | ███                  |
|   2024 |       15 | ███████              |
|   2025 |       24 | ████████████         |
|   2026 |       41 | ████████████████████ |

### Most popular models tagged for Tajik

| model                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)           | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —               |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small) | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —               |
| [bigscience/mt0-large](https://huggingface.co/bigscience/mt0-large) | 258,383                | 479                   | 1.2B         |                   90 |   2022 | —               |
| [bigscience/mt0-base](https://huggingface.co/bigscience/mt0-base)   | 176,408                | 1,151                 | 582.4M       |                   90 |   2022 | —               |
| [bigscience/mt0-xl](https://huggingface.co/bigscience/mt0-xl)       | 113,878                | 579                   | 3.7B         |                   90 |   2022 | —               |

### Most popular models tagged *only* for Tajik

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [goldfish-models/tgk_cyrl_1000mb](https://huggingface.co/goldfish-models/tgk_cyrl_1000mb)               |                    499 |                    28 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tgk_cyrl_100mb](https://huggingface.co/goldfish-models/tgk_cyrl_100mb)                 |                    407 |                    18 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tgk_cyrl_5mb](https://huggingface.co/goldfish-models/tgk_cyrl_5mb)                     |                    401 |                    16 | unknown      |                    1 |   2024 | —                             |
| [goldfish-models/tgk_cyrl_10mb](https://huggingface.co/goldfish-models/tgk_cyrl_10mb)                   |                    385 |                    21 | unknown      |                    1 |   2024 | —                             |
| [NikolayKozloff/kakugo-3B-tgk-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-tgk-Q8_0-GGUF) |                    119 |                    29 | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |

### Largest models tagged for Tajik

| model                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                               |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) |                    875 |                   175 | 34.7B        |                   80 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [SaidzodaEng/Qwen3.6-27B-Tajik-Instruct](https://huggingface.co/SaidzodaEng/Qwen3.6-27B-Tajik-Instruct)               |                      0 |                     0 | 27.4B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [SaidzodaEng/Asad_Gemma3-27B_Adapter](https://huggingface.co/SaidzodaEng/Asad_Gemma3-27B_Adapter)                     |                     30 |                     0 | 27.0B        |                    1 |   2025 | unsloth/gemma-3-27b-it-bnb-4bit |

### Largest models tagged *only* for Tajik

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [SaidzodaEng/Qwen3.6-27B-Tajik-Instruct](https://huggingface.co/SaidzodaEng/Qwen3.6-27B-Tajik-Instruct) |                      0 |                     0 | 27.4B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [SaidzodaEng/Asad_Gemma3-27B_Adapter](https://huggingface.co/SaidzodaEng/Asad_Gemma3-27B_Adapter)       |                     30 |                     0 | 27.0B        |                    1 |   2025 | unsloth/gemma-3-27b-it-bnb-4bit |
| [SaidzodaEng/Ameena_Qwen3-8B_e3](https://huggingface.co/SaidzodaEng/Ameena_Qwen3-8B_e3)                 |                     19 |                    19 | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base              |
| [alphaedge-ai/Qwen3.5-4B-tgk-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-tgk-32768)           |                     51 |                    12 | 4.0B         |                    1 |   2026 | Qwen3.5-4B                      |
| [alphaedge-ai/gemma-3-4b-it-tgk-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-tgk-32768)     |                     41 |                     6 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it            |

_20 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Tajik.

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
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | Construction                                                     |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                          | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 29             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tajik datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tajik? Does it make sense to train one?
  - ~1.29 GB English-equivalent text ≈ 0.32B tokens, enough for a compute-optimal model of ~16.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tajik-only model is 27.4B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 34 of ~18,460 papers (0.18%) (rank 102 of 252 in the set); English is mentioned in 8,441.
- Search terms: Tajik

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 34):

| title                                                                                                               | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| POWSM: A Phonetic Open Whisper-Style Speech Foundation Model                                                        | [2026.acl-long.813](https://aclanthology.org/2026.acl-long.813/)               |
| ParsBench: A Benchmark for Evaluating Fine-Grained Culturally Grounded Commonsense Reasoning in Persian             | [2026.emnlp-main.2635](https://aclanthology.org/2026.emnlp-main.2635/)         |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                 | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| Computationally Invisible: Charting the NLP Landscape of Iranic Languages                                           | [2026.findings-emnlp.2362](https://aclanthology.org/2026.findings-emnlp.2362/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation        | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                          | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                      | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| Shughni Machine Translation Enhanced by Donor Languages                                                             | [2026.silkroadnlp-1.12](https://aclanthology.org/2026.silkroadnlp-1.12/)       |
| A Computational Approach to Language Contact – A Case Study of Persian                                              | [2026.silkroadnlp-1.5](https://aclanthology.org/2026.silkroadnlp-1.5/)         |

{% endraw %}
