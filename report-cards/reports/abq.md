---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/abq.html
---
{% raw %}
# So you want to work on Abaza?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `abq`

**Official / recognised in:** Russia

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                         |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                         |
| FineWeb                | 2.1 MB (abq_Cyrl (0.00)); 0.4 MB removed by filtering. This is ~1/25,439,098 of English data and ranks 182 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- Support across the 8 evaluated LangID models is unknown: there is no labelled test data to run them on.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Abaza to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Abaza *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Abaza and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Abaza?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Abaza (and whether the model is exclusively tagged for Abaza or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Abaza.**

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

**2** benchmark datasets in the survey include Abaza.

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
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
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
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                                       | # test items   | Construction                                   |
|:--------------------|:--------------------|:------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| Machine translation | Machine translation | [SMOL – SmolDoc (from Russian)](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional, from Russian) |
| Machine translation | Machine translation | [SMOL – SmolSent (from Russian)](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from Russian) |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Abaza datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Abaza? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,460 papers (0.06%) (rank 136 of 252 in the set); English is mentioned in 8,441.
- Search terms: Abaza

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 11):

| title                                                                                                                                                                 | paper                                                              |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| HCMUS_PrisonDilemma at AbjadAuthorID Shared Task: Less is More with Base Models                                                                                       | [2026.abjadnlp-1.54](https://aclanthology.org/2026.abjadnlp-1.54/) |
| QalamID at AbjadAuthorID Shared Task: Morphology Matters, A Hybrid Ensemble for Arabic Authorship Attribution                                                         | [2026.abjadnlp-1.59](https://aclanthology.org/2026.abjadnlp-1.59/) |
| Uslub at AbjadAuthorID Shared Task: A Comparative Analysis of Traditional Machine Learning and Transformer-Based Models for Authorship Attribution in Arabic and Urdu | [2026.abjadnlp-1.65](https://aclanthology.org/2026.abjadnlp-1.65/) |
| Arabic Author Attribution Using Transformer-Based Models: Insights from the AbjadAuthorID Shared Task                                                                 | [2026.abjadnlp-1.66](https://aclanthology.org/2026.abjadnlp-1.66/) |
| AbjadAuthorID: Authorship Identification for Arabic-Script Languages at AbjadNLP 2026                                                                                 | [2026.abjadnlp-1.69](https://aclanthology.org/2026.abjadnlp-1.69/) |
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                                             | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)           |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems                                                                      | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)           |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                                              | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)       |
| Complex Predicates in Universal Dependencies                                                                                                                          | [2026.udw-1.19](https://aclanthology.org/2026.udw-1.19/)           |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                                                                                             | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)     |

{% endraw %}
