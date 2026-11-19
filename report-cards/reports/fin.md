---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fin.html
---
{% raw %}
# So you want to work on Finnish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fin`

**Language family:** **Uralic** › Finnic › Coastal Finnic › … › Nuclear Finnish ([Glottolog](https://glottolog.org/resource/languoid/id/finn1318))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 5.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 5.4 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q1412#P1098), 2012)

**Official / recognised in:** Finland

**Status:** Official language


## What does Finnish look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/finnish.htm):

> Kaikki ihmiset syntyvät vapaina ja tasavertaisina arvoltaan ja
> oikeuksiltaan. Heille on annettu järki ja omatunto, ja heidän
> on toimittava toisiaan kohtaan veljeyden hengessä.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_fi.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fin/) has 5 videos of Finnish speakers. Watch [Max speaking Finnish, Swedish](https://wikitongues.org/videos/max_20150904_fin-swe/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                          |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 627,947 articles in fi.wikipedia; 3,293 active users. This is ~1/12 of English data and ranks 25 of 168 languages in the set in Wikipedia.                                                                      |
| Common Crawl           | 8,062,776 pages per crawl on average, which is 0.3741% of the crawl (2026). This is ~1/111 of English data and ranks 24 of 113 languages in the set in Common Crawl.                                            |
| FineWeb                | 66.56 GB (fin_Latn 66.56 GB), equivalent to ≈62.86 GB of English after byte-premium scaling; 67.26 GB removed by filtering. This is ~1/803 of English data and ranks 25 of 248 languages in the set in FineWeb. |
| Goldfish training data | 7.38 GB (fin_Latn 7.38 GB) (rank 30 of 166 in the set)                                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 4 treebanks, 36,981 sentences / 396,434 tokens in total: [UD_Finnish-FTB](https://github.com/UniversalDependencies/UD_Finnish-FTB) (18,723 sentences), [UD_Finnish-OOD](https://github.com/UniversalDependencies/UD_Finnish-OOD) (2,122 sentences), [UD_Finnish-PUD](https://github.com/UniversalDependencies/UD_Finnish-PUD) (1,000 sentences), [UD_Finnish-TDT](https://github.com/UniversalDependencies/UD_Finnish-TDT) (15,136 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 57,027 lemmas, 2,737,048 inflected forms ([unimorph/fin](https://github.com/unimorph/fin))                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Wikidata labels        | 7,703,297 Wikidata items have a label in Finnish. (Wikidata codes (labels): fi (7,703,297))                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Wordnets               | [FinnWordNet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-fi-1.4.tar.xz): 116,763 synsets, 130,742 words, 189,227 senses; licence: https://creativecommons.org/licenses/by/3.0/.                                                                                                                                                                                                                                                                                                                        |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.978 (P 0.963, R 0.994, FPR 3.11e-04) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.874).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.963 |    0.994 | 0.978 | 0.000 | ✓                |
| cld2         |       0.837 |    0.977 | 0.874 | 0.003 | ✓                |
| pyfranc      |       0.940 |    0.810 | 0.866 | 0.001 | ✓                |
| funlangid    |       0.871 |    0.844 | 0.837 | 0.001 | ✓                |
| commonlingua |       0.819 |    0.907 | 0.831 | 0.003 | ✓                |
| py3langid    |       0.766 |    0.998 | 0.827 | 0.007 | ✓                |
| fasttext     |       0.738 |    0.996 | 0.801 | 0.007 | ✓                |
| OpenLID-v2   |       0.683 |    0.994 | 0.753 | 0.012 | ✓                |
| cld3         |       0.618 |    0.974 | 0.718 | 0.014 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.881 |    0.983 | 0.929 |
| UDHR-LID  |  61 |       0.953 |    1.000 | 0.976 |
| Wikipedia | 300 |       0.961 |    0.997 | 0.979 |
| CommonLID | 300 |       0.980 |    0.983 | 0.982 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Finnish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Finnish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Finnish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Finnish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Finnish (and whether the model is exclusively tagged for Finnish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **948** text-generation models are explicitly tagged for Finnish (258 original uploads, 690 fine-tunes/quantisations/merges).
- **103** are tagged *only* for Finnish.
- Including tags inherited from base models: **1,861**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       20 | █                    |
|   2023 |       41 | ██                   |
|   2024 |      225 | █████████████        |
|   2025 |      326 | ███████████████████  |
|   2026 |      336 | ████████████████████ |

### Largest models tagged for Finnish

| model                                                                                                                           | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                       | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                           | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                           | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [ff670/openbuddy-mixtral-22bx8-preview0-65k](https://huggingface.co/ff670/openbuddy-mixtral-22bx8-preview0-65k)                 | 140.8B       |                    9 |   2024 | —                                      |
| [nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16) | 123.6B       |                   20 |   2026 | —                                      |

### Largest models tagged *only* for Finnish

| model                                                                                                         | parameters   |   # languages tagged |   year | derivative of             |
|:--------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [mpasila/Finnish-Chatty-Tiny-V1-1-33B](https://huggingface.co/mpasila/Finnish-Chatty-Tiny-V1-1-33B)           | 33.1B        |                    1 |   2024 | LumiOpen/Viking-33B       |
| [vividfog/sahkovatkain-gemma4-31b-lora](https://huggingface.co/vividfog/sahkovatkain-gemma4-31b-lora)         | 32.7B        |                    1 |   2026 | —                         |
| [randomicity/gpt3-finnish-13B-Q8_0-GGUF](https://huggingface.co/randomicity/gpt3-finnish-13B-Q8_0-GGUF)       | 13.3B        |                    1 |   2025 | TurkuNLP/gpt3-finnish-13B |
| [Vetehinen/gpt3-finnish-13B-GGML](https://huggingface.co/Vetehinen/gpt3-finnish-13B-GGML)                     | 13.0B        |                    1 |   2023 | —                         |
| [overthelex/fi-legal-citation-grounded-12b](https://huggingface.co/overthelex/fi-legal-citation-grounded-12b) | 12.0B        |                    1 |   2026 | google/gemma-4-12B-it     |

_101 tagged models have unknown parameter counts and are not ranked by size._

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

**20** benchmark datasets in the survey include Finnish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [6]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [2]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [5]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [2]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                           | 400            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge       | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 2,570          | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)           | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)     | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                   | 1,727          | Native (TyDi questions)                                          |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 11,786         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Finnish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Finnish? Does it make sense to train one?
  - ~62.86 GB English-equivalent text ≈ 15.72B tokens, enough for a compute-optimal model of ~785.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Finnish-only model is 33.1B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 253 of ~18,498 papers (1.37%) (rank 30 of 278 in the set); English is mentioned in 8,465.
- Search terms: Finnish

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 253):

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| The Language–Energy Divide: Measuring Energy Costs of Multilingual LLM Inference                                                              | [2026.emnlp-main.2113](https://aclanthology.org/2026.emnlp-main.2113/)       |
| SAFE: An LLM-as-Verifier Framework for Evidence-Grounded Multi-Hop Reasoning                                                                  | [2026.emnlp-main.853](https://aclanthology.org/2026.emnlp-main.853/)         |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                                           | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)   |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                                  | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                 |
| ConGA: Guidelines for Contextual Gender Annotation. a Framework for Annotating Gender in Machine Translation                                  | [2026.lrec-1.320](https://aclanthology.org/2026.lrec-1.320/)                 |
| A Semi-Automatic Workflow for Transcribing and Annotating Broadcast News                                                                      | [2026.lrec-1.508](https://aclanthology.org/2026.lrec-1.508/)                 |
| Simple Additions, Substantial Gains: Expanding Scripts, Languages, and Lineage Coverage in URIEL+                                             | [2026.lrec-1.863](https://aclanthology.org/2026.lrec-1.863/)                 |
| PressMint: Towards Interoperable Corpora of Historical Newspapers                                                                             | [2026.pressmint-1.1](https://aclanthology.org/2026.pressmint-1.1/)           |
| Probing the Dynamics of Syntactic Ability Acquisition Throughout LLM Pretraining                                                              | [2026.udw-1.1](https://aclanthology.org/2026.udw-1.1/)                       |

{% endraw %}
