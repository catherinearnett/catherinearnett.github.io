---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/knc.html
---
{% raw %}
# So you want to work on Kanuri?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `knc` · macrolanguage `kau`

**Language family:** **Saharan** › Western Saharan › Kanuri-Kanembu › … › East Kanuri ([Glottolog](https://glottolog.org/resource/languoid/id/cent2050))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** 9.3 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q15637215#P1098), 2024)

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Kanuri look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/kanuri.htm):

> Adamgana woso kambe katambo ye daraja-a hakkiwa-ason kalkalye. Hankal-a nazaru-asoro kəzəpkə ye suro hal nəmharamiben kamazasoga letaiyin ye.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/knc/) has 3 videos of Kanuri speakers. Watch [Ali speaking Hausa and Kanuri](https://wikitongues.org/videos/ali_20150626_hau-knc/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,150 articles in knc.wikipedia; 14 active users. This is ~1/3,510 of English data and ranks 139 of 168 languages in the set in Wikipedia. |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._                                                                                       |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._                                                                                       |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._                                                                                       |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                          |
|:-----------------------|:-----------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                       |
| UniMorph               | **None found**                                                                                       |
| Wikidata labels        | 440,307 Wikidata items have a label in Kanuri. (Wikidata codes (labels): kr (440,307), knc (35,592)) |
| Wordnets               | **None found**                                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=64)
- **Best model:** GlotLID — F1 0.993 (P 0.995, R 0.990, FPR 1.97e-05) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.892).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.990 | 0.993 | 0.000 | ✓                |
| OpenLID-v2   |       0.900 |    0.916 | 0.892 | 0.001 | ✓                |
| funlangid    |       0.971 |    0.781 | 0.860 | 0.000 | ✓                |
| fasttext     |       0.819 |    0.902 | 0.815 | 0.003 | ✓                |
| pyfranc      |       0.978 |    0.669 | 0.767 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.997 |    0.983 | 0.990 |
| SmolSent  | 300 |       1.000 |    0.983 | 0.992 |
| UDHR-LID  |  64 |       0.985 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    0.993 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Kanuri to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Kanuri *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Kanuri and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Kanuri has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Kanuri?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Kanuri (and whether the model is exclusively tagged for Kanuri or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **29** text-generation models are explicitly tagged for Kanuri (13 original uploads, 16 fine-tunes/quantisations/merges).
- **7** are tagged *only* for Kanuri.
- Including tags inherited from base models: **37**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |       10 | ██████████████       |
|   2025 |        5 | ███████              |
|   2026 |       14 | ████████████████████ |

### Largest models tagged for Kanuri

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                           | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)               | 856.0B       |                  143 |   2025 | —                    |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)               | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B     |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs) | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base |
| [Sunbird/Sunflower-Qwen3.5-9B](https://huggingface.co/Sunbird/Sunflower-Qwen3.5-9B)                 | 9.4B         |                   24 |   2026 | Qwen/Qwen3.5-9B      |

### Largest models tagged *only* for Kanuri

_none_

_13 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Kanuri.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                                                     | # test items   | construction                                                        |
|:--------------------|:--------------------|:--------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                 | 854            | Human translation via English pivot                                 |
| Machine translation | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (2 varieties/pairs) | 2,024          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                               | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                               | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                              | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Kanuri datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Kanuri? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 13 of ~18,498 papers (0.07%) (rank 140 of 278 in the set); English is mentioned in 8,465.
- Search terms: Central Kanuri | Kanuri

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 13):

| title                                                                                                                                         | paper                                                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| The African Languages Lab: A Collaborative Approach to Advancing Low-Resource African NLP                                                     | [2026.acl-long.1965](https://aclanthology.org/2026.acl-long.1965/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                                   | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Temporal Taxation Compounds Under Post-Training Compression of Whisper Models                                                                 | [2026.impactspeech-1.8](https://aclanthology.org/2026.impactspeech-1.8/)       |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| SALAN: A Massive ASR Dataset for the Languages of Niger                                                                                       | [2026.lrec-1.460](https://aclanthology.org/2026.lrec-1.460/)                   |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                                                 | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)                   |

{% endraw %}
