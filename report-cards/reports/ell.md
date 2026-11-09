---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ell.html
---
{% raw %}
# So you want to work on Greek?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ell`

**Writing systems:** `Grek`

**Official / recognised in:** Cyprus, Greece, South Africa

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 275,091 articles in el.wikipedia (rank 35 of 161 in the set) — ~1/27 of English; 2,113 active users                                                                                                                      |
| Common Crawl 2026      | 11,595,458 pages per crawl on average, which is 0.5380% of the crawl. This is ~1/77 of English data and ranks 19 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 78.61 GB (ell_Grek (78.61)); which is equivalent to ≈39.96 GB English data after byte-premium scaling; 100.72 GB removed by filtering. This is ~1/680 of English data and ranks 22 of 248 official languages in FineWeb. |
| Goldfish training data | 12.84 GB (ell_grek) (rank 4 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=116), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.997 (P 0.997, R 0.997, FPR 2.82e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.997).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.997 |    0.997 | 0.997 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.996 | 0.997 | 0.000 | ✓                |
| pyfranc      |       0.999 |    0.990 | 0.994 | 0.000 | ✗                |
| GlotLID      |       0.997 |    0.989 | 0.993 | 0.000 | ✓                |
| cld2         |       0.956 |    0.997 | 0.974 | 0.000 | ✓                |
| py3langid    |       0.996 |    0.895 | 0.929 | 0.000 | ✓                |
| funlangid    |       0.959 |    0.904 | 0.925 | 0.000 | ✓                |
| commonlingua |       0.995 |    0.866 | 0.914 | 0.000 | ✓                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.983 |    0.983 | 0.983 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 116 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Greek to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Greek *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Greek and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Greek?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Greek (and whether the model is exclusively tagged for Greek or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **740** text-generation models are explicitly tagged for Greek (239 original uploads, 501 fine-tunes/quantisations/merges).
- **91** are tagged *only* for Greek.
- Including tags inherited from base models: **1,327**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       18 | █                    |
|   2023 |       22 | ██                   |
|   2024 |      215 | ████████████████     |
|   2025 |      213 | ████████████████     |
|   2026 |      272 | ████████████████████ |

### Most popular models tagged for Greek

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)                                   | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —                                      |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |

