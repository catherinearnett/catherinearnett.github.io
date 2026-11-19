---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nup.html
---
{% raw %}
# So you want to work on Nupe?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nup`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Nupoid ([Glottolog](https://glottolog.org/resource/languoid/id/nupe1254))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 3 (Wider communication))

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Nupe look and sound like?

**Written (Nupe)**, sample text from [Omniglot](https://www.omniglot.com/writing/nupe.htm):

> Wun ayike yi ga gạ, ga, yi de lefi ndondo à na, yi eta nimi yi ta, gasikiya ma da nimi yi bo à : wun ayike yi ga ye lefi yizi na, U yi Eza aminci, to Gasikiyadeci nạ Wun a jin yi gafara lefi yizi nạ, to nạ Wun a la yi li be eli dede nyi nạ kpata.

*Translation:* He was not that Light, but was sent to bear witness of that Light. That was the true Light, which lighteth every man that cometh into the world.

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://mammana.org/bcp/nupe/nupe.pdf; Source: https://www.kingjamesbibleonline.org/John-Chapter-1/#8.</sub>

**Spoken:** no Wikitongues video of Nupe yet ([its Wikitongues page](https://wikitongues.org/languages/nup/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                      |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,238 articles in nup.wikipedia; 21 active users. This is ~1/6,096 of English data and ranks 149 of the 168 languages in the set with any data in Wikipedia; 164 have none. |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._                                                                                                                        |

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

- **1 of 10** LangID models evaluated have this language code as a label that can be predicted: funlangid.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Nupe to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Nupe *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Nupe and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Nupe has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/nup/) video of Nupe yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Nupe?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Nupe (and whether the model is exclusively tagged for Nupe or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **12** text-generation models are explicitly tagged for Nupe (1 original uploads, 11 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Nupe.
- Including tags inherited from base models: **14**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |       12 | ████████████████████ |

### Largest models tagged for Nupe

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of                         |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:--------------------------------------|
| [hypaai/Hypa-Llama3.1-8b-SFT](https://huggingface.co/hypaai/Hypa-Llama3.1-8b-SFT)                       | 8.0B         |                   11 |   2026 | meta-llama/Llama-3.1-8B               |
| [hypaai/Hypa-Gemma4-E2B-v1](https://huggingface.co/hypaai/Hypa-Gemma4-E2B-v1)                           | 5.1B         |                   10 |   2026 | google/gemma-4-E2B-it                 |
| [hypaai/Hypa-Orpheus-3b-TTS-VC](https://huggingface.co/hypaai/Hypa-Orpheus-3b-TTS-VC)                   | 3.3B         |                   14 |   2026 | unsloth/orpheus-3b-0.1-ft             |
| [hypaai/Hypa-SmolLM-135M-Instruct-LoRAs](https://huggingface.co/hypaai/Hypa-SmolLM-135M-Instruct-LoRAs) | 135.0M       |                   18 |   2026 | unsloth/smollm-135m-instruct-bnb-4bit |

### Largest models tagged *only* for Nupe

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

**0** benchmark datasets in the survey include Nupe.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

Nupe isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Nupe datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Nupe? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 8.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,498 papers (0.02%) (rank 199 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Nupe

Here are up to ten papers published in 2026 that mention Nupe. None of the 4 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                             | paper                                                              | mentioned in   |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|:---------------|
| SAFARI: A Community-Engaged Approach and Dataset of Stereotype Resources in the Sub-Saharan African Context                                                       | [2026.eacl-short.27](https://aclanthology.org/2026.eacl-short.27/) | body only      |
| Anchoring the Judge: Curriculum-Based Adaptation and Reference-Anchored MQM for LLM-Based Machine Translation of an Unseen Low-Resource Language - A Case of Nupe | [2026.loreslm-1.19](https://aclanthology.org/2026.loreslm-1.19/)   | body only      |
| Overview of the Second Workshop on Language Models for Low-Resource Languages (LoResLM 2026)                                                                      | [2026.loreslm-1.56](https://aclanthology.org/2026.loreslm-1.56/)   | body only      |
| Algebraic Classification of Reduplicative Processes                                                                                                               | [2026.scil-main.42](https://aclanthology.org/2026.scil-main.42/)   | body only      |

{% endraw %}
