---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/aii.html
---
{% raw %}
# So you want to work on Syriac?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `aii` · macrolanguage `syr`

**Language family:** **Afro-Asiatic** › Semitic › West Semitic › … › North-Eastern Neo-Aramaic ([Glottolog](https://glottolog.org/resource/languoid/id/assy1241))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: Glottolog)

**Speakers:** about 230,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `syr`, so includes other varieties

**Official / recognised in:** Iraq

**Status:** Regional official language


## What does Syriac look and sound like?

**Written:** Omniglot has [a page on Syriac](https://www.omniglot.com/writing/syriac.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/aii/) has 7 videos of Syriac speakers. Watch [See all](https://wikitongues.org/videos/?language=aii).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                     |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                                                                                                   |
| Common Crawl           | 7,332 pages per crawl on average, which is 0.0003% of the crawl (2026). ⚠️ NB: recorded under the macrolanguage code `syr`, which can include other varieties of Syriac.                                                                   |
| FineWeb                | 2.1 MB (aii_Syrc 0), equivalent to ≈1.1 MB of English after byte-premium scaling; 2.4 MB removed by filtering. This is ~1/25,538,572 of English data and ranks 183 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                      |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 57 sentences / 453 tokens in total: [UD_Assyrian-AS](https://github.com/UniversalDependencies/UD_Assyrian-AS) (57 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                   |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                   |
| Wordnets               | **None found**                                                                                                                                                                                                   |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                           |
| Bible translations (eBible corpus)                                                       | **Yes** — 1 translation: New Testament + parts of the Old Testament ([aii](https://ebible.org/details.php?id=aii), by-nc-nd 4.0). |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                        |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                 |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                 |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_aii) en → aii: 3,717 lexicon entries                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, funlangid.
- **Eval datasets (2):** Tatoeba (n=22), UDHR-LID (n=57)
- **Best model:** GlotLID — F1 1.000 (P 1.000, R 1.000, FPR 0.00e+00) averaged over 2 dataset(s). Runner-up: cld2 (F1 1.000).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| cld2         |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| pyfranc      |       1.000 |    0.955 | 0.976 | 0.000 | ✗                |
| funlangid    |       1.000 |    0.481 | 0.625 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  22 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  57 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Syriac to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Syriac *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Syriac and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Syriac has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Syriac?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Syriac (and whether the model is exclusively tagged for Syriac or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Syriac.**

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

**1** benchmark datasets in the survey include Syriac.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)   | Size                  | Human reference   |
|:---------------------------------------------------------------------------------------------------|:---------------|:----------------------|:------------------|
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_aii) (training data) | en → aii       | 3,717 lexicon entries | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Syriac datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Syriac? Does it make sense to train one?
  - ~1.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~13.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,498 papers (0.06%) (rank 145 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Assyrian Neo-Aramaic | Syriac

Here are up to ten papers published in 2026 that mention Syriac. None of the 11 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                       | paper                                                                  | mentioned in   |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|:---------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                                                                                   | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               | body only      |
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                                                                 | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/) | body only      |
| Under-resourced studies of under-resourced languages: lemmatization and POS-tagging with LLM annotators for historical Armenian, Georgian, Greek and Syriac | [2026.loreslm-1.28](https://aclanthology.org/2026.loreslm-1.28/)       | body only      |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                                                | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)       | body only      |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                                     | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)           | body only      |
| The Patrologia Graeca Corpus: OCR, Annotation, and Open Release of Noisy Nineteenth-Century Polytonic Greek Editions                                        | [2026.lrec-1.517](https://aclanthology.org/2026.lrec-1.517/)           | body only      |
| A Layered Annotation Workflow for Semitic Epigraphy                                                                                                         | [2026.lt4hala-1.18](https://aclanthology.org/2026.lt4hala-1.18/)       | body only      |
| Quantifying Text Reuse Across Three Kṛṣṇa Yajurveda Recensions: Using Multi-Algorithm Computational Collation                                               | [2026.nlp4dh-1.5](https://aclanthology.org/2026.nlp4dh-1.5/)           | body only      |
| LLM as a Morphological Disambiguator for Belarusian: A Preliminary Study                                                                                    | [2026.sigul-1.4](https://aclanthology.org/2026.sigul-1.4/)             | body only      |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                                                                    | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)           | body only      |

{% endraw %}
