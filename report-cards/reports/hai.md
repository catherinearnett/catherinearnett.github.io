---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/hai.html
---
{% raw %}
# So you want to work on Haida?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `hai`

**Language family:** **Haida** (all 2 member languages of the macrolanguage) (Glottolog)

**Endangerment:** nearly extinct (all 2 member languages; Glottolog)

**Speakers:** no estimate found in CLDR or Wikidata

**Official / recognised in:** United States

**Status:** Regional official language


## What does Haida look and sound like?

**Written (Haida)**, sample text from [Omniglot](https://www.omniglot.com/writing/haida.htm):

> Yáahl uu st'igáalaan, hal st'i'áwyaagaan.
> 'Wáadluu xíl hal tlaahláayaan.
> Gut'iláa ḵ'íit ḵ'uts hal ts'asláangaan.
> 'Wáadluu sáng ḵwáan hal néilaan gyaan hal 'lagáalaan
> Asgáayst hal xitgwáangaan táawk uu hal diyáangaan.
> 'Wáadluu, chíin ḵwáan gándlaay aa hal táagaan.
> Hal sk'ísdlaayaan gyaan xitgáay aa hal jagíyaayaan.
> 'Wáadluu hingáan an sáanjuudaayaan.
> Ahljíihl uu tl' hlgúujuu jahlíis gám …

*Translation:* Raven got sick, he was very sick. Then he made some medicine. He boiled different kinds of tree roots. Then he drank it for many days and got well. Then he flew around looking for food. Then he ate a lot of fish in a creek. He got full and couldn't fly. So, then, he just rested. That is why it doesn't pay to be too greedy. Yáahl (Raven), a story by Erma Lawrence

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://www.haidalanguage.org/raven.html.</sub>

**Spoken:** no Wikitongues video of Haida yet ([its Wikitongues page](https://wikitongues.org/languages/hai/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                   |
|:-----------------------|:---------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                 |
| Common Crawl           | **Not identified in Common Crawl's language statistics** |
| FineWeb                | **Not in FineWeb / FineWeb-2**                           |
| Goldfish training data | **No Goldfish model / data**                             |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                                     |
| UniMorph               | 41 lemmas, 7,040 inflected forms ([unimorph/hai](https://github.com/unimorph/hai)) |
| Wikidata labels        | **None found**                                                                     |
| Wordnets               | **None found**                                                                     |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | 145 sentence pairs with English across 1 corpora; largest: [QED](https://opus.nlpl.eu/QED) (145).                                                           |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                                                                                  | 3 sentences, 2 with an English translation ([browse](https://tatoeba.org/en/sentences/show_all_in/hdn/none)).                                               |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                           |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | **Not included.**                                                                                                                                           |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **0 of 10** LangID models evaluated have this language code as a label that can be predicted.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Haida to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Haida *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Haida and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Haida has no UD treebank, wordnet or Wikidata labels yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/); add Wikidata labels in the language (e.g. through [Wikidata](https://www.wikidata.org) label-a-thons).
- **Add sentences and translations on [Tatoeba](https://tatoeba.org)**: it is openly licensed, easy to contribute to, and feeds LangID and translation datasets.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/hai/) video of Haida yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Haida?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Haida (and whether the model is exclusively tagged for Haida or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **5** text-generation models are explicitly tagged for Haida (2 original uploads, 3 fine-tunes/quantisations/merges).
- **0** are tagged *only* for Haida.
- Including tags inherited from base models: **5**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2025 |        1 | █████                |
|   2026 |        4 | ████████████████████ |

### Largest models tagged for Haida

| model                                                                                                             | parameters   |   # languages tagged |   year | derivative of                      |
|:------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-----------------------------------|
| [Haiintel/hai-indexer-7B](https://huggingface.co/Haiintel/hai-indexer-7B)                                         | 7.2B         |                    2 |   2026 | mistralai/Mistral-7B-Instruct-v0.2 |
| [jegan902/qwen2.5-3b-vietnam-legal-logistics](https://huggingface.co/jegan902/qwen2.5-3b-vietnam-legal-logistics) | 3.1B         |                    2 |   2025 | —                                  |
| [DALabCommunity/Haidass-143M-v1](https://huggingface.co/DALabCommunity/Haidass-143M-v1)                           | 143.1M       |                    3 |   2026 | —                                  |

### Largest models tagged *only* for Haida

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

**0** benchmark datasets in the survey include Haida.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

Haida isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Haida datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Haida? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 7.2B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 2 of ~18,498 papers (0.01%) (rank 227 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Haida

Here are up to ten papers published in 2026 that mention Haida. None of the 2 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                       | paper                                                              |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/) |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                              | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)       |

{% endraw %}
