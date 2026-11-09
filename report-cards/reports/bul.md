---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bul.html
---
{% raw %}
# So you want to work on Bulgarian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bul`

**Writing systems:** `Cyrl`

**Official / recognised in:** Bulgaria

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 312,933 articles in bg.wikipedia (rank 33 of 161 in the set) — ~1/24 of English; 1,806 active users                                                                                                                       |
| Common Crawl 2026      | 6,062,008 pages per crawl on average, which is 0.2814% of the crawl. This is ~1/147 of English data and ranks 26 of 113 official languages in Common Crawl.                                                               |
| FineWeb                | 49.12 GB (bul_Cyrl (49.12)); which is equivalent to ≈27.10 GB English data after byte-premium scaling; 40.66 GB removed by filtering. This is ~1/1,088 of English data and ranks 26 of 248 official languages in FineWeb. |
| Goldfish training data | 9.69 GB (bul_cyrl) (rank 13 of 166 in the set)                                                                                                                                                                            |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=109), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.983 (P 0.985, R 0.982, FPR 1.17e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.958).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.985 |    0.982 | 0.983 | 0.000 | ✓                |
| fasttext     |       0.936 |    0.986 | 0.958 | 0.001 | ✓                |
| cld2         |       0.951 |    0.899 | 0.922 | 0.000 | ✓                |
| commonlingua |       0.922 |    0.883 | 0.901 | 0.001 | ✓                |
| OpenLID-v2   |       0.849 |    0.974 | 0.897 | 0.002 | ✓                |
| py3langid    |       0.780 |    0.962 | 0.849 | 0.004 | ✓                |
| pyfranc      |       0.725 |    0.821 | 0.768 | 0.004 | ✓                |
| funlangid    |       0.719 |    0.806 | 0.752 | 0.003 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 109 |       0.971 |    0.917 | 0.943 |
| Tatoeba   | 300 |       0.951 |    0.980 | 0.966 |
| Wikipedia | 300 |       0.990 |    1.000 | 0.995 |
| NTREX     | 300 |       0.997 |    0.997 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bulgarian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bulgarian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bulgarian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bulgarian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bulgarian (and whether the model is exclusively tagged for Bulgarian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **508** text-generation models are explicitly tagged for Bulgarian (152 original uploads, 356 fine-tunes/quantisations/merges).
- **46** are tagged *only* for Bulgarian.
- Including tags inherited from base models: **975**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       17 | ██                   |
|   2023 |       29 | ███                  |
|   2024 |      117 | ████████████         |
|   2025 |      151 | ████████████████     |
|   2026 |      194 | ████████████████████ |

### Most popular models tagged for Bulgarian

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [facebook/xglm-564M](https://huggingface.co/facebook/xglm-564M)                                   | 1,709,301              | 8,655                 | 564.0M       |                   30 |   2022 | —                                      |
| [utter-project/EuroLLM-1.7B-Instruct](https://huggingface.co/utter-project/EuroLLM-1.7B-Instruct) | 945,088                | 19,557                | 1.7B         |                   35 |   2024 | utter-project/EuroLLM-1.7B             |
| [ai-forever/mGPT](https://huggingface.co/ai-forever/mGPT)                                         | 933,850                | 3,003                 | unknown      |                   58 |   2022 | —                                      |
| [BSC-LT/salamandra-7b-instruct](https://huggingface.co/BSC-LT/salamandra-7b-instruct)             | 713,529                | 36,481                | 7.8B         |                   33 |   2024 | BSC-LT/salamandra-7b                   |

### Most popular models tagged *only* for Bulgarian

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------|
| [INSAIT-Institute/BgGPT-7B-Instruct-v0.1](https://huggingface.co/INSAIT-Institute/BgGPT-7B-Instruct-v0.1) | 13,084                 |                    46 | 7.3B         |                    1 |   2024 | mistralai/Mistral-7B-v0.1 |
| [rmihaylov/gpt2-medium-bg](https://huggingface.co/rmihaylov/gpt2-medium-bg)                               | 2,774                  |                   108 | unknown      |                    1 |   2022 | —                         |
| [YanaS/llama2-bg-GGUF](https://huggingface.co/YanaS/llama2-bg-GGUF)                                       | 2,306                  |                   177 | 6.7B         |                    1 |   2023 | —                         |
| [rmihaylov/gpt2-small-bg](https://huggingface.co/rmihaylov/gpt2-small-bg)                                 | 1,771                  |                   101 | unknown      |                    1 |   2022 | —                         |
| [usmiva/gpt-web-bg](https://huggingface.co/usmiva/gpt-web-bg)                                             | 1,211                  |                    40 | 137.0M       |                    1 |   2023 | —                         |

### Largest models tagged for Bulgarian

| model                                                                                                 | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                      |
| [nu11secur1ty/DeepSeek-V4-Pro-Base](https://huggingface.co/nu11secur1ty/DeepSeek-V4-Pro-Base)         | 536                    | 33                    | 1.6T         |                    2 |   2026 | —                                      |
| [nu11secur1ty/DeepSeek-V4-Pro](https://huggingface.co/nu11secur1ty/DeepSeek-V4-Pro)                   | 85                     | 9                     | 861.6B       |                    2 |   2026 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 23,979                 | 3,521                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |

### Largest models tagged *only* for Bulgarian

| model                                                                                                                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:--------------------------------------------|
| [burgasdotpro/bgGPT-DeepSeek-R1-Distill-Qwen-14B](https://huggingface.co/burgasdotpro/bgGPT-DeepSeek-R1-Distill-Qwen-14B)                             |                    293 |                    20 | 14.8B        |                    1 |   2025 | deepseek-ai/DeepSeek-R1-Distill-Qwen-14B    |
| [burgasdotpro/bgGPT-Phi-4](https://huggingface.co/burgasdotpro/bgGPT-Phi-4)                                                                           |                    149 |                    18 | 14.7B        |                    1 |   2025 | unsloth/Phi-4-unsloth-bnb-4bit              |
| [NikolayKozloff/LLMBG-Llama-3.1-8B-BG-Reasoning-v0.1-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/LLMBG-Llama-3.1-8B-BG-Reasoning-v0.1-Q8_0-GGUF) |                    614 |                   338 | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B                     |
| [burgasdotpro/bgGPT-GRPO-Llama-3.1-8B-Inst](https://huggingface.co/burgasdotpro/bgGPT-GRPO-Llama-3.1-8B-Inst)                                         |                    230 |                    11 | 8.0B         |                    1 |   2025 | unsloth/meta-llama-3.1-8b-instruct-bnb-4bit |
| [burgasdotpro/bgGPT-llama-3.1-8B](https://huggingface.co/burgasdotpro/bgGPT-llama-3.1-8B)                                                             |                    461 |                    62 | 8.0B         |                    1 |   2024 | unsloth/meta-llama-3.1-8b-bnb-4bit          |

_60 tagged models have unknown parameter counts and are not ranked by size._

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

**24** benchmark datasets in the survey include Bulgarian.

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
         /       reasoning [6]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [2]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 131            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 2,458          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                             | —              | Derived from XNLI (human-translated) + manual editing            |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                              | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)                  | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline)       |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                    | 2,937          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 10,000         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bulgarian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bulgarian? Does it make sense to train one?
  - ~27.10 GB English-equivalent text ≈ 6.78B tokens, enough for a compute-optimal model of ~338.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bulgarian-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 144 of ~18,460 papers (0.78%) (rank 44 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bulgarian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 144):

| title                                                                                                        | paper                                                                                |
|:-------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------|
| Authorship Attribution in Multilingual Machine-Generated Texts                                               | [2026.acl-long.2091](https://aclanthology.org/2026.acl-long.2091/)                   |
| A Large Dataset Representing Bulgarian, with the Bulgarian National Corpus as Its Core                       | [2026.cmlc-1.2](https://aclanthology.org/2026.cmlc-1.2/)                             |
| cantnlp@DravidianLangTech 2026: organic domain adaptation improves multi-class hope speech detection in Tulu | [2026.dravidianlangtech-1.21](https://aclanthology.org/2026.dravidianlangtech-1.21/) |
| Finding Culture-Sensitive Neurons in Vision-Language Models                                                  | [2026.eacl-long.155](https://aclanthology.org/2026.eacl-long.155/)                   |
| To Each Language Its Tokenizer: Modular Tokenizers for Efficient Multilingual LLMs                           | [2026.findings-emnlp.1019](https://aclanthology.org/2026.findings-emnlp.1019/)       |
| Goldfish: Monolingual Language Models for 350 Languages                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                         |
| Linguistic and Demographic Factors in an Online Free Translation Task                                        | [2026.lrec-1.678](https://aclanthology.org/2026.lrec-1.678/)                         |
| From Form to Meaning: Interlingua Sense-Alignment of Offensive Language with LLMs                            | [2026.ltedi-1.6](https://aclanthology.org/2026.ltedi-1.6/)                           |
| GUIR at SemEval-2026 Task 7: Probing Cultural Knowledge in LLMs via Multi-Agent Debate                       | [2026.semeval-1.438](https://aclanthology.org/2026.semeval-1.438/)                   |
| SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                | [2026.semeval-1.455](https://aclanthology.org/2026.semeval-1.455/)                   |

{% endraw %}
