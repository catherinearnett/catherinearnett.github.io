---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fao.html
---
{% raw %}
# So you want to work on Faroese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fao`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Icelandic-Faroese ([Glottolog](https://glottolog.org/resource/languoid/id/faro1244))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Latn`

**Speakers:** about 73,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 69,000 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q25258#P1098), 2015)

**Official / recognised in:** Denmark

**Status:** Official language


## What does Faroese look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/faroese.htm):

> Øll menniskju eru fødd fræls og jøvn til virðingar og mannarættindi. Tey hava skil og samvitsku og eiga at fara hvørt um annað í bróðuranda.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_faroese.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Faroese yet ([its Wikitongues page](https://wikitongues.org/languages/fao/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                          |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 14,219 articles in fo.wikipedia; 40 active users. This is ~1/531 of English data and ranks 93 of 168 languages in the set in Wikipedia.                                                                         |
| Common Crawl           | 115,983 pages per crawl on average, which is 0.0054% of the crawl (2026). This is ~1/7,687 of English data and ranks 63 of 113 languages in the set in Common Crawl.                                            |
| FineWeb                | 0.29 GB (fao_Latn 0.29 GB), equivalent to ≈0.25 GB of English after byte-premium scaling; 0.31 GB removed by filtering. This is ~1/186,430 of English data and ranks 94 of 248 languages in the set in FineWeb. |
| Goldfish training data | 0.50 GB (fao_Latn 0.50 GB) (rank 89 of 166 in the set)                                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 2,829 sentences / 50,473 tokens in total: [UD_Faroese-FarPaHC](https://github.com/UniversalDependencies/UD_Faroese-FarPaHC) (1,621 sentences), [UD_Faroese-OFT](https://github.com/UniversalDependencies/UD_Faroese-OFT) (1,208 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 3,077 lemmas, 45,474 inflected forms ([unimorph/fao](https://github.com/unimorph/fao))                                                                                                                                                                                                                                            |
| Wikidata labels        | 866,537 Wikidata items have a label in Faroese. (Wikidata codes (labels): fo (866,537))                                                                                                                                                                                                                                           |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                    |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** OpenLID-v2 — F1 0.987 (P 0.991, R 0.983, FPR 7.24e-05) averaged over 5 dataset(s). Runner-up: GlotLID (F1 0.984).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.991 |    0.983 | 0.987 | 0.000 | ✓                |
| GlotLID      |       0.995 |    0.973 | 0.984 | 0.000 | ✓                |
| py3langid    |       0.989 |    0.953 | 0.970 | 0.000 | ✓                |
| cld2         |       0.997 |    0.935 | 0.963 | 0.000 | ✓                |
| funlangid    |       0.908 |    0.848 | 0.870 | 0.001 | ✓                |
| commonlingua |       0.895 |    0.815 | 0.847 | 0.001 | ✓                |
| pyfranc      |       0.877 |    0.778 | 0.819 | 0.001 | ✓                |
| fasttext     |       0.975 |    0.319 | 0.460 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.983 |    0.937 | 0.959 |
| Wikipedia | 300 |       0.990 |    0.983 | 0.987 |
| UDHR-LID  |  57 |       0.983 |    1.000 | 0.991 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Faroese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Faroese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Faroese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Faroese has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/fao/) video of Faroese yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Faroese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Faroese (and whether the model is exclusively tagged for Faroese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **122** text-generation models are explicitly tagged for Faroese (64 original uploads, 58 fine-tunes/quantisations/merges).
- **85** are tagged *only* for Faroese.
- Including tags inherited from base models: **127**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | █                    |
|   2024 |        5 | ██                   |
|   2025 |       58 | ████████████████████ |
|   2026 |       55 | ███████████████████  |

### Largest models tagged for Faroese

| model                                                                                           | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                       | 1.9T         |                  143 |   2025 | —                                |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)           | 856.0B       |                  143 |   2025 | —                                |
| [Hob-forge/NorMistral-11B-long-GGUF](https://huggingface.co/Hob-forge/NorMistral-11B-long-GGUF) | 11.4B        |                    7 |   2026 | norallm/normistral-11b-warm      |
| [ltg/normistral-11b-warm](https://huggingface.co/ltg/normistral-11b-warm)                       | 11.4B        |                    7 |   2024 | mistralai/Mistral-Nemo-Base-2407 |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                         | 8.6B         |                  189 |   2023 | —                                |

### Largest models tagged *only* for Faroese

| model                                                                                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [NikolayKozloff/kakugo-3B-fao-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-fao-Q8_0-GGUF)                             | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [svanhvit/byt5-ocr-post-processing-faroese](https://huggingface.co/svanhvit/byt5-ocr-post-processing-faroese)                       | 581.7M       |                    1 |   2023 | —                             |
| [liu-nlp/HyperLlama-572M-central-kurdish-1x-cloned-v2](https://huggingface.co/liu-nlp/HyperLlama-572M-central-kurdish-1x-cloned-v2) | 572.5M       |                    1 |   2026 | —                             |
| [liu-nlp/HyperLlama-572M-central-kurdish-2x-v2](https://huggingface.co/liu-nlp/HyperLlama-572M-central-kurdish-2x-v2)               | 572.5M       |                    1 |   2026 | —                             |
| [liu-nlp/HyperLlama-572M-english-1x-cloned-v2](https://huggingface.co/liu-nlp/HyperLlama-572M-english-1x-cloned-v2)                 | 572.5M       |                    1 |   2026 | —                             |

_11 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Faroese.

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
          /    ✅ 3. Commonsense     \
         /      reasoning [2]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                    | task                | dataset                                                                                             | # test items   | construction                                                     |
|:-------------------------|:--------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge  | BLiMP               | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 232            | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning | PIQA                | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 4. Reading comprehension | QA – extractive RC  | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation      | Machine translation | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      | Machine translation | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation      | Machine translation | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 294            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Faroese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Faroese? Does it make sense to train one?
  - ~0.43 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Faroese-only model is 3.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 30 of ~18,498 papers (0.16%) (rank 112 of 278 in the set); English is mentioned in 8,465.
- Search terms: Faroese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 30):

| title                                                                                                                                         | paper                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| SoS: Analysis of Surface over Semantics in Multilingual Text-To-Image Generation                                                              | [2026.eacl-long.185](https://aclanthology.org/2026.eacl-long.185/)       |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)             |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)             |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)             |
| Reformulate and Create, Don’t Translate: Creating Natural Prompts for Underserved Languages                                                   | [2026.lrec-1.841](https://aclanthology.org/2026.lrec-1.841/)             |
| Progressing beyond Art Masterpieces or Touristic Clichés: how to assess your LLMs for cultural alignment?                                     | [2026.resourceful-4.13](https://aclanthology.org/2026.resourceful-4.13/) |
| Stage-Aware Cross-Lingual Transfer for Faroese ASR: When and Which Languages Matter                                                           | [2026.speakable-1.17](https://aclanthology.org/2026.speakable-1.17/)     |
| Which languages are "hot", and which are "cool"? Using Universal Dependencies for large-scale comparisons of subject expression               | [2026.udw-1.2](https://aclanthology.org/2026.udw-1.2/)                   |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                                     | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                   |
| OpenLID-v3: Improving the Precision of Closely Related Language Identification – An Experience Report                                         | [2026.vardial-1.23](https://aclanthology.org/2026.vardial-1.23/)         |

{% endraw %}
