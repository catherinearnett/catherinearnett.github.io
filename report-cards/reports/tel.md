---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tel.html
---
{% raw %}
# So you want to work on Telugu?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tel`

**Writing systems:** `Telu`

**Official / recognised in:** India, South Africa

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                  |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 130,448 articles in te.wikipedia (rank 51 of 161 in the set) — ~1/58 of English; 318 active users                                                                                                                                       |
| Common Crawl 2026      | 450,946 pages per crawl on average, which is 0.0209% of the crawl. This is ~1/1,977 of English data and ranks 47 of 113 official languages in Common Crawl.                                                                             |
| FineWeb                | 4.04 GB (tel_Latn (0.05); tel_Telu (3.99)); which is equivalent to ≈1.52 GB English data after byte-premium scaling; 6.21 GB removed by filtering. This is ~1/13,233 of English data and ranks 53 of 248 official languages in FineWeb. |
| Goldfish training data | 5.84 GB (tel_telu) (rank 33 of 166 in the set)                                                                                                                                                                                          |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.999 (P 0.999, R 0.999, FPR 1.51e-05) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.999).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.999 | 0.999 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| cld2         |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| py3langid    |       1.000 |    0.997 | 0.999 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.996 | 0.998 | 0.000 | ✓                |
| commonlingua |       0.998 |    0.996 | 0.997 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.986 | 0.993 | 0.000 | ✗                |
| funlangid    |       0.970 |    0.916 | 0.941 | 0.000 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.997 |    0.997 | 0.997 |
| Wikipedia | 300 |       1.000 |    0.997 | 0.998 |
| Tatoeba   | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Telugu to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Telugu *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Telugu and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Telugu?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Telugu (and whether the model is exclusively tagged for Telugu or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **701** text-generation models are explicitly tagged for Telugu (243 original uploads, 458 fine-tunes/quantisations/merges).
- **114** are tagged *only* for Telugu.
- Including tags inherited from base models: **1,067**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       42 | ██                   |
|   2023 |       33 | ██                   |
|   2024 |       99 | ██████               |
|   2025 |      189 | ███████████          |
|   2026 |      338 | ████████████████████ |

### Most popular models tagged for Telugu

| model                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m) | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom-560m](https://huggingface.co/bigscience/bloom-560m)   | 27,007,025             | 377,922               | 559.2M       |                   35 |   2022 | —               |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)             | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —               |
| [bigscience/bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)     | 3,688,796              | 2,877                 | 7.1B         |                   35 |   2022 | —               |
| [bigscience/bloom-1b7](https://huggingface.co/bigscience/bloom-1b7)     | 3,135,379              | 2,904                 | 1.7B         |                   35 |   2022 | —               |

### Most popular models tagged *only* for Telugu

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------|
| [jayasuryajsk/Llama-3-8b-Telugu-Romanized](https://huggingface.co/jayasuryajsk/Llama-3-8b-Telugu-Romanized) | 2,812                  | 19                    | 8.0B         |                    1 |   2024 | —               |
| [jayasuryajsk/Llama-3-telugu](https://huggingface.co/jayasuryajsk/Llama-3-telugu)                           | 2,417                  | 164                   | 8.0B         |                    1 |   2024 | —               |
| [mradermacher/Kavya-1-7B-GGUF](https://huggingface.co/mradermacher/Kavya-1-7B-GGUF)                         | 1,362                  | 380                   | 7.6B         |                    1 |   2026 | Qwen/Qwen2.5-7B |
| [udgamlabs/Vemana-Base](https://huggingface.co/udgamlabs/Vemana-Base)                                       | 1,049                  | 1,049                 | 278.2M       |                    1 |   2026 | —               |
| [samvaran/chandohasam](https://huggingface.co/samvaran/chandohasam)                                         | 842                    | 538                   | 120.0M       |                    1 |   2026 | —               |

### Largest models tagged for Telugu

| model                                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                   | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                       | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [diablomike20/command-a-plus-05-2026-GGUF](https://huggingface.co/diablomike20/command-a-plus-05-2026-GGUF) | 2,352                  | 2,352                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [bigscience/bloom](https://huggingface.co/bigscience/bloom)                                                 | 4,907,569              | 9,383                 | 176.2B       |                   35 |   2022 | —                                      |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                                       | 109                    | 13                    | 176.2B       |                   35 |   2026 | —                                      |

### Largest models tagged *only* for Telugu

| model                                                                                                                               | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Qwen3-14B-Base-te-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Qwen3-14B-Base-te-madlad-mean-tuned) | 83                     |                     8 | 14.9B        |                    1 |   2025 | Qwen/Qwen3-14B-Base     |
| [bharadwajswarna/Zephyr-Gemma-7B-Telugu](https://huggingface.co/bharadwajswarna/Zephyr-Gemma-7B-Telugu)                             | 425                    |                    47 | 8.5B         |                    1 |   2024 | —                       |
| [saucam/Navrasa-2.0-Rudra-7b-dare-ties](https://huggingface.co/saucam/Navrasa-2.0-Rudra-7b-dare-ties)                               | 84                     |                    11 | 8.5B         |                    1 |   2024 | google/gemma-7b         |
| [atsuki-yamaguchi/Llama-3.1-8B-te-madlad-mean-tuned](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-te-madlad-mean-tuned)     | 139                    |                     6 | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [jayasuryajsk/Llama-3-telugu](https://huggingface.co/jayasuryajsk/Llama-3-telugu)                                                   | 2,417                  |                   164 | 8.0B         |                    1 |   2024 | —                       |

_95 tagged models have unknown parameter counts and are not ranked by size._

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

**33** benchmark datasets in the survey include Telugu.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [9]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [5]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [9]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [8]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                        |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MIDI / MultIdiom](https://huggingface.co/datasets/Almheiri/MultIdiom)                                     | —              | Native (curated by native speakers; generated contexts + MCQs)      |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 8,724          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                      | 1,511          | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 10,489         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)                      | 1,734          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | TeQuAD                                                                                                     | 82,000         | Translation (SQuAD → Telugu)                                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                      | 14,042         | MT + community post-editing                                         |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                              | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 7,304          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                          | 1,087          | Native (TyDi questions)                                             |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                             | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 262            | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Telugu datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Telugu? Does it make sense to train one?
  - ~2.23 GB English-equivalent text ≈ 0.56B tokens, enough for a compute-optimal model of ~27.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Telugu-only model is 14.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 256 of ~18,460 papers (1.39%) (rank 29 of 252 in the set); English is mentioned in 8,441.
- Search terms: Telugu

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 256):

| title                                                                                                                   | paper                                                                              |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| The Reasoning Lingua Franca: A Double-Edged Sword for Multilingual AI                                                   | [2026.eacl-short.25](https://aclanthology.org/2026.eacl-short.25/)                 |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                             | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)             |
| VLURes: Benchmarking Long-Text Grounding and Cross-Lingual Robustness in Vision Language Models                         | [2026.findings-acl.1367](https://aclanthology.org/2026.findings-acl.1367/)         |
| Better as Generators Than Classifiers: Leveraging LLMs and Synthetic Data for Low-Resource Multilingual Classification  | [2026.findings-eacl.148](https://aclanthology.org/2026.findings-eacl.148/)         |
| XLGoBench: Detecting cross-lingual skill gaps with algorithmic tasks                                                    | [2026.findings-emnlp.2139](https://aclanthology.org/2026.findings-emnlp.2139/)     |
| Mind the Gap... or Not? How Translation Errors and Evaluation Details Skew Multilingual Results                         | [2026.gem-main.22](https://aclanthology.org/2026.gem-main.22/)                     |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                              | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)                     |
| Contextualizing Toxicity: An Annotation Framework for Unveiling Pragmatics in Conversations of Online Discussion Forums | [2026.lrec-1.314](https://aclanthology.org/2026.lrec-1.314/)                       |
| Algebraic Classification of Reduplicative Processes                                                                     | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)                   |
| Annotating Indian Regional Biases using Large Language Models: Evaluation and Analysis                                  | [2026.starsem-conference.16](https://aclanthology.org/2026.starsem-conference.16/) |

{% endraw %}
