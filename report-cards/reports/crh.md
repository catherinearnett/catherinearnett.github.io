---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/crh.html
---
{% raw %}
# So you want to work on Crimean Tatar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `crh`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › Crimeaic ([Glottolog](https://glottolog.org/resource/languoid/id/crim1257))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (60% certain))

**Writing systems:** `Latn` and `Cyrl`

**Speakers:** about 200,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 553,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33357#P1098), 2021)

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Crimean Tatar look and sound like?

**Written:** no Omniglot page found for Crimean Tatar.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/crh/) has 2 videos of Crimean Tatar speakers. Watch [Neceadin speaking Crimean Tatar](https://wikitongues.org/videos/neceadin_20170617_crh/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 29,793 articles in crh.wikipedia; 62 active users. This is ~1/253 of English data and ranks 77 of 168 languages in the set in Wikipedia.                                                                                                                                                                                                                     |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                                                                                                                                     |
| FineWeb                | 50.5 MB (crh_Latn 40.0 MB; crh_Cyrl 10.0 MB), equivalent to ≈31.4 MB of English after byte-premium scaling (⚠️ only 81% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 1.34 GB removed by filtering. This is ~1/1,057,338 of English data and ranks 118 of 248 languages in the set in FineWeb. |
| Goldfish training data | 75.3 MB (crh_Latn 63.0 MB; crh_Cyrl 12.0 MB) (rank 125 of 166 in the set)                                                                                                                                                                                                                                                                                    |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   | Goldfish   | Goldfish, English-equivalent   |
|:------------------|:----------|:------------------------------|:-----------|:-------------------------------|
| Latin (`Latn`)    | 40.0 MB   | — (no byte premium yet)       | 63.0 MB    | — (no byte premium yet)        |
| Cyrillic (`Cyrl`) | 10.0 MB   | — (no byte premium yet)       | 12.0 MB    | — (no byte premium yet)        |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                    |
|:-----------------------|:-----------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                 |
| UniMorph               | 1,230 lemmas, 7,514 inflected forms ([unimorph/crh](https://github.com/unimorph/crh))          |
| Wikidata labels        | 342,719 Wikidata items have a label in Crimean Tatar. (Wikidata codes (labels): crh (342,719)) |
| Wordnets               | **None found**                                                                                 |

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
- **Eval datasets (5):** CommonLID (n=300), FLORES (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.888 (P 0.953, R 0.859, FPR 3.84e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.849).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.953 |    0.859 | 0.888 | 0.000 | ✓                |
| py3langid    |       0.815 |    0.909 | 0.849 | 0.003 | ✓                |
| OpenLID-v2   |       0.795 |    0.912 | 0.836 | 0.002 | ✓                |
| fasttext     |       0.862 |    0.786 | 0.804 | 0.001 | ✓                |
| pyfranc      |       0.793 |    0.670 | 0.718 | 0.002 | ✓                |
| commonlingua |       0.918 |    0.561 | 0.684 | 0.000 | ✓                |
| funlangid    |       0.661 |    0.580 | 0.601 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.993 |    0.480 | 0.647 |
| Tatoeba   | 300 |       0.806 |    0.830 | 0.818 |
| Wikipedia | 300 |       0.967 |    0.987 | 0.977 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Crimean Tatar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Crimean Tatar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Crimean Tatar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Crimean Tatar has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Crimean Tatar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Crimean Tatar (and whether the model is exclusively tagged for Crimean Tatar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **9** text-generation models are explicitly tagged for Crimean Tatar (8 original uploads, 1 fine-tunes/quantisations/merges).
- **5** are tagged *only* for Crimean Tatar.
- Including tags inherited from base models: **9**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ████████             |
|   2024 |        5 | ████████████████████ |
|   2025 |        1 | ████                 |
|   2026 |        1 | ████                 |

### Largest models tagged for Crimean Tatar

| model                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                 | 8.6B         |                  189 |   2023 | —                    |
| [EXAiStudio/EX-Ai1-3.88B-Gemma3](https://huggingface.co/EXAiStudio/EX-Ai1-3.88B-Gemma3) | 3.9B         |                  155 |   2026 | google/gemma-3-4b-it |

### Largest models tagged *only* for Crimean Tatar

_none_

_6 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Crimean Tatar.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [1]    \
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

| level                         | task                    | dataset                                                                              | # test items   | construction                                                     |
|:------------------------------|:------------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 4,053          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                       | 355            | Native (school/entrance exams)                                   |
| Machine translation           | Machine translation     | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation     | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol) (2 varieties/pairs)    | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation     | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 22             | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Crimean Tatar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Crimean Tatar? Does it make sense to train one?
  - ~54.4 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~680.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,498 papers (0.05%) (rank 149 of 278 in the set); English is mentioned in 8,465.
- Search terms: Crimean Tatar

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| Processing Inconsistency Predicts Language Competence: LLM Evaluation Without Answer Labels on Turkic Languages                               | [2026.acl-srw.94](https://aclanthology.org/2026.acl-srw.94/)               |
| Are Language Models Script-Aware?                                                                                                             | [2026.findings-aacl.12](https://aclanthology.org/2026.findings-aacl.12/)   |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)               |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                                                | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)               |
| Dictionary-Based Speculative Decoding for Non-Latin-Script Languages                                                                          | [2026.unlp-1.15](https://aclanthology.org/2026.unlp-1.15/)                 |

{% endraw %}
