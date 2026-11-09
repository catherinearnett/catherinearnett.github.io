---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hrv.html
---
{% raw %}
# So you want to work on Croatian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hrv` · macrolanguage `hbs` (also listed as: Burgenland Croatian)

**Writing systems:** `Latn`

**Official / recognised in:** Austria, Bosnia and Herzegovina, Croatia

**Status:** Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 236,370 articles in hr.wikipedia (rank 40 of 161 in the set) — ~1/32 of English; 1,007 active users                                                                                                                       |
| Common Crawl 2026      | 4,662,570 pages per crawl on average, which is 0.2163% of the crawl. This is ~1/191 of English data and ranks 30 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 17.60 GB (hrv_Latn (17.60)); which is equivalent to ≈17.78 GB English data after byte-premium scaling; 51.73 GB removed by filtering. This is ~1/3,036 of English data and ranks 36 of 248 official languages in FineWeb. |
| Goldfish training data | 7.20 GB (hrv_latn) (rank 32 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.705 (P 0.637, R 0.819, FPR 2.92e-03) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.670).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.637 |    0.819 | 0.705 | 0.003 | ✓                |
| OpenLID-v2   |       0.577 |    0.834 | 0.670 | 0.006 | ✓                |
| fasttext     |       0.502 |    0.878 | 0.629 | 0.008 | ✓                |
| py3langid    |       0.500 |    0.695 | 0.574 | 0.007 | ✓                |
| cld2         |       0.531 |    0.627 | 0.574 | 0.005 | ✓                |
| commonlingua |       0.497 |    0.577 | 0.529 | 0.005 | ✓                |
| funlangid    |       0.401 |    0.530 | 0.450 | 0.007 | ✓                |
| pyfranc      |       0.484 |    0.360 | 0.405 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.577 |    0.487 | 0.528 |
| UDHR-LID  |  58 |       0.479 |    0.983 | 0.644 |
| NTREX     | 300 |       0.651 |    0.840 | 0.734 |
| FLORES    | 300 |       0.713 |    0.860 | 0.779 |
| Wikipedia | 300 |       0.764 |    0.927 | 0.837 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Croatian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Croatian *and* from closely related languages that might be confused with it. Likely confusions to include: Bosnian (`bos`), Montenegrin (`cnr`), Serbian (`srp`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Croatian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Croatian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Croatian (and whether the model is exclusively tagged for Croatian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **442** text-generation models are explicitly tagged for Croatian (114 original uploads, 328 fine-tunes/quantisations/merges).
- **27** are tagged *only* for Croatian.
- Including tags inherited from base models: **891**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        2 | █                    |
|   2023 |       15 | █                    |
|   2024 |       87 | █████████            |
|   2025 |      134 | █████████████        |
|   2026 |      204 | ████████████████████ |

### Most popular models tagged for Croatian

| model                                                                                                     | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct)         | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct)         | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)                     | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |
| [utter-project/EuroLLM-22B-Instruct-2512](https://huggingface.co/utter-project/EuroLLM-22B-Instruct-2512) | 603,901                | 7,106                 | 22.6B        |                   35 |   2025 | utter-project/EuroLLM-22B-2512         |
| [kyutai/helium-1-2b](https://huggingface.co/kyutai/helium-1-2b)                                           | 551,842                | 1,269                 | 2.0B         |                   24 |   2025 | —                                      |

### Most popular models tagged *only* for Croatian

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [macedonizer/hr-gpt2](https://huggingface.co/macedonizer/hr-gpt2)                         | 11,221                 |                    27 | unknown      |                    1 |   2022 | —                    |
| [domsebalj/GPcroaT](https://huggingface.co/domsebalj/GPcroaT)                             | 1,069                  |                    14 | unknown      |                    1 |   2022 | —                    |
| [goldfish-models/hrv_latn_1000mb](https://huggingface.co/goldfish-models/hrv_latn_1000mb) | 543                    |                    34 | unknown      |                    1 |   2024 | —                    |
| [goldfish-models/hrv_latn_5mb](https://huggingface.co/goldfish-models/hrv_latn_5mb)       | 501                    |                    25 | unknown      |                    1 |   2024 | —                    |
| [Shome/croguana-RC2-gguf](https://huggingface.co/Shome/croguana-RC2-gguf)                 | 500                    |                    19 | 7.2B         |                    1 |   2025 | gordicaleksa/YugoGPT |

### Largest models tagged for Croatian

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [CRD716/ggml-LLaMa-65B-quantized](https://huggingface.co/CRD716/ggml-LLaMa-65B-quantized)             | 0                      | 0                     | 65.0B        |                   20 |   2023 | —                                      |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                           | 213                    | 26                    | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |

### Largest models tagged *only* for Croatian

| model                                                                                               |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:---------------------|
| [Shome/croguana-RC2-gguf](https://huggingface.co/Shome/croguana-RC2-gguf)                           |                    500 |                    19 | 7.2B         |                    1 |   2025 | gordicaleksa/YugoGPT |
| [alphaedge-ai/Qwen3.5-4B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-hrv-32768)       |                     56 |                    11 | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-hrv-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-hrv-32768) |                     49 |                     5 | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/Qwen3.5-2B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-hrv-32768)       |                     58 |                    13 | 1.8B         |                    1 |   2026 | Qwen3.5-2B           |
| [alphaedge-ai/Qwen3-1.7B-hrv-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-hrv-32768)       |                     51 |                     6 | 1.5B         |                    1 |   2026 | Qwen3-1.7B           |

_58 tagged models have unknown parameter counts and are not ranked by size._

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

**17** benchmark datasets in the survey include Croatian (plus 1 labelled with the macrolanguage `hbs`, included below).

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
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                          | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                         | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 71             | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`)                     | 3,286          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | COPA                          | [COPA-HR](http://hdl.handle.net/11356/1404)                                                         | 500            | Human translation                                                |
| 3. Commonsense reasoning      | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,471          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 2,879          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| Machine translation           | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 10,498         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation           | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Croatian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Croatian? Does it make sense to train one?
  - ~17.78 GB English-equivalent text ≈ 4.44B tokens, enough for a compute-optimal model of ~222.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Croatian-only model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 129 of ~18,460 papers (0.70%) (rank 47 of 252 in the set); English is mentioned in 8,441.
- Search terms: Croatian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 129):

| title                                                                                                                                       | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Different types of syntactic agreement recruit the same units within large language models                                                  | [2026.acl-long.7](https://aclanthology.org/2026.acl-long.7/)                   |
| One Workflow Does Not Fit All Relations: A System Description for the AKBC 2026 LM-KBC Shared Task                                          | [2026.akbc-1.41](https://aclanthology.org/2026.akbc-1.41/)                     |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                                                    | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)           |
| Sequence Repetition Enhances Token Embeddings and Improves Sequence Labeling with Decoder-only Language Models                              | [2026.findings-eacl.339](https://aclanthology.org/2026.findings-eacl.339/)     |
| What Makes Blood Thicker than Water: Related Word Discrimination in Romance Languages from a Multi-dimensional Perspective                  | [2026.findings-emnlp.1916](https://aclanthology.org/2026.findings-emnlp.1916/) |
| From Oral History to Structured Data: The MalachNER Dataset                                                                                 | [2026.htres-2.7](https://aclanthology.org/2026.htres-2.7/)                     |
| Exploring Social Bias in Slovenia: The EEC-SL Dataset                                                                                       | [2026.lrec-1.318](https://aclanthology.org/2026.lrec-1.318/)                   |
| Pluralistic Annotation of Cultural Weaponization on Wikipedia: A Multi-Annotator Case Study across Ukraine and Armenia                      | [2026.pandora-1.5](https://aclanthology.org/2026.pandora-1.5/)                 |
| Supercharging Agenda Setting Research: The ParlaCAP Dataset of 28 European Parliaments and a Scalable Multilingual LLM-Based Classification | [2026.politicalnlp-1.11](https://aclanthology.org/2026.politicalnlp-1.11/)     |
| OpenLID-v3: Improving the Precision of Closely Related Language Identification – An Experience Report                                       | [2026.vardial-1.23](https://aclanthology.org/2026.vardial-1.23/)               |

{% endraw %}
