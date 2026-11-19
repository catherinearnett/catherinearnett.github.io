---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hio.html
---
{% raw %}
# So you want to work on Khoisan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hio`

**Language family:** **Khoe-Kwadi** › Khoe › Non-Khoekhoe › … › Tshwa Khoe ([Glottolog](https://glottolog.org/resource/languoid/id/tsoa1238))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (20% certain))

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Zimbabwe

**Status:** Official language


## What does Khoisan look and sound like?

**Written:** no Omniglot page found for Khoisan.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hio/) has 1 video of Khoisan speakers. Watch [Thumbnail unavailable Kagiso speaking Tshila](https://wikitongues.org/videos/kagiso_20250430_hio/).


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

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Khoisan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Khoisan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Khoisan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Khoisan has no UD treebank, UniMorph data, wordnet or Wikidata labels yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).


## What models are available for Khoisan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Khoisan (and whether the model is exclusively tagged for Khoisan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Khoisan.**

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

**0** benchmark datasets in the survey include Khoisan.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Khoisan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Khoisan? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 3 of ~18,498 papers (0.02%) (rank 210 of 278 in the set); English is mentioned in 8,465.
- Search terms: Tjwao (Tshwa) | Khoisan | Tshwa | Tjwao

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                 | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Power Asymmetries, Bias, and AI, a Reflection of Society on Low-Resourced Languages - African Languages as Case Study | [2026.africanlp-main.24](https://aclanthology.org/2026.africanlp-main.24/) |
| AfriCaption: Establishing a New Paradigm for Image Captioning in African Languages                                    | [2026.africanlp-main.5](https://aclanthology.org/2026.africanlp-main.5/)   |
| Comparing Source Language Selection Strategies for Multi-Source Cross-Lingual Transfer to African Languages           | [2026.rail-1.4](https://aclanthology.org/2026.rail-1.4/)                   |

{% endraw %}
