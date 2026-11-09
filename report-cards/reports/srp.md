---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/srp.html
---
{% raw %}
# So you want to work on Serbian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `srp` · macrolanguage `hbs`

**Writing systems:** `Cyrl` and `Latn`

**Official / recognised in:** Bosnia and Herzegovina, Kosovo, Serbia

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 710,638 articles in sr.wikipedia (rank 20 of 161 in the set) — ~1/11 of English; 1,491 active users                                                                                                                                     |
| Common Crawl 2026      | 5,491,412 pages per crawl on average, which is 0.2549% of the crawl. This is ~1/162 of English data and ranks 27 of 113 official languages in Common Crawl.                                                                             |
| FineWeb                | 10.49 GB (srp_Cyrl (9.37); srp_Latn (1.12)); which is equivalent to ≈7.93 GB English data after byte-premium scaling; 8.22 GB removed by filtering. This is ~1/5,093 of English data and ranks 40 of 248 official languages in FineWeb. |
| Goldfish training data | 3.39 GB (srp_cyrl; srp_latn) (rank 51 of 166 in the set)                                                                                                                                                                                |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=118), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.793 (P 0.773, R 0.847, FPR 2.43e-03) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.774).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.773 |    0.847 | 0.793 | 0.002 | ✓                |
| OpenLID-v2   |       0.833 |    0.748 | 0.774 | 0.002 | ✓                |
| fasttext     |       0.823 |    0.749 | 0.768 | 0.002 | ✓                |
| py3langid    |       0.742 |    0.792 | 0.750 | 0.004 | ✓                |
| commonlingua |       0.667 |    0.794 | 0.722 | 0.004 | ✓                |
| cld2         |       0.656 |    0.814 | 0.720 | 0.005 | ✓                |
| funlangid    |       0.787 |    0.602 | 0.667 | 0.002 | ✓                |
| pyfranc      |       0.487 |    0.499 | 0.491 | 0.006 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 118 |       0.527 |    0.653 | 0.583 |
| Tatoeba   | 300 |       0.517 |    0.937 | 0.666 |
| NTREX     | 300 |       0.860 |    0.653 | 0.742 |
| FLORES    | 300 |       0.968 |    1.000 | 0.984 |
| Wikipedia | 300 |       0.993 |    0.990 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Serbian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Serbian *and* from closely related languages that might be confused with it. Likely confusions to include: Bosnian (`bos`), Montenegrin (`cnr`), Croatian (`hrv`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Serbian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Serbian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Serbian (and whether the model is exclusively tagged for Serbian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **540** text-generation models are explicitly tagged for Serbian (115 original uploads, 425 fine-tunes/quantisations/merges).
- **46** are tagged *only* for Serbian.
- Including tags inherited from base models: **908**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | █                    |
|   2023 |       20 | ██                   |
|   2024 |       69 | ██████               |
|   2025 |      211 | ██████████████████   |
|   2026 |      232 | ████████████████████ |

### Most popular models tagged for Serbian

| model                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)                         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [lmstudio-community/Devstral-Small-2507-MLX-8bit](https://huggingface.co/lmstudio-community/Devstral-Small-2507-MLX-8bit) | 817,747                | 10,371                | 23.6B        |                   24 |   2025 | mistralai/Devstral-Small-2507          |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [lmstudio-community/Devstral-Small-2505-MLX-4bit](https://huggingface.co/lmstudio-community/Devstral-Small-2505-MLX-4bit) | 638,937                | 6,557                 | 23.6B        |                   24 |   2025 | mistralai/Devstral-Small-2505          |
| [bigscience/mt0-small](https://huggingface.co/bigscience/mt0-small)                                                       | 460,248                | 4,349                 | 300.2M       |                   90 |   2022 | —                                      |

### Most popular models tagged *only* for Serbian

| model                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:--------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [jerteh/gpt2-orao](https://huggingface.co/jerteh/gpt2-orao)                     | 9,917                  |                   755 | 810.4M       |                    1 |   2023 | —                                     |
| [macedonizer/sr-gpt2](https://huggingface.co/macedonizer/sr-gpt2)               | 6,792                  |                   223 | unknown      |                    1 |   2022 | —                                     |
| [jerteh/gpt2-vrabac](https://huggingface.co/jerteh/gpt2-vrabac)                 | 5,312                  |                   182 | 136.2M       |                    1 |   2023 | —                                     |
| [edukom/Serbian-GPT-2](https://huggingface.co/edukom/Serbian-GPT-2)             | 2,632                  |                    25 | unknown      |                    1 |   2023 | —                                     |
| [datatab/Yugo55-GPT-v4-4bit](https://huggingface.co/datatab/Yugo55-GPT-v4-4bit) | 1,161                  |                    25 | 7.5B         |                    1 |   2024 | datatab/YugoGPT-Alpaca-v1-epoch1-good |

### Largest models tagged for Serbian

| model                                                                                                   |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                               |                      0 |                     0 | 1.9T         |                  140 |   2025 | —                            |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                   |                      0 |                     0 | 856.0B       |                  140 |   2025 | —                            |
| [GreatZM/GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/GreatZM/GLM-5.3-CYBERSECURITY-FP8)           |                     75 |                    22 | 753.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-FP8         |
| [Devopsopraiz/Baanzon-Revgarden-V5-R](https://huggingface.co/Devopsopraiz/Baanzon-Revgarden-V5-R)       |                     46 |                    46 | 753.3B       |                   10 |   2026 | —                            |
| [AIAgens/GLM-5.3-Flash-UNCENSORED-W4A16](https://huggingface.co/AIAgens/GLM-5.3-Flash-UNCENSORED-W4A16) |                    682 |                   233 | 321.3B       |                   10 |   2026 | JANGQ-AI/GLM-5.3-Flash-W4A16 |

### Largest models tagged *only* for Serbian

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                         |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------|
| [IvanCvetanovic/Slava-Qwen3-14B-Serbian](https://huggingface.co/IvanCvetanovic/Slava-Qwen3-14B-Serbian)   | 174                    |                    19 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                   |
| [te-sla/serbian-emotion-qwen3.5-9b](https://huggingface.co/te-sla/serbian-emotion-qwen3.5-9b)             | 284                    |                    35 | 9.4B         |                    1 |   2026 | unsloth/Qwen3.5-9B                    |
| [datatab/Yugo55A-4bit](https://huggingface.co/datatab/Yugo55A-4bit)                                       | 719                    |                    10 | 7.5B         |                    1 |   2024 | mistralai/Mistral-7B-v0.1             |
| [datatab/Yugo55-GPT-v4-4bit](https://huggingface.co/datatab/Yugo55-GPT-v4-4bit)                           | 1,161                  |                    25 | 7.5B         |                    1 |   2024 | datatab/YugoGPT-Alpaca-v1-epoch1-good |
| [MarkoRadojcic/YugoGPT-Florida_Q8_0-GGUF](https://huggingface.co/MarkoRadojcic/YugoGPT-Florida_Q8_0-GGUF) | 239                    |                    15 | 7.2B         |                    1 |   2025 | datatab/YugoGPT-Florida               |

_74 tagged models have unknown parameter counts and are not ranked by size._

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

**30** benchmark datasets in the survey include Serbian (plus 1 labelled with the macrolanguage `hbs`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [7]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [14]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 24             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                                   | 3,286          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 3. Commonsense reasoning               | COPA                           | [COPA-SR](https://huggingface.co/datasets/classla/COPA-SR)                                                        | 500            | Human translation                                                |
| 3. Commonsense reasoning               | COPA                           | [COPA-SR_lat](https://huggingface.co/datasets/classla/COPA-SR_lat)                                                | 500            | Human translation (transliterated)                               |
| 3. Commonsense reasoning               | COPA                           | [DIALECT-COPA (COPA-SR-TOR)](https://github.com/clarinsi/dialect-copa)                                            | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 9,449          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                    | 1,637          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Serbian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Serbian? Does it make sense to train one?
  - ~7.93 GB English-equivalent text ≈ 1.98B tokens, enough for a compute-optimal model of ~99.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Serbian-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 115 of ~18,460 papers (0.62%) (rank 51 of 252 in the set); English is mentioned in 8,441.
- Search terms: Serbian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 115):

| title                                                                                                           | paper                                                            |
|:----------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Adam’s Law: Textual Frequency Law on Large Language Models                                                      | [2026.acl-long.188](https://aclanthology.org/2026.acl-long.188/) |
| The Degree of Language Diacriticity and Its Effect on Tasks                                                     | [2026.cawl-1.1](https://aclanthology.org/2026.cawl-1.1/)         |
| State of the Art in Text Classification for South Slavic Languages: Fine-Tuning or Prompting?                   | [2026.llms4ssh-1.1](https://aclanthology.org/2026.llms4ssh-1.1/) |
| Who Benchmarks the Benchmarks? A Case Study of LLM Evaluation in Icelandic                                      | [2026.lrec-1.369](https://aclanthology.org/2026.lrec-1.369/)     |
| ROG: A Multi-Layer Manually Annotated Corpus of Spoken Slovenian                                                | [2026.lrec-1.449](https://aclanthology.org/2026.lrec-1.449/)     |
| A Parallel Cross-Lingual Benchmark for Multimodal Idiomaticity Understanding                                    | [2026.lrec-1.741](https://aclanthology.org/2026.lrec-1.741/)     |
| Where Are Language-Specific Features Represented in Multilingual LLMs? Everywhere                               | [2026.mrl-1.27](https://aclanthology.org/2026.mrl-1.27/)         |
| Edition 2.0 of the PARSEME shared task on multilingual identification and paraphrasing of multiword expressions | [2026.mwe-1.33](https://aclanthology.org/2026.mwe-1.33/)         |
| OPENER: A Frugal Open-World NER Pipeline for the Legal Domain                                                   | [2026.nllp-1.40](https://aclanthology.org/2026.nllp-1.40/)       |
| Towards Universal Dependencies for L2 Learners of Modern Greek: Annotation and Challenges                       | [2026.udw-1.8](https://aclanthology.org/2026.udw-1.8/)           |

{% endraw %}
