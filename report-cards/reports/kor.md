---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/kor.html
---
{% raw %}
# So you want to work on Korean?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `kor`

**Language family:** **Koreanic** ([Glottolog](https://glottolog.org/resource/languoid/id/kore1280))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Hang`

**Speakers:** about 79.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** North Korea, People's Republic of China, South Korea

**Status:** Official language; Regional official language


## What does Korean look and sound like?

**Written:** Omniglot has [a page on Korean](https://www.omniglot.com/writing/korean.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/kor/) has 7 videos of Korean speakers. Watch [See all](https://wikitongues.org/videos/?language=kor).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 770,480 articles in ko.wikipedia; 4,943 active users. This is ~1/10 of English data and ranks 20 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 17,959,416 pages per crawl on average, which is 0.8336% of the crawl (2026). This is ~1/50 of English data and ranks 15 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                              |
| FineWeb                | 105.82 GB (kor_Hang 105.82 GB), equivalent to ≈81.82 GB of English after byte-premium scaling; 166.19 GB removed by filtering. This is ~1/505 of English data and ranks 17 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 9.81 GB (kor_Hang 9.81 GB) (rank 11 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                  |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 5 treebanks, 53,622 sentences / 615,755 tokens in total: [UD_Korean-GSD](https://github.com/UniversalDependencies/UD_Korean-GSD) (6,339 sentences), [UD_Korean-KSL](https://github.com/UniversalDependencies/UD_Korean-KSL) (17,369 sentences), [UD_Korean-Kaist](https://github.com/UniversalDependencies/UD_Korean-Kaist) (27,363 sentences), [UD_Korean-LittlePrince](https://github.com/UniversalDependencies/UD_Korean-LittlePrince) (1,551 sentences), [UD_Korean-PUD](https://github.com/UniversalDependencies/UD_Korean-PUD) (1,000 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 2,686 lemmas, 241,323 inflected forms ([unimorph/kor](https://github.com/unimorph/kor))                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Wordnets               | nan (size not listed); [KorLex (Korean WordNet)](http://www.lt-world.org/kb/resources-and-tools/language-descriptions/ltw_x3alanguage_x5fdescriptions_.2010-10-28.2540969419) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                                                                                                                                                                                                                                                                                                                    |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                                                                      |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.998 (P 0.999, R 0.997, FPR 3.99e-06) averaged over 5 dataset(s). Runner-up: OpenLID-v2 (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.997 | 0.998 | 0.000 | ✓                |
| OpenLID-v2   |       0.995 |    0.997 | 0.996 | 0.000 | ✓                |
| cld2         |       0.996 |    0.995 | 0.996 | 0.000 | ✓                |
| cld3         |       0.974 |    0.983 | 0.978 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.945 | 0.969 | 0.000 | ✗                |
| commonlingua |       0.890 |    0.997 | 0.925 | 0.001 | ✓                |
| fasttext     |       0.784 |    0.996 | 0.869 | 0.002 | ✓                |
| funlangid    |       1.000 |    0.695 | 0.807 | 0.000 | ✓                |
| py3langid    |       0.503 |    0.997 | 0.636 | 0.014 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.997 |    0.987 | 0.992 |
| Tatoeba   | 300 |       1.000 |    0.997 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Korean to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Korean *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Korean and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Korean?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Korean (and whether the model is exclusively tagged for Korean or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,767** text-generation models are explicitly tagged for Korean (2,012 original uploads, 5,755 fine-tunes/quantisations/merges).
- **1,638** are tagged *only* for Korean.
- Including tags inherited from base models: **16,153**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       41 | █                    |
|   2023 |      499 | ███                  |
|   2024 |     1902 | ███████████          |
|   2025 |     2011 | ████████████         |
|   2026 |     3314 | ████████████████████ |

### Largest models tagged for Korean

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                     |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                 | 1.9T         |                  143 |   2025 | —                                 |
| [batiai/DeepSeek-V4-Pro-GGUF](https://huggingface.co/batiai/DeepSeek-V4-Pro-GGUF)                         | 1.6T         |                    3 |   2026 | deepseek-ai/DeepSeek-V4-Pro       |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF) | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [batiai/Kimi-K2.6-GGUF](https://huggingface.co/batiai/Kimi-K2.6-GGUF)                                     | 1.0T         |                    4 |   2026 | moonshotai/Kimi-K2.6              |
| [batiai/Kimi-K2.7-Code-GGUF](https://huggingface.co/batiai/Kimi-K2.7-Code-GGUF)                           | 1.0T         |                    3 |   2026 | moonshotai/Kimi-K2.7-Code         |

### Largest models tagged *only* for Korean

| model                                                                                                                     | parameters   |   # languages tagged |   year | derivative of                          |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [FINAL-Bench/POCKET-Qwen3.8-Flash-Next-GGUF](https://huggingface.co/FINAL-Bench/POCKET-Qwen3.8-Flash-Next-GGUF)           | 176.9B       |                    1 |   2026 | Qwen/Qwen3.8-Flash-Next                |
| [ada-flo/kor-road-finance-agent-oss-120b-lora](https://huggingface.co/ada-flo/kor-road-finance-agent-oss-120b-lora)       | 120.0B       |                    1 |   2025 | axolotl-ai-co/gpt-oss-120b-dequantized |
| [ktl-bmrc/MedReg-SLM-v0.1](https://huggingface.co/ktl-bmrc/MedReg-SLM-v0.1)                                               | 116.8B       |                    1 |   2025 | openai/gpt-oss-120b                    |
| [hell0ks/DeepSeek-V4.1-Flash-1017-EXL3-2.9bpw-ko](https://huggingface.co/hell0ks/DeepSeek-V4.1-Flash-1017-EXL3-2.9bpw-ko) | 105.3B       |                    1 |   2026 | deepseek-ai/DeepSeek-V4.1-Flash-1017   |
| [KISTI-KONI/KONI-Llama3.1-70B-Instruct-20241115](https://huggingface.co/KISTI-KONI/KONI-Llama3.1-70B-Instruct-20241115)   | 70.6B        |                    1 |   2024 | —                                      |

_576 tagged models have unknown parameter counts and are not ranked by size._

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

**36** benchmark datasets in the survey include Korean.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 7 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 11 datasets; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 7 datasets; Commonsense reasoning: 8 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 11 datasets; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">11 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">8 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">7 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                        | # test items   | construction                                                        |
|:---------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | KIM Bench                                                                                                      | 1,175          | Native                                                              |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | MIDAS                                                                                                          | —              | Native (dictionaries; LLM-refined meanings checked by natives)      |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Korean pragmatic competence test set](https://github.com/DojunPark/pragmatic_eval_korean)                     | 120            | Native (expert-written)                                             |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                    | 300            | Native                                                              |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers | [Multilingual indirect yes/no answers (Wang & Blanco)](https://github.com/wang-zijie/yn-question-multilingual) | 240            | Native                                                              |
| 2. Pragmatics, discourse & coreference | Negation                       | Thunder-KoNUBench                                                                                              | 1,284          | Native (Korean Wikipedia, author-written negations)                 |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | Ko-WinoGrande (Open Ko-LLM Leaderboard2)                                                                       | 1,267          | Human translation (professional) + review                           |
| 3. Commonsense reasoning               | COPA                           | [KB-COPA (KoBEST)](https://huggingface.co/datasets/skt/kobest_v1)                                              | 1,000          | Native                                                              |
| 3. Commonsense reasoning               | HellaSwag                      | [KB-HellaSwag (KoBEST)](https://huggingface.co/datasets/skt/kobest_v1)                                         | 1,404          | Native                                                              |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                           | Ko-PIQA                                                                                                        | 441            | Native (web-crawled, LLM-filtered, human-validated)                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)            | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                   | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | Physical commonsense           | [EPiK](https://huggingface.co/datasets/jjae/EPiK)                                                              | 181            | Native (LLM-generated, expert-certified)                            |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                  | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [KorQuAD 1.0](https://korquad.github.io/)                                                                      | 5,774          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                     | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | HAE-RAE Bench                                                                                                  | —              | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                          | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                                | —              | Native (local exams)                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [KMMLU](https://huggingface.co/datasets/HAERAE-HUB/KMMLU)                                                      | 35,030         | Native (Korean exams)                                               |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                  | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                                 | 14,042         | Human translation (professional)                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                     | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                        | 1,000          | Native (cultural; native-speaker answers)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                       | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                | 250            | Native (locally sourced)                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [XOR-TyDi QA](https://github.com/AkariAsai/XORQA)                                                              | 1,154          | Native (TyDi questions)                                             |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                    | 854            | Human translation via English pivot                                 |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                        | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                      | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    |                                | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                                  | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                                 | —              | Human translation (professional, from English)                      |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                           | 2,479          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                      | 998            | Human translation (professional) + post-edits                       |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Korean datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Korean? Does it make sense to train one?
  - ~81.82 GB English-equivalent text ≈ 20.46B tokens, enough for a compute-optimal model of ~1.0B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Korean-only model is 176.9B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 855 of ~18,498 papers (4.62%) (rank 9 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Korean

Here are up to ten papers published in 2026 that mention Korean. None of the 855 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                 | paper                                                                    | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|:---------------|
| Index-Time Prefix Injection for Multi-Tenant Retrieval: Improving Search Relevance Without Model Fine-Tuning          | [2026.acl-industry.149](https://aclanthology.org/2026.acl-industry.149/) | body only      |
| Sequence Labeling for Constituent Parsing: A Comparative Study and Encoding Innovations                               | [2026.cl-2.3](https://aclanthology.org/2026.cl-2.3/)                     | body only      |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)   | body only      |
| Visual Framing for News Stance Detection via Image Generation                                                         | [2026.emnlp-main.2524](https://aclanthology.org/2026.emnlp-main.2524/)   | body only      |
| Talent or Luck? Evaluating Attribution Bias in Large Language Models                                                  | [2026.findings-acl.534](https://aclanthology.org/2026.findings-acl.534/) | body only      |
| Tracing Mathematical Proficiency Through Problem-Solving Processes                                                    | [2026.findings-acl.961](https://aclanthology.org/2026.findings-acl.961/) | body only      |
| StarDrinks: An English and Korean Test Set for SLU Evaluation in a Drink Ordering Scenario                            | [2026.lrec-1.453](https://aclanthology.org/2026.lrec-1.453/)             | body only      |
| Can NLP Tackle Hate Speech in the Real World? Stakeholder-Informed Feedback and Survey on Counterspeech               | [2026.lrec-1.655](https://aclanthology.org/2026.lrec-1.655/)             | body only      |
| Correction Is Not Response: Reframing the Unverifiable Majority of Health Infodemic Discourse as Communicative Acts   | [2026.nlp4pi-1.13](https://aclanthology.org/2026.nlp4pi-1.13/)           | body only      |
| Multi-Test Nation Bias Benchmarking of LLMs with Explicit Unbiased Baselines                                          | [2026.tacl-1.109](https://aclanthology.org/2026.tacl-1.109/)             | body only      |

{% endraw %}
