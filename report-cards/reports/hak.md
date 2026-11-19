---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hak.html
---
{% raw %}
# So you want to work on Hakka?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hak` · macrolanguage `zho`

**Language family:** **Sino-Tibetan** › Sinitic › Classical-Middle-Modern Sinitic › Middle-Modern Sinitic ([Glottolog](https://glottolog.org/resource/languoid/id/hakk1236))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 5 (Developing))

**Speakers:** about 35.2 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Taiwan

**Status:** National language


## What does Hakka look and sound like?

**Written:** no Omniglot page found for Hakka.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/hak/) has 2 videos of Hakka speakers. Watch [Sanda speaking Hakka](https://wikitongues.org/videos/sanda_20181022_hak/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                        |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 10,511 articles in hak.wikipedia; 27 active users. This is ~1/718 of English data and ranks 103 of the 168 languages in the set with any data in Wikipedia; 164 have none.                                    |
| Common Crawl           | 100,182,847 pages per crawl on average, which is 4.6477% of the crawl (2026). ⚠️ NB: counted under the macrolanguage code `zho`, so this number is shared with Standard Chinese (`cmn`) and overstates Hakka. |
| FineWeb                | 2.1 MB (hak_Hani 0; hak_Latn 0); 0.12 GB removed by filtering. This is ~1/25,432,776 of English data and ranks 181 of the 248 languages in the set with any data in FineWeb; 84 have none.                    |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                                                  |

**By writing system:**

| Writing system   |   FineWeb | FineWeb, English-equivalent   |
|:-----------------|----------:|:------------------------------|
| Han (`Hani`)     |         0 | — (no byte premium yet)       |
| Latin (`Latn`)   |         0 | — (no byte premium yet)       |

_Common Crawl and Wikipedia statistics are not broken down by writing system._

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

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (3):** Tatoeba (n=64), UDHR-LID (n=57), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.494 (P 0.641, R 0.443, FPR 7.56e-05) averaged over 3 dataset(s). Runner-up: commonlingua (F1 0.336).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.641 |    0.443 | 0.494 | 0.000 | ✓                |
| commonlingua |       0.338 |    0.334 | 0.336 | 0.001 | ✓                |
| funlangid    |       0.333 |    0.326 | 0.329 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  |  57 |       0.000 |    0.000 | 0.000 |
| Tatoeba   |  64 |       0.957 |    0.344 | 0.506 |
| Wikipedia | 300 |       0.967 |    0.987 | 0.977 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hakka to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is unreliable)**: label text from Hakka *and* from closely related languages that might be confused with it. Likely confusions to include: Standard Chinese (`cmn`).
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hakka and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Hakka has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Hakka?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hakka (and whether the model is exclusively tagged for Hakka or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **1** text-generation models are explicitly tagged for Hakka (1 original uploads, 0 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Hakka.
- Including tags inherited from base models: **1**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |        1 | ████████████████████ |

### Models tagged for Hakka

None of these has a known parameter count:

| model                                                 |   # languages tagged |   year | derivative of   |
|:------------------------------------------------------|---------------------:|-------:|:----------------|
| [wikilangs/hak](https://huggingface.co/wikilangs/hak) |                    2 |   2026 | —               |

### Largest models tagged *only* for Hakka

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

**1** benchmark datasets in the survey include Hakka.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                    |   # test items | construction                                  |
|:-------------------------|:-------------------|:---------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) |          1,945 | Synthetic (LLM-generated) on native Wikipedia |

### Standard machine translation test sets

Hakka isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hakka datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hakka? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 12 of ~18,498 papers (0.06%) (rank 142 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Hakka Chinese | Hakka

Here are up to ten papers published in 2026 that mention Hakka. None of the 12 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                         | paper                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| MMAC: A Multilingual, Multimodal Alignment Framework for Cultural Grounding Evaluation                                        | [2026.acl-long.989](https://aclanthology.org/2026.acl-long.989/)           |
| Anchoring Speech with Semantics: A Multimodal Adapter Mechanism for Automatic Speech Recognition in Low-Resource Languages    | [2026.emnlp-main.1380](https://aclanthology.org/2026.emnlp-main.1380/)     |
| FuzhouBench: A Benchmark for Eastern Min Chinese with Tone Sandhi Annotations                                                 | [2026.emnlp-main.618](https://aclanthology.org/2026.emnlp-main.618/)       |
| TIPA: Typologically Informed Parameter Aggregation                                                                            | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| What Drives Dialectal Jailbreaks? An Ablation of Surface Form, Cultural Framing, and Strategy Banks                           | [2026.impactspeech-1.10](https://aclanthology.org/2026.impactspeech-1.10/) |
| Efficient Dialect-Aware Modeling and Conditioning for Low-Resource Taiwanese Hakka Speech Processing                          | [2026.lrec-1.491](https://aclanthology.org/2026.lrec-1.491/)               |
| SiniticMTError: A Machine Translation Dataset with Error Annotations for Sinitic Languages                                    | [2026.lrec-1.683](https://aclanthology.org/2026.lrec-1.683/)               |
| Subword-Based Comparative Linguistics across 242 Languages Using Wikipedia Glottosets                                         | [2026.mrl-1.4](https://aclanthology.org/2026.mrl-1.4/)                     |
| FLANS at SemEval-2026 Task 7: RAG with Open-Sourced Smaller LLMs for Everyday Knowledge Across Diverse Languages and Cultures | [2026.semeval-1.119](https://aclanthology.org/2026.semeval-1.119/)         |
| Benchmarking Multilingual LLM Translation Accuracy for Fuzhounese                                                             | [2026.sigul-1.20](https://aclanthology.org/2026.sigul-1.20/)               |

{% endraw %}
