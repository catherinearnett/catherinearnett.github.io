---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/uig.html
---
{% raw %}
# So you want to work on Uyghur?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `uig`

**Language family:** **Turkic** › Common Turkic › Kipchak-Turkestan › … › Uyghuric ([Glottolog](https://glottolog.org/resource/languoid/id/uigh1240))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Writing systems:** `Arab` and `Latn` and `Cyrl`

**Speakers:** about 8.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** People's Republic of China

**Status:** Regional official language


## What does Uyghur look and sound like?

**Written:** Omniglot has [a page on Uyghur](https://www.omniglot.com/writing/uyghur.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/uig/) has 1 video of Uyghur speakers. Watch [Mustafa, Gulnisa and Elise speaking Uyghur](https://wikitongues.org/videos/mustafa-gulnisa-elise_20190306_uig/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                              |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 9,765 articles in ug.wikipedia; 32 active users. This is ~1/773 of English data and ranks 105 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                            |
| Common Crawl           | 40,585 pages per crawl on average, which is 0.0019% of the crawl (2026). This is ~1/21,966 of English data and ranks 80 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                               |
| FineWeb                | 0.41 GB (uig_Arab 0.33 GB; uig_Latn 50.0 MB; uig_Cyrl 30.0 MB), equivalent to ≈0.20 GB of English after byte-premium scaling; 0.34 GB removed by filtering. This is ~1/131,701 of English data and ranks 83 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 1.02 GB (uig_Arab 1.02 GB) (rank 72 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                   |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Arabic (`Arab`)   | 0.33 GB   | — (no byte premium yet)       | 1.02 GB      | 0.44 GB                        |
| Latin (`Latn`)    | 50.0 MB   | — (no byte premium yet)       | not included | —                              |
| Cyrillic (`Cyrl`) | 30.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                             |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 3,456 sentences / 40,236 tokens in total: [UD_Uyghur-UDT](https://github.com/UniversalDependencies/UD_Uyghur-UDT) (3,456 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 90 lemmas, 8,178 inflected forms ([unimorph/uig](https://github.com/unimorph/uig))                                                                                                                                      |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                          |
| Wordnets               | **None found**                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                                                                                                                                                                                               |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                                   |
| Bible translations (eBible corpus) | **Yes** — 4 translations: full Bible ([uigara](https://ebible.org/details.php?id=uigara), by-sa 4.0); full Bible ([uigcyr](https://ebible.org/details.php?id=uigcyr), by-sa 4.0); full Bible ([uiglat](https://ebible.org/details.php?id=uiglat), by-sa 4.0); full Bible ([uigpin](https://ebible.org/details.php?id=uigpin), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                                |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                                                                                                                                                                                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=117), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.980, R 0.974, FPR 1.50e-04) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.910).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.974 | 0.976 | 0.000 | ✓                |
| OpenLID-v2   |       0.998 |    0.860 | 0.910 | 0.000 | ✓                |
| py3langid    |       0.999 |    0.859 | 0.910 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.858 | 0.908 | 0.000 | ✓                |
| pyfranc      |       0.869 |    0.955 | 0.905 | 0.002 | ✓                |
| commonlingua |       0.960 |    0.865 | 0.897 | 0.000 | ✓                |
| cld2         |       0.966 |    0.851 | 0.896 | 0.000 | ✓                |
| funlangid    |       0.970 |    0.794 | 0.862 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.877 | 0.934 |
| Tatoeba   | 300 |       0.949 |    0.993 | 0.971 |
| UDHR-LID  | 117 |       0.951 |    1.000 | 0.975 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Uyghur to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Uyghur *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Uyghur and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Uyghur has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Uyghur?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Uyghur (and whether the model is exclusively tagged for Uyghur or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **87** text-generation models are explicitly tagged for Uyghur (28 original uploads, 59 fine-tunes/quantisations/merges).
- **19** are tagged *only* for Uyghur.
- Including tags inherited from base models: **87**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        1 | █                    |
|   2023 |        2 | █                    |
|   2024 |        6 | ██                   |
|   2025 |       22 | ████████             |
|   2026 |       56 | ████████████████████ |

### Largest models tagged for Uyghur

| model                                                                                                                                     | parameters   |   # languages tagged |   year | derivative of          |
|:------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                 | 1.9T         |                  143 |   2025 | —                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                     | 856.0B       |                  143 |   2025 | —                      |
| [GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF](https://huggingface.co/GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF)                                               | 30.1B        |                   37 |   2026 | tencent/Hy-MT2-30B-A3B |
| [AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16](https://huggingface.co/AMAImedia/NOESIS-Qwopus3.5-9B-Coder-v3.5-BF16)                     | 9.0B         |                   99 |   2026 | unsloth/Qwen3.5-9B     |
| [AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF](https://huggingface.co/AMAImedia/Qwen3.5-9B-NeoHorse1-Heretic-NOESIS-BF16-GGUF) | 9.0B         |                   99 |   2026 | Qwen/Qwen3.5-9B        |

### Largest models tagged *only* for Uyghur

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of                 |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [pkupie/gemma-3-4b-ug-cpt](https://huggingface.co/pkupie/gemma-3-4b-ug-cpt)                         | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt          |
| [alphaedge-ai/gemma-3-4b-it-uig-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-uig-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [Rekipjan/kakugo-3B-uig-Q4_K_M-GGUF](https://huggingface.co/Rekipjan/kakugo-3B-uig-Q4_K_M-GGUF)     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [pkupie/Qwen2.5-3B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-ug-cpt)                         | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B               |
| [pkupie/Qwen2.5-1.5B-ug-cpt](https://huggingface.co/pkupie/Qwen2.5-1.5B-ug-cpt)                     | 1.5B         |                    1 |   2026 | Qwen/Qwen2.5-1.5B             |

_32 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Uyghur.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 1 dataset; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">1 dataset</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                    | dataset                                                                                             |   # test items | construction                                                     |
|:------------------------------|:------------------------|:----------------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------------------------|
| 1. Linguistic knowledge       | BLiMP                   | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                |            758 | Treebank-based (automatic, UD + UniMorph)                        |
| 3. Commonsense reasoning      | PIQA                    | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) |            100 | Native                                                           |
| 3. Commonsense reasoning      | PIQA                    | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        |            103 | MT + human post-editing                                          |
| 4. Reading comprehension      | QA – extractive RC      | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          |          5,000 | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      |            494 | Native (school/entrance exams)                                   |
| Machine translation           |                         | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         |            854 | Human translation via English pivot                              |
| Machine translation           |                         | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             |          1,012 | Human translation (professional, from English Wikimedia sources) |
| Machine translation           |                         | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           |          1,997 | Human translation (professional, from English)                   |
| Machine translation           |                         | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                |          3,024 | Native (crowdsourced Tatoeba sentence pairs)                     |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Uyghur datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Uyghur? Does it make sense to train one?
  - ~0.44 GB English-equivalent text ≈ 0.11B tokens, enough for a compute-optimal model of ~5.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Uyghur-only model is 4.3B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 43 of ~18,498 papers (0.23%) (rank 96 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Uyghur

Here are up to ten papers published in 2026 that mention Uyghur. None of the 43 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                | paper                                                                          | mentioned in   |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| Diversity in Unity, Theory in Practice: Hierarchical Multitask Benchmarks for Chinese Minority Languages             | [2026.acl-long.1684](https://aclanthology.org/2026.acl-long.1684/)             | body only      |
| Processing Inconsistency Predicts Language Competence: LLM Evaluation Without Answer Labels on Turkic Languages      | [2026.acl-srw.94](https://aclanthology.org/2026.acl-srw.94/)                   | body only      |
| Aspects of Selecting the Right ASR Training Languages for Under-Resourced Languages                                  | [2026.computel-1.16](https://aclanthology.org/2026.computel-1.16/)             | body only      |
| Which Language Should a Skeleton Speak? Language Choices in Multilingual Reasoning                                   | [2026.findings-emnlp.1500](https://aclanthology.org/2026.findings-emnlp.1500/) | body only      |
| RING: Retrieval-Internalized Generation for Continual Large-Scale Knowledge Injection                                | [2026.findings-emnlp.1940](https://aclanthology.org/2026.findings-emnlp.1940/) | body only      |
| Clustering Analysis for Error Detection in Named Entity Recognition Datasets                                         | [2026.law-main.17](https://aclanthology.org/2026.law-main.17/)                 | body only      |
| A Comprehensive Full-Form Lexicon for Arabic NLP and Speech Technology                                               | [2026.lrec-1.108](https://aclanthology.org/2026.lrec-1.108/)                   | body only      |
| Investigating the Role of Synthetic Data Augmentation and Training Strategies on Improving Low-Resource Language ASR | [2026.lrec-1.442](https://aclanthology.org/2026.lrec-1.442/)                   | body only      |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                               | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)               | body only      |
| A Unified Turkic Idiom Understanding Benchmark: Idiom Detection and Semantic Retrieval Across Five Turkic Languages  | [2026.sigturk-1.4](https://aclanthology.org/2026.sigturk-1.4/)                 | body only      |

{% endraw %}