### Most popular models tagged *only* for Greek

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [lighteternal/gpt2-finetuned-greek](https://huggingface.co/lighteternal/gpt2-finetuned-greek)             | 23,586                 |                   195 | unknown      |                    1 |   2022 | —                     |
| [nikokons/gpt2-greek](https://huggingface.co/nikokons/gpt2-greek)                                         | 19,256                 |                   814 | unknown      |                    1 |   2022 | openai-community/gpt2 |
| [AUEB-NLP/ByT5_g2g](https://huggingface.co/AUEB-NLP/ByT5_g2g)                                             | 18,570                 |                   333 | unknown      |                    1 |   2024 | —                     |
| [lighteternal/gpt2-finetuned-greek-small](https://huggingface.co/lighteternal/gpt2-finetuned-greek-small) | 7,346                  |                   859 | unknown      |                    1 |   2022 | —                     |
| [goldfish-models/ell_grek_1000mb](https://huggingface.co/goldfish-models/ell_grek_1000mb)                 | 4,088                  |                    91 | unknown      |                    1 |   2024 | —                     |

### Largest models tagged for Greek

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                     | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)   | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)     | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [unsloth/c4ai-command-a-03-2025-bnb-4bit](https://huggingface.co/unsloth/c4ai-command-a-03-2025-bnb-4bit) | 51,547                 | 503                   | 114.4B       |                   23 |   2025 | CohereLabs/c4ai-command-a-03-2025      |

### Largest models tagged *only* for Greek

| model                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                   |
|:------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:------------------------------------------------|
| [MikCil/PREMOVE_llama3.3-70b_float16](https://huggingface.co/MikCil/PREMOVE_llama3.3-70b_float16)     |                    311 |                    28 | 70.6B        |                    1 |   2026 | unsloth/llama-3.3-70b-instruct-unsloth-bnb-4bit |
| [Efso/Nemotron-3-Nano-30B-A3B-GR](https://huggingface.co/Efso/Nemotron-3-Nano-30B-A3B-GR)             |                    117 |                    50 | 31.6B        |                    1 |   2026 | nvidia/NVIDIA-Nemotron-3-Nano-30B-A3B-BF16      |
| [d-michail/Mitos-Qwen3-14B-Process](https://huggingface.co/d-michail/Mitos-Qwen3-14B-Process)         |                    157 |                   157 | 14.8B        |                    1 |   2026 | Qwen/Qwen3-14B-Base                             |
| [IMISLab/Maistros-8B-Instruct-4bit](https://huggingface.co/IMISLab/Maistros-8B-Instruct-4bit)         |                    304 |                    11 | 9.2B         |                    1 |   2026 | mistralai/Ministral-3-8B-Instruct-2512-BF16     |
| [themetron/Krikri-Cypriot-8B-v0.1-GGUF](https://huggingface.co/themetron/Krikri-Cypriot-8B-v0.1-GGUF) |                     93 |                    93 | 8.2B         |                    1 |   2026 | ilsp/Llama-Krikri-8B-Base                       |

_75 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Greek.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [6]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [3]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 87             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 1,096          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge       | BLiMP                          | [el-BLiMP](https://github.com/eirisel/el-blimp)                                                     | 600            | Mixed (template + LLM-assisted + web-extracted)                  |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)    | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline)       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                        |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 13,055         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Greek datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Greek? Does it make sense to train one?
  - ~39.96 GB English-equivalent text ≈ 9.99B tokens, enough for a compute-optimal model of ~499.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Greek-only model is 70.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 422 of ~18,460 papers (2.28%) (rank 17 of 252 in the set); English is mentioned in 8,441.
- Search terms: Greek

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 422):

| title                                                                                                                   | paper                                                                          |
|:------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Mitigating Tokenization-Induced Distance Distortion in Long-Context Multilingual Machine Translation                    | [2026.acl-long.1696](https://aclanthology.org/2026.acl-long.1696/)             |
| Macaron: Controlled, Human-Written Benchmark for Multilingual and Multicultural Reasoning via Template-Filling          | [2026.acl-long.2211](https://aclanthology.org/2026.acl-long.2211/)             |
| GreekMMLU: A Native-Sourced Multitask Benchmark for Evaluating Language Models in Greek                                 | [2026.findings-acl.448](https://aclanthology.org/2026.findings-acl.448/)       |
| Thinking While Speaking: Inference-Time Knowledge Transfer for Responsive and Intelligent Conversational Voice Agents   | [2026.findings-emnlp.1371](https://aclanthology.org/2026.findings-emnlp.1371/) |
| Fables-DTR: A Corpus of Fables Annotated for Discourse and Temporal Relations                                           | [2026.lrec-1.145](https://aclanthology.org/2026.lrec-1.145/)                   |
| MultiCoS: A Multilingual Dataset of Connective Semantics with Context–Sentence Compatibility                            | [2026.lrec-1.381](https://aclanthology.org/2026.lrec-1.381/)                   |
| Ancient Greek to Modern Greek Machine Translation: A Novel Benchmark and Fine-Tuning Experiments on LLMs and NMT Models | [2026.lrec-1.684](https://aclanthology.org/2026.lrec-1.684/)                   |
| ITUNLP2 at MWE-2026 AdMIRe 2: Modular Zero-Shot Pipelines for Multimodal Idiom Grounding and Ranking                    | [2026.mwe-1.32](https://aclanthology.org/2026.mwe-1.32/)                       |
| The Linguist’s Lie Detector: Linguistic Knowledge in Large Language Models                                              | [2026.nslp-1.23](https://aclanthology.org/2026.nslp-1.23/)                     |
| Probing the Dynamics of Syntactic Ability Acquisition Throughout LLM Pretraining                                        | [2026.udw-1.1](https://aclanthology.org/2026.udw-1.1/)                         |

{% endraw %}
