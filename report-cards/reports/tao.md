---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tao.html
---
{% raw %}
# So you want to work on Tao?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tao`

**Language family:** **Austronesian** › Malayo-Polynesian › Batanic › Yami-Itbayat ([Glottolog](https://glottolog.org/resource/languoid/id/yami1254))

**Endangerment:** 🔴 moribund (level 4 of 6 on Glottolog’s scale; source: ElCat: Severely Endangered (100% certain))

**Speakers:** 3,800 first-language ([Wikidata](https://www.wikidata.org/wiki/Q715760#P1098), 2006)

**Official / recognised in:** Taiwan

**Status:** National language


## What does Tao look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/yami.htm):

> O nimanoma do pongso ta ya a tao nokakoa am, sira mina Paloy, aka nira mina Ozamen, aka nira Pacilalaw. Sira rana ori am, ji sia mingongoyod pa a tao, ta somavik sira a tao. Sira Paloy rana ya am, ji sia hakakaw, ta ji sia ateneng a omhakaw, so ikabo no kanen da, to sia nginonginom so sazowsaw am ranom, ori o ikaviay da nira ori am, iyangay da nira mina Paloy ya.

*Translation:* About the earliest humans on this island, there were si Paloy, si Ozamen, si Pacilalaw, etc. These people, though, were not real people, for some of the things they thought or did were not like normal people. Now, Si Paloy and that group, they did not work in the fields because they did not understand agriculture, and therefore they did not have food. They lived by drinking the wind and water. …

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://yamiproject.cs.pu.edu.tw/elearn/reading.php?sn=72.</sub>

**Spoken:** no Wikitongues video of Tao yet ([its Wikitongues page](https://wikitongues.org/languages/tao/) says how to contribute one).


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

| Resource               | What exists                                                              |
|:-----------------------|:-------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                           |
| UniMorph               | **None found**                                                           |
| Wikidata labels        | 5 Wikidata items have a label in Tao. (Wikidata codes (labels): tao (5)) |
| Wordnets               | **None found**                                                           |

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

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tao to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Tao *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tao and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tao has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/tao/) video of Tao yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Tao?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tao (and whether the model is exclusively tagged for Tao or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Tao.**

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

**0** benchmark datasets in the survey include Tao.

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tao datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tao? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 115 of ~18,498 papers (0.62%) (rank 52 of 278 in the set); English is mentioned in 8,465.
- Search terms: Yami | Tao
- Because 'Tao' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 115):

| title                                                                                                                         | paper                                                                |
|:------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------|
| WisPerMed at ArchEHR-QA 2026: Retrieval-Augmented Prompting for Grounded EHR Question Answering                               | [2026.cl4health-1.42](https://aclanthology.org/2026.cl4health-1.42/) |
| Neural at ArchEHR-QA 2026: One Method Fits All: Unified Prompt Optimization for Clinical QA over EHRs                         | [2026.cl4health-1.50](https://aclanthology.org/2026.cl4health-1.50/) |
| Automatic Speech Recognition for Documenting Endangered Languages: Case Study of Ikema Miyakoan                               | [2026.lrec-1.284](https://aclanthology.org/2026.lrec-1.284/)         |
| Southern Kurdish Speech Recognition Resources and Benchmarking                                                                | [2026.lrec-1.432](https://aclanthology.org/2026.lrec-1.432/)         |
| Listening for Ideology: Automatic Analysis of Character Speech in Historical Nazi Propaganda Films                            | [2026.lrec-1.461](https://aclanthology.org/2026.lrec-1.461/)         |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages                                    | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)         |
| Do Multimodal LLMs Understand Order? Measuring the Fragility of Multimodal Reasoning under Input Order Perturbations          | [2026.lrec-1.716](https://aclanthology.org/2026.lrec-1.716/)         |
| Reason-to-Learn (R2L): Multi-Agent Knowledge Distillation for Lightweight LLMs in Sentiment Analysis                          | [2026.lrec-1.809](https://aclanthology.org/2026.lrec-1.809/)         |
| Is Biomedical Specialization Still Worth It? Insights from Domain-Adaptive Language Modelling with a New French Health Corpus | [2026.lrec-1.833](https://aclanthology.org/2026.lrec-1.833/)         |
| A Meta-evaluation of Automatic Metrics for Elaborative Simplification                                                         | [2026.readi-1.15](https://aclanthology.org/2026.readi-1.15/)         |

{% endraw %}
