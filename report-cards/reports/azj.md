---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/azj.html
---
{% raw %}
# So you want to work on Azerbaijani?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `azj` · macrolanguage `aze`

**Language family:** **Turkic** › Common Turkic › Oghuz › … › Central Oghuz ([Glottolog](https://glottolog.org/resource/languoid/id/nort2697))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 33.8 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `aze`, so includes other varieties

**Official / recognised in:** Azerbaijan, Russia

**Status:** Official language; Regional official language


## What does Azerbaijani look and sound like?

**Written:** Omniglot has [a page on Azerbaijani](https://www.omniglot.com/writing/azeri.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/azj/) has 5 videos of Azerbaijani speakers. Watch [Tarlan speaking Azeri](https://wikitongues.org/videos/tarlan_20140729_azj/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 218,952 articles in az.wikipedia; 878 active users. ⚠️ NB: counted under the macrolanguage code `aze`, so this number is shared with Turkmen (`azb`) and overstates Azerbaijani.                                                                                                                                                                                                             |
| Common Crawl           | 1,304,787 pages per crawl on average, which is 0.0606% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `aze`, so this number is shared with Turkmen (`azb`) and overstates Azerbaijani.                                                                                                                                                                                     |
| FineWeb                | 11.31 GB (azj_Latn 11.30 GB; azj_Cyrl 10.0 MB), equivalent to ≈10.50 GB of English after byte-premium scaling (⚠️ only 100% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 22.86 GB removed by filtering. This is ~1/4,722 of English data and ranks 39 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.17 GB (azj_Latn 0.17 GB) (rank 111 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                           |

**By writing system:**

| Writing system    | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Latin (`Latn`)    | 11.30 GB  | 10.50 GB                      | 0.17 GB      | 0.15 GB                        |
| Cyrillic (`Cyrl`) | 10.0 MB   | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 148 sentences / 902 tokens in total: [UD_Azerbaijani-TueCL](https://github.com/UniversalDependencies/UD_Azerbaijani-TueCL) (148 sentences). It has POS tags, dependency syntax, lemmas and morphological features. ⚠️ Listed under the macrolanguage code `aze`, so this may cover other varieties as well as Azerbaijani. |
| UniMorph               | 340 lemmas, 8,004 inflected forms ([unimorph/aze](https://github.com/unimorph/aze)) ⚠️ Listed under the macrolanguage code `aze`, so this may cover other varieties as well as Azerbaijani.                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                         |
| Wordnets               | **None found**                                                                                                                                                                                                                                                                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.979 (P 0.973, R 0.986, FPR 2.34e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.884).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.973 |    0.986 | 0.979 | 0.000 | ✓                |
| OpenLID-v2   |       0.862 |    0.910 | 0.884 | 0.002 | ✓                |
| cld2         |       0.865 |    0.887 | 0.874 | 0.001 | ✓                |
| py3langid    |       0.853 |    0.898 | 0.873 | 0.003 | ✓                |
| commonlingua |       0.886 |    0.856 | 0.869 | 0.001 | ✓                |
| pyfranc      |       0.878 |    0.816 | 0.843 | 0.001 | ✓                |
| fasttext     |       0.781 |    0.908 | 0.835 | 0.003 | ✓                |
| funlangid    |       0.873 |    0.783 | 0.820 | 0.001 | ✓                |
| cld3         |       0.494 |    0.894 | 0.626 | 0.017 | ✗                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.887 |    0.943 | 0.914 |
| Wikipedia | 300 |       0.980 |    0.987 | 0.983 |
| CommonLID | 300 |       0.990 |    0.983 | 0.987 |
| UDHR-LID  | 114 |       0.983 |    1.000 | 0.991 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Azerbaijani to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Azerbaijani *and* from closely related languages that might be confused with it. Likely confusions to include: Turkmen (`azb`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Azerbaijani and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Azerbaijani has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Azerbaijani?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Azerbaijani (and whether the model is exclusively tagged for Azerbaijani or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **201** text-generation models are explicitly tagged for Azerbaijani (85 original uploads, 116 fine-tunes/quantisations/merges).
- **49** are tagged *only* for Azerbaijani.
- Including tags inherited from base models: **250**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |       12 | ███                  |
|   2024 |       36 | ██████████           |
|   2025 |       70 | ███████████████████  |
|   2026 |       75 | ████████████████████ |

### Largest models tagged for Azerbaijani

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [16th-research-lab-ai/actum-az-31b](https://huggingface.co/16th-research-lab-ai/actum-az-31b)                         | 31.3B        |                    3 |   2026 | —                    |
| [vrashad/gpt-oss-20b-medical-az](https://huggingface.co/vrashad/gpt-oss-20b-medical-az)                               | 20.0B        |                    1 |   2025 | openai/gpt-oss-20b   |

### Largest models tagged *only* for Azerbaijani

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [vrashad/gpt-oss-20b-medical-az](https://huggingface.co/vrashad/gpt-oss-20b-medical-az)             | 20.0B        |                    1 |   2025 | openai/gpt-oss-20b   |
| [lmnglzd/az-spellfix-qwen35-9b-short](https://huggingface.co/lmnglzd/az-spellfix-qwen35-9b-short)   | 9.0B         |                    1 |   2026 | Qwen/Qwen3.5-9B      |
| [omar07ibrahim/unt-8b](https://huggingface.co/omar07ibrahim/unt-8b)                                 | 8.0B         |                    1 |   2025 | —                    |
| [alphaedge-ai/Qwen3.5-4B-aze-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-aze-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B           |
| [alphaedge-ai/gemma-3-4b-it-aze-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-aze-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |

_67 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Azerbaijani (plus 2 labelled with the macrolanguage `aze`, included below).

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 4 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 3 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                   |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench) (as `aze`)                                    | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                         |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                        |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench) (as `aze`)                                   | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                           |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [TUMLU](https://github.com/ceferisbarov/TUMLU)                                                      | 700            | Native (school/entrance exams)                 |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)      |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 2,659          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Azerbaijani datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Azerbaijani? Does it make sense to train one?
  - ~10.50 GB English-equivalent text ≈ 2.63B tokens, enough for a compute-optimal model of ~131.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Azerbaijani-only model is 20.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 63 of ~18,498 papers (0.34%) (rank 78 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: North Azerbaijani | Azerbaijani

Here are up to ten papers published in 2026 that mention Azerbaijani. None of the 63 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Sign-Language Datasets at Scale: A Comprehensive Survey on Resources, Benchmarks, and Annotation Standards                                    | [2026.acl-long.1928](https://aclanthology.org/2026.acl-long.1928/)           |
| Language Family Matters: Evaluating LLM-based ASR Across Linguistic Boundaries                                                                | [2026.eacl-short.36](https://aclanthology.org/2026.eacl-short.36/)           |
| Phoneme- and Word-Level Metrics Using Self-Supervised Speech Representations for Forced Alignment Evaluation                                  | [2026.findings-emnlp.279](https://aclanthology.org/2026.findings-emnlp.279/) |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                 |
| MultiInpaintCOCO: Fine-Grained Visual Understanding in Multiple Languages                                                                     | [2026.mrl-1.45](https://aclanthology.org/2026.mrl-1.45/)                     |
| Quantifying mutual intelligibility gradients in Turkic languages using language models                                                        | [2026.scil-main.41](https://aclanthology.org/2026.scil-main.41/)             |
| wangkongqiang at SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                                | [2026.semeval-1.36](https://aclanthology.org/2026.semeval-1.36/)             |
| SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                                                 | [2026.semeval-1.455](https://aclanthology.org/2026.semeval-1.455/)           |
| Bukva: Russian Sign Language Alphabet                                                                                                         | [2026.wslp-1.15](https://aclanthology.org/2026.wslp-1.15/)                   |

{% endraw %}
