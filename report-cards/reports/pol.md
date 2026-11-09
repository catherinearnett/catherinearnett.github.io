---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pol.html
---
{% raw %}
# So you want to work on Polish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pol`

**Writing systems:** `Latn`

**Official / recognised in:** Poland

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,713,709 articles in pl.wikipedia (rank 10 of 161 in the set) — ~1/4 of English; 9,281 active users                                                                                                                        |
| Common Crawl 2026      | 43,509,173 pages per crawl on average, which is 2.0187% of the crawl. This is ~1/20 of English data and ranks 9 of 113 official languages in Common Crawl.                                                                  |
| FineWeb                | 225.92 GB (pol_Latn (225.92)); which is equivalent to ≈209.69 GB English data after byte-premium scaling; 273.59 GB removed by filtering. This is ~1/236 of English data and ranks 10 of 248 official languages in FineWeb. |
| Goldfish training data | 9.44 GB (pol_latn) (rank 15 of 166 in the set)                                                                                                                                                                              |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.988 (P 0.976, R 0.999, FPR 1.79e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.952).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.976 |    0.999 | 0.988 | 0.000 | ✓                |
| cld2         |       0.923 |    0.984 | 0.952 | 0.001 | ✓                |
| commonlingua |       0.913 |    0.951 | 0.931 | 0.001 | ✓                |
| pyfranc      |       0.948 |    0.875 | 0.904 | 0.001 | ✓                |
| funlangid    |       0.915 |    0.816 | 0.859 | 0.001 | ✓                |
| OpenLID-v2   |       0.746 |    0.995 | 0.840 | 0.004 | ✓                |
| fasttext     |       0.677 |    0.999 | 0.779 | 0.006 | ✓                |
| py3langid    |       0.663 |    0.997 | 0.776 | 0.006 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.943 |    1.000 | 0.971 |
| Tatoeba   | 300 |       0.952 |    0.997 | 0.974 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |
| NTREX     | 300 |       0.993 |    1.000 | 0.997 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Polish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Polish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Polish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Polish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Polish (and whether the model is exclusively tagged for Polish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **2,057** text-generation models are explicitly tagged for Polish (548 original uploads, 1,509 fine-tunes/quantisations/merges).
- **446** are tagged *only* for Polish.
- Including tags inherited from base models: **3,905**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | █                    |
|   2023 |      151 | ███                  |
|   2024 |      342 | ███████              |
|   2025 |      620 | █████████████        |
|   2026 |      931 | ████████████████████ |

### Most popular models tagged for Polish

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [microsoft/Phi-4-mini-instruct](https://huggingface.co/microsoft/Phi-4-mini-instruct)             | 9,633,401              | 331,860               | 3.8B         |                   23 |   2025 | —                                      |
| [LiquidAI/LFM2.5-2.6B-GGUF](https://huggingface.co/LiquidAI/LFM2.5-2.6B-GGUF)                     | 2,543,125              | 186,819               | 2.7B         |                   16 |   2026 | LiquidAI/LFM2.5-2.6B-Base              |
| [speakleash/Bielik-11B-v3.0-Instruct](https://huggingface.co/speakleash/Bielik-11B-v3.0-Instruct) | 2,509,473              | 30,615                | 11.2B        |                   31 |   2025 | speakleash/Bielik-11B-v3-Base-20250730 |
| [Voicelab/vlt5-base-keywords](https://huggingface.co/Voicelab/vlt5-base-keywords)                 | 1,840,805              | 219,744               | 275.1M       |                    2 |   2022 | —                                      |
| [BioMistral/BioMistral-7B](https://huggingface.co/BioMistral/BioMistral-7B)                       | 1,767,964              | 10,381                | 7.0B         |                    9 |   2024 | —                                      |

### Most popular models tagged *only* for Polish

| model                                                                                             | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:-------------------------|
| [speakleash/Bielik-11B-v2.3-Instruct](https://huggingface.co/speakleash/Bielik-11B-v2.3-Instruct) | 614,386                | 10,801                | 11.2B        |                    1 |   2024 | speakleash/Bielik-11B-v2 |
| [Azurro/APT3-1B-Base](https://huggingface.co/Azurro/APT3-1B-Base)                                 | 366,212                | 4,167                 | 1.0B         |                    1 |   2024 | —                        |
| [speakleash/Bielik-7B-Instruct-v0.1](https://huggingface.co/speakleash/Bielik-7B-Instruct-v0.1)   | 275,651                | 3,423                 | 7.2B         |                    1 |   2024 | —                        |
| [sdadas/polish-gpt2-xl](https://huggingface.co/sdadas/polish-gpt2-xl)                             | 190,737                | 4,471                 | 1.7B         |                    1 |   2023 | —                        |
| [speakleash/Bielik-7B-v0.1](https://huggingface.co/speakleash/Bielik-7B-v0.1)                     | 144,779                | 3,251                 | 7.2B         |                    1 |   2024 | —                        |

### Largest models tagged for Polish

| model                                                                                                         | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                      |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                                  |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 2,057                  |                   350 | 751.4B       |                   10 |   2026 | —                                  |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-FP8](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-FP8)       | 4,060                  |                   509 | 749.4B       |                   10 |   2026 | LGAI-EXAONE/K-EXAONE-2.0-750B-A37B |
| [Vanedap/K-EXAONE-2.0-750B-A37B](https://huggingface.co/Vanedap/K-EXAONE-2.0-750B-A37B)                       | 462                    |                    43 | 749.4B       |                   10 |   2026 | —                                  |

### Largest models tagged *only* for Polish

| model                                                                                                       | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------|
| [OsaurusAI/Laguna-M.1-JANG_2L](https://huggingface.co/OsaurusAI/Laguna-M.1-JANG_2L)                         | 335                    |                    24 | 225.8B       |                    1 |   2026 | poolside/Laguna-M.1   |
| [SC117/Laguna-S-2.1-Uncensored](https://huggingface.co/SC117/Laguna-S-2.1-Uncensored)                       | 856                    |                   155 | 117.6B       |                    1 |   2026 | poolside/Laguna-S-2.1 |
| [CYFRAGOVPL/Llama-PLLuM-70B-chat-2508](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-chat-2508)         | 1,654                  |                    24 | 70.6B        |                    1 |   2025 | —                     |
| [CYFRAGOVPL/Llama-PLLuM-70B-instruct-2508](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-instruct-2508) | 3,129                  |                    86 | 70.6B        |                    1 |   2025 | —                     |
| [CYFRAGOVPL/Llama-PLLuM-70B-chat-2512](https://huggingface.co/CYFRAGOVPL/Llama-PLLuM-70B-chat-2512)         | 8,408                  |                   118 | 70.6B        |                    1 |   2025 | —                     |

_175 tagged models have unknown parameter counts and are not ranked by size._

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

**29** benchmark datasets in the survey include Polish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [14]    \
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
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | Construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 764            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 3,272          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension      | QA – extractive RC             | [PoQuAD](https://huggingface.co/datasets/clarin-pl/poquad)                                          | —              | Native                                                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                      | 1,971          | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                               | 14,042         | Machine translation (Google Translate)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | LLMzSzŁ                                                                                             | —              | Native (national exams)                                          |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | Complex Q&A Corpus                                                                                  | —              | Native (human-annotated)                                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [KLEJ-DYK (Polish Wikipedia "Czy wiesz")](https://huggingface.co/datasets/allegro/klej-dyk)         | 1,029          | Native                                                           |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                         |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [PolQA](https://huggingface.co/datasets/ipipan/polqa)                                               | 1,000          | Native (quiz questions)                                          |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 11,713         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Polish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Polish? Does it make sense to train one?
  - ~209.69 GB English-equivalent text ≈ 52.42B tokens, enough for a compute-optimal model of ~2.6B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Polish-only model is 225.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 438 of ~18,460 papers (2.37%) (rank 15 of 252 in the set); English is mentioned in 8,441.
- Search terms: Polish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 438):

| title                                                                                              | paper                                                                          |
|:---------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| SOAPTriage: SOAP-Guided Multi-View Clinical Text Modeling Framework for Automated ESI Prediction   | [2026.acl-long.1608](https://aclanthology.org/2026.acl-long.1608/)             |
| BNLI: A Linguistically-Refined Bengali Dataset for Natural Language Inference                      | [2026.chipsal-1.9](https://aclanthology.org/2026.chipsal-1.9/)                 |
| Reasoning-Aware AIGC Detection via Alignment and Reinforcement                                     | [2026.findings-acl.1043](https://aclanthology.org/2026.findings-acl.1043/)     |
| AI translation of literary texts is ’fine’, but readers still prefer human translations            | [2026.findings-emnlp.2138](https://aclanthology.org/2026.findings-emnlp.2138/) |
| Charting the European LLM Benchmarking Landscape: A New Taxonomy and Registry                      | [2026.llms4ssh-1.22](https://aclanthology.org/2026.llms4ssh-1.22/)             |
| FalAR: A Large-scale Speaker-Annotated European Portuguese Speech Corpus of Parliamentary Sessions | [2026.lrec-1.435](https://aclanthology.org/2026.lrec-1.435/)                   |
| Evaluating the Impact of Source Diversity for RAG in Historical Research                           | [2026.lrec-1.53](https://aclanthology.org/2026.lrec-1.53/)                     |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings     | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |
| Tracing Morph Origins in Czech: A Computational Approach to Morph-Level Etymology                  | [2026.lt4hala-1.2](https://aclanthology.org/2026.lt4hala-1.2/)                 |
| The Polish PressMint Corpus                                                                        | [2026.pressmint-1.2](https://aclanthology.org/2026.pressmint-1.2/)             |

{% endraw %}
