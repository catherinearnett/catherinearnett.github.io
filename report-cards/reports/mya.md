---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mya.html
---
{% raw %}
# So you want to work on Burmese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mya`

**Language family:** **Sino-Tibetan** › Burmo-Qiangic › Lolo-Burmese › … › Nuclear Mranmaic ([Glottolog](https://glottolog.org/resource/languoid/id/nucl1310))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Mymr`

**Speakers:** about 37.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Myanmar

**Status:** Official language


## What does Burmese look and sound like?

**Written:** Omniglot has [a page on Burmese](https://www.omniglot.com/writing/burmese.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mya/) has 3 videos of Burmese speakers. Watch [Naw speaking Burmese](https://wikitongues.org/videos/naw_20180425_mya/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                         |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 113,397 articles in my.wikipedia; 260 active users. This is ~1/67 of English data and ranks 55 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                      |
| Common Crawl           | 359,828 pages per crawl on average, which is 0.0167% of the crawl (2026). This is ~1/2,478 of English data and ranks 49 of the 115 languages in the set with any data in Common Crawl; 217 have none.                                          |
| FineWeb                | 3.14 GB (mya_Mymr 3.14 GB), equivalent to ≈0.62 GB of English after byte-premium scaling; 1.32 GB removed by filtering. This is ~1/16,996 of English data and ranks 59 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | 4.29 GB (mya_Mymr 4.29 GB) (rank 44 of the 171 languages in the set that have any; 161 have none)                                                                                                                                              |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                             |
|:-----------------------|:----------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                          |
| UniMorph               | **None found**                                                                          |
| Wikidata labels        | 391,709 Wikidata items have a label in Burmese. (Wikidata codes (labels): my (391,709)) |
| Wordnets               | [Asian WordNet](http://www.asianwordnet.org/about) (size not listed); licence: BSD.     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 13,711,267 sentence pairs with English across 17 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (10,014,948), [ParaCrawl-Bonus](https://opus.nlpl.eu/ParaCrawl-Bonus) (1,666,564), [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles) (1,398,025), [CCAligned](https://opus.nlpl.eu/CCAligned) (294,946), [TED2020](https://opus.nlpl.eu/TED2020) (63,427). |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([mya](https://ebible.org/details.php?id=mya), Public Domain); full Bible ([myajvb](https://ebible.org/details.php?id=myajvb), Public Domain).                                                                                                                                                                               |
| Tatoeba                                                                                  | 592 sentences, 502 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mya/none)).                                                                                                                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Mymr script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                                                              |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Mymr script) — paired with English                                                                                                                                                                                                                                                                                                               |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_my) en → my: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_my) en → my: size not listed                                                                                                                                                    |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=56), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.999 (P 0.999, R 0.998, FPR 3.96e-06) averaged over 5 dataset(s). Runner-up: pyfranc (F1 0.979).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.999 |    0.998 | 0.999 | 0.000 | ✓                |
| pyfranc      |       0.998 |    0.963 | 0.979 | 0.000 | ✓                |
| commonlingua |       0.996 |    0.909 | 0.946 | 0.000 | ✓                |
| OpenLID-v2   |       0.904 |    1.000 | 0.938 | 0.001 | ✓                |
| fasttext     |       0.905 |    0.993 | 0.935 | 0.001 | ✓                |
| funlangid    |       0.999 |    0.841 | 0.903 | 0.000 | ✓                |
| cld2         |       0.841 |    1.000 | 0.889 | 0.002 | ✓                |
| py3langid    |       0.841 |    1.000 | 0.889 | 0.003 | ✓                |
| cld3         |       0.843 |    0.964 | 0.871 | 0.003 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       1.000 |    0.993 | 0.997 |
| NTREX     | 300 |       1.000 |    0.997 | 0.998 |
| Wikipedia | 300 |       0.997 |    1.000 | 0.998 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  56 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Burmese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Burmese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Burmese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Burmese has no UD treebank or UniMorph data yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Burmese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Burmese (and whether the model is exclusively tagged for Burmese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **417** text-generation models are explicitly tagged for Burmese (112 original uploads, 305 fine-tunes/quantisations/merges).
- **87** are tagged *only* for Burmese.
- Including tags inherited from base models: **658**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       13 | ██                   |
|   2023 |       15 | ██                   |
|   2024 |      104 | █████████████        |
|   2025 |      128 | ████████████████     |
|   2026 |      157 | ████████████████████ |

### Largest models tagged for Burmese

| model                                                                                                               | parameters   |   # languages tagged |   year | derivative of                                      |
|:--------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                           | 1.9T         |                  143 |   2025 | —                                                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                               | 856.0B       |                  143 |   2025 | —                                                  |
| [aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B](https://huggingface.co/aisingapore/Nemotron-SEA-LION-v4.8-120B-A12B) | 123.6B       |                    8 |   2026 | nvidia/NVIDIA-Nemotron-3-Super-120B-A12B-Base-BF16 |
| [bartowski/Tower-Babel_Babel-83B-Chat-GGUF](https://huggingface.co/bartowski/Tower-Babel_Babel-83B-Chat-GGUF)       | 83.2B        |                   24 |   2025 | Tower-Babel/Babel-83B-Chat                         |
| [Sakalti/ultiima-72B](https://huggingface.co/Sakalti/ultiima-72B)                                                   | 72.7B        |                   29 |   2025 | Qwen/Qwen2.5-72B                                   |

### Largest models tagged *only* for Burmese

| model                                                                                                                                                                         | parameters   |   # languages tagged |   year | derivative of           |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [atsuki-yamaguchi/Llama-3.1-8B-Instruct-my-madlad-mean-slerp0305-emb](https://huggingface.co/atsuki-yamaguchi/Llama-3.1-8B-Instruct-my-madlad-mean-slerp0305-emb)             | 8.1B         |                    1 |   2024 | meta-llama/Llama-3.1-8B |
| [atsuki-yamaguchi/Qwen2.5-7B-Instruct-my-madlad-mean-slerp0305-emb-special](https://huggingface.co/atsuki-yamaguchi/Qwen2.5-7B-Instruct-my-madlad-mean-slerp0305-emb-special) | 7.7B         |                    1 |   2024 | Qwen/Qwen2.5-7B         |
| [Turtle344/mistral-health-faq-v1](https://huggingface.co/Turtle344/mistral-health-faq-v1)                                                                                     | 7.4B         |                    1 |   2024 | —                       |
| [hmone231/mistral_burmese_health_update](https://huggingface.co/hmone231/mistral_burmese_health_update)                                                                       | 7.4B         |                    1 |   2024 | —                       |
| [la-min/mistral-health-faq](https://huggingface.co/la-min/mistral-health-faq)                                                                                                 | 7.2B         |                    1 |   2024 | —                       |

_48 tagged models have unknown parameter counts and are not ranked by size._

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

**13** benchmark datasets in the survey include Burmese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: 3 datasets; Reading comprehension: 3 datasets; Knowledge &amp; QA: none; Machine translation: 5 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="192.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#689f38" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#ffffff" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">5 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task                          | dataset                                                                              | # test items   | construction                                             |
|:-------------------------|:------------------------------|:-------------------------------------------------------------------------------------|:---------------|:---------------------------------------------------------|
| 3. Commonsense reasoning | HellaSwag                     | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                | 9,088          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning | StoryCloze                    | [MuBench StoryCloze](https://github.com/aialt/MuBench)                               | 1,332          | Machine translation (GPT-4o, auto-checked)               |
| 3. Commonsense reasoning | StoryCloze                    | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                | 1,511          | Human translation (professional)                         |
| 4. Reading comprehension | QA – MC reading comprehension | [Belebele](https://huggingface.co/datasets/facebook/belebele)                        | 900            | Human translation (professional)                         |
| 4. Reading comprehension | QA – MC reading comprehension | [Burmese-SAN (QA subtask)](https://leaderboard.sea-lion.ai/detailed/MY)              | —              | Native (native-speaker-led)                              |
| 4. Reading comprehension | QA – extractive RC            | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           | 5,000          | Synthetic (LLM-generated) on native Wikipedia            |
| Machine translation      |                               | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                            | 1,997          | Human translation (professional, from English)           |
| Machine translation      |                               | [TICO-19](https://github.com/tico-19/tico-19.github.io)                              | 2,100          | Human translation (professional/volunteer, from English) |
| Machine translation      |                               | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) | 220            | Native (crowdsourced Tatoeba sentence pairs)             |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | multi-way (all languages)         | 2,009 sentences (Mymr) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Mymr) | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_my) (training data)   | en → my                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_my) (training data) | en → my                           | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Burmese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Burmese? Does it make sense to train one?
  - ~0.84 GB English-equivalent text ≈ 0.21B tokens, enough for a compute-optimal model of ~10.5M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Burmese-only model is 8.1B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 105 of ~18,498 papers (0.57%) (rank 58 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Burmese

Here are up to ten papers published in 2026 that mention Burmese. None of the 105 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| SEA-NLI: Natural Language Inference as a Lens into Southeast Asian Cultural Understanding                                   | [2026.aacl-long.94](https://aclanthology.org/2026.aacl-long.94/)             |
| To Answer or to Abstain: Mitigating Search-Agent Hallucinations via Abstention-Aware Reinforcement Learning                 | [2026.emnlp-main.161](https://aclanthology.org/2026.emnlp-main.161/)         |
| Left-Branching Transformers Excel at Right-Branching Languages: Data Shapes Word Order Preferences in Language Models       | [2026.emnlp-main.2476](https://aclanthology.org/2026.emnlp-main.2476/)       |
| Low-Resource Safety Failures Are Action Failures, Not Representation Failures                                               | [2026.findings-emnlp.287](https://aclanthology.org/2026.findings-emnlp.287/) |
| When Multilingual Evaluation Assumptions Fail: Tokenization Effects Across Scripts                                          | [2026.loreslm-1.4](https://aclanthology.org/2026.loreslm-1.4/)               |
| Cross-Lingual Stability and Bias in Instruction-Tuned Language Models for Humanitarian NLP                                  | [2026.lrec-1.346](https://aclanthology.org/2026.lrec-1.346/)                 |
| Are the LLMs Capable of Maintaining at Least the Language Genus?                                                            | [2026.lrec-1.704](https://aclanthology.org/2026.lrec-1.704/)                 |
| Instruction-Tuned Urdu LLMs: Efficient Adaptation of Llama Models and Evaluation Resources for Urdu                         | [2026.lrec-1.832](https://aclanthology.org/2026.lrec-1.832/)                 |
| PolaFusion at SemEval-2026 Task 9: Ensemble Transformers with Targeted Augmentation for Multilingual Polarization Detection | [2026.semeval-1.361](https://aclanthology.org/2026.semeval-1.361/)           |
| A Direction-Specialized System for WMT26 Chinese-Southeast Asian Multilingual Machine Translation                           | [2026.wmt-main.183](https://aclanthology.org/2026.wmt-main.183/)             |

{% endraw %}
