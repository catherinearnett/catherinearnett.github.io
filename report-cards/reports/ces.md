---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ces.html
---
{% raw %}
# So you want to work on Czech?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ces`

**Writing systems:** `Latn`

**Official / recognised in:** Czech Republic

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 601,212 articles in cs.wikipedia (rank 25 of 161 in the set) — ~1/13 of English; 4,549 active users                                                                                                                         |
| Common Crawl 2026      | 24,730,182 pages per crawl on average, which is 1.1474% of the crawl. This is ~1/36 of English data and ranks 12 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 109.98 GB (ces_Latn (109.98)); which is equivalent to ≈106.17 GB English data after byte-premium scaling; 161.70 GB removed by filtering. This is ~1/486 of English data and ranks 15 of 248 official languages in FineWeb. |
| Goldfish training data | 8.25 GB (ces_latn) (rank 24 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.980, R 0.977, FPR 1.98e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.959).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.977 | 0.978 | 0.000 | ✓                |
| cld2         |       0.964 |    0.954 | 0.959 | 0.000 | ✓                |
| OpenLID-v2   |       0.882 |    0.967 | 0.916 | 0.001 | ✓                |
| py3langid    |       0.880 |    0.968 | 0.916 | 0.002 | ✓                |
| commonlingua |       0.912 |    0.879 | 0.895 | 0.001 | ✓                |
| fasttext     |       0.826 |    0.978 | 0.886 | 0.002 | ✓                |
| pyfranc      |       0.959 |    0.721 | 0.811 | 0.000 | ✓                |
| funlangid    |       0.793 |    0.633 | 0.700 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.898 |    0.970 | 0.933 |
| CommonLID | 300 |       0.990 |    0.943 | 0.966 |
| Wikipedia | 300 |       0.993 |    0.947 | 0.969 |
| NTREX     | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Czech to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Czech *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Czech and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Czech?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Czech (and whether the model is exclusively tagged for Czech or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,262** text-generation models are explicitly tagged for Czech (300 original uploads, 962 fine-tunes/quantisations/merges).
- **78** are tagged *only* for Czech.
- Including tags inherited from base models: **2,339**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       12 | █                    |
|   2023 |       33 | █                    |
|   2024 |      212 | ███████              |
|   2025 |      423 | ███████████████      |
|   2026 |      582 | ████████████████████ |

### Most popular models tagged for Czech

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)             | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |

### Most popular models tagged *only* for Czech

