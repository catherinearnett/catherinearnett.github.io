---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bul.html
---
{% raw %}
# So you want to work on Bulgarian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bul`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Macedo-Bulgarian ([Glottolog](https://glottolog.org/resource/languoid/id/bulg1262))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Cyrl`

**Speakers:** about 7.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Bulgaria

**Status:** Official language


## What does Bulgarian look and sound like?

**Written**, sample text from [Omniglot](https://www.omniglot.com/writing/bulgarian.htm):

> Recordings on this page by Стефан Валериев
> Станчев (Stefan Valeriev Stančev)

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/bulgarian.htm):

> Всички хора се раждат свободни и равни по достойнство и права. Tе са надарени с разум и съвест и следва да се отнасят помежду си в дух на братство.

*Transliteration:* Vsichki hora se razhdat svobodni i ravni po dostoynstvo i prava. Te sa nadareni s razum i savest i sledva da se otnasyat pomezhdu si v duh na bratstvo. Listen to a recording of this text by Стефан Валериев Станчев

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_bg.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/bul/) has 4 videos of Bulgarian speakers. Watch [Dr. Karel Oliva speaking Czech, English, Bulgarian, Italian, Standard German, Russian](https://wikitongues.org/videos/dr-kareloliva_20160330_ces-eng-bul-ita-deu-rus/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 312,933 articles in bg.wikipedia; 1,806 active users. This is ~1/24 of English data and ranks 34 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | 6,062,008 pages per crawl on average, which is 0.2814% of the crawl (2026). This is ~1/147 of English data and ranks 26 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 49.12 GB (bul_Cyrl 49.12 GB), equivalent to ≈27.10 GB of English after byte-premium scaling; 40.66 GB removed by filtering. This is ~1/1,088 of English data and ranks 26 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.69 GB (bul_Cyrl 9.69 GB) (rank 13 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 11,138 sentences / 156,149 tokens in total: [UD_Bulgarian-BTB](https://github.com/UniversalDependencies/UD_Bulgarian-BTB) (11,138 sentences). It has POS tags, dependency syntax, lemmas and morphological features.                                                                                                                                           |
| UniMorph               | 2,468 lemmas, 55,730 inflected forms ([unimorph/bul](https://github.com/unimorph/bul))                                                                                                                                                                                                                                                                                     |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                             |
| Wordnets               | [BulTreeBank Wordnet (BTB-WN)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-bg-1.4.tar.xz): 4,959 synsets, 6,737 words, 8,936 senses; licence: https://creativecommons.org/licenses/by/3.0/; [BalkaNet](http://www.dblab.upatras.gr/balkanet/) (size not listed); [BulNet](http://dcl.bas.bg/BulNet/wordnet_en.html) (size not listed); licence: CC By 3.0. |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=109), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.983 (P 0.984, R 0.982, FPR 1.20e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.959).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.984 |    0.982 | 0.983 | 0.000 | ✓                |
| fasttext     |       0.938 |    0.986 | 0.959 | 0.001 | ✓                |
| cld2         |       0.950 |    0.899 | 0.921 | 0.000 | ✓                |
| commonlingua |       0.921 |    0.883 | 0.901 | 0.001 | ✓                |
| OpenLID-v2   |       0.851 |    0.974 | 0.899 | 0.002 | ✓                |
| py3langid    |       0.782 |    0.962 | 0.850 | 0.004 | ✓                |
| pyfranc      |       0.726 |    0.821 | 0.768 | 0.004 | ✓                |
| cld3         |       0.664 |    0.938 | 0.763 | 0.007 | ✓                |
| funlangid    |       0.718 |    0.806 | 0.752 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 109 |       0.971 |    0.917 | 0.943 |
| Tatoeba   | 300 |       0.948 |    0.980 | 0.964 |
| Wikipedia | 300 |       0.990 |    1.000 | 0.995 |
| NTREX     | 300 |       0.997 |    0.997 | 0.997 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Bulgarian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Bulgarian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Bulgarian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Bulgarian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Bulgarian (and whether the model is exclusively tagged for Bulgarian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **508** text-generation models are explicitly tagged for Bulgarian (152 original uploads, 356 fine-tunes/quantisations/merges).
- **46** are tagged *only* for Bulgarian.
- Including tags inherited from base models: **975**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       17 | ██                   |
|   2023 |       29 | ███                  |
|   2024 |      117 | ████████████         |
|   2025 |      151 | ████████████████     |
|   2026 |      194 | ████████████████████ |

### Largest models tagged for Bulgarian

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [nu11secur1ty/DeepSeek-V4-Pro-Base](https://huggingface.co/nu11secur1ty/DeepSeek-V4-Pro-Base)         | 1.6T         |                    2 |   2026 | —                                      |
| [nu11secur1ty/DeepSeek-V4-Pro](https://huggingface.co/nu11secur1ty/DeepSeek-V4-Pro)                   | 861.6B       |                    2 |   2026 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |

### Largest models tagged *only* for Bulgarian

| model                                                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                               |
|:------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [burgasdotpro/bgGPT-DeepSeek-R1-Distill-Qwen-14B](https://huggingface.co/burgasdotpro/bgGPT-DeepSeek-R1-Distill-Qwen-14B)                             | 14.8B        |                    1 |   2025 | deepseek-ai/DeepSeek-R1-Distill-Qwen-14B    |
| [burgasdotpro/bgGPT-Phi-4](https://huggingface.co/burgasdotpro/bgGPT-Phi-4)                                                                           | 14.7B        |                    1 |   2025 | unsloth/Phi-4-unsloth-bnb-4bit              |
| [NikolayKozloff/LLMBG-Llama-3.1-8B-BG-Reasoning-v0.1-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/LLMBG-Llama-3.1-8B-BG-Reasoning-v0.1-Q8_0-GGUF) | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B                     |
| [burgasdotpro/bgGPT-GRPO-Llama-3.1-8B-Inst](https://huggingface.co/burgasdotpro/bgGPT-GRPO-Llama-3.1-8B-Inst)                                         | 8.0B         |                    1 |   2025 | unsloth/meta-llama-3.1-8b-instruct-bnb-4bit |
| [burgasdotpro/bgGPT-llama-3.1-8B](https://huggingface.co/burgasdotpro/bgGPT-llama-3.1-8B)                                                             | 8.0B         |                    1 |   2024 | unsloth/meta-llama-3.1-8b-bnb-4bit          |

_60 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Bulgarian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 6 datasets; Reading comprehension: 2 datasets; Knowledge &amp; QA: 6 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">6 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                               |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 131            | Treebank-based (automatic)                                 |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 2,458          | Treebank-based (automatic, UD + UniMorph)                  |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                    |
| 2. Pragmatics, discourse & coreference | Negation                       | Multilingual negation minimal pairs (Hartmann et al.)                                                             | —              | Derived from XNLI (human-translated) + manual editing      |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                              | —              | Machine translation (DeepL)                                |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                 |
| 3. Commonsense reasoning               | HellaSwag                      | [Recovered in Translation (INSAIT)](https://github.com/insait-institute/multilingual-benchmarks)                  | 10,042         | Machine translation (Gemini-2.0-Flash, automated pipeline) |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                     |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                    |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                 |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                                    | 2,937          | Native (high-school exams)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                   | —              | Native (local exams)                                       |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                  |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)             |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 10,000         | Native (crowdsourced Tatoeba sentence pairs)               |

### Standard machine translation test sets

| Test set                                                                  | Direction(s)                      | Size                   | Human reference   |
|:--------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)   | multi-way (all languages)         | 2,009 sentences (Cyrl) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)               | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |
| [WMT24++](https://huggingface.co/datasets/google/wmt24pp/viewer/en-bg_BG) | en → bg_BG                        | 998 segments           | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Bulgarian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Bulgarian? Does it make sense to train one?
  - ~27.10 GB English-equivalent text ≈ 6.78B tokens, enough for a compute-optimal model of ~338.8M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Bulgarian-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 144 of ~18,498 papers (0.78%) (rank 45 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bulgarian

Here are up to ten papers published in 2026 that mention Bulgarian. None of the 144 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                        | paper                                                                                | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------|:---------------|
| Authorship Attribution in Multilingual Machine-Generated Texts                                               | [2026.acl-long.2091](https://aclanthology.org/2026.acl-long.2091/)                   | body only      |
| A Large Dataset Representing Bulgarian, with the Bulgarian National Corpus as Its Core                       | [2026.cmlc-1.2](https://aclanthology.org/2026.cmlc-1.2/)                             | body only      |
| cantnlp@DravidianLangTech 2026: organic domain adaptation improves multi-class hope speech detection in Tulu | [2026.dravidianlangtech-1.21](https://aclanthology.org/2026.dravidianlangtech-1.21/) | body only      |
| Finding Culture-Sensitive Neurons in Vision-Language Models                                                  | [2026.eacl-long.155](https://aclanthology.org/2026.eacl-long.155/)                   | body only      |
| To Each Language Its Tokenizer: Modular Tokenizers for Efficient Multilingual LLMs                           | [2026.findings-emnlp.1019](https://aclanthology.org/2026.findings-emnlp.1019/)       | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                         | body only      |
| Linguistic and Demographic Factors in an Online Free Translation Task                                        | [2026.lrec-1.678](https://aclanthology.org/2026.lrec-1.678/)                         | body only      |
| From Form to Meaning: Interlingua Sense-Alignment of Offensive Language with LLMs                            | [2026.ltedi-1.6](https://aclanthology.org/2026.ltedi-1.6/)                           | body only      |
| GUIR at SemEval-2026 Task 7: Probing Cultural Knowledge in LLMs via Multi-Agent Debate                       | [2026.semeval-1.438](https://aclanthology.org/2026.semeval-1.438/)                   | body only      |
| SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                | [2026.semeval-1.455](https://aclanthology.org/2026.semeval-1.455/)                   | body only      |

{% endraw %}
