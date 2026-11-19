---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/fil.html
---
{% raw %}
# So you want to work on Filipino?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `fil`

**Language family:** **Austronesian** › Malayo-Polynesian › Greater Central Philippine › … › Tagalog-Filipino ([Glottolog](https://glottolog.org/resource/languoid/id/fili1244))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 73.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 90.0 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q33298#P1098))

**Official / recognised in:** Philippines

**Status:** Official language


## What does Filipino look and sound like?

**Written (Filipino)**, sample text from [Omniglot](https://www.omniglot.com/writing/filipino.htm):

> Ang lahat ng tao'y isinilang na malaya at pantay-pantay sa karangalan at mga karapatan. Sila'y pinagkalooban ng katwiran at budhi at dapat magpalagayan ang isa't isa sa diwa ng pagkakapatiran.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_tl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/fil/) has 3 videos of Filipino speakers. Watch [Kouta speaking Pampangan, Filipino](https://wikitongues.org/videos/kouta_20190508_pam-fil/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                         |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                         |
| FineWeb                | 3.62 GB (fil_Latn 3.62 GB); 4.05 GB removed by filtering. This is ~1/14,764 of English data and ranks 55 of 248 languages in the set in FineWeb. |
| Goldfish training data | 4.21 GB (fil_Latn 4.21 GB) (rank 45 of 166 in the set)                                                                                           |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                     |
|:-----------------------|:--------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                  |
| UniMorph               | **None found**                                                                  |
| Wikidata labels        | 56 Wikidata items have a label in Filipino. (Wikidata codes (labels): fil (56)) |
| Wordnets               | **None found**                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: OpenLID-v2, cld3, funlangid.
- **Eval datasets (3):** CommonLID (n=58), FLORES (n=300), NTREX (n=300)
- **Best model:** OpenLID-v2 — F1 0.729 (P 0.702, R 0.958, FPR 9.02e-03) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.713).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| OpenLID-v2   |       0.702 |    0.958 | 0.729 | 0.009 | ✓                |
| funlangid    |       0.711 |    0.845 | 0.713 | 0.006 | ✓                |
| cld3         |       0.573 |    0.963 | 0.644 | 0.015 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| GlotLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (OpenLID-v2) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  58 |       0.108 |    0.879 | 0.192 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       0.997 |    1.000 | 0.998 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Filipino to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Filipino *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Filipino and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Filipino has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Filipino?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Filipino (and whether the model is exclusively tagged for Filipino or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **111** text-generation models are explicitly tagged for Filipino (27 original uploads, 84 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Filipino.
- Including tags inherited from base models: **157**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       12 | █████                |
|   2023 |        5 | ██                   |
|   2024 |       18 | ███████              |
|   2025 |       27 | ███████████          |
|   2026 |       49 | ████████████████████ |

### Largest models tagged for Filipino

| model                                                                                                               | parameters   |   # languages tagged |   year | derivative of                                      |
|:--------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)               | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16             |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B) | 123.6B       |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF](https://huggingface.co/aisingapore/Llama-SEA-LION-v3-70B-IT-GGUF)       | 70.6B        |                   11 |   2024 | meta-llama/Llama-3.1-70B                           |
| [aisingapore/Nemotron-SEA-LION-v4.8-30B-A3B](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-30B-A3B)     | 32.9B        |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Nano-30B-A3B-Base-BF16    |
| [aisingapore/Qwen-SEA-LION-v4-32B-IT](https://huggingface.co/aisingapore/Qwen-SEA-LION-v4-32B-IT)                   | 32.8B        |                   11 |   2025 | Qwen/Qwen3-32B                                     |

### Largest models tagged *only* for Filipino

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-fil-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-fil-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-fil-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-fil-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-fil-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-fil-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

_16 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Filipino.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [1]    \
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

| level                         | task                    | dataset                                                                 | # test items   | construction                                                        |
|:------------------------------|:------------------------|:------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)   | 14,042         | Machine translation (Google Translate)                              |
| Machine translation           | Machine translation     | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation           | Machine translation     | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)               | 1,997          | Human translation (professional, from English)                      |
| Machine translation           | Machine translation     | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)           | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation           | Machine translation     | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)          | —              | Human translation (professional, from English)                      |
| Machine translation           | Machine translation     | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)               | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Filipino datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Filipino? Does it make sense to train one?
  - ~3.17 GB English-equivalent text ≈ 0.79B tokens, enough for a compute-optimal model of ~39.6M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Filipino-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 53 of ~18,498 papers (0.29%) (rank 84 of 278 in the set); English is mentioned in 8,465.
- Search terms: Filipino

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 53):

| title                                                                                                            | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                        | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/)             |
| Translation-CoT: A Human-Inspired Chain-of-Thought Framework for Multilingual LLM Translation                    | [2026.amta-research.2](https://aclanthology.org/2026.amta-research.2/)         |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation              | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/)     |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                              | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)     |
| SEA-LION-Embedding: Open and Reproducible Text Embeddings for Southeast Asia                                     | [2026.findings-emnlp.1205](https://aclanthology.org/2026.findings-emnlp.1205/) |
| Tracing the Latent Threads: A Mechanistic Study of How LLMs Represent and Operationalize Race and Ethnicity Cues | [2026.findings-emnlp.1388](https://aclanthology.org/2026.findings-emnlp.1388/) |
| CultureVLM: Characterizing and Improving Cultural Understanding of Vision-Language Models                        | [2026.findings-emnlp.1603](https://aclanthology.org/2026.findings-emnlp.1603/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Cygnet: Refactoring the Open Multilingual Wordnet                                                                | [2026.lrec-1.628](https://aclanthology.org/2026.lrec-1.628/)                   |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                   | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)                   |

{% endraw %}