| model                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                |
|:------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-----------------------------|
| [jinymusim/gpt-czech-poet](https://huggingface.co/jinymusim/gpt-czech-poet)   | 131,443                | 120                   | 124.4M       |                    1 |   2023 | lchaloupsky/czech-gpt2-oscar |
| [MU-NLPC/CzeGPT-2](https://huggingface.co/MU-NLPC/CzeGPT-2)                   | 83,698                 | 2,039                 | 137.0M       |                    1 |   2022 | —                            |
| [StanfordAIMI/CheXagent-8b](https://huggingface.co/StanfordAIMI/CheXagent-8b) | 68,934                 | 918                   | 8.4B         |                    1 |   2023 | —                            |
| [BUT-FIT/csmpt7b](https://huggingface.co/BUT-FIT/csmpt7b)                     | 24,434                 | 798                   | 6.7B         |                    1 |   2024 | —                            |
| [fav-kky/gpt2-small-cs](https://huggingface.co/fav-kky/gpt2-small-cs)         | 14,466                 | 888                   | 42.9M        |                    1 |   2022 | —                            |

### Largest models tagged for Czech

| model                                                                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                         | 604                    | 604                   | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019        |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                           | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16) | 122,649                | 9,704                 | 123.6B       |                   20 |   2026 | —                                      |

### Largest models tagged *only* for Czech

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:------------------------------|
| [OJBLCZ/Qwen3.8-27B-Czech-4bit](https://huggingface.co/OJBLCZ/Qwen3.8-27B-Czech-4bit)                         | 58                     |                    58 | 26.9B        |                    1 |   2026 | oriyonay/Qwen3.8-27B-bnb-4bit |
| [vishinvents/OpenEuroLLM-Czech-Ollama-GGUF](https://huggingface.co/vishinvents/OpenEuroLLM-Czech-Ollama-GGUF) | 6,689                  |                   867 | 12.2B        |                    1 |   2026 | —                             |
| [Neptune1722/CheXagent-nf4-quantized](https://huggingface.co/Neptune1722/CheXagent-nf4-quantized)             | 106                    |                    16 | 8.6B         |                    1 |   2024 | —                             |
| [StanfordAIMI/CheXagent-8b](https://huggingface.co/StanfordAIMI/CheXagent-8b)                                 | 68,934                 |                   918 | 8.4B         |                    1 |   2023 | —                             |
| [ssmits/Falcon2-8B-Czech](https://huggingface.co/ssmits/Falcon2-8B-Czech)                                     | 274                    |                    14 | 8.1B         |                    1 |   2024 | tiiuae/falcon-11B             |

_97 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Czech.

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
         /       reasoning [5]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [3]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 1,213          | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 4,256          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                                  | 2,600          | Machine translation (DeepL) + sample check                       |
| 2. Pragmatics, discourse & coreference | Negation                       | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                                   | 6,261          | Machine translation (DeepL) + sample check                       |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                              | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | MT + community post-editing                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CUS-QA](https://huggingface.co/datasets/ufal/cus-qa)                                                             | 1,536          | Native (regional knowledge)                                      |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 18,434         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Original WMT24 reference + new post-edits                        |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Czech datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Czech? Does it make sense to train one?
  - ~106.17 GB English-equivalent text ≈ 26.54B tokens, enough for a compute-optimal model of ~1.3B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Czech-only model is 26.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 452 of ~18,460 papers (2.45%) (rank 14 of 252 in the set); English is mentioned in 8,441.
- Search terms: Czech

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 452):

| title                                                                                                                  | paper                                                                  |
|:-----------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| IGenBench: Benchmarking the Reliability of Text-to-Infographic Generation                                              | [2026.acl-long.1713](https://aclanthology.org/2026.acl-long.1713/)     |
| The Infrastructure behind Latvian National Corpora Collection                                                          | [2026.cmlc-1.5](https://aclanthology.org/2026.cmlc-1.5/)               |
| Towards Consistent UMR Annotation of Deverbal Nouns: Evidence from Czech and Latin                                     | [2026.dmr-1.6](https://aclanthology.org/2026.dmr-1.6/)                 |
| Leveraging Routing Dynamics in Mixture-of-Experts Models for Efficient Language Adaptation                             | [2026.emnlp-main.2407](https://aclanthology.org/2026.emnlp-main.2407/) |
| AIC CTU@AVerImaTeC: dual-retriever RAG for image-text fact checking                                                    | [2026.fever-1.11](https://aclanthology.org/2026.fever-1.11/)           |
| SlovKE: A Large-Scale Dataset and LLM Evaluation for Slovak Keyphrase Extraction                                       | [2026.lrec-1.283](https://aclanthology.org/2026.lrec-1.283/)           |
| From CHAT to Coded CoNLL-U: A Reproducible Pipeline for the Syntactic Annotation and Querying of Child Language Data   | [2026.lrec-1.901](https://aclanthology.org/2026.lrec-1.901/)           |
| POS Tagging with Generative LLMs for Historical Germanic Low-Resource Languages: An Evaluation Against Fine-Tuned BERT | [2026.lt4hala-1.12](https://aclanthology.org/2026.lt4hala-1.12/)       |
| A Proposal for a More Universal Annotation of Relative Clauses in Universal Dependencies                               | [2026.udw-1.16](https://aclanthology.org/2026.udw-1.16/)               |
| Gathering valency frames for annotation and batch corrections                                                          | [2026.udw-1.26](https://aclanthology.org/2026.udw-1.26/)               |

{% endraw %}
