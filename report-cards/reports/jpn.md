---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/jpn.html
---
{% raw %}
# So you want to work on Japanese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `jpn`

**Writing systems:** `Jpan`

**Official / recognised in:** Japan

**Status:** De facto official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,526,339 articles in ja.wikipedia (rank 11 of 161 in the set) — ~1/5 of English; 23,391 active users                                                                                                                       |
| Common Crawl 2026      | 116,145,534 pages per crawl on average, which is 5.3887% of the crawl. This is ~1/8 of English data and ranks 4 of 113 official languages in Common Crawl.                                                                  |
| FineWeb                | 716.70 GB (jpn_Jpan (716.70)); which is equivalent to ≈542.14 GB English data after byte-premium scaling; 1,292.06 GB removed by filtering. This is ~1/75 of English data and ranks 5 of 248 official languages in FineWeb. |
| Goldfish training data | 13.59 GB (jpn_jpan) (rank 2 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=143), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.995 (P 0.996, R 0.994, FPR 3.84e-05) averaged over 6 dataset(s). Runner-up: GlotLID (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.996 |    0.994 | 0.995 | 0.000 | ✓                |
| GlotLID      |       0.991 |    0.992 | 0.992 | 0.000 | ✓                |
| pyfranc      |       0.998 |    0.967 | 0.982 | 0.000 | ✗                |
| commonlingua |       0.965 |    0.994 | 0.979 | 0.001 | ✓                |
| funlangid    |       0.962 |    0.991 | 0.976 | 0.000 | ✓                |
| cld2         |       0.959 |    0.996 | 0.975 | 0.000 | ✓                |
| OpenLID-v2   |       0.941 |    0.993 | 0.965 | 0.001 | ✓                |
| fasttext     |       0.914 |    0.905 | 0.897 | 0.002 | ✓                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.967 | 0.983 |
| Wikipedia | 300 |       0.977 |    1.000 | 0.988 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 143 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Japanese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Japanese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Japanese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Japanese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Japanese (and whether the model is exclusively tagged for Japanese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,448** text-generation models are explicitly tagged for Japanese (1,940 original uploads, 5,508 fine-tunes/quantisations/merges).
- **1,080** are tagged *only* for Japanese.
- Including tags inherited from base models: **16,414**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       48 | █                    |
|   2023 |      404 | ██                   |
|   2024 |     1642 | ██████████           |
|   2025 |     2019 | ████████████         |
|   2026 |     3335 | ████████████████████ |

### Most popular models tagged for Japanese

| model                                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [nvidia/NVIDIA-Nemotron-3-Nano-30B-A3B-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Nano-30B-A3B-BF16)         | 11,885,844             | 1,586,743             | 31.6B        |                    6 |   2025 | —               |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-NVFP4](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-NVFP4) | 10,754,911             | 445,133               | 67.2B        |                    7 |   2026 | —               |
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)                                   | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —               |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-BF16)   | 7,708,737              | 1,042,412             | 123.6B       |                    7 |   2026 | —               |
| [rinna/japanese-gpt-neox-small](https://huggingface.co/rinna/japanese-gpt-neox-small)                                   | 5,106,466              | 519,734               | 203.6M       |                    1 |   2022 | —               |

### Most popular models tagged *only* for Japanese

| model                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [rinna/japanese-gpt-neox-small](https://huggingface.co/rinna/japanese-gpt-neox-small) | 5,106,466              | 519,734               | 203.6M       |                    1 |   2022 | —               |
| [cyberagent/open-calm-3b](https://huggingface.co/cyberagent/open-calm-3b)             | 1,434,723              | 655                   | 3.0B         |                    1 |   2023 | —               |
| [abeja/gpt-neox-japanese-2.7b](https://huggingface.co/abeja/gpt-neox-japanese-2.7b)   | 995,347                | 3,332                 | 2.7B         |                    1 |   2022 | —               |
| [rinna/japanese-gpt2-medium](https://huggingface.co/rinna/japanese-gpt2-medium)       | 807,021                | 5,004                 | 361.3M       |                    1 |   2022 | —               |
| [rinna/japanese-gpt-1b](https://huggingface.co/rinna/japanese-gpt-1b)                 | 785,767                | 1,533                 | 1.3B         |                    1 |   2022 | —               |

### Largest models tagged for Japanese

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF](https://huggingface.co/GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF)   | 291                    | 72                    | 2.8T         |                    3 |   2026 | Uniboshi/Kimi-K3-Abliterated-V1   |
| [hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF](https://huggingface.co/hellohazime/Kimi-K3-REAP640ja-IQ1_S-GGUF) | 766                    | 40                    | 2.0T         |                    2 |   2026 | unsloth/Kimi-K3-GGUF              |
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [sakamakismile/Nex-N2.5-Max-GGUF](https://huggingface.co/sakamakismile/Nex-N2.5-Max-GGUF)                   | 292                    | 21                    | 1.6T         |                    3 |   2026 | nex-agi/Nex-N2.5-Max              |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)   | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |

### Largest models tagged *only* for Japanese

| model                                                                                                                           |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [mmnga-o/Kimi-K3-REAP50-UD-gguf](https://huggingface.co/mmnga-o/Kimi-K3-REAP50-UD-gguf)                                         |                    728 |                    39 | 1.4T         |                    1 |   2026 | unsloth/Kimi-K3-GGUF               |
| [weblab-LLM-M/Weblab-MedLLM-GLM-4.7](https://huggingface.co/weblab-LLM-M/Weblab-MedLLM-GLM-4.7)                                 |                    115 |                    25 | 352.8B       |                    1 |   2026 | —                                  |
| [weblab-llm-competition-2025-bridge/RAMEN-SHIO-235B](https://huggingface.co/weblab-llm-competition-2025-bridge/RAMEN-SHIO-235B) |                    176 |                    13 | 235.1B       |                    1 |   2025 | Qwen/Qwen3-235B-A22B-Thinking-2507 |
| [team-suzuki/Qwen3-235B-A22B_SFT_004_origin_1](https://huggingface.co/team-suzuki/Qwen3-235B-A22B_SFT_004_origin_1)             |                    188 |                    10 | 235.1B       |                    1 |   2025 | Qwen/Qwen3-235B-A22B               |
| [weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Instruct](https://huggingface.co/weblab-LLM-M/Weblab-MedLLM-Qwen3-235B-Instruct)         |                     16 |                     8 | 235.1B       |                    1 |   2026 | —                                  |

_546 tagged models have unknown parameter counts and are not ranked by size._

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

**34** benchmark datasets in the survey include Japanese.

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
         /       reasoning [5]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [7]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                                | dataset                                                                                             | # test items   | Construction                                                        |
|:---------------------------------------|:------------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                               | [JBLiMP](https://github.com/osekilab/JBLiMP)                                                        | 331            | Existing material (extracted from linguistics journals)             |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms        | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                              | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | Presupposition & scalar implicature | Japanese numeral-expression inference set (Koyano et al.)                                           | —              | Native (from annotated treebank)                                    |
| 2. Pragmatics, discourse & coreference | WSC                                 | Japanese WSC                                                                                        | —              | Human translation                                                   |
| 2. Pragmatics, discourse & coreference | WSC                                 | Japanese WSC – ChatGPT vs humans study (CHI '24 EA)                                                 | —              | Human translation (existing JWSC)                                   |
| 2. Pragmatics, discourse & coreference | WSC                                 | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                    | —              | Human translation (collected)                                       |
| 2. Pragmatics, discourse & coreference | WSC                                 | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                  | 959            | Human translation (collected)                                       |
| 2. Pragmatics, discourse & coreference | WinoGrande                          | [Japanese WinoGrande (jwinogrande)](https://huggingface.co/datasets/weblab-GENIAC/jwinogrande)      | 97             | Translation                                                         |
| 3. Commonsense reasoning               | HellaSwag                           | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                          | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | Temporal reasoning                  | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases              |
| 4. Reading comprehension               | QA – MC reading comprehension       | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC                  | [JSQuAD (JGLUE)](https://github.com/yahoojapan/JGLUE)                                               | 4,442          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC                  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [JMMLU](https://github.com/nlp-waseda/JMMLU)                                                        | 7,536          | MT + human edit (+ native Japanese subjects)                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ             | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book      | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                   | 1,318          | Native (TyDi questions)                                             |
| Machine translation                    | Machine translation                 | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation                 | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation                 | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation                 | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation                 | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation                 | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 20,796         | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation                 | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Original WMT24 reference + new post-edits                           |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Pronoun/coref (WSC-style), WNLI
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Japanese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Japanese? Does it make sense to train one?
  - ~542.14 GB English-equivalent text ≈ 135.54B tokens, enough for a compute-optimal model of ~6.8B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Japanese-only model is 1.4T, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,111 of ~18,460 papers (6.01%) (rank 6 of 252 in the set); English is mentioned in 8,441.
- Search terms: Japanese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,111):

| title                                                                                                                                          | paper                                                                      |
|:-----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Somatic in the East, Psychological in the West?: A Clinically-Grounded Evaluation of Cross-Cultural Depression Symptoms in LLMs                | [2026.c3nlp-1.2](https://aclanthology.org/2026.c3nlp-1.2/)                 |
| A Method for Learning Large-Scale Computational Construction Grammars from Semantically Annotated Corpora                                      | [2026.conll-main.13](https://aclanthology.org/2026.conll-main.13/)         |
| Portuguese-IFEval: Instruction-Following Evaluation in Portuguese                                                                              | [2026.emnlp-main.742](https://aclanthology.org/2026.emnlp-main.742/)       |
| Subjective and Hierarchical Annotation of Text Difficulty in Japanese                                                                          | [2026.emnlp-main.926](https://aclanthology.org/2026.emnlp-main.926/)       |
| ILSIC: Corpora for Identifying Indian Legal Statutes from Queries by Laymen                                                                    | [2026.findings-eacl.354](https://aclanthology.org/2026.findings-eacl.354/) |
| Investigating the Automatic Translation of Korean Honorifics                                                                                   | [2026.iaai-1.3](https://aclanthology.org/2026.iaai-1.3/)                   |
| Evaluating Discriminability of Vision-Language Models                                                                                          | [2026.lrec-1.736](https://aclanthology.org/2026.lrec-1.736/)               |
| PAINT: A Framework for Multilingual Pain Representation from Medical Licensing Exams to Real-World Clinical Texts                              | [2026.mrl-1.51](https://aclanthology.org/2026.mrl-1.51/)                   |
| Scmhl5 at SemEval-2026 Task 3: Uncertainty-Aware Adversarial Learning for Embedding Enhancement in Dimensional Aspect-Based Sentiment Analysis | [2026.semeval-1.222](https://aclanthology.org/2026.semeval-1.222/)         |
| Quantifying Social Sentiment in Hostels Using A Domain-Specific Transformer Pipeline                                                           | [2026.wassa-1.3](https://aclanthology.org/2026.wassa-1.3/)                 |

{% endraw %}
