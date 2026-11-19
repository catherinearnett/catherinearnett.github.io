---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lld.html
---
{% raw %}
# So you want to work on Ladin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lld`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Italian Romance ([Glottolog](https://glottolog.org/resource/languoid/id/ladi1250))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (80% certain))

**Speakers:** about 29,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 30,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q36202#P1098))

**Official / recognised in:** Italy

**Status:** Regional official language


## What does Ladin look and sound like?

**Written (Gardena Ladin)**, sample text from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Duta la jënt ie nasciuda liedia y à la medema denità y i medemi dërc. I à na mënt y na cuscienza y dëssa cunviver coche fredesc.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ladin-gardena.mp3) (Omniglot).

**Written (Val Badia Ladin)**, sample text from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Dötes les porsones nasc lëdies y cun la medema dignité y i medemi dërć. Ares à na rajun y na cosciënza y mëss sʼincuntè öna cun lʼatra te n spirit de fraternité.

**Written (Comelico Ladin)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Duce cuance i omin nasse libere e conpains zla dignité e zi derite. Löre inà la reson e la cossenzia e dovaraa tnisse duce a une conpagn de frades.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/lld/) has 2 videos of Ladin speakers. Watch [Andrea speaking Solandro](https://wikitongues.org/videos/andrea_20151117_lld/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                        |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 183,227 articles in lld.wikipedia; 28 active users. This is ~1/41 of English data and ranks 48 of 168 languages in the set in Wikipedia.      |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                      |
| FineWeb                | 1.5 MB (lld_Latn 0); 7.6 MB removed by filtering. This is ~1/35,019,483 of English data and ranks 189 of 248 languages in the set in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                  |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                         |
| UniMorph               | 180 lemmas, 7,656 inflected forms ([unimorph/lld](https://github.com/unimorph/lld))    |
| Wikidata labels        | 226,742 Wikidata items have a label in Ladin. (Wikidata codes (labels): lld (226,742)) |
| Wordnets               | **None found**                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=85), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.893 (P 0.988, R 0.830, FPR 2.65e-05) averaged over 4 dataset(s). Runner-up: pyfranc (F1 0.701).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.988 |    0.830 | 0.893 | 0.000 | ✓                |
| pyfranc      |       0.782 |    0.648 | 0.701 | 0.001 | ✓                |
| commonlingua |       0.792 |    0.505 | 0.605 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.593 | 0.745 |
| Tatoeba   |  85 |       0.970 |    0.765 | 0.855 |
| UDHR-LID  |  59 |       0.983 |    0.983 | 0.983 |
| FLORES    | 300 |       1.000 |    0.980 | 0.990 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ladin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Ladin *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ladin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Ladin has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Ladin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ladin (and whether the model is exclusively tagged for Ladin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Ladin (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Ladin.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Largest models tagged for Ladin

_none_

### Largest models tagged *only* for Ladin

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Ladin.

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

| level                    | task                | dataset                                                                                     |   # test items | construction                                                     |
|:-------------------------|:--------------------|:--------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                  |          4,745 | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) (2 varieties/pairs)             |          1,708 | Community-contributed translation                                |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (2 varieties/pairs) |          2,024 | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)        |             21 | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ladin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ladin? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 26 of ~18,498 papers (0.14%) (rank 118 of 278 in the set); English is mentioned in 8,465.
- Search terms: Ladin

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 26):

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| An Empirical Study of Many-Shot In-Context Learning for Machine Translation of Low-Resource Languages                                         | [2026.findings-aacl.142](https://aclanthology.org/2026.findings-aacl.142/) |
| Modeling Topics as Linguistic Linked Open Data: A First Attempt Using BERTopic, Ontolex-Lemon and FrAC                                        | [2026.ldl-1.1](https://aclanthology.org/2026.ldl-1.1/)                     |
| Rebelòt: Datasets and Token-Level Language Identification for Lombard-Italian-English Code-Mixing                                             | [2026.sigul-1.25](https://aclanthology.org/2026.sigul-1.25/)               |
| Leveraging Verbalized Confidence in LLM-as-a-Judge for Automated Translation Quality Evaluation                                               | [2026.wmt-main.107](https://aclanthology.org/2026.wmt-main.107/)           |
| SpinPop: A Fast Spin Metric for the WMT26 Metrics Shared Task                                                                                 | [2026.wmt-main.110](https://aclanthology.org/2026.wmt-main.110/)           |
| Findings of the WMT26 General Machine Translation Shared Task: Contrastive Dynamic Human Evaluation at Scale                                  | [2026.wmt-main.48](https://aclanthology.org/2026.wmt-main.48/)             |
| Findings of the WMT26 Shared Task on Automated Translation Quality Evaluation Systems: Compact Open Models are Competitive Quality Evaluators | [2026.wmt-main.49](https://aclanthology.org/2026.wmt-main.49/)             |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                                                                     | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)             |
| LiLa at WMT 2026 General MT Task: Exploring Beyond NMT and Learning the Limits of LLM Adaptation for Ligurian and Ladin                       | [2026.wmt-main.60](https://aclanthology.org/2026.wmt-main.60/)             |
| Grammatist at WMT 2026 General MT Task: An Agentic LLM Framework for Machine Translation with Explicit Linguistic Knowledge                   | [2026.wmt-main.65](https://aclanthology.org/2026.wmt-main.65/)             |

{% endraw %}
