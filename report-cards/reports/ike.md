---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/ike.html
---
{% raw %}
# So you want to work on Inuktitut?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `ike` · macrolanguage `iku`

**Language family:** **Eskimo-Aleut** › Eskimo › Inuit ([Glottolog](https://glottolog.org/resource/languoid/id/east2534))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable (40% certain))

**Writing systems:** `Cans`

**Speakers:** about 85,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) — counted for the macrolanguage `iku`, so includes other varieties

**Official / recognised in:** Canada

**Status:** Regional official language


## What does Inuktitut look and sound like?

**Written:** Omniglot has [a page on Inuktitut](https://www.omniglot.com/writing/inuktitut.htm) but no sample text.

**Spoken:** no Wikitongues video of Inuktitut yet ([its Wikitongues page](https://wikitongues.org/languages/ike/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                            |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 424 articles in iu.wikipedia; 32 active users. ⚠️ NB: counted under the macrolanguage code `iku`, so this number is shared with Inuinnaqtun (`ikt`) and overstates Inuktitut.                                                                     |
| Common Crawl           | 9,010 pages per crawl on average, which is 0.0004% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `iku`, so this number is shared with Inuinnaqtun (`ikt`) and overstates Inuktitut.                                            |
| FineWeb                | 11.6 MB (ike_Cans 12.0 MB), equivalent to ≈5.7 MB of English after byte-premium scaling; 18.7 MB removed by filtering. This is ~1/4,622,503 of English data and ranks 150 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                      |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                       |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                                                                    |
| UniMorph               | **None found**                                                                                                                    |
| Wikidata labels        | 469,350 Wikidata items have a label in Inuktitut. (Wikidata codes (labels): ike-latn (469,350), iu (198,452), ike-cans (156,403)) |
| Wordnets               | **None found**                                                                                                                    |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                        |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,284 sentence pairs with English across 2 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (1,235), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (49).                                                            |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                        |
| Tatoeba                                                                                  | 51 sentences, 48 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/ike/none)).                                                                                                                    |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                  |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                  |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_iu) en → iu: 3,999 lexicon entries; [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_iu-Latn) en → iu-Latn: 4,001 lexicon entries |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, commonlingua, funlangid, pyfranc.
- **Eval datasets (3):** Tatoeba (n=51), UDHR-LID (n=44), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.616 (P 0.665, R 0.580, FPR 6.60e-06) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.610).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.665 |    0.580 | 0.616 | 0.000 | ✓                |
| pyfranc      |       0.665 |    0.570 | 0.610 | 0.000 | ✓                |
| funlangid    |       0.667 |    0.497 | 0.553 | 0.000 | ✓                |
| commonlingua |       0.384 |    0.620 | 0.445 | 0.003 | ✓                |
| cld2         |       0.372 |    0.606 | 0.434 | 0.004 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  51 |       0.000 |    0.000 | 0.000 |
| Wikipedia | 300 |       0.996 |    0.740 | 0.849 |
| UDHR-LID  |  44 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Inuktitut to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from Inuktitut *and* from closely related languages that might be confused with it. Likely confusions to include: Inuinnaqtun (`ikt`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Inuktitut and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Inuktitut has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/ike/) video of Inuktitut yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Inuktitut?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Inuktitut (and whether the model is exclusively tagged for Inuktitut or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **15** text-generation models are explicitly tagged for Inuktitut (9 original uploads, 6 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Inuktitut.
- Including tags inherited from base models: **15**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ███████              |
|   2024 |        3 | ██████████           |
|   2025 |        6 | ████████████████████ |
|   2026 |        4 | █████████████        |

### Largest models tagged for Inuktitut

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 8.2B         |                  143 |   2026 | Qwen/Qwen3-8B-Base |

### Models tagged *only* for Inuktitut

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/iku_cans_10mb](https://huggingface.co/goldfish-models/iku_cans_10mb) |                    1 |   2024 | —               |
| [goldfish-models/iku_cans_5mb](https://huggingface.co/goldfish-models/iku_cans_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/iku_cans_full](https://huggingface.co/goldfish-models/iku_cans_full) |                    1 |   2024 | —               |

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**3** benchmark datasets in the survey include Inuktitut.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |            148 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             49 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Inuktitut has been part of the WMT translation task in **1** year (2020).

| Test set                                                                                               | Direction(s)                             | Size                  | Human reference   |
|:-------------------------------------------------------------------------------------------------------|:-----------------------------------------|:----------------------|:------------------|
| [WMT20 general task](https://www2.statmt.org/wmt20/)                                                   | English → Inuktitut; Inuktitut → English | 2,971 segments        | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_iu) (training data)      | en → iu                                  | 3,999 lexicon entries | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_iu-Latn) (training data) | en → iu-Latn                             | 4,001 lexicon entries | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Inuktitut datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Inuktitut? Does it make sense to train one?
  - ~5.7 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~71.8K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 6 of ~18,498 papers (0.03%) (rank 180 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Eastern Canadian Inuktitut | Inuktitut

Here are up to ten papers published in 2026 that mention Inuktitut. None of the 6 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                    | paper                                                          |
|:-----------------------------------------------------------------------------------------|:---------------------------------------------------------------|
| Goldfish: Monolingual Language Models for 350 Languages                                  | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)   |
| GlossMATE: Multi-Agent Translator Explanations for Glosses                               | [2026.lrec-1.709](https://aclanthology.org/2026.lrec-1.709/)   |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets    | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)         |
| Language Identification for Low-Resource Formosan Languages                              | [2026.sigul-1.24](https://aclanthology.org/2026.sigul-1.24/)   |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)   |
| AmanaMT: Translation Direction Predicts Automatic Metric Reliability                     | [2026.wmt-main.42](https://aclanthology.org/2026.wmt-main.42/) |

{% endraw %}
