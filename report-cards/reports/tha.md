---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tha.html
---
{% raw %}
# So you want to work on Thai?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tha`

**Writing systems:** `Thai`

**Official / recognised in:** Thailand

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 189,539 articles in th.wikipedia (rank 46 of 161 in the set) — ~1/40 of English; 2,471 active users                                                                                                                      |
| Common Crawl 2026      | 8,082,765 pages per crawl on average, which is 0.3748% of the crawl. This is ~1/110 of English data and ranks 23 of 113 official languages in Common Crawl.                                                              |
| FineWeb                | 75.11 GB (tha_Thai (75.11)); which is equivalent to ≈27.40 GB English data after byte-premium scaling; 104.56 GB removed by filtering. This is ~1/711 of English data and ranks 23 of 248 official languages in FineWeb. |
| Goldfish training data | 13.14 GB (tha_thai) (rank 3 of 166 in the set)                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.997 (P 0.999, R 0.995, FPR 1.04e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.995 | 0.997 | 0.000 | ✓                |
| cld2         |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| commonlingua |       0.996 |    0.993 | 0.994 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.989 | 0.993 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.971 | 0.985 | 0.000 | ✗                |
| funlangid    |       1.000 |    0.886 | 0.933 | 0.000 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.997 |    0.980 | 0.988 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 114 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Thai to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Thai *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Thai and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Thai?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Thai (and whether the model is exclusively tagged for Thai or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,304** text-generation models are explicitly tagged for Thai (1,003 original uploads, 3,301 fine-tunes/quantisations/merges).
- **168** are tagged *only* for Thai.
- Including tags inherited from base models: **26,019**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       15 | █                    |
|   2023 |       73 | █                    |
|   2024 |     1524 | ████████████████████ |
|   2025 |     1450 | ███████████████████  |
|   2026 |     1242 | ████████████████     |

### Most popular models tagged for Thai

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct)                                     | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)                                     | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                                                       | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct)                                     | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |
| [context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16](https://huggingface.co/context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16) | 27,918,610             | 132                   | 3.2B         |                    8 |   2025 | —                       |

### Most popular models tagged *only* for Thai

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [typhoon-ai/typhoon-7b](https://huggingface.co/typhoon-ai/typhoon-7b)                 | 124,601                | 1,065                 | 7.3B         |                    1 |   2023 | —               |
| [flax-community/gpt2-base-thai](https://huggingface.co/flax-community/gpt2-base-thai) | 66,473                 | 788                   | unknown      |                    1 |   2022 | —               |
| [wannaphong/han-llm-7b-v1](https://huggingface.co/wannaphong/han-llm-7b-v1)           | 10,077                 | 67                    | 7.3B         |                    1 |   2024 | —               |
| [wannaphong/han-llm-7b-v2](https://huggingface.co/wannaphong/han-llm-7b-v2)           | 9,842                  | 55                    | 7.3B         |                    1 |   2024 | —               |
| [wannaphong/han-llm-7b-v3](https://huggingface.co/wannaphong/han-llm-7b-v3)           | 9,335                  | 55                    | 7.3B         |                    1 |   2024 | —               |

### Largest models tagged for Thai

| model                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                             | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                 | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                               | 604                    |                   604 | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [hugging-quants/Meta-Llama-3.1-405B-Instruct-BNB-NF4](https://huggingface.co/hugging-quants/Meta-Llama-3.1-405B-Instruct-BNB-NF4)     | 6,898                  |                    22 | 422.8B       |                    8 |   2024 | meta-llama/Llama-3.1-405B       |
| [hugging-quants/Meta-Llama-3.1-405B-Instruct-GPTQ-INT4](https://huggingface.co/hugging-quants/Meta-Llama-3.1-405B-Instruct-GPTQ-INT4) | 36,449                 |                   105 | 410.1B       |                    8 |   2024 | —                               |

### Largest models tagged *only* for Thai

| model                                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:--------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [ThaiLLM/ThaiLLM-30B-IQ](https://huggingface.co/ThaiLLM/ThaiLLM-30B-IQ)                                                               |                    143 |                    14 | 30.5B        |                    1 |   2026 | —                                        |
| [ThaiLLM/ThaiLLM-8B-SFT-IQ](https://huggingface.co/ThaiLLM/ThaiLLM-8B-SFT-IQ)                                                         |                    316 |                    24 | 8.2B         |                    1 |   2026 | —                                        |
| [kunzaka001/LangTaiLLM-8B-Instruct](https://huggingface.co/kunzaka001/LangTaiLLM-8B-Instruct)                                         |                      0 |                     0 | 8.0B         |                    1 |   2026 | Qwen/Qwen3-8B-Base                       |
| [aminomewza/Llama-3.1-Typhoon2-8B-LoRA-NorthernThai-v2](https://huggingface.co/aminomewza/Llama-3.1-Typhoon2-8B-LoRA-NorthernThai-v2) |                    101 |                     9 | 8.0B         |                    1 |   2026 | typhoon-ai/llama3.1-typhoon2-8b-instruct |
| [wannaphong/llama-3-8b-han-16bit](https://huggingface.co/wannaphong/llama-3-8b-han-16bit)                                             |                    337 |                     8 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B               |

_137 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Thai.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [8]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [5]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WSC                            | [Thai Winograd Schemas](https://huggingface.co/datasets/pakphum/winograd_th)                        | 285            | Human translation (professional) + native review                    |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | [iapp_wiki_qa_squad](https://huggingface.co/datasets/iapp/iapp_wiki_qa_squad)                       | —              | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 2,595          | Native (national exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ThaiExam](https://huggingface.co/datasets/scb10x/thai_exam)                                        | —              | Native (ONET, TGAT, TPAT, IC, A-Level)                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,178          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Thai datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Thai? Does it make sense to train one?
  - ~27.40 GB English-equivalent text ≈ 6.85B tokens, enough for a compute-optimal model of ~342.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Thai-only model is 30.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 412 of ~18,460 papers (2.23%) (rank 18 of 252 in the set); English is mentioned in 8,441.
- Search terms: Thai

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 412):

| title                                                                                                      | paper                                                                        |
|:-----------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| FahMai-TeleBench: A Thai Grounded Tool-Use Benchmark for the Deployable Model Tier                         | [2026.aacl-short.15](https://aclanthology.org/2026.aacl-short.15/)           |
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                  | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/)           |
| Mirrored Frames: LLM-Based Narrative Framing Analysis of Thai-Cambodian Border Conflict Coverage           | [2026.findings-aacl.45](https://aclanthology.org/2026.findings-aacl.45/)     |
| SEA-SafeguardBench: Culturally Grounded Safety Benchmark for Southeast Asian Languages                     | [2026.findings-acl.194](https://aclanthology.org/2026.findings-acl.194/)     |
| SEATauBench: Progressively Adapting Tool-Agent-User Evaluation Into Low-Resource Southeast Asian Languages | [2026.findings-emnlp.502](https://aclanthology.org/2026.findings-emnlp.502/) |
| Off the Hamster Wheel: Rethinking Dialogue Research through a Meta-Analysis of the ACL Anthology 2024      | [2026.lrec-1.207](https://aclanthology.org/2026.lrec-1.207/)                 |
| Where Are Language-Specific Features Represented in Multilingual LLMs? Everywhere                          | [2026.mrl-1.27](https://aclanthology.org/2026.mrl-1.27/)                     |
| An Empirical Study of Evidence Retrieval for Retrieval Augmented Generation over the Thai Royal Gazette    | [2026.nllp-1.19](https://aclanthology.org/2026.nllp-1.19/)                   |
| Probing the Dynamics of Syntactic Ability Acquisition Throughout LLM Pretraining                           | [2026.udw-1.1](https://aclanthology.org/2026.udw-1.1/)                       |
| Full-Video Context and Anonymous Candidate Selection for WMT26 Video Subtitle Translation                  | [2026.wmt-main.207](https://aclanthology.org/2026.wmt-main.207/)             |

{% endraw %}
