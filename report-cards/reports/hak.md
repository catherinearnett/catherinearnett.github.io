---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hak.html
---
{% raw %}
# So you want to work on Hakka?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hak` · macrolanguage `zho`

**Official / recognised in:** Taiwan

**Status:** National language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                              |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,511 articles in hak.wikipedia (rank 99 of 161 in the set) — ~1/718 of English; 27 active users                                                                                                   |
| Common Crawl 2026      | 100,182,847 pages per crawl on average, which is 4.6477% of the crawl. ⚠️ NB: this is counted using `zho` (macrolanguage code), so this number is shared with other varieties and overstates Hakka. |
| FineWeb                | 2.1 MB (hak_Hani (0.00); hak_Latn (0.00)); 0.12 GB removed by filtering. This is ~1/25,432,776 of English data and ranks 181 of 248 official languages in FineWeb.                                  |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                        |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (3):** Tatoeba (n=64), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.494 (P 0.641, R 0.443, FPR 7.68e-05) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.336).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.641 |    0.443 | 0.494 | 0.000 | ✓                |
| commonlingua |       0.339 |    0.334 | 0.336 | 0.001 | ✓                |
| funlangid    |       0.333 |    0.326 | 0.329 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  57 |       0.000 |    0.000 | 0.000 |
| Tatoeba   |  64 |       0.957 |    0.344 | 0.506 |
| Wikipedia | 300 |       0.967 |    0.987 | 0.977 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hakka to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is unreliable)**: label text from Hakka *and* from closely related languages that might be confused with it. Likely confusions to include: Standard Chinese (`cmn`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hakka and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Hakka?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hakka (and whether the model is exclusively tagged for Hakka or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Hakka (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Hakka.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Most popular models tagged for Hakka

| model                                                 |   downloads (all time) |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------|-----------------------:|----------------------:|:-------------|---------------------:|-------:|:----------------|
| [wikilangs/hak](https://huggingface.co/wikilangs/hak) |                      0 |                     0 | unknown      |                    2 |   2026 | —               |

### Most popular models tagged *only* for Hakka

_none_

### Largest models tagged for Hakka

_none_

### Largest models tagged *only* for Hakka

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**1** benchmark datasets in the survey include Hakka.

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

| level                    | task               | dataset                                                                    | # test items   | Construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|:---------------|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 1,945          | Synthetic (LLM-generated) on native Wikipedia |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hakka datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hakka? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 12 of ~18,460 papers (0.06%) (rank 133 of 252 in the set); English is mentioned in 8,441.
- Search terms: Hakka Chinese | Hakka

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 12):

| title                                                                                                                         | paper                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| MMAC: A Multilingual, Multimodal Alignment Framework for Cultural Grounding Evaluation                                        | [2026.acl-long.989](https://aclanthology.org/2026.acl-long.989/)           |
| Anchoring Speech with Semantics: A Multimodal Adapter Mechanism for Automatic Speech Recognition in Low-Resource Languages    | [2026.emnlp-main.1380](https://aclanthology.org/2026.emnlp-main.1380/)     |
| FuzhouBench: A Benchmark for Eastern Min Chinese with Tone Sandhi Annotations                                                 | [2026.emnlp-main.618](https://aclanthology.org/2026.emnlp-main.618/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| What Drives Dialectal Jailbreaks? An Ablation of Surface Form, Cultural Framing, and Strategy Banks                           | [2026.impactspeech-1.10](https://aclanthology.org/2026.impactspeech-1.10/) |
| Efficient Dialect-Aware Modeling and Conditioning for Low-Resource Taiwanese Hakka Speech Processing                          | [2026.lrec-1.491](https://aclanthology.org/2026.lrec-1.491/)               |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages                                    | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)               |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets                                         | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)                     |
| FLANS at SemEval-2026 Task 7: RAG with Open-Sourced Smaller LLMs for Everyday Knowledge Across Diverse Languages and Cultures | [2026.semeval-1.119](https://aclanthology.org/2026.semeval-1.119/)         |
| Benchmarking Multilingual LLM Translation Accuracy for Fuzhounese                                                             | [2026.sigul-1.20](https://aclanthology.org/2026.sigul-1.20/)               |

{% endraw %}
