---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kor.html
---
{% raw %}
# So you want to work on Korean?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kor`

**Writing systems:** `Hang`

**Official / recognised in:** North Korea, People's Republic of China, South Korea

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 770,480 articles in ko.wikipedia (rank 19 of 161 in the set) — ~1/10 of English; 4,943 active users                                                                                                                        |
| Common Crawl 2026      | 17,959,416 pages per crawl on average, which is 0.8336% of the crawl. This is ~1/50 of English data and ranks 15 of 113 official languages in Common Crawl.                                                                |
| FineWeb                | 105.82 GB (kor_Hang (105.82)); which is equivalent to ≈81.82 GB English data after byte-premium scaling; 166.19 GB removed by filtering. This is ~1/505 of English data and ranks 17 of 248 official languages in FineWeb. |
| Goldfish training data | 9.81 GB (kor_hang) (rank 11 of 166 in the set)                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.998 (P 0.999, R 0.997, FPR 4.05e-06) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| OpenLID-v2   |       0.995 |    0.997 | 0.996 | 0.000 | ✓                |
| cld2         |       0.996 |    0.995 | 0.996 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.945 | 0.969 | 0.000 | ✗                |
| commonlingua |       0.891 |    0.997 | 0.926 | 0.001 | ✓                |
| fasttext     |       0.787 |    0.996 | 0.870 | 0.002 | ✓                |
| funlangid    |       1.000 |    0.695 | 0.807 | 0.000 | ✓                |
| py3langid    |       0.503 |    0.997 | 0.636 | 0.014 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.987 | 0.992 |
| Tatoeba   | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Korean to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Korean *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Korean and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Korean?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Korean (and whether the model is exclusively tagged for Korean or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,767** text-generation models are explicitly tagged for Korean (2,012 original uploads, 5,755 fine-tunes/quantisations/merges).
- **1,638** are tagged *only* for Korean.
- Including tags inherited from base models: **16,153**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       41 | █                    |
|   2023 |      499 | ███                  |
|   2024 |     1902 | ███████████          |
|   2025 |     2011 | ████████████         |
|   2026 |     3314 | ████████████████████ |

### Most popular models tagged for Korean

| model                                                                                                               | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)                               | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —               |
| [skt/kogpt2-base-v2](https://huggingface.co/skt/kogpt2-base-v2)                                                     | 5,167,484              | 38,396                | unknown      |                    1 |   2022 | —               |
| [unsloth/Qwen2.5-7B-Instruct-unsloth-bnb-4bit](https://huggingface.co/unsloth/Qwen2.5-7B-Instruct-unsloth-bnb-4bit) | 4,438,987              | 87,208                | 7.8B         |                   13 |   2025 | Qwen/Qwen2.5-7B |
| [LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct](https://huggingface.co/LGAI-EXAONE/EXAONE-3.5-7.8B-Instruct)                 | 4,347,465              | 410,768               | 7.8B         |                    2 |   2024 | —               |
| [davidkim205/komt-mistral-7b-v1](https://huggingface.co/davidkim205/komt-mistral-7b-v1)                             | 3,654,937              | 24                    | 7.0B         |                    2 |   2023 | —               |

### Most popular models tagged *only* for Korean

| model                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------|
| [skt/kogpt2-base-v2](https://huggingface.co/skt/kogpt2-base-v2)                   | 5,167,484              | 38,396                | unknown      |                    1 |   2022 | —                         |
| [EleutherAI/polyglot-ko-1.3b](https://huggingface.co/EleutherAI/polyglot-ko-1.3b) | 1,422,035              | 2,134                 | 1.4B         |                    1 |   2022 | —                         |
| [FINAL-Bench/POCKET-26B-GGUF](https://huggingface.co/FINAL-Bench/POCKET-26B-GGUF) | 923,933                | 234,467               | 25.2B        |                    1 |   2026 | google/gemma-4-26B-A4B-it |
| [EleutherAI/polyglot-ko-5.8b](https://huggingface.co/EleutherAI/polyglot-ko-5.8b) | 449,075                | 1,169                 | 6.0B         |                    1 |   2022 | —                         |
| [kyujinpy/Ko-PlatYi-6B](https://huggingface.co/kyujinpy/Ko-PlatYi-6B)             | 434,554                | 38,772                | 6.0B         |                    1 |   2023 | —                         |

### Largest models tagged for Korean

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [batiai/DeepSeek-V4-Pro-GGUF](https://huggingface.co/batiai/DeepSeek-V4-Pro-GGUF)                         | 4,802                  | 51                    | 1.6T         |                    3 |   2026 | deepseek-ai/DeepSeek-V4-Pro       |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [batiai/Kimi-K2.6-GGUF](https://huggingface.co/batiai/Kimi-K2.6-GGUF)                                     | 8,200                  | 50                    | 1.0T         |                    4 |   2026 | moonshotai/Kimi-K2.6              |
| [batiai/Kimi-K2.7-Code-GGUF](https://huggingface.co/batiai/Kimi-K2.7-Code-GGUF)                           | 410                    | 54                    | 1.0T         |                    3 |   2026 | moonshotai/Kimi-K2.7-Code         |

### Largest models tagged *only* for Korean

| model                                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [FINAL-Bench/POCKET-Qwen3.8-Flash-Next-GGUF](https://huggingface.co/FINAL-Bench/POCKET-Qwen3.8-Flash-Next-GGUF)           | 6,027                  | 5,299                 | 176.9B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next                |
| [ada-flo/kor-road-finance-agent-oss-120b-lora](https://huggingface.co/ada-flo/kor-road-finance-agent-oss-120b-lora)       | 41                     | 41                    | 120.0B       |                    1 |   2025 | axolotl-ai-co/gpt-oss-120b-dequantized |
| [ktl-bmrc/MedReg-SLM-v0.1](https://huggingface.co/ktl-bmrc/MedReg-SLM-v0.1)                                               | 2,290                  | 37                    | 116.8B       |                    1 |   2025 | openai/gpt-oss-120b                    |
| [hell0ks/DeepSeek-V4.1-Flash-1017-EXL3-2.9bpw-ko](https://huggingface.co/hell0ks/DeepSeek-V4.1-Flash-1017-EXL3-2.9bpw-ko) | 294                    | 294                   | 105.3B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash-1017   |
| [onioncomcom/llama3](https://huggingface.co/onioncomcom/llama3)                                                           | 121                    | 10                    | 70.6B        |                    1 |   2025 | meta-llama/Llama-3.1-70B               |

_576 tagged models have unknown parameter counts and are not ranked by size._

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

**37** benchmark datasets in the survey include Korean.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [11]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [3]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [7]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | Construction                                                                     |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | KIM Bench                                                                                                      | 1,175          | Native                                                                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                          | —              | Native (dictionaries; LLM-refined meanings checked by natives)                   |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Korean pragmatic competence test set](https://github.com/DojunPark/pragmatic_eval_korean)                     | 120            | Native (expert-written)                                                          |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                    | 300            | Native                                                                           |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                                           |
| 2. Pragmatics, discourse & coreference | Negation                       | Thunder-KoNUBench                                                                                              | 1,284          | Native (Korean Wikipedia, author-written negations)                              |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | Ko-WinoGrande (Open Ko-LLM Leaderboard2)                                                                       | 1,267          | Human translation (professional) + review                                        |
| 3. Commonsense reasoning               | COPA                           | [KB-COPA (KoBEST)](https://huggingface.co/datasets/skt/kobest_v1)                                              | 1,000          | Native                                                                           |
| 3. Commonsense reasoning               | HellaSwag                      | [KB-HellaSwag (KoBEST)](https://huggingface.co/datasets/skt/kobest_v1)                                         | 1,404          | Native                                                                           |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                                       |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                                          |
| 3. Commonsense reasoning               | PIQA                           | Ko-PIQA                                                                                                        | 441            | Native (web-crawled, LLM-filtered, human-validated)                              |
| 3. Commonsense reasoning               | Physical commonsense           | [EPiK](https://huggingface.co/datasets/jjae/EPiK)                                                              | 181            | Native (LLM-generated, expert-certified)                                         |
| 3. Commonsense reasoning               | Physical commonsense           | Ko-PIQA                                                                                                        | 441            | Native (filtered from Naver Knowledge iN, GPT-4o distractors, native validation) |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                                 |
| 4. Reading comprehension               | QA – extractive RC             | [KorQuAD 1.0](https://korquad.github.io/)                                                                      | 5,774          | Native                                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Human translation (professional)                                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | HAE-RAE Bench                                                                                                  | —              | Native                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [KMMLU](https://huggingface.co/datasets/HAERAE-HUB/KMMLU)                                                      | 35,030         | Native (Korean exams)                                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                 | 14,042         | Human translation (professional)                                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                     | —              | Native (local exams/publications)                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                        | 1,000          | Native (cultural; native-speaker answers)                                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                                         |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                              | 1,154          | Native (TyDi questions)                                                          |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)                 |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                                   |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional) of LLM-generated English documents              |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 2,479          | Native (crowdsourced Tatoeba sentence pairs)                                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Human translation (professional) + post-edits                                    |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Korean datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Korean? Does it make sense to train one?
  - ~81.82 GB English-equivalent text ≈ 20.46B tokens, enough for a compute-optimal model of ~1.0B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Korean-only model is 176.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 852 of ~18,460 papers (4.61%) (rank 9 of 252 in the set); English is mentioned in 8,441.
- Search terms: Korean

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 852):

| title                                                                                                                                                                              | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Index-Time Prefix Injection for Multi-Tenant Retrieval: Improving Search Relevance Without Model Fine-Tuning                                                                       | [2026.acl-industry.149](https://aclanthology.org/2026.acl-industry.149/)       |
| Sequence Labeling for Constituent Parsing: A Comparative Study and Encoding Innovations                                                                                            | [2026.cl-2.3](https://aclanthology.org/2026.cl-2.3/)                           |
| Axis-LoRA: Probing and Adapting Embedding Models for Personal-Memory Retrieval                                                                                                     | [2026.emnlp-main.542](https://aclanthology.org/2026.emnlp-main.542/)           |
| Routing Before Looking: Query-Adaptive Evidence Acquisition for Long-form Video Understanding                                                                                      | [2026.findings-emnlp.1984](https://aclanthology.org/2026.findings-emnlp.1984/) |
| Mind the Implicit Gap: Quantifying Attribute Inference Leakage in Privacy-Conscious Delegation                                                                                     | [2026.findings-emnlp.998](https://aclanthology.org/2026.findings-emnlp.998/)   |
| How Much Data for Stable Formant Values? Pipeline for Convergence Detection Based on Read Speech                                                                                   | [2026.lrec-1.470](https://aclanthology.org/2026.lrec-1.470/)                   |
| Surfacing Subtle Stereotypes: A Multilingual, Debate-Oriented Evaluation of Modern LLMs                                                                                            | [2026.lrec-1.643](https://aclanthology.org/2026.lrec-1.643/)                   |
| Cultural and Knowledge Biases in LLMs through the Lens of Entity-Aware Machine Translation                                                                                         | [2026.lrec-1.692](https://aclanthology.org/2026.lrec-1.692/)                   |
| Evaluating Bias in LLM-Synthetic Data across Majority and Minority Groups on General and Stigmatized Topics: The Case of Multicultural and Monocultural Adolescents in South Korea | [2026.nlp4pi-1.15](https://aclanthology.org/2026.nlp4pi-1.15/)                 |
| Beyond the Token: Correcting the Tokenization Bias in XAI via Morphologically-Aligned Projection                                                                                   | [2026.sigturk-1.19](https://aclanthology.org/2026.sigturk-1.19/)               |

{% endraw %}
