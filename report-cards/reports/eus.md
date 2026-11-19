---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/eus.html
---
{% raw %}
# So you want to work on Basque?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `eus`

**Language family:** none: a language isolate (no demonstrated relatives) ([Glottolog](https://glottolog.org/resource/languoid/id/basq1248))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Latn`

**Speakers:** about 1.0 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Spain

**Status:** Regional official language


## What does Basque look and sound like?

**Written (Basque)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/basque.htm):

> Gizon-emakume guztiak aske jaiotzen dira, duintasun eta eskubide berberak dituztela; eta ezaguera eta kontzientzia dutenez gero, elkarren artean senide legez jokatu beharra dute.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Iberiar Penintsulan bizirik dirauen erromatarren aurreko hizkuntza bakarra da euskara. Gutxitze prozesu gogorra jasan du, etenik gabe lurraldeak eta hiztunak galduz. …

[Hear this text read aloud](https://www.omniglot.com/soundfiles/basque/smp_basque.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/eus/) has 5 videos of Basque speakers. Watch [Txeli speaking Euskara](https://wikitongues.org/videos/txeli_20171103_eus/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 500,116 articles in eu.wikipedia; 898 active users. This is ~1/15 of English data and ranks 29 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 831,392 pages per crawl on average, which is 0.0386% of the crawl (2026). This is ~1/1,072 of English data and ranks 40 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 2.06 GB (eus_Latn 2.06 GB), equivalent to ≈1.94 GB of English after byte-premium scaling; 3.59 GB removed by filtering. This is ~1/25,968 of English data and ranks 63 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 4.36 GB (eus_Latn 4.36 GB) (rank 42 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 8,993 sentences / 121,443 tokens in total: [UD_Basque-BDT](https://github.com/UniversalDependencies/UD_Basque-BDT) (8,993 sentences). It has POS tags, dependency syntax, lemmas and morphological features.   |
| UniMorph               | 26 lemmas, 11,889 inflected forms ([unimorph/eus](https://github.com/unimorph/eus))                                                                                                                                        |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                             |
| Wordnets               | [Multilingual Central Repository (Basque)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-eu-1.4.tar.xz): 29,413 synsets, 26,390 words, 48,934 senses; licence: https://creativecommons.org/licenses/by/3.0/. |

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

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.987 (P 0.980, R 0.994, FPR 1.23e-04) averaged over 5 dataset(s). Runner-up: cld2 (F1 0.980).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.980 |    0.994 | 0.987 | 0.000 | ✓                |
| cld2         |       0.991 |    0.969 | 0.980 | 0.000 | ✓                |
| fasttext     |       0.892 |    0.996 | 0.937 | 0.001 | ✓                |
| pyfranc      |       0.969 |    0.910 | 0.936 | 0.000 | ✓                |
| funlangid    |       0.989 |    0.871 | 0.920 | 0.000 | ✓                |
| commonlingua |       0.940 |    0.904 | 0.919 | 0.001 | ✓                |
| py3langid    |       0.868 |    0.993 | 0.915 | 0.002 | ✓                |
| OpenLID-v2   |       0.792 |    1.000 | 0.838 | 0.006 | ✓                |
| cld3         |       0.700 |    0.965 | 0.779 | 0.008 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.951 |    0.970 | 0.960 |
| UDHR-LID  |  59 |       0.967 |    1.000 | 0.983 |
| Wikipedia | 300 |       0.984 |    1.000 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Basque to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Basque *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Basque and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Basque?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Basque (and whether the model is exclusively tagged for Basque or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **472** text-generation models are explicitly tagged for Basque (147 original uploads, 325 fine-tunes/quantisations/merges).
- **65** are tagged *only* for Basque.
- Including tags inherited from base models: **907**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       43 | █████                |
|   2023 |       28 | ███                  |
|   2024 |       80 | █████████            |
|   2025 |      139 | ███████████████      |
|   2026 |      182 | ████████████████████ |

### Largest models tagged for Basque

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Basque

| model                                                                                                           | parameters   |   # languages tagged |   year | derivative of            |
|:----------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------|
| [Iker/Latxa-Llama-3.1-70B-Instruct-w8a8_fp8](https://huggingface.co/Iker/Latxa-Llama-3.1-70B-Instruct-w8a8_fp8) | 70.6B        |                    1 |   2025 | meta-llama/Llama-3.1-70B |
| [SimpleLLM/kode-32b-lora](https://huggingface.co/SimpleLLM/kode-32b-lora)                                       | 32.0B        |                    1 |   2026 | Qwen/Qwen2.5-32B         |
| [HiTZ/eu_Qwen3-14B-Base](https://huggingface.co/HiTZ/eu_Qwen3-14B-Base)                                         | 14.0B        |                    1 |   2025 | Qwen/Qwen3-14B-Base      |
| [aetxebeste/Gemma-Kimu-9b-it-Q4_K_M-GGUF](https://huggingface.co/aetxebeste/Gemma-Kimu-9b-it-Q4_K_M-GGUF)       | 9.2B         |                    1 |   2025 | google/gemma-2-9b        |
| [HiTZ/eu_Qwen3-8B-Base](https://huggingface.co/HiTZ/eu_Qwen3-8B-Base)                                           | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base       |

_66 tagged models have unknown parameter counts and are not ranked by size._

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

**27** benchmark datasets in the survey include Basque.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 3 datasets; Pragmatics &amp; discourse: 3 datasets; Commonsense reasoning: 9 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">9 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">3 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">3 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                          | dataset                                                                                             | # test items   | construction                                                      |
|:---------------------------------------|:------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                         | [BHS](https://github.com/dariakryvosheieva/syntactic_generalization_multilingual)                   | 8,000          | Template-based                                                    |
| 1. Linguistic knowledge                | BLiMP                         | [BL2MP](https://huggingface.co/datasets/orai-nlp/bl2mp)                                             | 1,800          | Existing material                                                 |
| 1. Linguistic knowledge                | BLiMP                         | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                | 273            | Treebank-based (automatic, UD + UniMorph)                         |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)     | [EpecKorrefBin (BasqueGLUE)](https://huggingface.co/datasets/orai-nlp/basqueGLUE)                   | 587            | Native (coreference corpus recast)                                |
| 2. Pragmatics, discourse & coreference | WNLI                          | [WNLI-eu](https://huggingface.co/datasets/HiTZ/wnli-eu)                                             | 146            | Human translation (professional)                                  |
| 2. Pragmatics, discourse & coreference | WinoGrande                    | Winogrande_HT_eu_sample                                                                             | 250            | Human translation (native speaker)                                |
| 3. Commonsense reasoning               | COPA                          | [XCOPA-eu](https://huggingface.co/datasets/HiTZ/XCOPA-eu)                                           | 500            | Human translation (professional)                                  |
| 3. Commonsense reasoning               | HellaSwag                     | [HellaSwag_HT_eu_sample](https://huggingface.co/datasets/orai-nlp/HellaSwag_HT_eu_sample)           | 250            | Human translation (sample)                                        |
| 3. Commonsense reasoning               | HellaSwag                     | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)            | 9,255          | Machine translation (GPT-3.5-turbo)                               |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                            |
| 3. Commonsense reasoning               | PIQA                          | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                           |
| 3. Commonsense reasoning               | Physical commonsense          | [BasPhyCo-west](https://github.com/hitz-zentroa/BasPhyCo)                                           | 356            | LLM conversion (Latxa) from standard Basque + native post-editing |
| 3. Commonsense reasoning               | Physical commonsense          | [BasPhyCo](https://github.com/hitz-zentroa/BasPhyCo)                                                | 356            | Human translation from Italian GITA (with localisation)           |
| 3. Commonsense reasoning               | Physical commonsense          | [PIQA-eu](https://huggingface.co/datasets/HiTZ/PIQA-eu)                                             | —              | Human translation (professional)                                  |
| 3. Commonsense reasoning               | StoryCloze                    | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                               | 1,511          | Human translation (professional)                                  |
| 4. Reading comprehension               | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                  |
| 4. Reading comprehension               | QA – MC reading comprehension | [EusReading](https://github.com/hitz-zentroa/latxa)                                                 | 352            | Native                                                            |
| 4. Reading comprehension               | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusExams](https://github.com/hitz-zentroa/latxa)                                                   | 16,774         | Native (public-service exams)                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusProficiency](https://github.com/hitz-zentroa/latxa)                                             | 5,169          | Native (EGA C1 exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [EusTrivia](https://github.com/hitz-zentroa/latxa)                                                  | 1,715          | Native                                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                     | —              | Native (local exams)                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ       | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)              | —              | Machine translation (GPT-3.5, Okapi)                              |
| Machine translation                    |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                    |
| Machine translation                    |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,060          | Native (crowdsourced Tatoeba sentence pairs)                      |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, WSC
- **3. Commonsense reasoning:** Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Basque datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Basque? Does it make sense to train one?
  - ~4.11 GB English-equivalent text ≈ 1.03B tokens, enough for a compute-optimal model of ~51.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Basque-only model is 70.6B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 178 of ~18,498 papers (0.96%) (rank 35 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Basque

Here are up to ten papers published in 2026 that mention Basque. None of the 178 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                                        | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|:---------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)           | body only      |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                         | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)   | body only      |
| QFrBLiMP: a Quebec-French Benchmark of Linguistic Minimal Pairs                                                             | [2026.findings-eacl.224](https://aclanthology.org/2026.findings-eacl.224/)   | body only      |
| Translation Asymmetry in LLMs as a Data Augmentation Factor: A Case Study for 6 Romansh Language Varieties                  | [2026.findings-emnlp.230](https://aclanthology.org/2026.findings-emnlp.230/) | body only      |
| Benchmarking Mathematical Reasoning in a Low-Resource Language: Structured Prompting and Evaluation in Basque               | [2026.lrec-1.412](https://aclanthology.org/2026.lrec-1.412/)                 | body only      |
| A Single Model Ensemble Framework for Neural Machine Translation Using Pivot Translation                                    | [2026.lrec-1.672](https://aclanthology.org/2026.lrec-1.672/)                 | body only      |
| Extracting Medical Image-Related Entities from Spanish Electronic Health Records Using NER Methods                          | [2026.lrec-1.829](https://aclanthology.org/2026.lrec-1.829/)                 | body only      |
| Proffiliadur: Welsh Language Text Profiling Toolkit                                                                         | [2026.lrec-1.88](https://aclanthology.org/2026.lrec-1.88/)                   | body only      |
| Register Sensitivity in Scalar MT Evaluation: Evidence from Spanish–Basque Informal Discourse                               | [2026.sigul-1.2](https://aclanthology.org/2026.sigul-1.2/)                   | body only      |
| CUS-QA: Local-Knowledge-Oriented Open-Ended Question Answering Dataset                                                      | [2026.tacl-1.67](https://aclanthology.org/2026.tacl-1.67/)                   | body only      |

{% endraw %}
