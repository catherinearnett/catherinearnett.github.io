---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/aar.html
---
{% raw %}
# So you want to work on Afar?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `aar`

**Language family:** **Afro-Asiatic** › Cushitic › East Cushitic › … › Saho-Afar ([Glottolog](https://glottolog.org/resource/languoid/id/afar1241))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Speakers:** about 2.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 1.6 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q27811#P1098))

**Official / recognised in:** Ethiopia

**Status:** Official language


## What does Afar look and sound like?

**Written (Afar)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/afar.htm):

> Karaamat kee garwawagittaamal seehada inkih gide akkuk, currik taabuke. Usun kas kee cissi loonuuh, keenik mariiy mara lih toobokinni kasat gexsitam faxximta.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://www.ohchr.org/EN/UDHR/Pages/Language.aspx?LangID=aar.</sub>

**Spoken:** no Wikitongues video of Afar yet ([its Wikitongues page](https://wikitongues.org/languages/aar/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 0 articles in aa.wikipedia; 0 active users.                                                                                                                           |
| Common Crawl           | 2,016 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/442,216 of English data and ranks 107 of 113 languages in the set in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                        |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                       |
| UniMorph               | **None found**                                                                       |
| Wikidata labels        | 481,696 Wikidata items have a label in Afar. (Wikidata codes (labels): aa (481,696)) |
| Wordnets               | **None found**                                                                       |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, cld2, funlangid, pyfranc.
- **Eval datasets (2):** SmolSent (n=300), UDHR-LID (n=57)
- **Best model:** GlotLID — F1 0.991 (P 1.000, R 0.981, FPR 0.00e+00) averaged over 2 dataset(s). Runner-up: cld2 (F1 0.952).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.981 | 0.991 | 0.000 | ✓                |
| cld2         |       0.916 |    0.995 | 0.952 | 0.001 | ✓                |
| pyfranc      |       0.971 |    0.927 | 0.946 | 0.000 | ✓                |
| funlangid    |       0.961 |    0.794 | 0.860 | 0.000 | ✓                |
| AfroLID      |       0.925 |    0.808 | 0.856 | 0.001 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       1.000 |    0.980 | 0.990 |
| UDHR-LID  |  57 |       1.000 |    0.982 | 0.991 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Afar to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Afar *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Afar and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Afar has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/aar/) video of Afar yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Afar?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Afar (and whether the model is exclusively tagged for Afar or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **70** text-generation models are explicitly tagged for Afar (24 original uploads, 46 fine-tunes/quantisations/merges).
- **20** are tagged *only* for Afar.
- Including tags inherited from base models: **70**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        9 | █████                |
|   2024 |       20 | ████████████         |
|   2025 |       34 | ████████████████████ |
|   2026 |        7 | ████                 |

### Largest models tagged for Afar

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                   | 1.9T         |                  143 |   2025 | —                                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                       | 856.0B       |                  143 |   2025 | —                                        |
| [Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8](https://huggingface.co/Phpcool/DeepSeek-R1-Distill-SRE-Qwen-32B-INT8)       | 32.8B        |                    2 |   2025 | deepseek-ai/DeepSeek-R1-Distill-Qwen-32B |
| [SedimentLabs/Pebble-1-30B](https://huggingface.co/SedimentLabs/Pebble-1-30B)                                               | 29.8B        |                    2 |   2026 | meta-models/Muse-Glimmer-30B             |
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base                      |

### Largest models tagged *only* for Afar

| model                                                                           | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [apartejs/aparte-souffleurs](https://huggingface.co/apartejs/aparte-souffleurs) | 1.2B         |                    1 |   2026 | LiquidAI/LFM2.5-VL-1.6B |

_46 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Afar.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                        | # test items   | construction                                                        |
|:--------------------|:--------------------|:---------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)    | 854            | Human translation via English pivot                                 |
| Machine translation | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional, from English)                      |
| Machine translation | Machine translation | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation | Machine translation | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol) | —              | Human translation (professional, from English)                      |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Afar datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Afar? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Afar-only model is 1.2B, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 1 of ~18,498 papers (0.01%) (rank 241 of 278 in the set); English is mentioned in 8,465.
- Search terms: Afar
- Because 'Afar' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                  | paper                                                                          |
|:-----------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |

{% endraw %}
