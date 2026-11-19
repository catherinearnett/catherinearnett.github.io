---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dzo.html
---
{% raw %}
# So you want to work on Dzongkha?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dzo`

**Language family:** **Sino-Tibetan** › Bodic › Bodish › … › Nuclear Dzongkhic ([Glottolog](https://glottolog.org/resource/languoid/id/dzon1239))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Tibt`

**Speakers:** about 419,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Bhutan

**Status:** Official language


## What does Dzongkha look and sound like?

**Written:** no Omniglot page found for Dzongkha.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/dzo/) has 1 video of Dzongkha speakers. Watch [Kinley speaking Dzongkha](https://wikitongues.org/videos/kinley_20160816_dzo/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 387 articles in dz.wikipedia; 13 active users. This is ~1/19,500 of English data and ranks 162 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                         |
| Common Crawl           | 2,261 pages per crawl on average, which is 0.0001% of the crawl (2026). This is ~1/394,298 of English data and ranks 105 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                            |
| FineWeb                | 30.9 MB (dzo_Tibt 30.0 MB), equivalent to ≈9.5 MB of English after byte-premium scaling; 37.2 MB removed by filtering. This is ~1/1,726,890 of English data and ranks 124 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 56.9 MB (dzo_Tibt 57.0 MB) (rank 132 of the 166 languages in the set that have any; 166 have none)                                                                                                                                                |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                    |
|:-----------------------|:-------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                 |
| UniMorph               | **None found**                                                                 |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._ |
| Wordnets               | **None found**                                                                 |

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

- **8 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), NTREX (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.936 (P 0.933, R 0.941, FPR 4.00e-04) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.863).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.933 |    0.941 | 0.936 | 0.000 | ✓                |
| OpenLID-v2   |       0.791 |    0.951 | 0.863 | 0.002 | ✓                |
| fasttext     |       1.000 |    0.783 | 0.856 | 0.000 | ✓                |
| commonlingua |       0.888 |    0.831 | 0.850 | 0.001 | ✓                |
| pyfranc      |       0.835 |    0.806 | 0.818 | 0.001 | ✓                |
| py3langid    |       0.497 |    0.986 | 0.661 | 0.009 | ✓                |
| funlangid    |       0.731 |    0.389 | 0.501 | 0.001 | ✓                |
| cld2         |       0.219 |    0.006 | 0.011 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.844 |    0.777 | 0.809 |
| NTREX     | 300 |       0.952 |    0.987 | 0.969 |
| UDHR-LID  |  59 |       0.952 |    1.000 | 0.975 |
| FLORES    | 300 |       0.984 |    1.000 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dzongkha to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Dzongkha *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dzongkha and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Dzongkha has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Dzongkha?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dzongkha (and whether the model is exclusively tagged for Dzongkha or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **875** text-generation models are explicitly tagged for Dzongkha (271 original uploads, 604 fine-tunes/quantisations/merges).
- **191** are tagged *only* for Dzongkha.
- Including tags inherited from base models: **911**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       10 | █                    |
|   2023 |      116 | ██████               |
|   2024 |      145 | ███████              |
|   2025 |      216 | ███████████          |
|   2026 |      388 | ████████████████████ |

### Largest models tagged for Dzongkha

| model                                                                                                                                               | parameters   |   # languages tagged |   year | derivative of                                          |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                                                           | 1.9T         |                  143 |   2025 | —                                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                                               | 856.0B       |                  143 |   2025 | —                                                      |
| [morningstarxcdcode/adaption-medical-reasoning-sft-120b-model](https://huggingface.co/morningstarxcdcode/adaption-medical-reasoning-sft-120b-model) | 120.0B       |                    2 |   2026 | togethercomputer/Meta-Llama-3.3-70B-Instruct-Reference |
| [narendarcodes/adaption-gpt-oss-120b-telugu-instruct](https://huggingface.co/narendarcodes/adaption-gpt-oss-120b-telugu-instruct)                   | 120.0B       |                    2 |   2026 | togethercomputer/gpt-oss-120b-bf16                     |
| [narendarcodes/adaption-contract-clause-analyzer-109b](https://huggingface.co/narendarcodes/adaption-contract-clause-analyzer-109b)                 | 109.0B       |                    2 |   2026 | meta-llama/Llama-4-Scout-17B-16E-Instruct              |

### Largest models tagged *only* for Dzongkha

| model                                                                                                                             | parameters   |   # languages tagged |   year | derivative of                               |
|:----------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------------|
| [jay2219/Q-Route-70B](https://huggingface.co/jay2219/Q-Route-70B)                                                                 | 70.0B        |                    1 |   2026 | meta-llama/Llama-3.3-70B-Instruct-Reference |
| [MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Alpaca](https://huggingface.co/MaziyarPanahi/Nous-Hermes-2-Mixtral-8x7B-SFT-Alpaca) | 56.0B        |                    1 |   2024 | mistralai/Mixtral-8x7B-v0.1                 |
| [forkjoin-ai/buleyean-qwen2.5-32b-anxious](https://huggingface.co/forkjoin-ai/buleyean-qwen2.5-32b-anxious)                       | 32.0B        |                    1 |   2026 | Qwen/Qwen2.5-32B                            |
| [hassanshka/Biomni-R0-32B-LoRA-Dequantized-Rank256](https://huggingface.co/hassanshka/Biomni-R0-32B-LoRA-Dequantized-Rank256)     | 32.0B        |                    1 |   2026 | Qwen/Qwen3-32B                              |
| [Taimwe/securecoder-30b-pro](https://huggingface.co/Taimwe/securecoder-30b-pro)                                                   | 30.0B        |                    1 |   2026 | Qwen/Qwen3-Coder-30B-A3B-Instruct           |

_397 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Dzongkha.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                    | # test items   | construction                                                     |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) | 2,679          | Synthetic (LLM-generated) on native Wikipedia                    |
| Machine translation      |                    | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                | 854            | Human translation via English pivot                              |
| Machine translation      |                    | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)    | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation      |                    | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)              | —              | Human translation (professional, from English)                   |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                  | 1,997          | Human translation (professional, from English)                   |

### Standard machine translation test sets

_Not computed yet: run `python -m lrc build mt-sets`._

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dzongkha datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dzongkha? Does it make sense to train one?
  - ~17.4 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~218.1K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Dzongkha-only model is 70.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 13 of ~18,498 papers (0.07%) (rank 140 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Dzongkha

Here are up to ten papers published in 2026 that mention Dzongkha. None of the 13 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                          | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| IndicJR: A Judge-Free Benchmark of Jailbreak Robustness in South Asian Languages                                                              | [2026.eacl-industry.50](https://aclanthology.org/2026.eacl-industry.50/)       | body only      |
| Seeing the Unseen: Visual Similarity for Pixel Language Model Adaptation                                                                      | [2026.emnlp-main.1509](https://aclanthology.org/2026.emnlp-main.1509/)         | body only      |
| FineWeb-CLaR: Culture, Language, and Region Annotations for Benchmark-Aligned Corpus Auditing                                                 | [2026.emnlp-main.2216](https://aclanthology.org/2026.emnlp-main.2216/)         | body only      |
| Towards the Roof of the World: NLP Progress in Tibetan Languages                                                                              | [2026.findings-aacl.56](https://aclanthology.org/2026.findings-aacl.56/)       | body only      |
| IndicSafe: A Benchmark for Evaluating Multilingual LLM Safety in South Asia                                                                   | [2026.findings-emnlp.2135](https://aclanthology.org/2026.findings-emnlp.2135/) | body only      |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)                   | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   | body only      |
| NepTam: A Nepali-Tamang Parallel Corpus and Baseline Machine Translation Experiments                                                          | [2026.lrec-1.696](https://aclanthology.org/2026.lrec-1.696/)                   | body only      |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                      | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)                   | body only      |

{% endraw %}
