---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mvf.html
---
{% raw %}
# So you want to work on Mongolian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mvf` · macrolanguage `mon`

**Language family:** **Mongolic-Khitan** › Mongolic › Eastern Mongolic › … › Mongolian ([Glottolog](https://glottolog.org/resource/languoid/id/peri1253))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (20% certain))

**Speakers:** about 6.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `mon`, so includes other varieties

**Official / recognised in:** People's Republic of China

**Status:** Regional official language


## What does Mongolian look and sound like?

**Written:** Omniglot has [a page on Mongolian](https://www.omniglot.com/writing/mongolian.htm) but no sample text.

**Spoken:** no Wikitongues video of Mongolian yet ([its Wikitongues page](https://wikitongues.org/languages/mvf/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                 |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 28,674 articles in mn.wikipedia; 223 active users. ⚠️ NB: counted under the macrolanguage code `mon`, so this number is shared with Mongolian (`khk`) and overstates Mongolian.                        |
| Common Crawl           | 342,482 pages per crawl on average, which is 0.0159% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `mon`, so this number is shared with Mongolian (`khk`) and overstates Mongolian. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                                                         |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                           |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                    |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 80 sentences / 274 tokens in total: [UD_Peripheral_Mongolian-Ordos](https://github.com/UniversalDependencies/UD_Peripheral_Mongolian-Ordos) (80 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                 |
| Wikidata labels        | **None found**                                                                                                                                                                                                                                 |
| Wordnets               | **None found**                                                                                                                                                                                                                                 |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 357 sentence pairs with English across 1 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (357).                                                                                                       |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                 |
| Tatoeba                                                                                  | 2,801 sentences, 2,563 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/mon/none)). ⚠️ Listed under the macrolanguage code `mon`, so this may cover other varieties as well as Mongolian. |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **0 of 10** LangID models evaluated have this language code as a label that can be predicted.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Mongolian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Mongolian *and* from closely related languages that might be confused with it. Likely confusions to include: Mongolian (`khk`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Mongolian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Mongolian has no UniMorph data, wordnet or Wikidata labels yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/mvf/) video of Mongolian yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Mongolian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Mongolian (and whether the model is exclusively tagged for Mongolian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Mongolian (0 original uploads, 1 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Mongolian.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Largest models tagged for Mongolian

| model                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:----------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [suzuvoice/LMT-60-0.6B-mlx-8bit](https://huggingface.co/suzuvoice/LMT-60-0.6B-mlx-8bit) | 596.0M       |                   58 |   2026 | NiuTrans/LMT-60-0.6B |

### Largest models tagged *only* for Mongolian

_none_

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

**0** benchmark datasets in the survey include Mongolian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

Mongolian isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Mongolian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Mongolian? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 596.0M, aim no higher than
  *3. Commonsense reasoning* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 80 of ~18,498 papers (0.43%) (rank 66 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Peripheral Mongolian (Inner Mongolia) | Peripheral Mongolian | Halh Mongolian | Inner Mongolia | Mongolian
- ⚠️ The name *Mongolian* is shared with Mongolian (`khk`), so this count covers all of them.

Here are up to ten papers published in 2026 that mention Mongolian. None of the 80 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                               | paper                                                                    |
|:--------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| MUDIDI: A Two-Stage Framework for Multilingual Dictionary Digitization with Language Models                         | [2026.emnlp-main.2501](https://aclanthology.org/2026.emnlp-main.2501/)   |
| Masking Stale Observations Helps Search Agents — Until It Doesn’t: A Regime Map and Its Mechanism                   | [2026.emnlp-main.756](https://aclanthology.org/2026.emnlp-main.756/)     |
| RAG-KT: Cross-platform Explainable Knowledge Tracing with Multi-view Fusion Retrieval Generation                    | [2026.findings-acl.257](https://aclanthology.org/2026.findings-acl.257/) |
| Lightweight Haar Wavelet Subband Pruning for LLMs                                                                   | [2026.findings-acl.798](https://aclanthology.org/2026.findings-acl.798/) |
| CausalityCheck: A Framework for Evaluating Causal Reasoning in Large Language Models                                | [2026.findings-acl.808](https://aclanthology.org/2026.findings-acl.808/) |
| Adapting Multilingual NMT to Language Isolates: The Role of Proxy Language Selection and Dialect Handling for Nivkh | [2026.loresmt-1.11](https://aclanthology.org/2026.loresmt-1.11/)         |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                          | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)             |
| Cygnet: Refactoring the Open Multilingual Wordnet                                                                   | [2026.lrec-1.628](https://aclanthology.org/2026.lrec-1.628/)             |
| CREST: Universal Safety Guardrails through Cluster-Guided Cross-Lingual Transfer                                    | [2026.lrec-1.701](https://aclanthology.org/2026.lrec-1.701/)             |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings                            | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)             |

{% endraw %}
