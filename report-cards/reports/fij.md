---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fij.html
---
{% raw %}
# So you want to work on Fijian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fij`

**Language family:** **Austronesian** › Malayo-Polynesian › Eastern Malayo-Polynesian › … › Viwa-Lomaiviti-East Viti Levu ([Glottolog](https://glottolog.org/resource/languoid/id/fiji1243))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 4 (Educational))

**Writing systems:** `Latn`

**Speakers:** about 371,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 330,000 first-language + 320,000 second-language ([Wikidata](https://www.wikidata.org/wiki/Q33295#P1098), 1996)

**Official / recognised in:** Fiji

**Status:** Official language


## What does Fijian look and sound like?

**Written (Fijian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/fijian.htm):

> Era sucu ena galala na tamata yadua, era tautauvata ena nodra dokai kei na nodra dodonu. E tiko na nodra vakasama kei na nodra lewaeloma, sa dodonu mera veidokadokai ena yalo ni veitacini.
> A recording of this text by Tamati Taylor

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_fijian.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fij/) has 2 videos of Fijian speakers. Watch [Ratulevu speaking Kadavu](https://wikitongues.org/videos/ratulevu_20150530_fij/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                             |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,729 articles in fj.wikipedia; 7 active users. This is ~1/4,365 of English data and ranks 141 of 168 languages in the set in Wikipedia.                                                                           |
| Common Crawl           | 2,868 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/310,846 of English data and ranks 102 of 113 languages in the set in Common Crawl.                                              |
| FineWeb                | 19.4 MB (fij_Latn 20.0 MB), equivalent to ≈16.0 MB of English after byte-premium scaling; 0.10 GB removed by filtering. This is ~1/2,759,614 of English data and ranks 129 of 248 languages in the set in FineWeb. |
| Goldfish training data | 46.3 MB (fij_Latn 46.0 MB) (rank 135 of 166 in the set)                                                                                                                                                            |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                         |
| UniMorph               | **None found**                                                                         |
| Wikidata labels        | 597,906 Wikidata items have a label in Fijian. (Wikidata codes (labels): fj (597,906)) |
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

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=38), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.939 (P 0.966, R 0.916, FPR 3.55e-05) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.892).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.966 |    0.916 | 0.939 | 0.000 | ✓                |
| OpenLID-v2   |       0.855 |    0.938 | 0.892 | 0.001 | ✓                |
| fasttext     |       0.915 |    0.875 | 0.890 | 0.000 | ✓                |
| cld2         |       0.985 |    0.818 | 0.873 | 0.000 | ✓                |
| funlangid    |       0.852 |    0.798 | 0.820 | 0.000 | ✓                |
| pyfranc      |       0.786 |    0.810 | 0.791 | 0.001 | ✓                |
| commonlingua |       0.666 |    0.790 | 0.704 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  38 |       0.839 |    0.684 | 0.754 |
| Wikipedia | 300 |       0.993 |    0.893 | 0.940 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Fijian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Fijian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Fijian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Fijian has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Fijian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Fijian (and whether the model is exclusively tagged for Fijian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **18** text-generation models are explicitly tagged for Fijian (9 original uploads, 9 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Fijian.
- Including tags inherited from base models: **18**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██████               |
|   2024 |        3 | █████████            |
|   2025 |        6 | █████████████████    |
|   2026 |        7 | ████████████████████ |

### Largest models tagged for Fijian

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 8.2B         |                  143 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Fijian

_none_

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Fijian.

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
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                              | # test items   | construction                                                     |
|:-------------------------|:--------------------|:-------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 745            | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)              | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                        | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 44             | Native (crowdsourced Tatoeba sentence pairs)                     |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Fijian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Fijian? Does it make sense to train one?
  - ~38.3 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~478.4K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,498 papers (0.06%) (rank 145 of 278 in the set); English is mentioned in 8,465.
- Search terms: Fijian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 11):

| title                                                                                                     | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                         | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| Towards Trustworthy AI-Mediated Communication Across Languages and Cultures                               | [2026.bigpicture-main.5](https://aclanthology.org/2026.bigpicture-main.5/) |
| Creating ConLangs to Probe the Metalinguistic Grammatical Knowledge of LLMs                               | [2026.findings-acl.1455](https://aclanthology.org/2026.findings-acl.1455/) |
| Many-Shot Scaling of In-Context Learning with Self-Generated Demonstrations                               | [2026.findings-acl.2013](https://aclanthology.org/2026.findings-acl.2013/) |
| TIPA: Typologically Informed Parameter Aggregation                                                        | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                   | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Progressing beyond Art Masterpieces or Touristic Clichés: how to assess your LLMs for cultural alignment? | [2026.resourceful-4.13](https://aclanthology.org/2026.resourceful-4.13/)   |
| Algebraic Classification of Reduplicative Processes                                                       | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)           |
| Speech Act Constructions in Universal Dependencies                                                        | [2026.udw-1.29](https://aclanthology.org/2026.udw-1.29/)                   |
| Wiktionary as a Crowdsourced Lexicon for English Dialects                                                 | [2026.wac-1.23](https://aclanthology.org/2026.wac-1.23/)                   |

{% endraw %}
