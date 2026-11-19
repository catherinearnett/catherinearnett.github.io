---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tha.html
---
{% raw %}
# So you want to work on Thai?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tha`

**Language family:** **Tai-Kadai** › Kam-Tai › Daic-Beic › … › Lao-Thai ([Glottolog](https://glottolog.org/resource/languoid/id/thai1261))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Thai`

**Speakers:** about 55.9 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Thailand

**Status:** Official language


## What does Thai look and sound like?

**Written (Thai)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/thai.htm):

> A recording of this text by Jo S.

*Transliteration:* Rao túk kon gèrt maa yàang ìt-sà-rà, rao túk kon mee kwaam kît láe kwaam kâo jai bpen kŏng rao ayng. Rao túk kon kuan dâi ráp gaan bpà-dtì-bàt nai taang dieow gan.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) [top]

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_th.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors: Transliteration by http://www.thai2english.com/online/.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tha/) has 4 videos of Thai speakers. Watch [Tao speaking Thai](https://wikitongues.org/videos/tao_20180327_tha/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 189,539 articles in th.wikipedia; 2,471 active users. This is ~1/40 of English data and ranks 47 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 8,082,765 pages per crawl on average, which is 0.3748% of the crawl (2026). This is ~1/110 of English data and ranks 23 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 75.11 GB (tha_Thai 75.11 GB), equivalent to ≈27.40 GB of English after byte-premium scaling; 104.56 GB removed by filtering. This is ~1/711 of English data and ranks 23 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 13.14 GB (tha_Thai 13.14 GB) (rank 3 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 4,866 sentences / 105,351 tokens in total: [UD_Thai-PUD](https://github.com/UniversalDependencies/UD_Thai-PUD) (1,000 sentences), [UD_Thai-TDT](https://github.com/UniversalDependencies/UD_Thai-TDT) (239 sentences), [UD_Thai-TUD](https://github.com/UniversalDependencies/UD_Thai-TUD) (3,627 sentences). All have POS tags, dependency syntax, morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                                                                           |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                           |
| Wordnets               | [Thai Wordnet](https://github.com/omwn/omw-data/releases/download/v1.4/omw-th-1.4.tar.xz): 73,350 synsets, 83,481 words, 95,517 senses; licence: wordnet; [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD.                                                                                                                                            |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                             |
|:-----------------------------------|:--------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                 |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([thaKJV](https://ebible.org/details.php?id=thaKJV), by-nc-nd 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                              |
| FLORES+, BOUQuET, SMOL             | _Not computed yet: run `python -m lrc build mt-sets`._                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=114), Wikipedia (n=300)
- **Best model:** py3langid — F1 0.997 (P 0.999, R 0.995, FPR 1.02e-05) averaged over 6 dataset(s). Runner-up: cld2 (F1 0.996).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| py3langid    |       0.999 |    0.995 | 0.997 | 0.000 | ✓                |
| cld2         |       0.999 |    0.993 | 0.996 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| OpenLID-v2   |       1.000 |    0.991 | 0.995 | 0.000 | ✓                |
| commonlingua |       0.996 |    0.993 | 0.994 | 0.000 | ✓                |
| fasttext     |       0.997 |    0.989 | 0.993 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.971 | 0.985 | 0.000 | ✗                |
| cld3         |       0.996 |    0.951 | 0.971 | 0.000 | ✓                |
| funlangid    |       1.000 |    0.886 | 0.933 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (py3langid) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.997 |    0.980 | 0.988 |
| Wikipedia | 300 |       1.000 |    0.990 | 0.995 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| Tatoeba   | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  | 114 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Thai to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Thai *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Thai and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Thai has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Thai?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Thai (and whether the model is exclusively tagged for Thai or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **4,304** text-generation models are explicitly tagged for Thai (1,003 original uploads, 3,301 fine-tunes/quantisations/merges).
- **168** are tagged *only* for Thai.
- Including tags inherited from base models: **26,019**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       15 | █                    |
|   2023 |       73 | █                    |
|   2024 |     1524 | ████████████████████ |
|   2025 |     1450 | ███████████████████  |
|   2026 |     1242 | ████████████████     |

### Largest models tagged for Thai

| model                                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                   |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                             | 1.9T         |                  143 |   2025 | —                               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                 | 856.0B       |                  143 |   2025 | —                               |
| [AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF](https://huggingface.co/AMAImedia/Ling-3.1-Flash-1019-FP8-GGUF)                               | 572.1B       |                   30 |   2026 | inclusionAI/Ling-3.1-flash-1019 |
| [hugging-quants/Meta-Llama-3.1-405B-Instruct-BNB-NF4](https://huggingface.co/hugging-quants/Meta-Llama-3.1-405B-Instruct-BNB-NF4)     | 422.8B       |                    8 |   2024 | meta-llama/Llama-3.1-405B       |
| [hugging-quants/Meta-Llama-3.1-405B-Instruct-GPTQ-INT4](https://huggingface.co/hugging-quants/Meta-Llama-3.1-405B-Instruct-GPTQ-INT4) | 410.1B       |                    8 |   2024 | —                               |

### Largest models tagged *only* for Thai

| model                                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                            |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [ThaiLLM/ThaiLLM-30B-IQ](https://huggingface.co/ThaiLLM/ThaiLLM-30B-IQ)                                                               | 30.5B        |                    1 |   2026 | —                                        |
| [ThaiLLM/ThaiLLM-8B-SFT-IQ](https://huggingface.co/ThaiLLM/ThaiLLM-8B-SFT-IQ)                                                         | 8.2B         |                    1 |   2026 | —                                        |
| [Jnx03/kanitakorn-qwen3-8b-sft-v1](https://huggingface.co/Jnx03/kanitakorn-qwen3-8b-sft-v1)                                           | 8.0B         |                    1 |   2026 | Qwen/Qwen3-8B-Base                       |
| [aminomewza/Llama-3.1-Typhoon2-8B-LoRA-NorthernThai-v2](https://huggingface.co/aminomewza/Llama-3.1-Typhoon2-8B-LoRA-NorthernThai-v2) | 8.0B         |                    1 |   2026 | typhoon-ai/llama3.1-typhoon2-8b-instruct |
| [wannaphong/llama-3-8b-han-16bit](https://huggingface.co/wannaphong/llama-3-8b-han-16bit)                                             | 8.0B         |                    1 |   2024 | meta-llama/Meta-Llama-3-8B               |

_137 tagged models have unknown parameter counts and are not ranked by size._

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

**23** benchmark datasets in the survey include Thai.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 5 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 7 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: 1 dataset; Commonsense reasoning: 5 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: 7 datasets; Machine translation: 7 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">1 dataset</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">7 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                             | # test items   | construction                                                        |
|:---------------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 2. Pragmatics, discourse & coreference | WSC                            | [Thai Winograd Schemas](https://huggingface.co/datasets/pakphum/winograd_th)                        | 285            | Human translation (professional) + native review                    |
| 3. Commonsense reasoning               | COPA                           | [XCOPA](https://huggingface.co/datasets/cambridgeltl/xcopa)                                         | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                               | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)        | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                              | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 4. Reading comprehension               | QA – extractive RC             | [iapp_wiki_qa_squad](https://huggingface.co/datasets/iapp/iapp_wiki_qa_squad)                       | —              | Native                                                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                     | 2,595          | Native (national exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                       | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                          | —              | Native (local exams/publications)                                   |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ThaiExam](https://huggingface.co/datasets/scb10x/thai_exam)                                        | —              | Native (ONET, TGAT, TPAT, IC, A-Level)                              |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                            | 10,000         | Human translation                                                   |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                     | 250            | Native (locally sourced)                                            |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                                 |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                           | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    |                                | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    |                                | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                      | —              | Human translation (professional, from English)                      |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 1,178          | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                           | 998            | Human translation (professional) + post-edits                       |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Thai datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Thai? Does it make sense to train one?
  - ~27.40 GB English-equivalent text ≈ 6.85B tokens, enough for a compute-optimal model of ~342.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Thai-only model is 30.5B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 413 of ~18,498 papers (2.23%) (rank 18 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Thai

Here are up to ten papers published in 2026 that mention Thai. None of the 413 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                       | paper                                                                        | mentioned in   |
|:------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|:---------------|
| FahMai-TeleBench: A Thai Grounded Tool-Use Benchmark for the Deployable Model Tier                          | [2026.aacl-short.15](https://aclanthology.org/2026.aacl-short.15/)           | body only      |
| Knowledge Beyond Language: Bridging the Gap in Multilingual Machine Unlearning Evaluation                   | [2026.acl-long.1105](https://aclanthology.org/2026.acl-long.1105/)           | body only      |
| Mirrored Frames: LLM-Based Narrative Framing Analysis of Thai-Cambodian Border Conflict Coverage            | [2026.findings-aacl.45](https://aclanthology.org/2026.findings-aacl.45/)     | body only      |
| SEA-SafeguardBench: Culturally Grounded Safety Benchmark for Southeast Asian Languages                      | [2026.findings-acl.194](https://aclanthology.org/2026.findings-acl.194/)     | body only      |
| SEATauBench: Progressively Adapting Tool-Agent-User Evaluation Into Low-Resource Southeast Asian Languages  | [2026.findings-emnlp.502](https://aclanthology.org/2026.findings-emnlp.502/) | body only      |
| Off the Hamster Wheel: Rethinking Dialogue Research through a Meta-Analysis of the ACL Anthology 2024       | [2026.lrec-1.207](https://aclanthology.org/2026.lrec-1.207/)                 | body only      |
| Where Are Language-Specific Features Represented in Multilingual LLMs? Everywhere                           | [2026.mrl-1.27](https://aclanthology.org/2026.mrl-1.27/)                     | body only      |
| An Empirical Study of Evidence Retrieval for Retrieval Augmented Generation over the Thai Royal Gazette     | [2026.nllp-1.19](https://aclanthology.org/2026.nllp-1.19/)                   | body only      |
| R1-T1: Fully Incentivizing Translation Capability in LLMs via Reasoning Learning                            | [2026.tacl-1.95](https://aclanthology.org/2026.tacl-1.95/)                   | body only      |
| Laniqo at WMT26 Video Subtitle Translation Shared Task: Multi-Objective Fusion of Pareto-Optimal Candidates | [2026.wmt-main.204](https://aclanthology.org/2026.wmt-main.204/)             | body only      |

{% endraw %}
