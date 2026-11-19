---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/gle.html
---
{% raw %}
# So you want to work on Irish?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `gle`

**Language family:** **Indo-European** › Classical Indo-European › Celtic › … › Modern Goidelic ([Glottolog](https://glottolog.org/resource/languoid/id/iris1253))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: Glottolog)

**Writing systems:** `Latn`

**Speakers:** about 1.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Ireland, United Kingdom

**Status:** Regional official language; Official language


## What does Irish look and sound like?

**Written (Irish)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/irish.htm):

> Saolaítear na daoine uile saor agus comhionann ina ndínit
> agus ina gcearta. Tá bua an réasúin agus an choinsiasa
> acu agus dlíd iad féin d'iompar de mheon bráithreachais
> i leith a chéile.
> A recording of this text by Seán Ó Súilleabháin (from county Kerry)

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_irish.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/gle/) has 7 videos of Irish speakers. Watch [See all](https://wikitongues.org/videos/?language=gle).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 64,578 articles in ga.wikipedia; 106 active users. This is ~1/117 of English data and ranks 65 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 147,705 pages per crawl on average, which is 0.0069% of the crawl (2026). This is ~1/6,036 of English data and ranks 60 of the 113 languages in the set with any data in Common Crawl; 219 have none.                                          |
| FineWeb                | 0.99 GB (gle_Latn 0.99 GB), equivalent to ≈0.50 GB of English after byte-premium scaling; 1.10 GB removed by filtering. This is ~1/53,884 of English data and ranks 72 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 2.11 GB (gle_Latn 2.11 GB) (rank 59 of the 166 languages in the set that have any; 166 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 3 treebanks, 7,699 sentences / 168,489 tokens in total: [UD_Irish-Cadhan](https://github.com/UniversalDependencies/UD_Irish-Cadhan) (193 sentences), [UD_Irish-IDT](https://github.com/UniversalDependencies/UD_Irish-IDT) (4,910 sentences), [UD_Irish-TwittIrish](https://github.com/UniversalDependencies/UD_Irish-TwittIrish) (2,596 sentences). All have POS tags, dependency syntax, lemmas. |
| UniMorph               | 7,464 lemmas, 107,298 inflected forms ([unimorph/gle](https://github.com/unimorph/gle))                                                                                                                                                                                                                                                                                                            |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                                                                                                                                                                                                     |
| Wordnets               | [Líonra Séimeantach na Gaeilge (LSG) Irish Language Semantic Network](http://borel.slu.edu/lsg/index-en.html) (size not listed); licence: GNU GPL v3.                                                                                                                                                                                                                                              |

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
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.995 (P 0.995, R 0.994, FPR 3.57e-05) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.984).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.995 |    0.994 | 0.995 | 0.000 | ✓                |
| py3langid    |       0.974 |    0.994 | 0.984 | 0.000 | ✓                |
| cld2         |       0.977 |    0.974 | 0.975 | 0.000 | ✓                |
| OpenLID-v2   |       0.934 |    0.996 | 0.962 | 0.001 | ✓                |
| fasttext     |       0.916 |    0.993 | 0.951 | 0.001 | ✓                |
| commonlingua |       0.968 |    0.911 | 0.934 | 0.000 | ✓                |
| funlangid    |       0.923 |    0.902 | 0.912 | 0.001 | ✓                |
| pyfranc      |       0.935 |    0.843 | 0.885 | 0.001 | ✓                |
| cld3         |       0.772 |    0.981 | 0.852 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.983 |    0.980 | 0.982 |
| Wikipedia | 300 |       0.993 |    0.990 | 0.992 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  56 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Irish to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Irish *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Irish and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Irish?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Irish (and whether the model is exclusively tagged for Irish or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **348** text-generation models are explicitly tagged for Irish (121 original uploads, 227 fine-tunes/quantisations/merges).
- **22** are tagged *only* for Irish.
- Including tags inherited from base models: **712**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |        7 | █                    |
|   2023 |        8 | █                    |
|   2024 |       72 | █████████            |
|   2025 |      101 | █████████████        |
|   2026 |      160 | ████████████████████ |

### Largest models tagged for Irish

| model                                                                                                                 | parameters   |   # languages tagged |   year | derivative of                          |
|:----------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                             | 1.9T         |                  143 |   2025 | —                                      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                                 | 856.0B       |                  143 |   2025 | —                                      |
| [bartowski/command-a-plus-05-2026-GGUF](https://huggingface.co/bartowski/command-a-plus-05-2026-GGUF)                 | 218.3B       |                   48 |   2026 | CohereLabs/command-a-plus-05-2026-bf16 |
| [csala/ALIA-40b-Q3_K-GGUF](https://huggingface.co/csala/ALIA-40b-Q3_K-GGUF)                                           | 40.4B        |                   33 |   2025 | BSC-LT/ALIA-40b                        |
| [FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF](https://huggingface.co/FreedomAISVR/Qwen3.6-35B-A3B-NVFP4-NoMTP-GGUF) | 34.7B        |                   82 |   2026 | Qwen/Qwen3.6-35B-A3B                   |

### Largest models tagged *only* for Irish

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                 |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-gle-32768)           | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-gle-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-gle-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF](https://huggingface.co/NikolayKozloff/kakugo-3B-gle-Q8_0-GGUF) | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-gle-32768)           | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [alphaedge-ai/Qwen3-1.7B-gle-32768](https://huggingface.co/alphaedge-ai/Qwen3-1.7B-gle-32768)           | 1.5B         |                    1 |   2026 | Qwen3-1.7B                    |

_49 tagged models have unknown parameter counts and are not ranked by size._

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

**9** benchmark datasets in the survey include Irish.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: 2 datasets; Pragmatics &amp; discourse: none; Commonsense reasoning: 2 datasets; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="169.8" y="248.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">2 datasets</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                   |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:-----------------------------------------------|
| 1. Linguistic knowledge  | BLiMP              | Irish-BLiMP                                                                          |          1,020 | Hand-written (expert)                          |
| 1. Linguistic knowledge  | BLiMP              | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                 |             28 | Treebank-based (automatic, UD + UniMorph)      |
| 3. Commonsense reasoning | HellaSwag          | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                |          9,088 | Machine translation (GPT-4o, auto-checked)     |
| 3. Commonsense reasoning | StoryCloze         | [MuBench StoryCloze](https://github.com/aialt/MuBench)                               |          1,332 | Machine translation (GPT-4o, auto-checked)     |
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia  |
| Machine translation      |                    | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            |          1,997 | Human translation (professional, from English) |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |          1,913 | Native (crowdsourced Tatoeba sentence pairs)   |

### Standard machine translation test sets

| Test set                                                                | Direction(s)                      | Size                   | Human reference   |
|:------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)             | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Irish datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Irish? Does it make sense to train one?
  - ~1.07 GB English-equivalent text ≈ 0.27B tokens, enough for a compute-optimal model of ~13.4M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Irish-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **2. Pragmatics, discourse & coreference**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 143 of ~18,498 papers (0.77%) (rank 46 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Irish

Here are up to ten papers published in 2026 that mention Irish. None of the 143 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                 | paper                                                                          | mentioned in   |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|:---------------|
| Standard-to-Dialect Transfer Trends Differ across Text and Speech: A Case Study on Intent and Topic Classification in German Dialects | [2026.acl-long.309](https://aclanthology.org/2026.acl-long.309/)               | body only      |
| Cultural Binding Heads in Language Models                                                                                             | [2026.blackboxnlp-1.3](https://aclanthology.org/2026.blackboxnlp-1.3/)         | body only      |
| A Virtual Assistant for Architectural Design in a VR Environment                                                                      | [2026.eacl-demo.38](https://aclanthology.org/2026.eacl-demo.38/)               | body only      |
| LLM Multi-Agent Systems for Long Triple Set Data-to-Text Generation                                                                   | [2026.findings-acl.1712](https://aclanthology.org/2026.findings-acl.1712/)     | body only      |
| Tracing the Latent Threads: A Mechanistic Study of How LLMs Represent and Operationalize Race and Ethnicity Cues                      | [2026.findings-emnlp.1388](https://aclanthology.org/2026.findings-emnlp.1388/) | body only      |
| Modular Approach to Automating Morphological Components in Grammar Engineering                                                        | [2026.lrec-1.898](https://aclanthology.org/2026.lrec-1.898/)                   | body only      |
| Diversity patterns run deep: Impact of diversity intake on multiword expression identification                                        | [2026.mwe-1.13](https://aclanthology.org/2026.mwe-1.13/)                       | body only      |
| wangkongqiang at SemEval-2026 Task 7: Everyday Knowledge Across Diverse Languages and Cultures                                        | [2026.semeval-1.36](https://aclanthology.org/2026.semeval-1.36/)               | body only      |
| DANTE – A Treebank of Tweets in Brazilian Portuguese                                                                                  | [2026.stil-1.12](https://aclanthology.org/2026.stil-1.12/)                     | body only      |
| Cross-Dialectal Transfer for Low-Resource Arabic: The Tunisian Arabic Dependency Treebank                                             | [2026.udw-1.23](https://aclanthology.org/2026.udw-1.23/)                       | body only      |

{% endraw %}
