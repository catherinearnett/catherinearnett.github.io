---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bis.html
---
{% raw %}
# So you want to work on Bislama?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bis`

**Writing systems:** `Latn`

**Official / recognised in:** Vanuatu

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,516 articles in bi.wikipedia (rank 139 of 161 in the set) — ~1/4,978 of English; 11 active users                                                           |
| Common Crawl 2026      | 3,295 pages per crawl on average, which is 0.0002% of the crawl. This is ~1/270,564 of English data and ranks 100 of 113 official languages in Common Crawl. |
| FineWeb                | 6.0 MB (bis_Latn (0.01)); 10.3 MB removed by filtering. This is ~1/8,897,854 of English data and ranks 156 of 248 official languages in FineWeb.             |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                 |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=30), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.880 (P 0.928, R 0.842, FPR 4.65e-05) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.794).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.928 |    0.842 | 0.880 | 0.000 | ✓                |
| fasttext     |       0.718 |    0.914 | 0.794 | 0.002 | ✓                |
| pyfranc      |       0.727 |    0.826 | 0.756 | 0.001 | ✓                |
| commonlingua |       0.756 |    0.716 | 0.731 | 0.001 | ✓                |
| funlangid    |       0.709 |    0.739 | 0.711 | 0.001 | ✓                |
| cld2         |       0.317 |    0.818 | 0.445 | 0.008 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  30 |       0.783 |    0.600 | 0.679 |
| Wikipedia | 300 |       1.000 |    0.927 | 0.962 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bislama to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bislama *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bislama and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bislama?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bislama (and whether the model is exclusively tagged for Bislama or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **25** text-generation models are explicitly tagged for Bislama (6 original uploads, 19 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Bislama.
- Including tags inherited from base models: **25**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        0 |                      |
|   2025 |       21 | ████████████████████ |
|   2026 |        2 | ██                   |

### Most popular models tagged for Bislama

| model                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                                        |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                                        |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)             | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat             |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M) | 387                    |                    13 | 611.1M       |                    9 |   2025 | facebook/mbart-large-50-many-to-many-mmt |
| [Zihao-Li/L2-Bi-Code-Alt](https://huggingface.co/Zihao-Li/L2-Bi-Code-Alt)         | 180                    |                     4 | 6.7B         |                    6 |   2025 | meta-llama/Llama-2-7b-hf                 |

### Most popular models tagged *only* for Bislama

_none_

### Largest models tagged for Bislama

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 11,812                 |                   600 | 8.6B         |                  185 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 1,443                  |                    59 | 8.6B         |                  185 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Bislama

_none_

_7 tagged models have unknown parameter counts and are not ranked by size._

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

**1** benchmark datasets in the survey include Bislama.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [1]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task               | dataset                                                                    |   # test items | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) |            149 | Synthetic (LLM-generated) on native Wikipedia |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bislama datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bislama? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,460 papers (0.02%) (rank 189 of 252 in the set); English is mentioned in 8,441.
- Search terms: Bislama

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                   | paper                                                            |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                          | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)     |
| The University of Melbourne WMT 2026 CreoleMT Submission: A Domain-Balanced Approach to Low-Resource Pacific Creole Machine Translation | [2026.wmt-main.189](https://aclanthology.org/2026.wmt-main.189/) |
| Findings of the Second Shared Task for Creole Language Machine Translation, at WMT 2026                                                 | [2026.wmt-main.56](https://aclanthology.org/2026.wmt-main.56/)   |

{% endraw %}
