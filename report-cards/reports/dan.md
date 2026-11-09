---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dan.html
---
{% raw %}
# So you want to work on Danish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dan`

**Writing systems:** `Latn`

**Official / recognised in:** Denmark

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                  |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 316,593 articles in da.wikipedia (rank 32 of 161 in the set) — ~1/24 of English; 1,497 active users                                                                                                                     |
| Common Crawl 2026      | 11,221,514 pages per crawl on average, which is 0.5208% of the crawl. This is ~1/79 of English data and ranks 21 of 113 official languages in Common Crawl.                                                             |
| FineWeb                | 70.63 GB (dan_Latn (70.63)); which is equivalent to ≈69.18 GB English data after byte-premium scaling; 79.04 GB removed by filtering. This is ~1/756 of English data and ranks 24 of 248 official languages in FineWeb. |
| Goldfish training data | 7.79 GB (dan_latn) (rank 28 of 166 in the set)                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: cld2, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.957 (P 0.942, R 0.972, FPR 6.09e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.899).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.942 |    0.972 | 0.957 | 0.001 | ✓                |
| cld2         |       0.910 |    0.894 | 0.899 | 0.001 | ✓                |
| funlangid    |       0.841 |    0.523 | 0.643 | 0.001 | ✓                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.884 |    0.917 | 0.900 |
| UDHR-LID  |  61 |       0.923 |    0.984 | 0.952 |
| Wikipedia | 300 |       0.927 |    0.980 | 0.953 |
| NTREX     | 300 |       0.987 |    0.987 | 0.987 |
| FLORES    | 300 |       0.990 |    0.993 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Danish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Danish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Danish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Danish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Danish (and whether the model is exclusively tagged for Danish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **835** text-generation models are explicitly tagged for Danish (231 original uploads, 604 fine-tunes/quantisations/merges).
- **87** are tagged *only* for Danish.
- Including tags inherited from base models: **1,973**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       14 | █                    |
|   2023 |       46 | ███                  |
|   2024 |      185 | ████████████         |
|   2025 |      284 | ███████████████████  |
|   2026 |      306 | ████████████████████ |

### Most popular models tagged for Danish

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [bineric/lynx-instruct-30b](https://huggingface.co/bineric/lynx-instruct-30b)                     | 1,242,663              | 1,313                 | 30.5B        |                    5 |   2026 | Qwen/Qwen3-30B-A3B-Instruct-2507       |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |

### Most popular models tagged *only* for Danish

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [flax-community/dansk-gpt-wiki](https://huggingface.co/flax-community/dansk-gpt-wiki)     | 131,378                |                   266 | 137.0M       |                    1 |   2022 | —                           |
| [mhenrichsen/danskgpt-tiny](https://huggingface.co/mhenrichsen/danskgpt-tiny)             | 38,335                 |                   734 | 1.1B         |                    1 |   2024 | —                           |
| [mhenrichsen/hestenettetLM](https://huggingface.co/mhenrichsen/hestenettetLM)             | 27,689                 |                    48 | 7.2B         |                    1 |   2023 | —                           |
| [KennethTM/gpt2-medium-danish](https://huggingface.co/KennethTM/gpt2-medium-danish)       | 10,008                 |                   211 | 354.8M       |                    1 |   2023 | —                           |
| [afrideva/gpt2-small-danish-GGUF](https://huggingface.co/afrideva/gpt2-small-danish-GGUF) | 4,482                  |                   617 | 163.0M       |                    1 |   2023 | KennethTM/gpt2-small-danish |

### Largest models tagged for Danish

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                           | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16) | 122,649                | 9,704                 | 123.6B       |                   20 |   2026 | —                                      |
| [Unbabel/Tower-Plus-72B](https://huggingface.co/Unbabel/Tower-Plus-72B)                                                         | 13,521                 | 95                    | 72.7B        |                   22 |   2025 | Qwen/Qwen2.5-72B                       |

### Largest models tagged *only* for Danish

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of              |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------------|
| [syvai/danskgpt-v4-31b](https://huggingface.co/syvai/danskgpt-v4-31b)                                         | 219                    |                    41 | 30.7B        |                    1 |   2026 | google/gemma-4-31B-it      |
| [Hodfa71/viking-13b-da-saga-delta-dpo](https://huggingface.co/Hodfa71/viking-13b-da-saga-delta-dpo)           | 37                     |                     6 | 13.0B        |                    1 |   2026 | LumiOpen/Viking-13B        |
| [syvai/danskgpt-v4-12b](https://huggingface.co/syvai/danskgpt-v4-12b)                                         | 400                    |                    36 | 11.9B        |                    1 |   2026 | google/gemma-4-12B-it      |
| [DenisTheDev/Openchat-Passthrough-SLERP](https://huggingface.co/DenisTheDev/Openchat-Passthrough-SLERP)       | 83                     |                    10 | 10.7B        |                    1 |   2024 | —                          |
| [emillykkejensen/Llama-3-8B-instruct-dansk](https://huggingface.co/emillykkejensen/Llama-3-8B-instruct-dansk) | 1,431                  |                    30 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |

_77 tagged models have unknown parameter counts and are not ranked by size._

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

**22** benchmark datasets in the survey include Danish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [5]     \
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
   /   knowledge [4]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 330            | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 55             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [DaLA](https://huggingface.co/datasets/giannor/dala)                                                | 1,664          | Treebank-based + automatic corruption                            |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 50             | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,305          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 12,678         | Native (crowdsourced Tatoeba sentence pairs)                     |
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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Danish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Danish? Does it make sense to train one?
  - ~69.18 GB English-equivalent text ≈ 17.29B tokens, enough for a compute-optimal model of ~864.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Danish-only model is 30.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 214 of ~18,460 papers (1.16%) (rank 31 of 252 in the set); English is mentioned in 8,441.
- Search terms: Danish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 214):

| title                                                                                                           | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                       | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/)             |
| Learning Nested Named Entity Recognition from Flat Annotations                                                  | [2026.eacl-srw.50](https://aclanthology.org/2026.eacl-srw.50/)                 |
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model          | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Multi-turn Conversational AI from Text to Multimodal Interaction: Data, Models, Evaluation, and Open Challenges | [2026.findings-emnlp.2467](https://aclanthology.org/2026.findings-emnlp.2467/) |
| Scenario-based Probing and Steering Cultural Values in Large Language Models                                    | [2026.findings-emnlp.858](https://aclanthology.org/2026.findings-emnlp.858/)   |
| GPT-NL Public Corpus: A Permissively Licensed, Dutch-First Dataset for LLM Pre-training                         | [2026.lrec-1.548](https://aclanthology.org/2026.lrec-1.548/)                   |
| Multilingual Datasets for Augmentative and Alternative Communication                                            | [2026.mrl-1.31](https://aclanthology.org/2026.mrl-1.31/)                       |
| Naturalistic Measure of Social Norms Alignment                                                                  | [2026.oracle-main.34](https://aclanthology.org/2026.oracle-main.34/)           |
| Byte-pair Encoding Captures Aspects of Word Meaning that Distributional Semantics Overlooks                     | [2026.tacl-1.113](https://aclanthology.org/2026.tacl-1.113/)                   |

{% endraw %}
