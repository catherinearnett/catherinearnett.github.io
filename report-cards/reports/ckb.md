---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ckb.html
---
{% raw %}
# So you want to work on Kurdish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ckb` · macrolanguage `kur`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Kurdish ([Glottolog](https://glottolog.org/resource/languoid/id/cent1972))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Arab`

**Speakers:** about 11.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 7.2 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q36811#P1098))

**Official / recognised in:** Iraq

**Status:** Official language


## What does Kurdish look and sound like?

**Written (Arabic alphabet)**, sample text from [Omniglot](https://www.omniglot.com/writing/kurdish.htm):

> .هەموو مرۆڤ ئازاد و دوەقار و مافان دە وەکهەڤ تێن دنیایێ. ئەو خوەدی هش و شوئوورن و دڤێ لهەمبەر هەڤ بزهنیەتەکە براتیێ بلڤن
> Improvements to these charts and sample text in the Arabic alphabet provided by Michael Peter Füstumum

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/ckb/) has 7 videos of Kurdish speakers. Watch [See all](https://wikitongues.org/videos/?language=ckb).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                         |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 85,215 articles in ckb.wikipedia; 163 active users. This is ~1/89 of English data and ranks 60 of 168 languages in the set in Wikipedia.                                                                       |
| Common Crawl           | 142,651 pages per crawl on average, which is 0.0066% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `kur`, which can include other varieties of Kurdish.                                    |
| FineWeb                | 0.83 GB (ckb_Arab 0.83 GB), equivalent to ≈0.50 GB of English after byte-premium scaling; 0.35 GB removed by filtering. This is ~1/64,271 of English data and ranks 75 of 248 languages in the set in FineWeb. |
| Goldfish training data | 1.59 GB (ckb_Arab 1.59 GB) (rank 65 of 166 in the set)                                                                                                                                                         |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 138 sentences / 660 tokens in total: [UD_Central_Kurdish-Mukri](https://github.com/UniversalDependencies/UD_Central_Kurdish-Mukri) (138 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                         |
| Wikidata labels        | 614,779 Wikidata items have a label in Kurdish. (Wikidata codes (labels): ckb (614,779), ku-latn (523,544), ku (410,002), ku-arab (160,324))                                                                                           |
| Wordnets               | [KurdNet (Kurdish WordNet)](https://github.com/sinaahmadi/kurdnet/releases/download/kurdnet-1.0.tar.xz/kurdnet-1.0.tar.xz): 2,144 synsets, 3,885 words, 6,240 senses; licence: https://creativecommons.org/licenses/by-sa/4.0/.        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                    |
|:-----------------------------------|:-----------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                        |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([ckb](https://ebible.org/details.php?id=ckb), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.992 (P 0.998, R 0.987, FPR 4.04e-05) averaged over 5 dataset(s). Runner-up: fasttext (F1 0.981).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.998 |    0.987 | 0.992 | 0.000 | ✓                |
| fasttext     |       0.970 |    0.993 | 0.981 | 0.001 | ✓                |
| OpenLID-v2   |       0.971 |    0.991 | 0.980 | 0.001 | ✓                |
| commonlingua |       0.970 |    0.971 | 0.969 | 0.001 | ✓                |
| funlangid    |       0.882 |    0.931 | 0.901 | 0.002 | ✓                |
| cld2         |       0.977 |    0.677 | 0.795 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.022 | ✓                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.003 | ✓                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.001 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       1.000 |    0.950 | 0.974 |
| Wikipedia | 300 |       1.000 |    0.987 | 0.993 |
| SmolSent  | 300 |       0.990 |    0.997 | 0.993 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kurdish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kurdish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kurdish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kurdish has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Kurdish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kurdish (and whether the model is exclusively tagged for Kurdish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **25** text-generation models are explicitly tagged for Kurdish (11 original uploads, 14 fine-tunes/quantisations/merges).
- **11** are tagged *only* for Kurdish.
- Including tags inherited from base models: **25**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        4 | ███████              |
|   2025 |        7 | ████████████         |
|   2026 |       12 | ████████████████████ |

### Largest models tagged for Kurdish

| model                                                                                                                                     | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [PawanKrd/RastNus-Base-12B](https://huggingface.co/PawanKrd/RastNus-Base-12B)                                                             | 12.0B        |                    1 |   2026 | google/gemma-4-12b |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 9.0B         |                   99 |   2026 | unsloth/Qwen3.5-9B |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 9.0B         |                   99 |   2026 | Qwen/Qwen3.5-9B    |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                                                   | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                                                                   | 8.6B         |                  189 |   2023 | —                  |

### Largest models tagged *only* for Kurdish

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [PawanKrd/RastNus-Base-12B](https://huggingface.co/PawanKrd/RastNus-Base-12B)                               | 12.0B        |                    1 |   2026 | google/gemma-4-12b            |
| [ptrdvn/kakugo-3B-ckb](https://huggingface.co/ptrdvn/kakugo-3B-ckb)                                         | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [akam-ot/kurdish-spellchecker-sorani-byt5](https://huggingface.co/akam-ot/kurdish-spellchecker-sorani-byt5) | 582.8M       |                    1 |   2026 | google/byt5-base              |

_10 tagged models have unknown parameter counts and are not ranked by size._

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

**10** benchmark datasets in the survey include Kurdish.

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
            / comprehension [2]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [1]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [7]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                                             | # test items   | construction                                                     |
|:-------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (2 varieties/pairs)                     | 1,708          | Human translation via English pivot                              |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (2 varieties/pairs)         | 2,024          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                       | 3,994          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation           | [TICO-19](https://github.com/tico-19/tico-19.github.io) (2 varieties/pairs)                         | 4,200          | Human translation (professional/volunteer, from English)         |
| Machine translation      | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 750            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kurdish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kurdish? Does it make sense to train one?
  - ~0.96 GB English-equivalent text ≈ 0.24B tokens, enough for a compute-optimal model of ~12.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Kurdish-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 71 of ~18,498 papers (0.38%) (rank 72 of 278 in the set); English is mentioned in 8,465.
- Search terms: Central Kurdish (Sorani) | Central Kurdish | Kurdish | Sorani

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 71):

| title                                                                                                                     | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                 | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                       |
| Entropic properties of languages in phonetic versus orthographic alphabets                                                | [2026.emnlp-main.92](https://aclanthology.org/2026.emnlp-main.92/)             |
| Adapting Where It Matters: Depth-Aware Adaptation for Efficient Multilingual Speech Recognition in Low-Resource Languages | [2026.findings-acl.827](https://aclanthology.org/2026.findings-acl.827/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                                        | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Dialects of Translationese Shape Language Model Learning                                                                  | [2026.findings-emnlp.2272](https://aclanthology.org/2026.findings-emnlp.2272/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation              | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| English to Central Kurdish Speech Translation: Corpus Creation, Evaluation, and Orthographic Standardization              | [2026.lrec-1.436](https://aclanthology.org/2026.lrec-1.436/)                   |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)                   |
| A corpus of written Swedish texts and keystroke data from deaf and hard-of-hearing children and adolescents               | [2026.nlp4call-1.17](https://aclanthology.org/2026.nlp4call-1.17/)             |
| Findings of the WMT26 Multilingual Instruction Shared Task: Small Models Are Not Yet Polyglots                            | [2026.wmt-main.50](https://aclanthology.org/2026.wmt-main.50/)                 |

{% endraw %}
