---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/vec.html
---
{% raw %}
# So you want to work on Talian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `vec`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Venetian. Glottolog treats Talian (Brazilian Veneto) as a variety of Venetian ([Glottolog](https://glottolog.org/resource/languoid/id/tali1266))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: status of Venetian: ElCat: Critically endangered)

**Writing systems:** `Latn`

**Speakers:** about 1.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 2.0 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q32724#P1098))

**Official / recognised in:** Brazil

**Status:** Regional official language


## What does Talian look and sound like?

**Written (Venice dialect)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/venetian.htm):

> Tuti i eseri umani xe nati liberi e conpagni par dignità e diriti. I xe dotai de raxon e de cosiensa e i deve conportarse i uni co st'altri c spirito de fradelana.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/vec/) has 5 videos of Talian speakers. Watch [Nicholas speaking Chipileño](https://wikitongues.org/videos/nicholas_20170719_vec/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 69,633 articles in vec.wikipedia; 39 active users. This is ~1/108 of English data and ranks 63 of 168 languages in the set in Wikipedia.                                                                         |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                         |
| FineWeb                | 5.8 MB (vec_Latn 10.0 MB), equivalent to ≈5.9 MB of English after byte-premium scaling; 8.67 GB removed by filtering. This is ~1/9,153,490 of English data and ranks 157 of 248 languages in the set in FineWeb. |
| Goldfish training data | 0.16 GB (vec_Latn 0.16 GB) (rank 112 of 166 in the set)                                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | 368 lemmas, 18,227 inflected forms ([unimorph/vec](https://github.com/unimorph/vec))        |
| Wikidata labels        | 2,371,476 Wikidata items have a label in Talian. (Wikidata codes (labels): vec (2,371,476)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=298), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.949 (P 0.984, R 0.921, FPR 1.03e-04) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.903).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.984 |    0.921 | 0.949 | 0.000 | ✓                |
| fasttext     |       0.916 |    0.909 | 0.903 | 0.001 | ✓                |
| OpenLID-v2   |       0.796 |    0.936 | 0.846 | 0.002 | ✓                |
| commonlingua |       0.899 |    0.813 | 0.842 | 0.001 | ✓                |
| pyfranc      |       0.883 |    0.678 | 0.755 | 0.001 | ✓                |
| funlangid    |       0.760 |    0.776 | 0.754 | 0.002 | ✓                |
| py3langid    |       0.673 |    0.929 | 0.745 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       1.000 |    0.777 | 0.874 |
| Tatoeba   | 298 |       0.992 |    0.883 | 0.934 |
| Wikipedia | 300 |       0.927 |    0.970 | 0.948 |
| FLORES    | 300 |       1.000 |    0.973 | 0.986 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Talian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Talian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Talian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Talian has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Talian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Talian (and whether the model is exclusively tagged for Talian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **16** text-generation models are explicitly tagged for Talian (7 original uploads, 9 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Talian.
- Including tags inherited from base models: **21**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███████              |
|   2024 |        4 | █████████████        |
|   2025 |        4 | █████████████        |
|   2026 |        6 | ████████████████████ |

### Largest models tagged for Talian

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                     | 8.6B         |                  189 |   2023 | —                                           |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                     | 8.6B         |                  189 |   2023 | —                                           |
| [Marco-Danz/leoncino-ministral3-8b-veneto](https://huggingface.co/Marco-Danz/leoncino-ministral3-8b-veneto) | 8.5B         |                    2 |   2026 | mistralai/Ministral-3-8B-Instruct-2512-BF16 |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                                       | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base                          |
| [Marco-Danz/leoncino-mistral-7b-veneto](https://huggingface.co/Marco-Danz/leoncino-mistral-7b-veneto)       | 7.2B         |                    2 |   2026 | mistralai/Mistral-7B-Instruct-v0.3          |

### Largest models tagged *only* for Talian

_none_

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Talian.

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
             /   ✅ 4. Reading    \
            / comprehension [1]  \
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
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 19             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Talian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Talian? Does it make sense to train one?
  - ~0.16 GB English-equivalent text ≈ 0.04B tokens, enough for a compute-optimal model of ~2.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of 278 in the set); English is mentioned in 8,465.
- Search terms: Brazilian Venetian | Talian

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                               | paper                                                      |
|:--------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------|
| Preserving Endangered Linguistic Heritage: Developing a Corpus for the Study of Contact-induced Changes in Corfioto | [2026.lrec-1.76](https://aclanthology.org/2026.lrec-1.76/) |

{% endraw %}
