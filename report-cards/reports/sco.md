---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/sco.html
---
{% raw %}
# So you want to work on Scots?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `sco`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › Later Anglic ([Glottolog](https://glottolog.org/resource/languoid/id/scot1243))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Latn`

**Speakers:** about 1.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** United Kingdom

**Status:** Regional official language


## What does Scots look and sound like?

**Written (An Introduction to the Scots Language Society)**, sample text from [Omniglot](https://www.omniglot.com/writing/scots.htm):

> The Scots Leid Associe wis foondit in 1972 an ettles tae fordle Scots in leeteratur, drama, the media, eddication an in ilka day uiss. Akis Scots wis ance the state langage o Scotland, it's a vailid pairt o wir heirskip an the associe taks tent tae the fact that it shoud can tak its steid as a langage o Scotland, alang wi Gaelic an Inglis.

*Translation:* The Scots Language Society was founded in 1972 and exists to promote Scots in literature, drama, the media, education and in every day usage. Since Scots was once the state language of Scotland, it is a valid part of our heritage and the society recognises that it should be able to take its place as a language of Scotland, along with Gaelic and English.

**Written (Article 1 of the UDHR)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/scots.htm):

> Aw human sowels is born free and equal in dignity and richts. They are tochered wi mense and conscience and shuld guide theirsels ane til ither in a speirit o britherheid.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/sco/) has 2 videos of Scots speakers. Watch [David speaking Scots (Doric),English](https://wikitongues.org/videos/david_20140923_sco-eng/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 34,218 articles in sco.wikipedia; 116 active users. This is ~1/221 of English data and ranks 75 of the 168 languages in the set with any data in Wikipedia; 164 have none.                            |
| Common Crawl           | 14,779 pages per crawl on average, which is 0.0007% of the crawl (2026). This is ~1/60,323 of English data and ranks 97 of the 113 languages in the set with any data in Common Crawl; 219 have none. |
| FineWeb                | 15.4 MB (sco_Latn 20.0 MB); 16.39 GB removed by filtering. This is ~1/3,478,572 of English data and ranks 136 of the 248 languages in the set with any data in FineWeb; 84 have none.                 |
| Goldfish training data | 59.1 MB (sco_Latn 59.0 MB) (rank 131 of the 166 languages in the set that have any; 166 have none)                                                                                                    |

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

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, cld2, pyfranc.
- **Eval datasets (3):** Tatoeba (n=92), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.873 (P 0.969, R 0.800, FPR 1.10e-04) averaged over 3 dataset(s). Runner-up: pyfranc (F1 0.723).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.969 |    0.800 | 0.873 | 0.000 | ✓                |
| pyfranc      |       0.673 |    0.796 | 0.723 | 0.003 | ✓                |
| cld2         |       0.906 |    0.497 | 0.634 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| funlangid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  92 |       0.985 |    0.707 | 0.823 |
| UDHR-LID  |  58 |       0.957 |    0.776 | 0.857 |
| Wikipedia | 300 |       0.965 |    0.917 | 0.940 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Scots to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Scots *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Scots and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Scots has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Scots?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Scots (and whether the model is exclusively tagged for Scots or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **58** text-generation models are explicitly tagged for Scots (38 original uploads, 20 fine-tunes/quantisations/merges).
- **10** are tagged *only* for Scots.
- Including tags inherited from base models: **58**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2024 |        4 | ██                   |
|   2025 |       12 | ██████               |
|   2026 |       42 | ████████████████████ |

### Largest models tagged for Scots

| model                                                                                                                       | parameters   |   # languages tagged |   year | derivative of           |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------|
| [rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-14B-en-prompt-en-thinking) | 14.8B        |                   64 |   2025 | Qwen/Qwen3-14B-Base     |
| [rubricreward/mR3-Qwen3-8B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-8B-en-prompt-en-thinking)   | 8.2B         |                   64 |   2025 | Qwen/Qwen3-8B-Base      |
| [rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking](https://huggingface.co/rubricreward/mR3-Qwen3-4B-en-prompt-en-thinking)   | 4.0B         |                   64 |   2025 | Qwen/Qwen3-4B-Base      |
| [alphaedge-ai/gemma-3-4b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sco-32768)                         | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it    |
| [jonpojonpo/Machynlleth-3B-Instruct](https://huggingface.co/jonpojonpo/Machynlleth-3B-Instruct)                             | 2.7B         |                    5 |   2026 | britllm/britllm-3b-v0.1 |

### Largest models tagged *only* for Scots

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-sco-32768)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-sco-32768)     | 735.6M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-sco-32768](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-sco-32768) | 121.3M       |                    1 |   2026 | google/gemma-3-270m  |

_5 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include Scots.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 1 dataset</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             73 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

Scots isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Scots datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Scots? Does it make sense to train one?
  - ~55.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~689.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Scots-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 11 of ~18,498 papers (0.06%) (rank 145 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Scots

Here are up to ten papers published in 2026 that mention Scots. None of the 11 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                   | paper                                                                      |
|:--------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| CHASE: Adversarial Red-Blue Teaming for Improving LLM Safety using Reinforcement Learning               | [2026.aacl-long.36](https://aclanthology.org/2026.aacl-long.36/)           |
| Validator-Guided Hard Negative Mining for Masked Language Modeling in Low-Resource Ancient Languages    | [2026.acl-srw.69](https://aclanthology.org/2026.acl-srw.69/)               |
| Why Low-Resource NLP Needs More Than Cross-Lingual Transfer: Lessons Learned from Luxembourgish         | [2026.bigpicture-main.7](https://aclanthology.org/2026.bigpicture-main.7/) |
| Voices from the Margins: Modeling Linguistic Diversity in Spontaneous Speech for Low-Resource Languages | [2026.computel-1.5](https://aclanthology.org/2026.computel-1.5/)           |
| TIPA: Typologically Informed Parameter Aggregation                                                      | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                 | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Proffiliadur: Welsh Language Text Profiling Toolkit                                                     | [2026.lrec-1.88](https://aclanthology.org/2026.lrec-1.88/)                 |
| Building a Corpus and Database for Rare and Undeciphered Scripts                                        | [2026.lt4hala-1.17](https://aclanthology.org/2026.lt4hala-1.17/)           |
| MLingualFC: Evaluating Jailbreak Vulnerabilities in Multilingual Vision-Language Models                 | [2026.mellm-1.22](https://aclanthology.org/2026.mellm-1.22/)               |
| Wiktionary as a Crowdsourced Lexicon for English Dialects                                               | [2026.wac-1.23](https://aclanthology.org/2026.wac-1.23/)                   |

{% endraw %}
