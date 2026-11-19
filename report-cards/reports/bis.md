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

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Early Melanesian Pidgin ([Glottolog](https://glottolog.org/resource/languoid/id/bisl1239))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 286,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 10,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q35452#P1098), 2011)

**Official / recognised in:** Vanuatu

**Status:** Official language


## What does Bislama look and sound like?

**Written:** no Omniglot page found for Bislama.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bis/) has 2 videos of Bislama speakers. Watch [Toukala speaking Bislama](https://wikitongues.org/videos/toukala_20141111_bis/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,516 articles in bi.wikipedia; 11 active users. This is ~1/4,978 of English data and ranks 145 of 168 languages in the set in Wikipedia.                             |
| Common Crawl           | 3,295 pages per crawl on average, which is 0.0002% of the crawl (2026). This is ~1/270,564 of English data and ranks 100 of 113 languages in the set in Common Crawl. |
| FineWeb                | 6.0 MB (bis_Latn 10.0 MB); 10.3 MB removed by filtering. This is ~1/8,897,854 of English data and ranks 156 of 248 languages in the set in FineWeb.                   |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | **None found**                                                                          |
| Wikidata labels        | 511,982 Wikidata items have a label in Bislama. (Wikidata codes (labels): bi (511,982)) |
| Wordnets               | **None found**                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=30), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.880 (P 0.928, R 0.842, FPR 4.59e-05) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.794).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.928 |    0.842 | 0.880 | 0.000 | ✓                |
| fasttext     |       0.718 |    0.914 | 0.794 | 0.002 | ✓                |
| pyfranc      |       0.724 |    0.826 | 0.753 | 0.001 | ✓                |
| commonlingua |       0.755 |    0.716 | 0.730 | 0.001 | ✓                |
| funlangid    |       0.709 |    0.739 | 0.711 | 0.001 | ✓                |
| cld2         |       0.317 |    0.818 | 0.445 | 0.008 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
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
- **Create structured data:** Bislama has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


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

### Largest models tagged for Bislama

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 8.2B         |                  143 |   2026 | Qwen/Qwen3-8B-Base |

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
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task               | dataset                                                                    |   # test items | construction                                  |
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

- **Mentions in ACL papers in 2026:** 3 of ~18,498 papers (0.02%) (rank 210 of 278 in the set); English is mentioned in 8,465.
- Search terms: Bislama

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                   | paper                                                            |
|:----------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------|
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                          | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)     |
| The University of Melbourne WMT 2026 CreoleMT Submission: A Domain-Balanced Approach to Low-Resource Pacific Creole Machine Translation | [2026.wmt-main.189](https://aclanthology.org/2026.wmt-main.189/) |
| Findings of the Second Shared Task for Creole Language Machine Translation, at WMT 2026                                                 | [2026.wmt-main.56](https://aclanthology.org/2026.wmt-main.56/)   |

{% endraw %}
