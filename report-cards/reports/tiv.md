---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tiv.html
---
{% raw %}
# So you want to work on Tiv?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tiv`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Tiv-Iyive-Otanga ([Glottolog](https://glottolog.org/resource/languoid/id/tivv1240))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 3.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Tiv look and sound like?

**Written (Tiv)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/tiv.htm):

> I mar maor ken kpan ga, nan ngu a icivir man mbamkpeiyol cii. I na nan mhen man ishima i kaven kwagh; nahan gba keng u nana tema a orgen ken mtem u angbian a angbian.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Tiv yet ([its Wikitongues page](https://wikitongues.org/languages/tiv/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                               |
|:-----------------------|:-----------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                             |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._ |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._ |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._ |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                              |
|:-----------------------|:-------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                           |
| UniMorph               | **None found**                                                           |
| Wikidata labels        | 9 Wikidata items have a label in Tiv. (Wikidata codes (labels): tiv (9)) |
| Wordnets               | **None found**                                                           |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, funlangid, pyfranc.
- **Eval datasets (2):** SmolSent (n=300), UDHR-LID (n=67)
- **Best model:** GlotLID — F1 0.999 (P 1.000, R 0.998, FPR 0.00e+00) averaged over 2 dataset(s). Runner-up: pyfranc (F1 0.992).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    0.998 | 0.999 | 0.000 | ✓                |
| pyfranc      |       0.993 |    0.992 | 0.992 | 0.000 | ✓                |
| funlangid    |       0.983 |    0.970 | 0.977 | 0.000 | ✓                |
| AfroLID      |       0.970 |    0.896 | 0.930 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| SmolSent  | 300 |       1.000 |    0.997 | 0.998 |
| UDHR-LID  |  67 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tiv to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tiv *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tiv and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tiv has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/tiv/) video of Tiv yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Tiv?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tiv (and whether the model is exclusively tagged for Tiv or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **21** text-generation models are explicitly tagged for Tiv (4 original uploads, 17 fine-tunes/quantisations/merges).
- **2** are tagged *only* for Tiv.
- Including tags inherited from base models: **23**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██                   |
|   2024 |        2 | ██                   |
|   2025 |        0 |                      |
|   2026 |       17 | ████████████████████ |

### Largest models tagged for Tiv

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)               | 8.6B         |                  189 |   2023 | —                         |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)               | 8.6B         |                  189 |   2023 | —                         |
| [hypaai/Hypa-Llama3.1-8b-SFT](https://huggingface.co/hypaai/Hypa-Llama3.1-8b-SFT)     | 8.0B         |                   11 |   2026 | meta-llama/Llama-3.1-8B   |
| [hypaai/Hypa-Gemma4-E2B-v1](https://huggingface.co/hypaai/Hypa-Gemma4-E2B-v1)         | 5.1B         |                   10 |   2026 | google/gemma-4-E2B-it     |
| [hypaai/Hypa-Orpheus-3b-TTS-VC](https://huggingface.co/hypaai/Hypa-Orpheus-3b-TTS-VC) | 3.3B         |                   14 |   2026 | unsloth/orpheus-3b-0.1-ft |

### Largest models tagged *only* for Tiv

_none_

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Tiv.

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
 /         ✅ Machine translation [3]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                        | # test items   | construction                                                        |
|:--------------------|:--------------------|:---------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tiv datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tiv? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of 278 in the set); English is mentioned in 8,465.
- Search terms: Tiv

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                         | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)             |
| INFACT: A Diagnostic Benchmark for Induced Faithfulness and Factuality Hallucinations in Video-LLMs           | [2026.acl-long.2062](https://aclanthology.org/2026.acl-long.2062/)             |
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context   | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/)             |
| PACE: A Unified Condense-and-Extract Paradigm for Fast VLM Inference                                          | [2026.findings-emnlp.1138](https://aclanthology.org/2026.findings-emnlp.1138/) |
| AFROSCOPE: A Framework for Studying the Linguistic Landscape of Africa                                        | [2026.findings-emnlp.1308](https://aclanthology.org/2026.findings-emnlp.1308/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                 | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| Are Language Models Borrowing-Blind? A Multilingual Evaluation of Loanword Identification across 10 Languages | [2026.lrec-1.269](https://aclanthology.org/2026.lrec-1.269/)                   |
| Goldfish: Monolingual Language Models for 350 Languages                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |

{% endraw %}
