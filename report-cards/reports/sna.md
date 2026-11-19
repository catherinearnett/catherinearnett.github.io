---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sna.html
---
{% raw %}
# So you want to work on Shona?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sna`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Central Shona ([Glottolog](https://glottolog.org/resource/languoid/id/shon1251))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 13.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 8.3 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q34004#P1098), 2007)

**Official / recognised in:** Zimbabwe

**Status:** Official language


## What does Shona look and sound like?

**Written:** no Omniglot page found for Shona.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/sna/) has 2 videos of Shona speakers. Watch [Tatenda speaking Shona](https://wikitongues.org/videos/tatenda_20131103_sna/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                           |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 11,876 articles in sn.wikipedia; 16 active users. This is ~1/635 of English data and ranks 100 of 168 languages in the set in Wikipedia.                                                                         |
| Common Crawl           | 21,310 pages per crawl on average, which is 0.0010% of the crawl (2026). This is ~1/41,835 of English data and ranks 87 of 113 languages in the set in Common Crawl.                                             |
| FineWeb                | 0.15 GB (sna_Latn 0.15 GB), equivalent to ≈0.14 GB of English after byte-premium scaling; 0.49 GB removed by filtering. This is ~1/352,536 of English data and ranks 102 of 248 languages in the set in FineWeb. |
| Goldfish training data | 0.73 GB (sna_Latn 0.73 GB) (rank 81 of 166 in the set)                                                                                                                                                           |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                           |
|:-----------------------|:--------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                        |
| UniMorph               | 86 lemmas, 3,030 inflected forms ([unimorph/sna](https://github.com/unimorph/sna))    |
| Wikidata labels        | 638,072 Wikidata items have a label in Shona. (Wikidata codes (labels): sn (638,072)) |
| Wordnets               | **None found**                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=47), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.932 (P 0.921, R 0.956, FPR 1.74e-03) averaged over 7 dataset(s). Runner-up: cld2 (F1 0.891).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.921 |    0.956 | 0.932 | 0.002 | ✓                |
| cld2         |       0.900 |    0.911 | 0.891 | 0.004 | ✓                |
| AfroLID      |       0.879 |    0.851 | 0.850 | 0.005 | ✓                |
| OpenLID-v2   |       0.763 |    0.984 | 0.837 | 0.006 | ✓                |
| fasttext     |       0.761 |    0.972 | 0.832 | 0.006 | ✓                |
| pyfranc      |       0.843 |    0.791 | 0.796 | 0.004 | ✓                |
| funlangid    |       0.843 |    0.694 | 0.751 | 0.001 | ✓                |
| commonlingua |       0.672 |    0.851 | 0.722 | 0.007 | ✓                |
| cld3         |       0.428 |    0.933 | 0.548 | 0.033 | ✓                |
| py3langid    |       0.381 |    0.966 | 0.501 | 0.036 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       0.630 |    1.000 | 0.773 |
| Tatoeba   |  47 |       0.848 |    0.830 | 0.839 |
| CommonLID | 300 |       0.989 |    0.903 | 0.944 |
| Wikipedia | 300 |       0.980 |    0.960 | 0.970 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Shona to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Shona *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Shona and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Shona has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Shona?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Shona (and whether the model is exclusively tagged for Shona or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **248** text-generation models are explicitly tagged for Shona (103 original uploads, 145 fine-tunes/quantisations/merges).
- **13** are tagged *only* for Shona.
- Including tags inherited from base models: **534**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       36 | ███████              |
|   2023 |       24 | ████                 |
|   2024 |       35 | ██████               |
|   2025 |       44 | ████████             |
|   2026 |      109 | ████████████████████ |

### Largest models tagged for Shona

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Shona

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/gemma-3-4b-it-sna-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sna-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-sna](https://huggingface.co/ptrdvn/kakugo-3B-sna)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/gemma-3-1b-it-sna-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sna-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt          |
| [alphaedge-ai/gemma-3-270m-it-sna-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sna-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m           |

_28 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Shona.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [2]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [2]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                                        |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                                                   |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | Machine translation (Google Translate)                              |
| Machine translation                    | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                           | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                     | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                    | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation           | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 42             | Native (crowdsourced Tatoeba sentence pairs)                        |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Shona datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Shona? Does it make sense to train one?
  - ~0.65 GB English-equivalent text ≈ 0.16B tokens, enough for a compute-optimal model of ~8.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Shona-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 33 of ~18,498 papers (0.18%) (rank 110 of 278 in the set); English is mentioned in 8,465.
- Search terms: Shona

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 33):

| title                                                                                                                                    | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AfriqueLLM: How Data Mixing and Model Architecture Impact Continued Pre-training for African Languages                                   | [2026.acl-long.267](https://aclanthology.org/2026.acl-long.267/)               |
| MERLIN: Multi-Stage Curriculum Alignment for Multilingual Encoder-LLM Integration in Cross-Lingual Reasoning                             | [2026.eacl-long.277](https://aclanthology.org/2026.eacl-long.277/)             |
| Large-scale Multilingual News Image Captioning with LLMs                                                                                 | [2026.emnlp-main.1209](https://aclanthology.org/2026.emnlp-main.1209/)         |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                                      | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| PUMA: Projected Universal Multilingual ASR for Low-Resource Settings. Application to Diverse African Languages                           | [2026.findings-acl.17](https://aclanthology.org/2026.findings-acl.17/)         |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                           | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                             | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/)   |
| Evaluating Bias in Phoneme-Based Automatic Speech Recognition Systems: An Analysis of IPA Transcription Models                           | [2026.impactspeech-1.5](https://aclanthology.org/2026.impactspeech-1.5/)       |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                               | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| A Family of Effective Methods for Decompiling Canonical Acceptors, Instantiated for Languages of Dot-Depth One and Tier-Based Extensions | [2026.scil-main.3](https://aclanthology.org/2026.scil-main.3/)                 |

{% endraw %}
