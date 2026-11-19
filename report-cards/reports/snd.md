---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/snd.html
---
{% raw %}
# So you want to work on Sindhi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `snd`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Sindhi-Kachchi ([Glottolog](https://glottolog.org/resource/languoid/id/sind1272))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Writing systems:** `Arab`

**Speakers:** about 43.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** India, Pakistan

**Status:** Regional official language


## What does Sindhi look and sound like?

**Written:** Omniglot has [a page on Sindhi](https://www.omniglot.com/writing/sindhi.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/snd/) has 1 video of Sindhi speakers. Watch [Mazhar speaking Sindhi](https://wikitongues.org/videos/mazhar_20190211_snd/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 23,392 articles in sd.wikipedia; 43 active users. This is ~1/323 of English data and ranks 81 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                                                                                                                                                                         |
| Common Crawl           | 44,743 pages per crawl on average, which is 0.0021% of the crawl (2026). This is ~1/19,925 of English data and ranks 78 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                                                                                                                                                                            |
| FineWeb                | 0.42 GB (snd_Arab 0.42 GB; snd_Deva 0; snd_Latn 0), equivalent to ≈0.26 GB of English after byte-premium scaling (⚠️ only 100% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 0.30 GB removed by filtering. This is ~1/127,115 of English data and ranks 82 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.81 GB (snd_Arab 0.81 GB) (rank 79 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                                                                                                                                                                |

**By writing system:**

| Writing system      | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Arabic (`Arab`)     | 0.42 GB   | — (no byte premium yet)       | 0.81 GB      | 0.51 GB                        |
| Devanagari (`Deva`) | 0         | — (no byte premium yet)       | not included | —                              |
| Latin (`Latn`)      | 0         | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                               |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 5,766 sentences / 95,358 tokens in total: [UD_Sindhi-Isra](https://github.com/UniversalDependencies/UD_Sindhi-Isra) (5,766 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                            |
| Wordnets               | **None found**                                                                                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Arab script); 997 sentences (Deva script) — the same sentences in 200+ languages                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Arab script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_sd-Deva) en → sd-Deva: size not listed                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid.
- **Eval datasets (3):** FLORES (n=300), NTREX (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.997 (P 0.999, R 0.996, FPR 6.64e-06) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.959).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.996 | 0.997 | 0.000 | ✓                |
| funlangid    |       0.980 |    0.940 | 0.959 | 0.000 | ✓                |
| cld2         |       0.999 |    0.838 | 0.894 | 0.000 | ✓                |
| fasttext     |       0.998 |    0.838 | 0.893 | 0.000 | ✓                |
| OpenLID-v2   |       0.999 |    0.836 | 0.893 | 0.000 | ✓                |
| commonlingua |       0.949 |    0.830 | 0.877 | 0.000 | ✓                |
| cld3         |       0.733 |    0.826 | 0.773 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.990 | 0.993 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Sindhi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Sindhi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Sindhi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Sindhi has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Sindhi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Sindhi (and whether the model is exclusively tagged for Sindhi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **179** text-generation models are explicitly tagged for Sindhi (86 original uploads, 93 fine-tunes/quantisations/merges).
- **26** are tagged *only* for Sindhi.
- Including tags inherited from base models: **245**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        4 | █                    |
|   2024 |       23 | ████                 |
|   2025 |       39 | ███████              |
|   2026 |      106 | ████████████████████ |

### Largest models tagged for Sindhi

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                   | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)       | 856.0B       |                  143 |   2025 | —                    |
| [RedHatAI/sarvam-105b-FP8-dynamic](https://huggingface.co/RedHatAI/sarvam-105b-FP8-dynamic) | 106.1B       |                   23 |   2026 | sarvamai/sarvam-105b |
| [DurgaPrasad04/sarvam-105b](https://huggingface.co/DurgaPrasad04/sarvam-105b)               | 106.0B       |                   23 |   2026 | —                    |
| [anipleades/sarvam-105b](https://huggingface.co/anipleades/sarvam-105b)                     | 106.0B       |                   23 |   2026 | —                    |

### Largest models tagged *only* for Sindhi

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-snd-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-snd-32768)           | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-snd-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-snd-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-snd](https://huggingface.co/ptrdvn/kakugo-3B-snd)                                     | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-snd-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-snd-32768)           | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [dheeyantra/dhee-nxtgen-qwen3-sindhi-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-sindhi-v2) | 1.7B         |                    1 |   2025 | —                             |

_40 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Sindhi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 1 dataset; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#33691e" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                         | task                           | dataset                                                                                                                 |   # test items | construction                                   |
|:------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                                        |            500 | Human translation                              |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) (2 varieties/pairs) |            200 | Native                                         |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel) (2 varieties/pairs)        |            206 | MT + human post-editing                        |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                           |            900 | Human translation (professional)               |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                              |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                                  |            100 | Native (community-written, peer-verified)      |
| Machine translation           |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                               |          1,997 | Human translation (professional, from English) |
| Machine translation           |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                                    |              4 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                               | Direction(s)                      | Size                   | Human reference   |
|:-------------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                | multi-way (all languages)         | 2,009 sentences (Arab) | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                | multi-way (all languages)         | 997 sentences (Deva)   | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                            | ↔ English (and 8 pivot languages) | 1,358 sentences (Arab) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_sd-Deva) (training data) | en → sd-Deva                      | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Sindhi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Sindhi? Does it make sense to train one?
  - ~0.51 GB English-equivalent text ≈ 0.13B tokens, enough for a compute-optimal model of ~6.3M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Sindhi-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 44 of ~18,498 papers (0.24%) (rank 93 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Sindhi

Here are up to ten papers published in 2026 that mention Sindhi. None of the 44 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                        | paper                                                                      |
|:-----------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Revisiting Evaluation of Question Answering Systems in Low-Resource Indic Languages: Bridging Human and Metric Alignment     | [2026.acl-short.58](https://aclanthology.org/2026.acl-short.58/)           |
| Multilingual Tokenization through the Lens of Indian Languages: Challenges and Insights                                      | [2026.findings-acl.1632](https://aclanthology.org/2026.findings-acl.1632/) |
| Mending the Holes: Mitigating Reward Hacking in Reinforcement Learning for Multilingual Translation                          | [2026.findings-acl.1682](https://aclanthology.org/2026.findings-acl.1682/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                   | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| Common Voice for Pakistan: Developing an Open Speech Corpus for Low-Resource Pakistani Languages                             | [2026.lrec-1.265](https://aclanthology.org/2026.lrec-1.265/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Beyond Catalogue Counts: The Dataset Visibility Asymmetry in Low-Resource Multilingual NLP                                   | [2026.lrec-1.481](https://aclanthology.org/2026.lrec-1.481/)               |
| MaskedVerbalizer: Automatic Verbalizer Construction for Few-Shot Text Classification in Low-Resource Right-to-Left Languages | [2026.lrec-1.59](https://aclanthology.org/2026.lrec-1.59/)                 |
| SdQuAD: A Large Benchmark Question Answering Dataset for Low-resource Sindhi Language                                        | [2026.resourceful-4.6](https://aclanthology.org/2026.resourceful-4.6/)     |
| Beyond Fine-Tuning: Procrustes Alignment of Multilingual Embeddings for Low-Resource Cross-Lingual Retrieval                 | [2026.sigul-1.23](https://aclanthology.org/2026.sigul-1.23/)               |

{% endraw %}
