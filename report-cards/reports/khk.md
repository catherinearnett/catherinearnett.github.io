---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/khk.html
---
{% raw %}
# So you want to work on Mongolian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `khk` · macrolanguage `mon`

**Language family:** **Mongolic-Khitan** › Mongolic › Eastern Mongolic › … › Mongolian ([Glottolog](https://glottolog.org/resource/languoid/id/halh1238))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 6.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `mon`, so includes other varieties

**Official / recognised in:** Mongolia

**Status:** Official language


## What does Mongolian look and sound like?

**Written:** Omniglot has [a page on Mongolian](https://www.omniglot.com/writing/mongolian.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/khk/) has 2 videos of Mongolian speakers. Watch [Khulan speaking Halh Mongolian](https://wikitongues.org/videos/khulan_20160726_khk/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 28,674 articles in mn.wikipedia; 223 active users. ⚠️ NB: counted under the macrolanguage code `mon`, so this number is shared with Mongolian (`mvf`) and overstates Mongolian.                                                                |
| Common Crawl           | 342,482 pages per crawl on average, which is 0.0159% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `mon`, so this number is shared with Mongolian (`mvf`) and overstates Mongolian.                                         |
| FineWeb                | 2.80 GB (khk_Cyrl 2.80 GB), equivalent to ≈1.56 GB of English after byte-premium scaling; 5.33 GB removed by filtering. This is ~1/19,062 of English data and ranks 60 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.20 GB (khk_Cyrl 0.20 GB) (rank 106 of the 166 languages in the set that have any; 166 have none)                                                                                                                                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                  |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 88 sentences / 472 tokens in total: [UD_Mongolian-GDUD](https://github.com/UniversalDependencies/UD_Mongolian-GDUD) (88 sentences). It has POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `mon`, so this may cover other varieties as well as Mongolian. |
| UniMorph               | 2,140 lemmas, 30,143 inflected forms ([unimorph/khk](https://github.com/unimorph/khk))                                                                                                                                                                                                                                       |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                               |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD.                                                                                                                                                                                                                                          |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script); 1,012 sentences (Mong script) — the same sentences in 200+ languages                                                         |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.985 (P 0.976, R 0.995, FPR 1.75e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.898).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.976 |    0.995 | 0.985 | 0.000 | ✓                |
| cld2         |       0.839 |    0.994 | 0.898 | 0.003 | ✓                |
| funlangid    |       0.878 |    0.883 | 0.879 | 0.001 | ✓                |
| commonlingua |       0.838 |    0.922 | 0.876 | 0.002 | ✓                |
| pyfranc      |       0.798 |    0.955 | 0.852 | 0.004 | ✓                |
| fasttext     |       0.754 |    0.997 | 0.844 | 0.003 | ✓                |
| OpenLID-v2   |       0.631 |    0.998 | 0.734 | 0.008 | ✓                |
| py3langid    |       0.552 |    0.995 | 0.642 | 0.016 | ✓                |
| cld3         |       0.485 |    0.993 | 0.581 | 0.026 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.928 |    0.987 | 0.956 |
| Tatoeba   | 300 |       0.952 |    0.990 | 0.971 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Mongolian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Mongolian *and* from closely related languages that might be confused with it. Likely confusions to include: Mongolian (`mvf`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Mongolian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Mongolian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Mongolian (and whether the model is exclusively tagged for Mongolian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **173** text-generation models are explicitly tagged for Mongolian (68 original uploads, 105 fine-tunes/quantisations/merges).
- **32** are tagged *only* for Mongolian.
- Including tags inherited from base models: **199**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | ███                  |
|   2023 |        7 | ██                   |
|   2024 |       26 | ███████              |
|   2025 |       55 | ███████████████      |
|   2026 |       75 | ████████████████████ |

### Largest models tagged for Mongolian

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                      |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B   |
| [GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF](https://huggingface.co/GrahLnn/Hy-MT2-30B-A3B-4bit-GGUF)                           | 30.1B        |                   37 |   2026 | tencent/Hy-MT2-30B-A3B |
| [fenyo/H100-Qwen3-14B-MonEspaceSante-CPT](https://huggingface.co/fenyo/H100-Qwen3-14B-MonEspaceSante-CPT)             | 14.8B        |                    2 |   2026 | Qwen/Qwen3-14B-Base    |

### Largest models tagged *only* for Mongolian

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                           |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------|
| [onlysainaa/gemma3-12b-unsloth-finetuned](https://huggingface.co/onlysainaa/gemma3-12b-unsloth-finetuned) | 12.0B        |                    1 |   2025 | unsloth/gemma-3-12b-it-unsloth-bnb-4bit |
| [pkupie/gemma-3-4b-mn-cpt](https://huggingface.co/pkupie/gemma-3-4b-mn-cpt)                               | 4.3B         |                    1 |   2026 | google/gemma-3-4b-pt                    |
| [alphaedge-ai/gemma-3-4b-it-mon-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-mon-32768)       | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it                    |
| [NikolayKozloff/kakugo-3B-mon-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-mon-Q8_0-GGUF)   | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro           |
| [pkupie/Qwen2.5-3B-mn-cpt](https://huggingface.co/pkupie/Qwen2.5-3B-mn-cpt)                               | 3.1B         |                    1 |   2026 | Qwen/Qwen2.5-3B                         |

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

**6** benchmark datasets in the survey include Mongolian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 2 datasets; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        |            900 | Human translation (professional)               |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            417 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 1,012 sentences (Mong) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Mongolian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Mongolian? Does it make sense to train one?
  - ~1.56 GB English-equivalent text ≈ 0.39B tokens, enough for a compute-optimal model of ~19.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Mongolian-only model is 12.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 80 of ~18,498 papers (0.43%) (rank 66 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Peripheral Mongolian (Inner Mongolia) | Peripheral Mongolian | Halh Mongolian | Inner Mongolia | Mongolian
- ⚠️ The name *Mongolian* is shared with Mongolian (`mvf`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Mongolian. None of the 80 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                               | paper                                                                    |
|:--------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                         | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)   |
| Masking Stale Observations Helps Search Agents — Until It Doesn’t: A Regime Map and Its Mechanism                   | [2026.emnlp-main.756](https://aclanthology.org/2026.emnlp-main.756/)     |
| RAG-KT: Cross-platform Explainable Knowledge Tracing with Multi-view Fusion Retrieval Generation                    | [2026.findings-acl.257](https://aclanthology.org/2026.findings-acl.257/) |
| Lightweight Haar Wavelet Subband Pruning for LLMs                                                                   | [2026.findings-acl.798](https://aclanthology.org/2026.findings-acl.798/) |
| CausalityCheck: A Framework for Evaluating Causal Reasoning in Large Language Models                                | [2026.findings-acl.808](https://aclanthology.org/2026.findings-acl.808/) |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)         |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                          | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)             |
| Cygnet: Refactoring the Open Multilingual Wordnet                                                                   | [2026.lrec-1.628](https://aclanthology.org/2026.lrec-1.628/)             |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                    | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)             |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                            | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)             |

{% endraw %}
