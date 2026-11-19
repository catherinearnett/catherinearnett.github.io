---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/dsb.html
---
{% raw %}
# So you want to work on Lower Sorbian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `dsb`

**Language family:** **Indo-European** › Classical Indo-European › Balto-Slavic › … › Sorbian ([Glottolog](https://glottolog.org/resource/languoid/id/lowe1385))

**Endangerment:** 🟠 shifting (level 3 of 6 on Glottolog’s scale; source: ElCat: Threatened (20% certain))

**Writing systems:** `Latn`

**Speakers:** about 6,982 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Germany

**Status:** Regional official language


## What does Lower Sorbian look and sound like?

**Written (Upper Sorbian)**, sample text from [Omniglot](https://www.omniglot.com/writing/sorbian.htm):

> Wšitcy čłowjekojo su wot naroda swobodni a su
> jenacy po dostojnosći a prawach. Woni su z rozumom a swědomjom
> wobdarjeni a maja mjezsobu w duchu bratrowstwa wobchadźeć.

**Written (Lower Sorbian)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/sorbian.htm):

> Wšykne luźe su lichotne roźone a jadnake po
> dostojnosći a pšawach. Woni maju rozym a wědobnosć
> a maju ze sobu w duchu bratšojstwa wobchadaś.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Lower Sorbian yet ([its Wikitongues page](https://wikitongues.org/languages/dsb/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                              |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 3,458 articles in dsb.wikipedia; 19 active users. This is ~1/2,182 of English data and ranks 126 of the 168 languages in the set with any data in Wikipedia; 164 have none.         |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                            |
| FineWeb                | 7.0 MB (dsb_Latn 10.0 MB); 0.12 GB removed by filtering. This is ~1/7,625,286 of English data and ranks 153 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                                        |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                          |
|:-----------------------|:-------------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                       |
| UniMorph               | 994 lemmas, 20,121 inflected forms ([unimorph/dsb](https://github.com/unimorph/dsb)) |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._       |
| Wordnets               | **None found**                                                                       |

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

- **2 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua.
- **Eval datasets (2):** Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.961 (P 0.996, R 0.928, FPR 2.77e-05) averaged over 2 dataset(s). Runner-up: commonlingua (F1 0.836).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.996 |    0.928 | 0.961 | 0.000 | ✓                |
| commonlingua |       0.827 |    0.845 | 0.836 | 0.002 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.993 |    0.887 | 0.937 |
| Wikipedia | 300 |       1.000 |    0.970 | 0.985 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Lower Sorbian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Lower Sorbian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Lower Sorbian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Lower Sorbian has no UD treebank or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/dsb/) video of Lower Sorbian yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Lower Sorbian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Lower Sorbian (and whether the model is exclusively tagged for Lower Sorbian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **8** text-generation models are explicitly tagged for Lower Sorbian (1 original uploads, 7 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Lower Sorbian.
- Including tags inherited from base models: **8**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2025 |        2 | ███████              |
|   2026 |        6 | ████████████████████ |

### Largest models tagged for Lower Sorbian

| model                                                                                                           | parameters   |   # languages tagged |   year | derivative of          |
|:----------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------|
| [ahmedeltawel/Qwen3.5-4B-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen3.5-4B-hsb-dsb)                       | 4.8B         |                    3 |   2026 | Qwen/Qwen3.5-4B        |
| [Korla/Qwen2.5-3B-Instruct-hsb-dsb-mlx-4Bit](https://huggingface.co/Korla/Qwen2.5-3B-Instruct-hsb-dsb-mlx-4Bit) | 3.1B         |                    2 |   2026 | Qwen/Qwen2.5-3B        |
| [yhn112/WMT_Limited_Resources_Sorbian](https://huggingface.co/yhn112/WMT_Limited_Resources_Sorbian)             | 1.9B         |                    4 |   2026 | Qwen/Qwen3.5-2B        |
| [ahmedeltawel/Qwen2.5-1.5B-Instruct-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen2.5-1.5B-Instruct-hsb-dsb) | 1.5B         |                    3 |   2026 | Qwen/Qwen2.5-1.5B      |
| [ahmedeltawel/Qwen3.5-0.8B-hsb-dsb](https://huggingface.co/ahmedeltawel/Qwen3.5-0.8B-hsb-dsb)                   | 1.0B         |                    3 |   2026 | Qwen/Qwen3.5-0.8B-Base |

### Largest models tagged *only* for Lower Sorbian

_none_

_2 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Lower Sorbian.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |            105 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Lower Sorbian isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Lower Sorbian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Lower Sorbian? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 4.8B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 9 of ~18,498 papers (0.05%) (rank 155 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Lower Sorbian

Here are up to ten papers published in 2026 that mention Lower Sorbian. None of the 9 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                         | paper                                                              |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| Entropic properties of languages in phonetic versus orthographic alphabets                                                    | [2026.emnlp-main.92](https://aclanthology.org/2026.emnlp-main.92/) |
| LexiPhon: A Collection of Phonetically Transcribed Lexicons from Wikipedia                                                    | [2026.lrec-1.448](https://aclanthology.org/2026.lrec-1.448/)       |
| One Model, Five Tasks, Two RTX 3090 GPUs: The HSE System for the Sorbian Track of WMT26 Multitask LLMs with Limited Resources | [2026.wmt-main.209](https://aclanthology.org/2026.wmt-main.209/)   |
| HeyBusan at WMT26: A System for the Sorbian Track                                                                             | [2026.wmt-main.210](https://aclanthology.org/2026.wmt-main.210/)   |
| Getting More from Small LLMs and Limited Data: Fuzzy-Match Retrieval and Candidate Scoring for Multitask Sorbian NLP          | [2026.wmt-main.211](https://aclanthology.org/2026.wmt-main.211/)   |
| TUMHN@WMT2026: LLMs with Limited Resources for Slavic Languages                                                               | [2026.wmt-main.212](https://aclanthology.org/2026.wmt-main.212/)   |
| HITSZ at WMT 2026: Mixed Continued Pre-training and Supervised Fine-tuning for Low-Resource Sorbian                           | [2026.wmt-main.214](https://aclanthology.org/2026.wmt-main.214/)   |
| In-Context Learning for Upper Sorbian to German Translation: Comparing Lexical and Morpho-Syntactic Information               | [2026.wmt-main.39](https://aclanthology.org/2026.wmt-main.39/)     |
| Findings of the WMT 2026 Shared Task: Multitask LLMs with Limited Resources                                                   | [2026.wmt-main.59](https://aclanthology.org/2026.wmt-main.59/)     |

{% endraw %}
