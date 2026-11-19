---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/lld.html
---
{% raw %}
# So you want to work on Ladin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `lld`

**Language family:** **Indo-European** › Classical Indo-European › Italic › … › Italian Romance ([Glottolog](https://glottolog.org/resource/languoid/id/ladi1250))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (80% certain))

**Writing systems:** `Latn`

**Speakers:** about 29,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Italy

**Status:** Regional official language


## What does Ladin look and sound like?

**Written (Gardena Ladin)**, sample text from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Duta la jënt ie nasciuda liedia y à la medema denità y i medemi dërc. I à na mënt y na cuscienza y dëssa cunviver coche fredesc.

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ladin-gardena.mp3) (Omniglot).

**Written (Val Badia Ladin)**, sample text from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Dötes les porsones nasc lëdies y cun la medema dignité y i medemi dërć. Ares à na rajun y na cosciënza y mëss sʼincuntè öna cun lʼatra te n spirit de fraternité.

**Written (Comelico Ladin)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/ladin.htm):

> Duce cuance i omin nasse libere e conpains zla dignité e zi derite. Löre inà la reson e la cossenzia e dovaraa tnisse duce a une conpagn de frades.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/lld/) has 2 videos of Ladin speakers. Watch [Andrea speaking Solandro](https://wikitongues.org/videos/andrea_20151117_lld/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                          |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 183,227 articles in lld.wikipedia; 28 active users. This is ~1/41 of English data and ranks 48 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                                                       |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                                                                                        |
| FineWeb                | 1.5 MB (lld_Latn 2.0 MB), equivalent to ≈1.1 MB of English after byte-premium scaling; 7.6 MB removed by filtering. This is ~1/35,019,483 of English data and ranks 198 of the 261 languages in the set with any data in FineWeb; 71 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                                                    |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                            |
|:-----------------------|:---------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                         |
| UniMorph               | 180 lemmas, 7,656 inflected forms ([unimorph/lld](https://github.com/unimorph/lld))    |
| Wikidata labels        | 226,742 Wikidata items have a label in Ladin. (Wikidata codes (labels): lld (226,742)) |
| Wordnets               | **None found**                                                                         |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                     |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 1,845 sentence pairs with English across 4 corpora; largest: [translatewiki](https://opus.nlpl.eu/translatewiki) (1,718), [wikimedia](https://opus.nlpl.eu/wikimedia) (84), [QED](https://opus.nlpl.eu/QED) (22), [Tatoeba](https://opus.nlpl.eu/Tatoeba) (21). |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                     |
| Tatoeba                                                                                  | 85 sentences, 21 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/lld/none)).                                                                                                                                                 |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Latn script); 2,009 sentences (Latn script) — the same sentences in 200+ languages                                                                                                                                                             |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Latn script); 1,358 sentences (Latn script) — paired with English                                                                                                                                                                              |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                                                                                                                               |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, pyfranc.
- **Eval datasets (4):** FLORES (n=300), Tatoeba (n=85), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.893 (P 0.988, R 0.830, FPR 2.65e-05) averaged over 4 dataset(s). Runner-up: pyfranc (F1 0.701).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.988 |    0.830 | 0.893 | 0.000 | ✓                |
| pyfranc      |       0.782 |    0.648 | 0.701 | 0.001 | ✓                |
| commonlingua |       0.792 |    0.505 | 0.605 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       1.000 |    0.593 | 0.745 |
| Tatoeba   |  85 |       0.970 |    0.765 | 0.855 |
| UDHR-LID  |  59 |       0.983 |    0.983 | 0.983 |
| FLORES    | 300 |       1.000 |    0.980 | 0.990 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Ladin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Ladin *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Ladin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Ladin has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.


## What models are available for Ladin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Ladin (and whether the model is exclusively tagged for Ladin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Ladin (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Ladin.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Models tagged for Ladin

None of these has a known parameter count:

| model                                                 |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------|---------------------:|-------:|:----------------|
| [wikilangs/lld](https://huggingface.co/wikilangs/lld) |                    2 |   2026 | —               |

### Largest models tagged *only* for Ladin

_none_

_1 tagged models have unknown parameter counts and are not ranked by size._

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

**4** benchmark datasets in the survey include Ladin.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 4 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">4 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          4,745 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             21 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Ladin has been part of the WMT translation task in **1** year (2026).

| Test set                                                                 | Direction(s)                      | Size                                | Human reference   |
|:-------------------------------------------------------------------------|:----------------------------------|:------------------------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)  | multi-way (all languages)         | 2,009 sentences (Latn)              | ✅                |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)  | multi-way (all languages)         | 2,009 sentences (Latn)              | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)              | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)              | ↔ English (and 8 pivot languages) | 1,358 sentences (Latn)              | ✅                |
| [WMT26 general task](https://github.com/wmt-conference/wmt26-general-mt) | English → Ladin                   | 198 documents (28,523 source words) | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Ladin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Ladin? Does it make sense to train one?
  - ~1.1 MB English-equivalent text ≈ 0.00B tokens, enough for a compute-optimal model of ~14.3K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). That is larger than anything currently tagged, so a dedicated model (or continued pre-training of a multilingual base) could be worthwhile.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 26 of ~18,498 papers (0.14%) (rank 118 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Ladin

Here are up to ten papers published in 2026 that mention Ladin. None of the 26 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                         | paper                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| An Empirical Study of Many-Shot In-Context Learning for Machine Translation of Low-Resource Languages                                         | [2026.findings-aacl.142](https://aclanthology.org/2026.findings-aacl.142/) |
| Modeling Topics as Linguistic Linked Open Data: A First Attempt Using BERTopic, Ontolex-Lemon and FrAC                                        | [2026.ldl-1.1](https://aclanthology.org/2026.ldl-1.1/)                     |
| Rebelòt: Datasets and Token-Level Language Identification for Lombard-Italian-English Code-Mixing                                             | [2026.sigul-1.25](https://aclanthology.org/2026.sigul-1.25/)               |
| Leveraging Verbalized Confidence in LLM-as-a-Judge for Automated Translation Quality Evaluation                                               | [2026.wmt-main.107](https://aclanthology.org/2026.wmt-main.107/)           |
| SpinPop: A Fast Spin Metric for the WMT26 Metrics Shared Task                                                                                 | [2026.wmt-main.110](https://aclanthology.org/2026.wmt-main.110/)           |
| Findings of the WMT26 General Machine Translation Shared Task: Contrastive Dynamic Human Evaluation at Scale                                  | [2026.wmt-main.48](https://aclanthology.org/2026.wmt-main.48/)             |
| Findings of the WMT26 Shared Task on Automated Translation Quality Evaluation Systems: Compact Open Models are Competitive Quality Evaluators | [2026.wmt-main.49](https://aclanthology.org/2026.wmt-main.49/)             |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                                                                     | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)             |
| LiLa at WMT 2026 General MT Task: Exploring Beyond NMT and Learning the Limits of LLM Adaptation for Ligurian and Ladin                       | [2026.wmt-main.60](https://aclanthology.org/2026.wmt-main.60/)             |
| Grammatist at WMT 2026 General MT Task: An Agentic LLM Framework for Machine Translation with Explicit Linguistic Knowledge                   | [2026.wmt-main.65](https://aclanthology.org/2026.wmt-main.65/)             |

{% endraw %}
