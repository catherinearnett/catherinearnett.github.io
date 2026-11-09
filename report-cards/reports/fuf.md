---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fuf.html
---
{% raw %}
# So you want to work on Fulani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fuf` · macrolanguage `ful`

**Official / recognised in:** Guinea

**Status:** Official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                   |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                 |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                                                                                 |
| FineWeb                | 2.2 MB (fuf_Latn (0.00)); which is equivalent to ≈2.1 MB English data after byte-premium scaling; 3.3 MB removed by filtering. This is ~1/24,668,626 of English data and ranks 178 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid, pyfranc.
- **Eval datasets (1):** UDHR-LID (n=116)
- **Best model:** GlotLID — F1 0.915 (P 0.900, R 0.931, FPR 6.15e-04) averaged over 1 dataset(s). Runner-up: pyfranc (F1 0.637).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.900 |    0.931 | 0.915 | 0.001 | ✓                |
| pyfranc      |       0.879 |    0.500 | 0.637 | 0.000 | ✓                |
| funlangid    |       0.939 |    0.267 | 0.416 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fulani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Fulani *and* from closely related languages that might be confused with it. Likely confusions to include: Fula (`ffm`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fulani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Fulani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fulani (and whether the model is exclusively tagged for Fulani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Fulani.**

63 models are tagged with the macrolanguage `ful`, which may or may not cover it.

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

**0** benchmark datasets in the survey include Fulani (plus 12 labelled with the macrolanguage `ful`, included below).

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
            /  comprehension [2]   \
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
 /        ✅ Machine translation [10]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                                         | # test items   | Construction                                                        |
|:-------------------------|:------------------------------|:------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele) (as `ful`)                        | 900            | Human translation (professional)                                    |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) (as `ful`)           | 2,701          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (as `ful`)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (as `ful`)                          | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (as `ful`)              | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol) (as `ful`)                        | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (as `ful`)                            | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol) (as `ful`)                        | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) (as `ful`)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) (as `ful`)                       | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io) (as `ful`)                              | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) (as `ful`) | 41             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fulani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fulani? Does it make sense to train one?
  - ~2.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~26.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 12 of ~18,460 papers (0.06%) (rank 133 of 252 in the set); English is mentioned in 8,441.
- Search terms: Fulani | Pular

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 12):

| title                                                                                                       | paper                                                                    |
|:------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| Language Choice in Nigerian Social Media Hate Speech                                                        | [2026.africanlp-main.9](https://aclanthology.org/2026.africanlp-main.9/) |
| Indigenous Writing Systems Matter: Rethinking NLP beyond Alphabetic Bias through Script-Aware Modeling      | [2026.computel-1.13](https://aclanthology.org/2026.computel-1.13/)       |
| AfriVox: Probing Multilingual and Accent Robustness of Speech LLMs                                          | [2026.eacl-long.122](https://aclanthology.org/2026.eacl-long.122/)       |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)       |
| AfriStereo: A Culturally Grounded Dataset for Evaluating Stereotypical Bias in Large Language Models        | [2026.lrec-1.18](https://aclanthology.org/2026.lrec-1.18/)               |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                     | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)             |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings              | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)             |
| Open but Unvetted: The Ethics of African Language Data                                                      | [2026.rail-1.13](https://aclanthology.org/2026.rail-1.13/)               |
| HaYo: Repurposing DiaSafety Dataset for Dialogue Safety Evaluation in Hausa and Yoruba                      | [2026.rail-1.9](https://aclanthology.org/2026.rail-1.9/)                 |
| HurtNet: a Multilingual Dictionary of Hurtful Words                                                         | [2026.woah-1.43](https://aclanthology.org/2026.woah-1.43/)               |

{% endraw %}
