---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tau.html
---
{% raw %}
# So you want to work on Upper Tanana?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tau`

**Language family:** **Athabaskan-Eyak-Tlingit** › Athabaskan-Eyak › Athabaskan › … › Upper Tananaic ([Glottolog](https://glottolog.org/resource/languoid/id/uppe1437))

**Endangerment:** 🔴 nearly extinct (level 5 of 6 on Glottolog’s scale; source: ElCat: Critically Endangered (100% certain))

**Speakers:** 100 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q28281#P1098), 2007)

**Official / recognised in:** United States

**Status:** Regional official language


## What does Upper Tanana look and sound like?

**Written:** Omniglot has [a page on Upper Tanana](https://www.omniglot.com/writing/uppertanana.htm) but no sample text.

**Spoken:** no Wikitongues video of Upper Tanana yet ([its Wikitongues page](https://wikitongues.org/languages/tau/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists    |
|:-----------------------|:---------------|
| Universal Dependencies | **None found** |
| UniMorph               | **None found** |
| Wikidata labels        | **None found** |
| Wordnets               | **None found** |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **0 of 10** LangID models evaluated have this language code as a label that can be predicted.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Upper Tanana to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Upper Tanana *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Upper Tanana and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Upper Tanana has no UD treebank, UniMorph data, wordnet or Wikidata labels yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/tau/) video of Upper Tanana yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Upper Tanana?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Upper Tanana (and whether the model is exclusively tagged for Upper Tanana or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **12** text-generation models are explicitly tagged for Upper Tanana (0 original uploads, 12 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Upper Tanana.
- Including tags inherited from base models: **12**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |       12 | ████████████████████ |

### Largest models tagged for Upper Tanana

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [BillyWang1/qwen3-8b-tau-sft](https://huggingface.co/BillyWang1/qwen3-8b-tau-sft)                                     | 8.2B         |                    2 |   2026 | Qwen/Qwen3-8B-Base        |
| [willhx/Qwen3-8B-Base-Math-TauSFT](https://huggingface.co/willhx/Qwen3-8B-Base-Math-TauSFT)                           | 8.2B         |                    1 |   2026 | willhx/Qwen3-8B-Base-Math |
| [tau-emotion-bench/Tracer-High-4B](https://huggingface.co/tau-emotion-bench/Tracer-High-4B)                           | 4.0B         |                    2 |   2026 | Qwen/Qwen3-4B-Base        |
| [thang3092004/qwen3.5-4b-sft-tau-retail-silver](https://huggingface.co/thang3092004/qwen3.5-4b-sft-tau-retail-silver) | 4.0B         |                    1 |   2026 | unsloth/Qwen3.5-4B        |
| [tau-emotion-bench/Tracer-High-1.7B](https://huggingface.co/tau-emotion-bench/Tracer-High-1.7B)                       | 1.7B         |                    2 |   2026 | Qwen/Qwen3-1.7B-Base      |

### Largest models tagged *only* for Upper Tanana

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [willamazon1/sdft-tau-lora-iter160](https://huggingface.co/willamazon1/sdft-tau-lora-iter160)                         | 8.2B         |                    1 |   2026 | Qwen/Qwen3-8B-Base        |
| [willhx/Qwen3-8B-Base-Math-TauSFT](https://huggingface.co/willhx/Qwen3-8B-Base-Math-TauSFT)                           | 8.2B         |                    1 |   2026 | willhx/Qwen3-8B-Base-Math |
| [thang3092004/qwen3.5-4b-sft-tau-retail-silver](https://huggingface.co/thang3092004/qwen3.5-4b-sft-tau-retail-silver) | 4.0B         |                    1 |   2026 | unsloth/Qwen3.5-4B        |

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

**0** benchmark datasets in the survey include Upper Tanana.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /   [0]    \
                /______________\
               /                \
              /                  \
             /   ❌ 4. Reading    \
            / comprehension [0]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
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

_None found._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Upper Tanana datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Upper Tanana? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Upper Tanana-only model is 8.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of 278 in the set); English is mentioned in 8,465.
- Search terms: Upper Tanana

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                          | paper                                                        |
|:-----------------------------------------------------------------------------------------------|:-------------------------------------------------------------|
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/) |

{% endraw %}
