---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nld.html
---
{% raw %}
# So you want to work on Dutch?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nld`

**Writing systems:** `Latn`

**Official / recognised in:** Belgium, Kingdom of the Netherlands, Suriname

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,231,210 articles in nl.wikipedia (rank 6 of 161 in the set) — ~1/3 of English; 8,144 active users                                                                                                                         |
| Common Crawl 2026      | 38,521,061 pages per crawl on average, which is 1.7874% of the crawl. This is ~1/23 of English data and ranks 10 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 190.07 GB (nld_Latn (190.07)); which is equivalent to ≈180.74 GB English data after byte-premium scaling; 243.42 GB removed by filtering. This is ~1/281 of English data and ranks 11 of 248 official languages in FineWeb. |
| Goldfish training data | 9.02 GB (nld_latn) (rank 18 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.964, R 0.993, FPR 3.39e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.925).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.964 |    0.993 | 0.978 | 0.000 | ✓                |
| cld2         |       0.931 |    0.928 | 0.925 | 0.001 | ✓                |
| py3langid    |       0.850 |    0.983 | 0.904 | 0.002 | ✓                |
| commonlingua |       0.884 |    0.888 | 0.885 | 0.001 | ✓                |
| funlangid    |       0.888 |    0.869 | 0.878 | 0.001 | ✓                |
| pyfranc      |       0.893 |    0.851 | 0.869 | 0.001 | ✓                |
| fasttext     |       0.742 |    0.991 | 0.834 | 0.004 | ✓                |
| OpenLID-v2   |       0.748 |    0.967 | 0.830 | 0.004 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.925 |    0.980 | 0.951 |
| Wikipedia | 300 |       0.940 |    0.997 | 0.968 |
| CommonLID | 300 |       0.958 |    0.983 | 0.970 |
| UDHR-LID  |  58 |       0.967 |    1.000 | 0.983 |
| NTREX     | 300 |       0.997 |    0.997 | 0.997 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dutch to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dutch *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dutch and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Dutch?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dutch (and whether the model is exclusively tagged for Dutch or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1,568** text-generation models are explicitly tagged for Dutch (373 original uploads, 1,195 fine-tunes/quantisations/merges).
- **139** are tagged *only* for Dutch.
- Including tags inherited from base models: **3,431**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       16 | █                    |
|   2023 |       48 | █                    |
|   2024 |      322 | █████████            |
|   2025 |      495 | ██████████████       |
|   2026 |      687 | ████████████████████ |

### Most popular models tagged for Dutch

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [BioMistral/BioMistral-7B](https://huggingface.co/BioMistral/BioMistral-7B)                       | 1,767,964              | 10,381                | 7.0B         |                    9 |   2024 | —                                      |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b)                     | 1,136,081              | 22,682                | 8.0B         |                   23 |   2024 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |

### Most popular models tagged *only* for Dutch

| model                                                                                   | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [BramVanroy/GEITje-7B-ultra](https://huggingface.co/BramVanroy/GEITje-7B-ultra)         | 58,002                 |                   224 | 7.2B         |                    1 |   2024 | mistralai/Mistral-7B-v0.1 |
| [yhavinga/gpt2-medium-dutch](https://huggingface.co/yhavinga/gpt2-medium-dutch)         | 40,924                 |                   547 | 380.0M       |                    1 |   2022 | —                         |
| [BramVanroy/fietje-2-chat](https://huggingface.co/BramVanroy/fietje-2-chat)             | 25,743                 |                   429 | 2.8B         |                    1 |   2024 | microsoft/phi-2           |
| [antalvdb/bart-base-spelling-nl](https://huggingface.co/antalvdb/bart-base-spelling-nl) | 23,609                 |                    21 | 139.5M       |                    1 |   2023 | —                         |
| [Tweeties/tweety-7b-dutch-v24a](https://huggingface.co/Tweeties/tweety-7b-dutch-v24a)   | 17,820                 |                   352 | 7.4B         |                    1 |   2024 | —                         |

### Largest models tagged for Dutch

| model                                                                                                                           | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                                     |
|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                                 |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                                 |
| [FriendliAI/Mistral-Large-3-675B-Instruct-2512-BF16](https://huggingface.co/FriendliAI/Mistral-Large-3-675B-Instruct-2512-BF16) | 575                    |                    31 | 676.0B       |                   11 |   2025 | mistralai/Mistral-Large-3-675B-Instruct-2512-BF16 |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                         | 604                    |                   604 | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019                   |
| [ai21labs/AI21-Jamba-Large-1.5](https://huggingface.co/ai21labs/AI21-Jamba-Large-1.5)                                           | 57,657                 |                    27 | 398.6B       |                    9 |   2024 | —                                                 |

### Largest models tagged *only* for Dutch

| model                                                                                                                                       |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                              |
|:--------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:-------------------------------------------|
| [BramVanroy/falcon-40b-ft-alpaca-dolly-dutch](https://huggingface.co/BramVanroy/falcon-40b-ft-alpaca-dolly-dutch)                           |                    880 |                    28 | 41.3B        |                    1 |   2023 | tiiuae/falcon-40b                          |
| [MichielBuisman/granite-4.0-h-small-dutch-calibrated-gguf](https://huggingface.co/MichielBuisman/granite-4.0-h-small-dutch-calibrated-gguf) |                    416 |                    30 | 32.2B        |                    1 |   2026 | ibm-granite/granite-4.0-h-small            |
| [MeerDevelopment/gemma-4-31B-it-nl-lora](https://huggingface.co/MeerDevelopment/gemma-4-31B-it-nl-lora)                                     |                     27 |                    27 | 31.0B        |                    1 |   2026 | google/gemma-4-31B-it                      |
| [robinsmits/open_llama_13b_alpaca_clean_dutch_qlora](https://huggingface.co/robinsmits/open_llama_13b_alpaca_clean_dutch_qlora)             |                    610 |                    12 | 13.0B        |                    1 |   2023 | openlm-research/open_llama_13b             |
| [robinsmits/polylm_13b_ft_alpaca_clean_dutch](https://huggingface.co/robinsmits/polylm_13b_ft_alpaca_clean_dutch)                           |                    432 |                    10 | 13.0B        |                    1 |   2023 | DAMO-NLP-MT/polylm-13b-fine-grained-shards |

_98 tagged models have unknown parameter counts and are not ranked by size._

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

**32** benchmark datasets in the survey include Dutch.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [10]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [7]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [6]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [ACS](https://github.com/igorsterner/acs)                                                           | 1,000          | Corpus-extracted + automatic manipulation                        |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMP-NL](https://data.ru.nl/collections/ru/cls/blimp-nl_dsc_550)                                  | 8,400          | Template-based                                                   |
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 1,771          | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,331          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                    | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)        | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)       | 1,000          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)      | [DPR (Dutch Pronoun Resolution, DUMB)](https://github.com/wietsedv/dumb)                            | 1,216          | Native (SemEval-2010 coref recast)                               |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,265          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                    | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 17,138         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dutch datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dutch? Does it make sense to train one?
  - ~180.74 GB English-equivalent text ≈ 45.19B tokens, enough for a compute-optimal model of ~2.3B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Dutch-only model is 41.3B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 584 of ~18,460 papers (3.16%) (rank 12 of 252 in the set); English is mentioned in 8,441.
- Search terms: Dutch

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 584):

| title                                                                                                                        | paper                                                                    |
|:-----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| ALIGN: Word Association Learning for Cultural Alignment in Large Language Models                                             | [2026.acl-long.130](https://aclanthology.org/2026.acl-long.130/)         |
| Augustinian BabyLM: What Ostensive Definition Can and Cannot Teach a Small Language Model                                    | [2026.babylm-main.13](https://aclanthology.org/2026.babylm-main.13/)     |
| LLMs and Cultural Values: The Impact of Prompt Language and Explicit Cultural Framing                                        | [2026.cl-2.2](https://aclanthology.org/2026.cl-2.2/)                     |
| Plausibility as Commonsense Reasoning: Humans Succeed, Large Language Models Do not                                          | [2026.cmcl-1.24](https://aclanthology.org/2026.cmcl-1.24/)               |
| Q-Align: Query-Boundary Multilingual Alignment for LLM Safety Guardrails                                                     | [2026.emnlp-main.240](https://aclanthology.org/2026.emnlp-main.240/)     |
| Preserving Fairness and Safety in Quantized LLMs Through Critical Weight Protection                                          | [2026.findings-acl.993](https://aclanthology.org/2026.findings-acl.993/) |
| The Foggia Occupator Corpus: Digitisation, Annotation, and Computational Analysis of an Occupation-Era Newspaper (1945-1946) | [2026.lrec-1.536](https://aclanthology.org/2026.lrec-1.536/)             |
| HHU-SyLo at SemEval-2026 Task 11: Logic in the Loop – Hybridizing LLMs and Theorem Provers for Robust Formal Reasoning       | [2026.semeval-1.400](https://aclanthology.org/2026.semeval-1.400/)       |
| Seeing Who Is Signing and With Which Hand                                                                                    | [2026.signlang-1.5](https://aclanthology.org/2026.signlang-1.5/)         |
| Fast and Flexible Example-Based Treebank Search with Vector Symbolic Architectures                                           | [2026.slide-1.5](https://aclanthology.org/2026.slide-1.5/)               |

{% endraw %}
