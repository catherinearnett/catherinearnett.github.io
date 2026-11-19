---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/afr.html
---
{% raw %}
# So you want to work on Afrikaans?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `afr`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Afrikaansic ([Glottolog](https://glottolog.org/resource/languoid/id/afri1274))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 10.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** South Africa

**Status:** Official language


## What does Afrikaans look and sound like?

**Written:** Omniglot has [a page on Afrikaans](https://www.omniglot.com/writing/afrikaans.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/afr/) has 7 videos of Afrikaans speakers. Watch [See all](https://wikitongues.org/videos/?language=afr).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 143,882 articles in af.wikipedia; 279 active users. This is ~1/52 of English data and ranks 51 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 178,281 pages per crawl on average, which is 0.0083% of the crawl (2026). This is ~1/5,001 of English data and ranks 58 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 3.68 GB (afr_Latn 3.68 GB), equivalent to ≈3.55 GB of English after byte-premium scaling; 4.11 GB removed by filtering. This is ~1/14,508 of English data and ranks 54 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 5.35 GB (afr_Latn 5.35 GB) (rank 38 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                               |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 1,934 sentences / 49,258 tokens in total: [UD_Afrikaans-AfriBooms](https://github.com/UniversalDependencies/UD_Afrikaans-AfriBooms) (1,934 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 175,799 lemmas, 335,067 inflected forms ([unimorph/afr](https://github.com/unimorph/afr))                                                                                                                                                 |
| Wikidata labels        | 1,800,116 Wikidata items have a label in Afrikaans. (Wikidata codes (labels): af (1,800,116))                                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                      |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 50,309,449 sentence pairs with English across 20 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (39,314,717), [CCMatrix](https://opus.nlpl.eu/CCMatrix) (8,694,461), [CCAligned](https://opus.nlpl.eu/CCAligned) (1,504,065), [XLEnt](https://opus.nlpl.eu/XLEnt) (234,103), [GNOME](https://opus.nlpl.eu/GNOME) (127,323). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                      |
| Tatoeba                                                                                  | 4,940 sentences, 3,461 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/afr/none)).                                                                                                                                                                                                            |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                                                                                                                                                              |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_af) en → af: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_af) en → af: size not listed                                                                                                                   |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **10 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=88), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=60), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.975 (P 0.984, R 0.968, FPR 1.19e-04) averaged over 7 dataset(s). Runner-up: py3langid (F1 0.946).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.984 |    0.968 | 0.975 | 0.000 | ✓                |
| py3langid    |       0.928 |    0.968 | 0.946 | 0.001 | ✓                |
| cld2         |       0.972 |    0.918 | 0.942 | 0.000 | ✓                |
| fasttext     |       0.910 |    0.972 | 0.939 | 0.001 | ✓                |
| OpenLID-v2   |       0.888 |    0.982 | 0.929 | 0.001 | ✓                |
| cld3         |       0.866 |    0.939 | 0.899 | 0.002 | ✓                |
| funlangid    |       0.921 |    0.856 | 0.887 | 0.001 | ✓                |
| pyfranc      |       0.842 |    0.865 | 0.853 | 0.002 | ✓                |
| commonlingua |       0.954 |    0.775 | 0.847 | 0.000 | ✓                |
| AfroLID      |       0.380 |    0.970 | 0.509 | 0.102 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID |  88 |       0.974 |    0.841 | 0.902 |
| Tatoeba   | 300 |       0.938 |    0.963 | 0.951 |
| Wikipedia | 300 |       0.980 |    0.983 | 0.982 |
| NTREX     | 300 |       1.000 |    0.993 | 0.997 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| SmolSent  | 300 |       0.997 |    1.000 | 0.998 |
| UDHR-LID  |  60 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Afrikaans to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Afrikaans *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Afrikaans and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Afrikaans has no wordnet yet. You could build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Afrikaans?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Afrikaans (and whether the model is exclusively tagged for Afrikaans or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **179** text-generation models are explicitly tagged for Afrikaans (45 original uploads, 134 fine-tunes/quantisations/merges).
- **23** are tagged *only* for Afrikaans.
- Including tags inherited from base models: **253**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        8 | ██                   |
|   2023 |        6 | █                    |
|   2024 |       25 | ██████               |
|   2025 |       58 | ██████████████       |
|   2026 |       82 | ████████████████████ |

### Largest models tagged for Afrikaans

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                    |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                    |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B |
| [Sunbird/Sunflower-Qwen3.8-27B](https://huggingface.co/Sunbird/Sunflower-Qwen3.8-27B)                                 | 27.4B        |                   24 |   2026 | Qwen/Qwen3.8-27B     |
| [McGill-NLP/AfriqueQwen-14B](https://huggingface.co/McGill-NLP/AfriqueQwen-14B)                                       | 14.8B        |                   21 |   2026 | Qwen/Qwen3-14B-Base  |

### Largest models tagged *only* for Afrikaans

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of             |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------|
| [DGurgurov/llama-3.1-8b-afr_latn](https://huggingface.co/DGurgurov/llama-3.1-8b-afr_latn)           | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B   |
| [DGurgurov/aya-expanse-8b-afr_latn](https://huggingface.co/DGurgurov/aya-expanse-8b-afr_latn)       | 8.0B         |                    1 |   2026 | CohereLabs/aya-expanse-8b |
| [alphaedge-ai/Qwen3.5-4B-afr-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-afr-32768)       | 4.0B         |                    1 |   2026 | Qwen3.5-4B                |
| [alphaedge-ai/gemma-3-4b-it-afr-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-afr-32768) | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it      |
| [alphaedge-ai/Qwen3.5-2B-afr-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-afr-32768)       | 1.8B         |                    1 |   2026 | Qwen3.5-2B                |

_29 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Afrikaans.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 2 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 2 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#1b3d0a" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                                           | # test items   | construction                                   |
|:---------------------------------------|:------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------|
| 2. Pragmatics, discourse & coreference | WinoGrande                    | [WinoGrande-afr (Alhanai et al.)](https://huggingface.co/datasets/Institute-Disease-Modeling/mmlu-winogrande-afr) | —              | Human translation                              |
| 3. Commonsense reasoning               | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning               | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)               |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                                   | 446            | Native (national exams)                        |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | LLM translation + expert review                |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English) |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,374          | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_af) (training data)   | en → af                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_af) (training data) | en → af                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Afrikaans datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Afrikaans? Does it make sense to train one?
  - ~5.15 GB English-equivalent text ≈ 1.29B tokens, enough for a compute-optimal model of ~64.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Afrikaans-only model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 64 of ~18,498 papers (0.35%) (rank 77 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Afrikaans

Here are up to ten papers published in 2026 that mention Afrikaans. None of the 64 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Speak No Evil, Just Prompt: Low-resource Multilingual Toxic Speech Detection with Audio Language Model                          | [2026.findings-acl.439](https://aclanthology.org/2026.findings-acl.439/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                                              | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/)     |
| Is Multilingual LLM Watermarking Truly Multilingual? Scaling Robustness to 100+ Languages via Back-Translation                  | [2026.findings-emnlp.1115](https://aclanthology.org/2026.findings-emnlp.1115/) |
| Identifying Crucial Attention Heads for Multilingual Language Models: Retrieval and Retrieval-Transition Heads                  | [2026.findings-emnlp.2114](https://aclanthology.org/2026.findings-emnlp.2114/) |
| Linguistic Distance Segregates Latent Representations in Automatic Speech Recognition Systems                                   | [2026.findings-emnlp.2366](https://aclanthology.org/2026.findings-emnlp.2366/) |
| Prompts in the Wild: A Large Analyzed Collection of Transactional Prompts in Code                                               | [2026.law-main.19](https://aclanthology.org/2026.law-main.19/)                 |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                      | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| Goldfish: Monolingual Language Models for 350 Languages                                                                         | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Which languages are "hot", and which are "cool"? Using Universal Dependencies for large-scale comparisons of subject expression | [2026.udw-1.2](https://aclanthology.org/2026.udw-1.2/)                         |
| Verifying the Menzerath-Altmann law in the verbal domain in 180 languages                                                       | [2026.udw-1.5](https://aclanthology.org/2026.udw-1.5/)                         |

{% endraw %}
