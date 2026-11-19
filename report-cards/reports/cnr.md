---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cnr.html
---
{% raw %}
# So you want to work on Montenegrin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cnr` · macrolanguage `hbs`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Eastern Herzegovinian Shtokavian. Glottolog treats Montenegrin Standard as a variety of Serbian-Croatian-Bosnian ([Glottolog](https://glottolog.org/resource/languoid/id/mont1282))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Speakers:** about 630,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 233,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q8821#P1098))

**Official / recognised in:** Montenegro

**Status:** Official language


## What does Montenegrin look and sound like?

**Written (Latin)**, sample text from [Omniglot](https://www.omniglot.com/writing/montenegrin.htm):

> Sva ljudska bića rađaju se slobodna i jednaka u dostojanstvu i pravima. Ona su obdarena razumom i savješću i jedni prema drugima treba da postupaju u duhu bratstva.

**Written (Cyrillic )**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/montenegrin.htm):

> Сва људска бића рађају се слободна и једнака у достојанству и правима. Она су обдарена разумом и савјешћу и једни према другима треба да поступају у духу братства.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors: Source: https://ru.wikipedia.org/wiki/Черногорский_язык#Образец_текста.</sub>

**Spoken:** no Wikitongues video of Montenegrin yet ([its Wikitongues page](https://wikitongues.org/languages/cnr/) says how to contribute one).


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

| Resource               | What exists                                                                      |
|:-----------------------|:---------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                   |
| UniMorph               | **None found**                                                                   |
| Wikidata labels        | 2 Wikidata items have a label in Montenegrin. (Wikidata codes (labels): cnr (2)) |
| Wordnets               | **None found**                                                                   |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **1 of 10** LangID models evaluated have this language code as a label that can be predicted: pyfranc.
- **Eval datasets (1):** UDHR-LID (n=59)
- **Best model:** pyfranc — F1 0.496 (P 0.519, R 0.475, FPR 1.16e-03) averaged over 1 dataset(s). Runner-up: AfroLID (F1 0.000).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| pyfranc      |       0.519 |    0.475 | 0.496 | 0.001 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Montenegrin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is unreliable)**: label text from Montenegrin *and* from closely related languages that might be confused with it. Likely confusions to include: Bosnian (`bos`), Croatian (`hrv`), Serbian (`srp`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Montenegrin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Montenegrin has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/cnr/) video of Montenegrin yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Montenegrin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Montenegrin (and whether the model is exclusively tagged for Montenegrin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **5** text-generation models are explicitly tagged for Montenegrin (0 original uploads, 5 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Montenegrin.
- Including tags inherited from base models: **5**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        5 | ████████████████████ |

### Largest models tagged for Montenegrin

| model                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [sovasoft/zora-v1.12](https://huggingface.co/sovasoft/zora-v1.12) | 8.2B         |                   12 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Montenegrin

_none_

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

**0** benchmark datasets in the survey include Montenegrin (plus 1 labelled with the macrolanguage `hbs`, included below).

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
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                   | task   | dataset                                                                         |   # test items | construction                              |
|:------------------------|:-------|:--------------------------------------------------------------------------------|---------------:|:------------------------------------------|
| 1. Linguistic knowledge | BLiMP  | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp) (as `hbs`) |          3,286 | Treebank-based (automatic, UD + UniMorph) |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Montenegrin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Montenegrin? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of 278 in the set); English is mentioned in 8,465.
- Search terms: Montenegrin

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                             | paper                                                              |
|:------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| SoS: Analysis of Surface over Semantics in Multilingual Text-To-Image Generation                                  | [2026.eacl-long.185](https://aclanthology.org/2026.eacl-long.185/) |
| Charting the European LLM Benchmarking Landscape: A New Taxonomy and Registry                                     | [2026.llms4ssh-1.22](https://aclanthology.org/2026.llms4ssh-1.22/) |
| Serbian SuperGLUE: Towards an Evaluation Benchmark for South Slavic Language Models                               | [2026.loreslm-1.30](https://aclanthology.org/2026.loreslm-1.30/)   |
| Development of Serbian QA Datasets through Prompt-Based Generation and Human Validation                           | [2026.lrec-1.267](https://aclanthology.org/2026.lrec-1.267/)       |
| The Growing Gains and Pains of Iterative Web Corpora Crawling: Insights from South Slavic CLASSLA-web 2.0 Corpora | [2026.lrec-1.598](https://aclanthology.org/2026.lrec-1.598/)       |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation                        | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)       |
| Regional Variation in the Performance of ASR Models on Croatian and Serbian                                       | [2026.vardial-1.20](https://aclanthology.org/2026.vardial-1.20/)   |
| OpenLID-v3: Improving the Precision of Closely Related Language Identification – An Experience Report             | [2026.vardial-1.23](https://aclanthology.org/2026.vardial-1.23/)   |

{% endraw %}
