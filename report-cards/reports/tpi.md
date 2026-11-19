---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tpi.html
---
{% raw %}
# So you want to work on Tok Pisin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tpi`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Early Melanesian Pidgin ([Glottolog](https://glottolog.org/resource/languoid/id/tokp1240))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 7.1 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Papua New Guinea

**Status:** Official language


## What does Tok Pisin look and sound like?

**Written (Tok Pisin)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/tokpisin.htm):

> Yumi olgeta mama karim umi long stap fri na wankain long wei yumi lukim i gutpela na strepela tru. Uumi olgeta igat ting ting bilong wanem samting I rait na rong na mipela olgeta I mas mekim gutpela pasin long ol narapela long tingting bilong brata susa.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tpi/) has 2 videos of Tok Pisin speakers. Watch [Kini speaking Kalo](https://wikitongues.org/videos/kini_20190813_khz-tpi-eng/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                           |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,417 articles in tpi.wikipedia; 7 active users. This is ~1/5,326 of English data and ranks 146 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                         |
| FineWeb                | 5.4 MB (tpi_Latn 10.0 MB), equivalent to ≈4.6 MB of English after byte-premium scaling; 0.43 GB removed by filtering. This is ~1/9,922,929 of English data and ranks 159 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 20.0 MB (tpi_Latn 20.0 MB) (rank 151 of the 166 languages in the set that have any; 166 have none)                                                                                                                                               |

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

| Resource                                                                                 | What exists                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                             |
| Bible translations (eBible corpus)                                                       | **Yes** — 2 translations: full Bible ([tpi](https://ebible.org/details.php?id=tpi), by-nc-nd 4.0); full Bible ([tpiOTNT](https://ebible.org/details.php?id=tpiOTNT), by-nc-nd 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                          |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script) — paired with English                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_tpi) en → tpi: size not listed                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=135), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.980 (P 0.989, R 0.972, FPR 3.95e-05) averaged over 4 dataset(s). Runner-up: fasttext (F1 0.960).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.989 |    0.972 | 0.980 | 0.000 | ✓                |
| fasttext     |       0.971 |    0.952 | 0.960 | 0.000 | ✓                |
| pyfranc      |       0.911 |    0.917 | 0.914 | 0.001 | ✓                |
| funlangid    |       0.868 |    0.839 | 0.850 | 0.001 | ✓                |
| commonlingua |       0.723 |    0.900 | 0.790 | 0.002 | ✓                |
| OpenLID-v2   |       0.634 |    0.987 | 0.736 | 0.006 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 135 |       0.961 |    0.911 | 0.935 |
| Wikipedia | 300 |       0.997 |    0.980 | 0.988 |
| FLORES    | 300 |       1.000 |    0.997 | 0.998 |
| UDHR-LID  |  58 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tok Pisin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Tok Pisin *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tok Pisin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tok Pisin has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tok Pisin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tok Pisin (and whether the model is exclusively tagged for Tok Pisin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **13** text-generation models are explicitly tagged for Tok Pisin (4 original uploads, 9 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Tok Pisin.
- Including tags inherited from base models: **18**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        3 | ███████              |
|   2025 |        9 | ████████████████████ |
|   2026 |        1 | ██                   |

### Largest models tagged for Tok Pisin

| model                                                                                                     | parameters   |   # languages tagged |   year | derivative of                            |
|:----------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------------|
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                                     | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base                       |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                                     | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base                       |
| [Loom-Labs/Apollo-1-2B](https://huggingface.co/Loom-Labs/Apollo-1-2B)                                     | 1.7B         |                   90 |   2025 | Qwen/Qwen3-1.7B-Base                     |
| [JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM](https://huggingface.co/JLouisBiz/Qwen3-0.6B-GGUF-for-24GB-VRAM) | 751.6M       |                   88 |   2025 | Qwen/Qwen3-0.6B-Base                     |
| [AAU-NLP/CreoleVal-CreoleM2M](https://huggingface.co/AAU-NLP/CreoleVal-CreoleM2M)                         | 611.1M       |                   10 |   2025 | facebook/mbart-large-50-many-to-many-mmt |

### Models tagged *only* for Tok Pisin

None of these has a known parameter count:

| model                                                                                                 |   # languages tagged |   year | derivative of    |
|:------------------------------------------------------------------------------------------------------|---------------------:|-------:|:-----------------|
| [WilliamSotoM/PTHQL_language_Tok_Pisin](https://huggingface.co/WilliamSotoM/PTHQL_language_Tok_Pisin) |                    1 |   2025 | google/mt5-large |
| [goldfish-models/tpi_latn_10mb](https://huggingface.co/goldfish-models/tpi_latn_10mb)                 |                    1 |   2024 | —                |
| [goldfish-models/tpi_latn_5mb](https://huggingface.co/goldfish-models/tpi_latn_5mb)                   |                    1 |   2024 | —                |
| [goldfish-models/tpi_latn_full](https://huggingface.co/goldfish-models/tpi_latn_full)                 |                    1 |   2024 | —                |

_8 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Tok Pisin.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 3 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">3 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |            397 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             49 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)                      | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                            | multi-way (all languages)         | 2,009 sentences (Latn) | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                        | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_tpi) (training data) | en → tpi                          | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tok Pisin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tok Pisin? Does it make sense to train one?
  - ~17.0 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~212.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,498 papers (0.05%) (rank 155 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Tok Pisin

Here are up to ten papers published in 2026 that mention Tok Pisin. None of the 9 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| We’re Cooked! – Probing LLM Political Alignment Via Conflict-Framed Recipe Translation                                                        | [2026.oracle-main.18](https://aclanthology.org/2026.oracle-main.18/)       |
| The University of Melbourne WMT 2026 CreoleMT Submission: A Domain-Balanced Approach to Low-Resource Pacific Creole Machine Translation       | [2026.wmt-main.189](https://aclanthology.org/2026.wmt-main.189/)           |
| Gwo-K Kreyol Classifier: Rock Pidgins (RP) Submission to the WMT 2026 CreoleMT Language Identification Shared Task                            | [2026.wmt-main.191](https://aclanthology.org/2026.wmt-main.191/)           |
| Findings of the Second Shared Task for Creole Language Machine Translation, at WMT 2026                                                       | [2026.wmt-main.56](https://aclanthology.org/2026.wmt-main.56/)             |

{% endraw %}
