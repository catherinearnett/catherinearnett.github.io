---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dyu.html
---
{% raw %}
# So you want to work on Dyula?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dyu`

**Language family:** **Mande** › Western Mande › Manding-Kpelle › … › East Manding ([Glottolog](https://glottolog.org/resource/languoid/id/dyul1238))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 7.4 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Burkina Faso

**Status:** Official language


## What does Dyula look and sound like?

**Written:** no Omniglot page found for Dyula.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/dyu/) has 1 video of Dyula speakers. Watch [Achille speaking Mooré and Dioula](https://wikitongues.org/videos/achille_20180226_mos-dyu/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                   |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                   |
| FineWeb                | 2.3 MB (dyu_Latn 0), equivalent to ≈2.0 MB of English after byte-premium scaling; 5.4 MB removed by filtering. This is ~1/23,441,546 of English data and ranks 176 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 14.2 MB (dyu_Latn 14.0 MB) (rank 157 of the 166 languages in the set that have any; 166 have none)                                                                                                                                         |

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

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                           |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                       |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                        |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                                                                              |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_dyu) en → dyu: 3,997 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_dyu) en → dyu: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_dyu) en → dyu: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **6 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, OpenLID-v2, fasttext, funlangid, pyfranc.
- **Eval datasets (3):** FLORES (n=300), SmolSent (n=300), UDHR-LID (n=58)
- **Best model:** GlotLID — F1 0.572 (P 0.664, R 0.514, FPR 1.17e-03) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.333).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.664 |    0.514 | 0.572 | 0.001 | ✓                |
| pyfranc      |       0.333 |    0.333 | 0.333 | 0.000 | ✓                |
| funlangid    |       0.629 |    0.228 | 0.333 | 0.001 | ✓                |
| AfroLID      |       0.266 |    0.389 | 0.313 | 0.024 | ✓                |
| OpenLID-v2   |       0.386 |    0.206 | 0.246 | 0.004 | ✓                |
| fasttext     |       0.349 |    0.213 | 0.235 | 0.006 | ✓                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  58 |       0.211 |    0.069 | 0.104 |
| SmolSent  | 300 |       0.859 |    0.713 | 0.780 |
| FLORES    | 300 |       0.923 |    0.760 | 0.834 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Dyula to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Dyula *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Dyula and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Dyula has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Dyula?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Dyula (and whether the model is exclusively tagged for Dyula or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **18** text-generation models are explicitly tagged for Dyula (7 original uploads, 11 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Dyula.
- Including tags inherited from base models: **23**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███                  |
|   2024 |        3 | █████                |
|   2025 |        0 |                      |
|   2026 |       13 | ████████████████████ |

### Largest models tagged for Dyula

| model                                                                                               | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [McGill-NLP/AfriqueQwen3.5-9B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-9B-50Langs) | 9.4B         |                   32 |   2026 | Qwen/Qwen3.5-9B-Base |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                             | 8.6B         |                  189 |   2023 | —                    |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                             | 8.6B         |                  189 |   2023 | —                    |
| [McGill-NLP/AfriqueQwen3.5-4B-50Langs](https://huggingface.co/McGill-NLP/AfriqueQwen3.5-4B-50Langs) | 5.2B         |                   32 |   2026 | Qwen/Qwen3.5-4B-Base |
| [Tree-AI-lab/kouman-IA-1.5-1B](https://huggingface.co/Tree-AI-lab/kouman-IA-1.5-1B)                 | 1.2B         |                    3 |   2026 | —                    |

### Models tagged *only* for Dyula

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/dyu_latn_10mb](https://huggingface.co/goldfish-models/dyu_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/dyu_latn_5mb](https://huggingface.co/goldfish-models/dyu_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/dyu_latn_full](https://huggingface.co/goldfish-models/dyu_latn_full) |                    1 |   2024 | —               |

_4 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Dyula.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

| Test set                                                                                             | Direction(s)              | Size                   | Human reference   |
|:-----------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                              | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_dyu) (training data)   | en → dyu                  | 3,997 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_dyu) (training data)   | en → dyu                  | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__en_dyu) (training data) | en → dyu                  | size not listed        | ✅                |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Dyula datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Dyula? Does it make sense to train one?
  - ~12.3 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~154.0K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 9.4B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Dyula

Here are up to ten papers published in 2026 that mention Dyula. None of the 8 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      | mentioned in   |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models                   | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/)         | body only      |
| Grammar as Control: Modular Language Generation for the Long Tail                                                                             | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         | body only      |
| AfriCaption: Establishing a New Paradigm for Image Captioning in African Languages                                                            | [2026.africanlp-main.5](https://aclanthology.org/2026.africanlp-main.5/)   | body only      |
| TIPA: Typologically Informed Parameter Aggregation                                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) | body only      |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                                                    | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             | body only      |
| HPLT 3.0: Very Large-Scale Multilingual Resources for LLMs and MT. Mono- and Bi-lingual Data, Multilingual Evaluation, and Pre-Trained Models | [2026.lrec-1.110](https://aclanthology.org/2026.lrec-1.110/)               | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                       | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               | body only      |
| OpenLID-v3: Improving the Precision of Closely Related Language Identification – An Experience Report                                         | [2026.vardial-1.23](https://aclanthology.org/2026.vardial-1.23/)           | body only      |

{% endraw %}
