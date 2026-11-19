---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/cat.html
---
{% raw %}
# So you want to work on Catalan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `cat` (also listed as: Valencian)

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Southwestern Shifted Romance ([Glottolog](https://glottolog.org/resource/languoid/id/stan1289))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (60% certain))

**Writing systems:** `Latn`

**Speakers:** about 8.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Andorra, Spain

**Status:** Official language; Regional official language


## What does Catalan look and sound like?

**Written**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/catalan.htm):

> Tots els éssers humans neixen lliures i iguals en dignitat i en drets. Són dotats de raó i de consciència, i han de comportar-se fraternalment els uns amb els altres.
> A recording of this text by Sergi Giménez Palomo from Barcelona

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_catalan.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/cat/) has 7 videos of Catalan speakers. Watch [See all](https://wikitongues.org/videos/?language=cat).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 807,554 articles in ca.wikipedia; 2,163 active users. This is ~1/9 of English data and ranks 18 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                        |
| Common Crawl           | 4,430,838 pages per crawl on average, which is 0.2056% of the crawl (2026). This is ~1/201 of English data and ranks 31 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                             |
| FineWeb                | 19.93 GB (cat_Latn 19.93 GB), equivalent to ≈18.24 GB of English after byte-premium scaling; 20.36 GB removed by filtering. This is ~1/2,680 of English data and ranks 34 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 4.21 GB (cat_Latn 4.21 GB) (rank 46 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                 |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 16,678 sentences / 531,390 tokens in total: [UD_Catalan-AnCora](https://github.com/UniversalDependencies/UD_Catalan-AnCora) (16,678 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,547 lemmas, 81,576 inflected forms ([unimorph/cat](https://github.com/unimorph/cat))                                                                                                                                             |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                     |
| Wordnets               | [Multilingual Central Repository (Catalan)](https://github.com/omwn/omw-data/releases/download/v1.4/omw-ca-1.4.tar.xz): 45,826 synsets, 47,598 words, 70,622 senses; licence: https://creativecommons.org/licenses/by/3.0/.        |

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

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=93), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.969 (P 0.948, R 0.991, FPR 3.05e-04) averaged over 6 dataset(s). Runner-up: OpenLID-v2 (F1 0.960).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.948 |    0.991 | 0.969 | 0.000 | ✓                |
| OpenLID-v2   |       0.948 |    0.972 | 0.960 | 0.000 | ✓                |
| py3langid    |       0.906 |    0.971 | 0.936 | 0.001 | ✓                |
| cld2         |       0.951 |    0.885 | 0.914 | 0.000 | ✓                |
| commonlingua |       0.822 |    0.878 | 0.845 | 0.001 | ✓                |
| fasttext     |       0.758 |    0.989 | 0.842 | 0.003 | ✓                |
| pyfranc      |       0.872 |    0.775 | 0.816 | 0.001 | ✓                |
| funlangid    |       0.804 |    0.786 | 0.783 | 0.001 | ✓                |
| cld3         |       0.485 |    0.948 | 0.606 | 0.015 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.929 |    0.967 | 0.948 |
| CommonLID |  93 |       0.911 |    0.989 | 0.948 |
| UDHR-LID  |  58 |       0.906 |    1.000 | 0.951 |
| Wikipedia | 300 |       0.955 |    0.990 | 0.972 |
| FLORES    | 300 |       0.987 |    1.000 | 0.993 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Catalan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Catalan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Catalan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Catalan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Catalan (and whether the model is exclusively tagged for Catalan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **547** text-generation models are explicitly tagged for Catalan (197 original uploads, 350 fine-tunes/quantisations/merges).
- **37** are tagged *only* for Catalan.
- Including tags inherited from base models: **945**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       42 | ████                 |
|   2023 |       46 | █████                |
|   2024 |      134 | ██████████████       |
|   2025 |      135 | ██████████████       |
|   2026 |      190 | ████████████████████ |

### Largest models tagged for Catalan

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF) | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                                 | 176.2B       |                   37 |   2026 | —                                      |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                                 | 176.2B       |                   37 |   2026 | —                                      |

### Largest models tagged *only* for Catalan

| model                                                                       | parameters   |   # languages tagged |   year | derivative of                           |
|:----------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------------------------------|
| [HiTZ/cat_Qwen3-14B-Base](https://huggingface.co/HiTZ/cat_Qwen3-14B-Base)   | 14.8B        |                    1 |   2025 | Qwen/Qwen3-14B-Base                     |
| [ericrisco/gemma-maia-12b](https://huggingface.co/ericrisco/gemma-maia-12b) | 11.9B        |                    1 |   2026 | unsloth/gemma-4-12b-it                  |
| [HiTZ/cat_Qwen3-8B-Base](https://huggingface.co/HiTZ/cat_Qwen3-8B-Base)     | 8.2B         |                    1 |   2025 | Qwen/Qwen3-8B-Base                      |
| [HiTZ/cat_Llama-3.1-8B](https://huggingface.co/HiTZ/cat_Llama-3.1-8B)       | 8.0B         |                    1 |   2025 | meta-llama/Llama-3.1-8B                 |
| [ericrisco/gemma-maia-e4b](https://huggingface.co/ericrisco/gemma-maia-e4b) | 7.5B         |                    1 |   2026 | unsloth/gemma-4-E4B-it-unsloth-bnb-4bit |

_64 tagged models have unknown parameter counts and are not ranked by size._

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

**28** benchmark datasets in the survey include Catalan.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: 2 datasets; Commonsense reasoning: 10 datasets; Reading comprehension: 4 datasets; Knowledge &amp; QA: 5 datasets; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="86.0" text-anchor="middle" fill="#ffffff" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">10 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="430.2" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">2 datasets</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                                  | task                           | dataset                                                                                                           | # test items   | construction                                                     |
|:---------------------------------------|:-------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 220            | Treebank-based (automatic)                                       |
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 2,284          | Treebank-based (automatic, UD + UniMorph)                        |
| 2. Pragmatics, discourse & coreference | Coherence & discourse          | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                          |
| 2. Pragmatics, discourse & coreference | WNLI                           | [WNLI-ca](https://huggingface.co/datasets/projecte-aina/wnli-ca)                                                  | 146            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | COPA                           | [COPA-ca](https://huggingface.co/datasets/projecte-aina/COPA-ca)                                                  | 500            | Human translation (professional)                                 |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                          | 9,211          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [PIQA_ca](https://huggingface.co/datasets/projecte-aina/piqa_ca)                                                  | 1,838          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Physical commonsense           | [PIQA-ca](https://huggingface.co/datasets/projecte-aina/piqa_ca)                                                  | 1,838          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | Social commonsense             | [SIQA-ca](https://huggingface.co/datasets/projecte-aina/siqa_ca)                                                  | 1,954          | Human translation (professional)                                 |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | StoryCloze                     | [XStoryCloze_ca](https://huggingface.co/datasets/projecte-aina/xstorycloze_ca)                                    | 1,511          | Human translation                                                |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | [CatalanQA](https://huggingface.co/datasets/projecte-aina/catalanqa)                                              | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [CoQCat](https://huggingface.co/datasets/projecte-aina/CoQCat)                                                    | —              | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [ARC_ca](https://huggingface.co/datasets/projecte-aina/arc_ca)                                                    | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [OpenBookQA_ca](https://huggingface.co/datasets/projecte-aina/openbookqa_ca)                                      | —              | Translation                                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | VeritasQA                                                                                                         | —              | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                        |
| Machine translation                    |                                | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                       | 854            | Human translation via English pivot                              |
| Machine translation                    |                                | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (2 varieties/pairs)                       | 2,024          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    |                                | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                         | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    |                                | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                              | 1,631          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    |                                | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                         | 998            | Human translation (professional) + post-edits                    |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WSC, WinoGrande
- **3. Commonsense reasoning:** Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Catalan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Catalan? Does it make sense to train one?
  - ~18.24 GB English-equivalent text ≈ 4.56B tokens, enough for a compute-optimal model of ~228.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Catalan-only model is 14.8B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 170 of ~18,498 papers (0.92%) (rank 37 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Catalan (Valencian) | Valencian | Catalan

Here are up to ten papers published in 2026 that mention Catalan. None of the 170 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                       | paper                                                                      | mentioned in   |
|:--------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| Post Hoc Agentic Refinement for Improving Precision in Multilingual Clinical Text De-identification                                         | [2026.bionlp-1.11](https://aclanthology.org/2026.bionlp-1.11/)             | body only      |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                                                         | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/) | body only      |
| QFrBLiMP: a Quebec-French Benchmark of Linguistic Minimal Pairs                                                                             | [2026.findings-eacl.224](https://aclanthology.org/2026.findings-eacl.224/) | body only      |
| How Much Noise Can BERT Handle? Insights from Multilingual Sentence Difficulty Detection                                                    | [2026.lrec-1.485](https://aclanthology.org/2026.lrec-1.485/)               | body only      |
| Beyond Fake News Detection: A Community-based Study of the Multicultural Nature of Information Disorder                                     | [2026.lrec-1.515](https://aclanthology.org/2026.lrec-1.515/)               | body only      |
| Merge and Conquer: Instructing Multilingual Models by Adding Target Language Weights                                                        | [2026.lrec-1.800](https://aclanthology.org/2026.lrec-1.800/)               | body only      |
| Exploring Cross-Lingual Transfer in Transformer-Based Fraud Detection Models                                                                | [2026.nlpaics-1.1](https://aclanthology.org/2026.nlpaics-1.1/)             | body only      |
| Supercharging Agenda Setting Research: The ParlaCAP Dataset of 28 European Parliaments and a Scalable Multilingual LLM-Based Classification | [2026.politicalnlp-1.11](https://aclanthology.org/2026.politicalnlp-1.11/) | body only      |
| The Construction of the CORALSE Corpus, Now and Beyond: A Tool for Documenting Spanish Sign Language                                        | [2026.signlang-1.15](https://aclanthology.org/2026.signlang-1.15/)         | body only      |
| Zero-Shot Cross-Lingual Recognition of Sign Language Handshapes                                                                             | [2026.wslp-1.18](https://aclanthology.org/2026.wslp-1.18/)                 | body only      |

{% endraw %}
