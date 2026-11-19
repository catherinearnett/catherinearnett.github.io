---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/pag.html
---
{% raw %}
# So you want to work on Pangasinan?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `pag`

**Language family:** **Austronesian** › Malayo-Polynesian › Northern Luzon › … › West Southern Cordilleran ([Glottolog](https://glottolog.org/resource/languoid/id/pang1290))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** about 1.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Philippines

**Status:** Regional official language


## What does Pangasinan look and sound like?

**Written (Pangasinan)**, sample text from [Omniglot](https://www.omniglot.com/writing/pangasinan.htm):

> Say salitan Pangasinan so sakey ya salitan Malayo-Polynesian ya sanga na boleg ya salitan Austronesian. Onsulok ya 1 milyon so mansasalita na say salitan Pangasinan. Naananap ed luyag na Pangasinan, tan naanap ed bansa na Filipinas, so saray karaklan na makapansalita na sayan salita. Balet wala met ray naanap ya makapansalita na Pangasinan ed luyag na La Union, Tarlac, Zambales, tan diad Metro …

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://pag.wikipedia.org/wiki/Salitan_Pangasinan.</sub>

**Spoken:** no Wikitongues video of Pangasinan yet ([its Wikitongues page](https://wikitongues.org/languages/pag/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                      |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 2,654 articles in pag.wikipedia; 15 active users. This is ~1/2,843 of English data and ranks 134 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                    |
| FineWeb                | 3.6 MB (pag_Latn 0), equivalent to ≈3.5 MB of English after byte-premium scaling; 0.47 GB removed by filtering. This is ~1/14,687,941 of English data and ranks 167 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 38.7 MB (pag_Latn 39.0 MB) (rank 139 of the 166 languages in the set that have any; 166 have none)                                                                                                                                          |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                 |
|:-----------------------|:--------------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                              |
| UniMorph               | **None found**                                                                              |
| Wikidata labels        | 477,363 Wikidata items have a label in Pangasinan. (Wikidata codes (labels): pag (477,363)) |
| Wordnets               | **None found**                                                                              |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 3,358,884 sentence pairs with English across 4 corpora; largest: [NLLB](https://opus.nlpl.eu/NLLB) (3,357,840), [translatewiki](https://opus.nlpl.eu/translatewiki) (574), [wikimedia](https://opus.nlpl.eu/wikimedia) (420), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (50). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                 |
| Tatoeba                                                                                  | 62 sentences, 56 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/pag/none)).                                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                                                                        |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pag) en → pag: size not listed                                                                                                                                                                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **5 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, commonlingua, fasttext, funlangid.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=62), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.894 (P 0.942, R 0.857, FPR 1.00e-04) averaged over 3 dataset(s). Runner-up: fasttext (F1 0.835).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.942 |    0.857 | 0.894 | 0.000 | ✓                |
| fasttext     |       0.853 |    0.818 | 0.835 | 0.001 | ✓                |
| OpenLID-v2   |       0.689 |    0.888 | 0.766 | 0.002 | ✓                |
| funlangid    |       0.882 |    0.684 | 0.763 | 0.000 | ✓                |
| commonlingua |       0.799 |    0.598 | 0.681 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  62 |       0.825 |    0.839 | 0.832 |
| Wikipedia | 300 |       1.000 |    0.750 | 0.857 |
| FLORES    | 300 |       1.000 |    0.983 | 0.992 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Pangasinan to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Pangasinan *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Pangasinan and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Pangasinan has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/pag/) video of Pangasinan yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Pangasinan?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Pangasinan (and whether the model is exclusively tagged for Pangasinan or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **11** text-generation models are explicitly tagged for Pangasinan (6 original uploads, 5 fine-tunes/quantisations/merges).
- **3** are tagged *only* for Pangasinan.
- Including tags inherited from base models: **16**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        2 | ██████████           |
|   2024 |        3 | ███████████████      |
|   2025 |        4 | ████████████████████ |
|   2026 |        2 | ██████████           |

### Largest models tagged for Pangasinan

| model                                                                                       | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                     | 8.6B         |                  189 |   2023 | —                       |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                     | 8.6B         |                  189 |   2023 | —                       |
| [Loom-Labs/Apollo-1-8B](https://huggingface.co/Loom-Labs/Apollo-1-8B)                       | 8.2B         |                   90 |   2025 | Qwen/Qwen3-8B-Base      |
| [KiruuPixel/100-1eb-pag-llama-3.1](https://huggingface.co/KiruuPixel/100-1eb-pag-llama-3.1) | 8.0B         |                    2 |   2026 | meta-llama/Llama-3.1-8B |
| [Loom-Labs/Apollo-1-4B](https://huggingface.co/Loom-Labs/Apollo-1-4B)                       | 4.0B         |                   90 |   2025 | Qwen/Qwen3-4B-Base      |

### Models tagged *only* for Pangasinan

None of these has a known parameter count:

| model                                                                                 |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|---------------------:|-------:|:----------------|
| [goldfish-models/pag_latn_10mb](https://huggingface.co/goldfish-models/pag_latn_10mb) |                    1 |   2024 | —               |
| [goldfish-models/pag_latn_5mb](https://huggingface.co/goldfish-models/pag_latn_5mb)   |                    1 |   2024 | —               |
| [goldfish-models/pag_latn_full](https://huggingface.co/goldfish-models/pag_latn_full) |                    1 |   2024 | —               |

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

**4** benchmark datasets in the survey include Pangasinan.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |            802 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             49 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)              | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                            | multi-way (all languages) | 2,009 sentences (Latn) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_pag) (training data) | en → pag                  | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Pangasinan datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Pangasinan? Does it make sense to train one?
  - ~37.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~463.6K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.6B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8 of ~18,498 papers (0.04%) (rank 161 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Pangasinan

Here are up to ten papers published in 2026 that mention Pangasinan. None of the 8 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                      | paper                                                                      |
|:-----------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| How Good is Your Wikipedia? Auditing Data Quality for Low-resource and Multilingual NLP                    | [2026.acl-long.1373](https://aclanthology.org/2026.acl-long.1373/)         |
| Grammar as Control: Modular Language Generation for the Long Tail                                          | [2026.acl-long.1725](https://aclanthology.org/2026.acl-long.1725/)         |
| Adam’s Law: Textual Frequency Law on Large Language Models                                                 | [2026.acl-long.188](https://aclanthology.org/2026.acl-long.188/)           |
| TIPA: Typologically Informed Parameter Aggregation                                                         | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?                 | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)             |
| Tao–Filipino Neural Machine Translation: Strategies for Ultra–Low-Resource Settings                        | [2026.loresmt-1.2](https://aclanthology.org/2026.loresmt-1.2/)             |
| Goldfish: Monolingual Language Models for 350 Languages                                                    | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Disambiguating Geographic Names in Biodiversity Occurrence Data: A Retrieval-Augmented Generation Approach | [2026.nlp4ecology-1.4](https://aclanthology.org/2026.nlp4ecology-1.4/)     |

{% endraw %}
