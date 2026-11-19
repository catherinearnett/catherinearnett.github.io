---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ssw.html
---
{% raw %}
# So you want to work on Swazi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ssw`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Swatic ([Glottolog](https://glottolog.org/resource/languoid/id/swat1243))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Speakers:** about 2.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 2.0 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q34014#P1098))

**Official / recognised in:** Eswatini, South Africa

**Status:** Official language


## What does Swazi look and sound like?

**Written:** no Omniglot page found for Swazi.

**Spoken:** no Wikitongues video of Swazi yet ([its Wikitongues page](https://wikitongues.org/languages/ssw/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                      |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,195 articles in ss.wikipedia; 8 active users. This is ~1/6,315 of English data and ranks 152 of 168 languages in the set in Wikipedia.                                                                    |
| Common Crawl           | 1,073 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/830,855 of English data and ranks 110 of 113 languages in the set in Common Crawl.                                       |
| FineWeb                | 4.2 MB (ssw_Latn 0), equivalent to ≈3.7 MB of English after byte-premium scaling; 53.0 MB removed by filtering. This is ~1/12,676,467 of English data and ranks 164 of 248 languages in the set in FineWeb. |
| Goldfish training data | 24.7 MB (ssw_Latn 25.0 MB) (rank 146 of 166 in the set)                                                                                                                                                     |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                                                                  |
| UniMorph               | **None found**                                                                                                                                                                  |
| Wikidata labels        | 472,731 Wikidata items have a label in Swazi. (Wikidata codes (labels): ss (472,731))                                                                                           |
| Wordnets               | [African Wordnet](https://africanwordnet.wordpress.com/) (size not listed); licence: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (6):** FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=12), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.879 (P 0.902, R 0.861, FPR 3.54e-05) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.845).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.902 |    0.861 | 0.879 | 0.000 | ✓                |
| fasttext     |       0.862 |    0.836 | 0.845 | 0.000 | ✓                |
| cld2         |       0.875 |    0.789 | 0.828 | 0.000 | ✓                |
| OpenLID-v2   |       0.798 |    0.889 | 0.826 | 0.001 | ✓                |
| pyfranc      |       0.801 |    0.764 | 0.776 | 0.001 | ✓                |
| AfroLID      |       0.998 |    0.689 | 0.761 | 0.000 | ✓                |
| funlangid    |       0.833 |    0.684 | 0.741 | 0.000 | ✓                |
| commonlingua |       0.683 |    0.821 | 0.714 | 0.003 | ✓                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  12 |       0.417 |    0.417 | 0.417 |
| Wikipedia | 300 |       0.996 |    0.780 | 0.875 |
| SmolSent  | 300 |       1.000 |    0.983 | 0.992 |
| UDHR-LID  |  60 |       1.000 |    0.983 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Swazi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Swazi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Swazi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Swazi has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/ssw/) video of Swazi yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Swazi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Swazi (and whether the model is exclusively tagged for Swazi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **46** text-generation models are explicitly tagged for Swazi (29 original uploads, 17 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Swazi.
- Including tags inherited from base models: **53**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | ███                  |
|   2024 |        7 | ███████              |
|   2025 |       19 | ████████████████████ |
|   2026 |       17 | ██████████████████   |

### Largest models tagged for Swazi

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                         |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                         |
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs)                   | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base      |
| [AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4](https://huggingface.co/AMAImedia/Qwen3.5-VL-9B-UI-Venus-2-NOESIS-NF4) | 9.0B         |                   48 |   2026 | inclusionAI/UI-Venus-2-9B |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                                               | 8.6B         |                  189 |   2023 | —                         |

### Largest models tagged *only* for Swazi

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                       |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------------|
| [ncsgobubble/Llama-7B-rollercoaster_v2](https://huggingface.co/ncsgobubble/Llama-7B-rollercoaster_v2) | 6.7B         |                    1 |   2024 | SuvajitGB/rollercoaster_emotions_v2 |

_22 tagged models have unknown parameter counts and are not ranked by size._

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

**8** benchmark datasets in the survey include Swazi.

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
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [6]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                          | dataset                                                                    | # test items   | construction                                                        |
|:-------------------------|:------------------------------|:---------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 1,856          | Synthetic (LLM-generated) on native Wikipedia                       |
| Machine translation      | Machine translation           | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                | 854            | Human translation via English pivot                                 |
| Machine translation      | Machine translation           | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation      | Machine translation           | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation      | Machine translation           | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation      | Machine translation           | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)             | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Swazi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Swazi? Does it make sense to train one?
  - ~21.7 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~270.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Swazi-only model is 6.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 2 of ~18,498 papers (0.01%) (rank 227 of 278 in the set); English is mentioned in 8,465.
- Search terms: Swazi

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                           | paper                                                                      |
|:------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| SoS: Analysis of Surface over Semantics in Multilingual Text-To-Image Generation                | [2026.eacl-long.185](https://aclanthology.org/2026.eacl-long.185/)         |
| VLURes: Benchmarking Long-Text Grounding and Cross-Lingual Robustness in Vision Language Models | [2026.findings-acl.1367](https://aclanthology.org/2026.findings-acl.1367/) |

{% endraw %}
