---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tgl.html
---
{% raw %}
# So you want to work on Tagalog?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tgl`

**Language family:** **Austronesian** › Malayo-Polynesian › Greater Central Philippine › … › Tagalog-Filipino ([Glottolog](https://glottolog.org/resource/languoid/id/taga1270))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Latn`

**Speakers:** about 73.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Tagalog look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/tagalog.htm):

> Ang lahat ng tao'y isinilang na malaya at pantay-pantay sa karangalan at mga karapatan. Sila'y pinagkalooban ng katwiran at budhi at dapat magpalagayan ang isa't isa sa diwa ng pagkakapatiran.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_tl.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tgl/) has 1 video of Tagalog speakers. Watch [Josh speaking Tagalog](https://wikitongues.org/videos/josh_20180728_tgl/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 50,782 articles in tl.wikipedia; 311 active users. This is ~1/149 of English data and ranks 71 of the 168 languages in the set with any data in Wikipedia; 164 have none.                             |
| Common Crawl           | 235,294 pages per crawl on average, which is 0.0109% of the crawl (2026). This is ~1/3,789 of English data and ranks 53 of the 113 languages in the set with any data in Common Crawl; 219 have none. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                        |
| Goldfish training data | 1.24 GB (tgl_Latn 1.24 GB) (rank 71 of the 166 languages in the set that have any; 166 have none)                                                                                                     |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                    |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 222 sentences / 1,745 tokens in total: [UD_Tagalog-TRG](https://github.com/UniversalDependencies/UD_Tagalog-TRG) (128 sentences), [UD_Tagalog-Ugnayan](https://github.com/UniversalDependencies/UD_Tagalog-Ugnayan) (94 sentences). All have POS tags, dependency syntax, lemmas. |
| UniMorph               | 344 lemmas, 2,912 inflected forms ([unimorph/tgl](https://github.com/unimorph/tgl))                                                                                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                 |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                          |
|:-----------------------------------|:-----------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                              |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([tglulb](https://ebible.org/details.php?id=tglulb), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                           |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, fasttext, py3langid, pyfranc.
- **Eval datasets (4):** CommonLID (n=300), Tatoeba (n=300), UDHR-LID (n=61), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.942 (P 0.929, R 0.957, FPR 1.05e-03) averaged over 4 dataset(s). Runner-up: commonlingua (F1 0.790).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.929 |    0.957 | 0.942 | 0.001 | ✓                |
| commonlingua |       0.780 |    0.809 | 0.790 | 0.003 | ✓                |
| cld2         |       0.658 |    0.892 | 0.746 | 0.006 | ✓                |
| pyfranc      |       0.648 |    0.723 | 0.662 | 0.006 | ✓                |
| fasttext     |       0.517 |    0.962 | 0.661 | 0.010 | ✓                |
| py3langid    |       0.394 |    0.968 | 0.519 | 0.022 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.834 |    0.907 | 0.869 |
| Tatoeba   | 300 |       0.917 |    0.957 | 0.936 |
| Wikipedia | 300 |       0.980 |    0.980 | 0.980 |
| UDHR-LID  |  61 |       0.984 |    0.984 | 0.984 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tagalog to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tagalog *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tagalog and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tagalog has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tagalog?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tagalog (and whether the model is exclusively tagged for Tagalog or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **290** text-generation models are explicitly tagged for Tagalog (74 original uploads, 216 fine-tunes/quantisations/merges).
- **26** are tagged *only* for Tagalog.
- Including tags inherited from base models: **500**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        6 | █                    |
|   2023 |       11 | ██                   |
|   2024 |       46 | ████████             |
|   2025 |      117 | ████████████████████ |
|   2026 |      110 | ███████████████████  |

### Largest models tagged for Tagalog

| model                                                                                                                                               | parameters   |   # languages tagged |   year | derivative of                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                           | 1.9T         |                  143 |   2025 | —                                             |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                               | 856.0B       |                  143 |   2025 | —                                             |
| [from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit](https://huggingface.co/from-our-page/Llama-4-Maverick-17B-128E-mlx-4bit)                         | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E          |
| [mlx-community/Llama-4-Maverick-17B-16E-Instruct-4bit](https://huggingface.co/mlx-community/Llama-4-Maverick-17B-16E-Instruct-4bit)                 | 400.7B       |                   12 |   2025 | meta-llama/Llama-4-Maverick-17B-128E-Instruct |
| [bartowski/meta-llama_Llama-4-Scout-17B-16E-Instruct-old-GGUF](https://huggingface.co/bartowski/meta-llama_Llama-4-Scout-17B-16E-Instruct-old-GGUF) | 107.8B       |                   12 |   2025 | meta-llama/Llama-4-Scout-17B-16E-Instruct     |

### Largest models tagged *only* for Tagalog

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [sapinsapin/llama31-8b-balitanlp-cpt](https://huggingface.co/sapinsapin/llama31-8b-balitanlp-cpt)   | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B |
| [alphaedge-ai/Qwen3.5-4B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-tgl-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B              |
| [alphaedge-ai/gemma-3-4b-it-tgl-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-tgl-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [alphaedge-ai/Qwen3.5-2B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-tgl-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B              |
| [alphaedge-ai/Qwen3-1.7B-tgl-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-tgl-32768)       | 1.5B         |                    1 |   2026 | Qwen3-1.7B              |

_43 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Tagalog.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                             |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                   |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                  |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                         |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                     |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                 |
| Machine translation           |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                      |
| Machine translation           |                                | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                             | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 3,978          | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tagalog datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tagalog? Does it make sense to train one?
  - ~1.11 GB English-equivalent text ≈ 0.28B tokens, enough for a compute-optimal model of ~13.9M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Tagalog-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 67 of ~18,498 papers (0.36%) (rank 74 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tagalog

Here are up to ten papers published in 2026 that mention Tagalog. None of the 67 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| CultureConverse: A Multilingual Multi-turn Simulation Harness for Culturally Grounded Assistance in East and Southeast Asia | [2026.emnlp-main.976](https://aclanthology.org/2026.emnlp-main.976/)           | body only      |
| SEA-SafeguardBench: Culturally Grounded Safety Benchmark for Southeast Asian Languages                                      | [2026.findings-acl.194](https://aclanthology.org/2026.findings-acl.194/)       | body only      |
| Idiom Understanding as a Tool to Measure the Dialect Gap                                                                    | [2026.findings-acl.24](https://aclanthology.org/2026.findings-acl.24/)         | body only      |
| EchoLens: A Human-Speech Dataset for Auditing Demographic Sensitivity in Audio-Language Models                              | [2026.findings-emnlp.2027](https://aclanthology.org/2026.findings-emnlp.2027/) | body only      |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                               | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) | body only      |
| On the Robustness of Code LLM Guardrails to Code-mixed and Transliterated Inputs                                            | [2026.findings-emnlp.568](https://aclanthology.org/2026.findings-emnlp.568/)   | body only      |
| MultiCoS: A Multilingual Dataset of Connective Semantics with Context–Sentence Compatibility                                | [2026.lrec-1.381](https://aclanthology.org/2026.lrec-1.381/)                   | body only      |
| APODICTUS: Automatic Processing of DICTionary Update candidateS                                                             | [2026.lrec-1.924](https://aclanthology.org/2026.lrec-1.924/)                   | body only      |
| Is Machine Translation Ready for the Next Crisis or Pandemic?                                                               | [2026.lt4cpr-1.8](https://aclanthology.org/2026.lt4cpr-1.8/)                   | body only      |
| Algebraic Classification of Reduplicative Processes                                                                         | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)               | body only      |

{% endraw %}
