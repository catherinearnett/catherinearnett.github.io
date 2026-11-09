---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ita.html
---
{% raw %}
# So you want to work on Italian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ita`

**Writing systems:** `Latn`

**Official / recognised in:** Italy, San Marino, Switzerland, Vatican City

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,994,311 articles in it.wikipedia (rank 9 of 161 in the set) — ~1/4 of English; 25,562 active users                                                                                                                       |
| Common Crawl 2026      | 52,377,309 pages per crawl on average, which is 2.4298% of the crawl. This is ~1/17 of English data and ranks 8 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 357.05 GB (ita_Latn (357.05)); which is equivalent to ≈334.67 GB English data after byte-premium scaling; 264.43 GB removed by filtering. This is ~1/150 of English data and ranks 8 of 248 official languages in FineWeb. |
| Goldfish training data | 10.16 GB (ita_latn) (rank 9 of 166 in the set)                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.936 (P 0.900, R 0.981, FPR 9.21e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.866).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.900 |    0.981 | 0.936 | 0.001 | ✓                |
| OpenLID-v2   |       0.877 |    0.886 | 0.866 | 0.001 | ✓                |
| fasttext     |       0.791 |    0.982 | 0.861 | 0.003 | ✓                |
| commonlingua |       0.852 |    0.848 | 0.841 | 0.001 | ✓                |
| cld2         |       0.811 |    0.873 | 0.828 | 0.003 | ✓                |
| py3langid    |       0.734 |    0.979 | 0.817 | 0.005 | ✓                |
| pyfranc      |       0.872 |    0.768 | 0.806 | 0.001 | ✓                |
| funlangid    |       0.832 |    0.806 | 0.806 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  58 |       0.725 |    1.000 | 0.841 |
| CommonLID | 300 |       0.850 |    0.927 | 0.887 |
| Wikipedia | 300 |       0.927 |    0.977 | 0.951 |
| Tatoeba   | 300 |       0.925 |    0.983 | 0.953 |
| FLORES    | 300 |       0.971 |    1.000 | 0.985 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Italian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Italian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Italian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Italian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Italian (and whether the model is exclusively tagged for Italian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,590** text-generation models are explicitly tagged for Italian (1,928 original uploads, 5,662 fine-tunes/quantisations/merges).
- **470** are tagged *only* for Italian.
- Including tags inherited from base models: **32,762**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       25 | █                    |
|   2023 |      303 | ██                   |
|   2024 |     2343 | ██████████████████   |
|   2025 |     2307 | ██████████████████   |
|   2026 |     2612 | ████████████████████ |

### Most popular models tagged for Italian

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct)                                     | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)                                     | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                                                       | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct)                                     | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |
| [context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16](https://huggingface.co/context-labs/meta-llama-Llama-3.2-3B-Instruct-FP16) | 27,918,610             | 132                   | 3.2B         |                    8 |   2025 | —                       |

### Most popular models tagged *only* for Italian

| model                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of              |
|:------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------|
| [LorenzoDeMattei/GePpeTto](https://huggingface.co/LorenzoDeMattei/GePpeTto)                                                   | 246,588                | 2,747                 | 121.5M       |                    1 |   2022 | —                          |
| [DeepMount00/Mistral-Ita-7b](https://huggingface.co/DeepMount00/Mistral-Ita-7b)                                               | 113,958                | 1,520                 | 7.2B         |                    1 |   2023 | —                          |
| [swap-uniba/LLaMAntino-2-7b-hf-ITA](https://huggingface.co/swap-uniba/LLaMAntino-2-7b-hf-ITA)                                 | 111,955                | 3,264                 | 6.7B         |                    1 |   2023 | —                          |
| [walid-iguider/Llama-3-8B-4bit-UltraChat-Ita](https://huggingface.co/walid-iguider/Llama-3-8B-4bit-UltraChat-Ita)             | 107,093                | 3,264                 | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B |
| [swap-uniba/LLaMAntino-2-chat-13b-hf-UltraChat-ITA](https://huggingface.co/swap-uniba/LLaMAntino-2-chat-13b-hf-UltraChat-ITA) | 101,416                | 3,312                 | 13.0B        |                    1 |   2023 | —                          |

### Largest models tagged for Italian

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)                       | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [buddalaw/DeepSeek-V4.1-Flash-buddalaw-K160-Q2-GGUF](https://huggingface.co/buddalaw/DeepSeek-V4.1-Flash-buddalaw-K160-Q2-GGUF) | 349                    | 349                   | 754.6B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash   |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark)                   | 2,057                  | 350                   | 751.4B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Italian

| model                                                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF](https://huggingface.co/buddalaw/DeepSeek-V4.1-Flash-buddalaw-K128-Q2-GGUF)               | 314                    | 314                   | 754.6B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash |
| [swap-uniba/LLaMAntino-2-70b-hf-UltraChat-ITA](https://huggingface.co/swap-uniba/LLaMAntino-2-70b-hf-UltraChat-ITA)                           | 62,367                 | 1,757                 | 69.0B        |                    1 |   2024 | —                               |
| [buddalaw/Qwen3.6-27B-buddalaw-UD-Q2-imatrix-GGUF](https://huggingface.co/buddalaw/Qwen3.6-27B-buddalaw-UD-Q2-imatrix-GGUF)                   | 73                     | 15                    | 26.9B        |                    1 |   2026 | Qwen/Qwen3.6-27B                |
| [buddalaw/Qwen3.6-35B-A3B-buddalaw-M179-Q5-imatrix-GGUF-v2](https://huggingface.co/buddalaw/Qwen3.6-35B-A3B-buddalaw-M179-Q5-imatrix-GGUF-v2) | 633                    | 55                    | 25.0B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B            |
| [OpenAdminOS/openadmin-20b-GGUF](https://huggingface.co/OpenAdminOS/openadmin-20b-GGUF)                                                       | 334                    | 10                    | 20.9B        |                    1 |   2026 | openai/gpt-oss-20b              |

_513 tagged models have unknown parameter counts and are not ranked by size._

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

**45** benchmark datasets in the survey include Italian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [17]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [10]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [7]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMP-IT](https://nets-lab.github.io/blimpit-generation/)                                          | 2,899          | Template-based (+ expert review)                                 |
| 1. Linguistic knowledge                | BLiMP                          | [Colorless green (Gulordava et al.)](https://github.com/facebookresearch/colorlessgreenRNNs)        | 119            | Treebank-extracted (+ nonce variants)                            |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,999          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA OpenAI MT (EleutherAI)](https://huggingface.co/datasets/EleutherAI/lambada_openai)         | 5,153          | Machine translation (Google Translate)                           |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                    | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)        | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)       | 1,000          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [WinoGrande (ITA-Bench)](https://huggingface.co/datasets/s-conia/winogrande_italian)                | 1,267          | Machine translation (LLM, OBenTO)                                |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,193          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | HellaSwag                      | [hellaswag_italian](https://huggingface.co/datasets/sapienzanlp/hellaswag_italian)                  | —              | Translation (method not checked)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | Physical commonsense           | [GITA](https://github.com/hitz-zentroa/BasPhyCo)                                                    | 356            | Native (Italian stories, TRIP-style)                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – MC reading comprehension  | [QuandHO (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                     | —              | Native (adapted)                                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [SQuAD-it](https://github.com/crux82/squad-it)                                                      | 7,609          | Machine translation                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 1,256          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 1,236          | Native (national exams)                                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                        | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                      | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [TruthfulQA (ITA-Bench)](https://github.com/SapienzaNLP/ita-bench)                                  | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 29,212         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Italian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Italian? Does it make sense to train one?
  - ~334.67 GB English-equivalent text ≈ 83.67B tokens, enough for a compute-optimal model of ~4.2B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Italian-only model is 754.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1,003 of ~18,460 papers (5.43%) (rank 7 of 252 in the set); English is mentioned in 8,441.
- Search terms: Italian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 1,003):

| title                                                                                                                            | paper                                                                  |
|:---------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| TOWER+: Bridging Generality and Translation Specialization in Multilingual LLMs                                                  | [2026.acl-long.1366](https://aclanthology.org/2026.acl-long.1366/)     |
| Can We Still Trace L1 Signals? Investigating the Resilience of Native Language Signals in the LLM Era                            | [2026.emnlp-main.2042](https://aclanthology.org/2026.emnlp-main.2042/) |
| EVALITA 2026: Overview of the 9th evaluation campaign of natural language processing and speech tools for italian                | [2026.evalita-1.2](https://aclanthology.org/2026.evalita-1.2/)         |
| INFOTEC-NLP at MultiPRIDE: Region-Aware Transformer Models for Spanish Reclaimed Language Classification                         | [2026.evalita-1.27](https://aclanthology.org/2026.evalita-1.27/)       |
| ProverbIT - Easy to complete, hard to choose: A CALAMITA Challenge                                                               | [2026.evalita-1.72](https://aclanthology.org/2026.evalita-1.72/)       |
| Can Linguistically Related Languages Guide LLM Translation in Low-Resource Settings?                                             | [2026.loresmt-1.14](https://aclanthology.org/2026.loresmt-1.14/)       |
| An Enhanced Pipeline for the Manzini-Savoia Dialect Corpus                                                                       | [2026.lrec-1.268](https://aclanthology.org/2026.lrec-1.268/)           |
| RespondeoQA: A Benchmark for Bilingual Latin-English Question Answering                                                          | [2026.lrec-1.80](https://aclanthology.org/2026.lrec-1.80/)             |
| MKJ at SemEval-2026 Task 9: A Comparative Study of Generalist, Specialist, and Ensemble Strategies for Multilingual Polarization | [2026.semeval-1.181](https://aclanthology.org/2026.semeval-1.181/)     |
| Overview of the 11th Social Media Mining for Health (#SMM4H) and Health Real-World Data (HeaRD) Shared Tasks at ACL 2026         | [2026.smm4h-1.53](https://aclanthology.org/2026.smm4h-1.53/)           |

{% endraw %}
