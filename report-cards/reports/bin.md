---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/bin.html
---
{% raw %}
# So you want to work on Edo?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `bin`

**Language family:** **Atlantic-Congo** › Volta-Congo › Benue-Congo › … › Central Plains Edoid ([Glottolog](https://glottolog.org/resource/languoid/id/bini1246))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 4 (Educational))

**Speakers:** about 1.7 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Nigeria

**Status:** Major language (added to the set; not official)


## What does Edo look and sound like?

**Written (Edo)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/edo.htm):

> Emwan ne agbon hia ne a biere, a bie iran noyan-egbe iran kevbe wee, umwon-mwen o ree etin hia ne o kheke iran khin. A ye ewaen kevbe ekhoe ne o maa wu iran, ne iran gha yin da egbe vbe orhion oghe eten-okpa.

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Edo yet ([its Wikitongues page](https://wikitongues.org/languages/bin/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                               |
|:-----------------------|:-----------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                             |
| Common Crawl           | _Not computed yet: run `python -m lrc build sizes`._ |
| FineWeb                | _Not computed yet: run `python -m lrc build sizes`._ |
| Goldfish training data | _Not computed yet: run `python -m lrc build sizes`._ |

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

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: AfroLID, GlotLID, funlangid, pyfranc.
- **Eval datasets (1):** UDHR-LID (n=47)
- **Best model:** pyfranc — F1 1.000 (P 1.000, R 1.000, FPR 0.00e+00) averaged over 1 dataset(s). Runner-up: GlotLID (F1 0.967).
- ⚠️ Only one eval dataset — treat the ranking as indicative only.

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| pyfranc      |       1.000 |    1.000 | 1.000 | 0.000 | ✓                |
| GlotLID      |       1.000 |    0.936 | 0.967 | 0.000 | ✓                |
| funlangid    |       1.000 |    0.851 | 0.920 | 0.000 | ✓                |
| AfroLID      |       1.000 |    0.830 | 0.907 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |


### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Edo to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Edo *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Edo and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Edo has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/bin/) video of Edo yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Edo?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Edo (and whether the model is exclusively tagged for Edo or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **14** text-generation models are explicitly tagged for Edo (1 original uploads, 13 fine-tunes/quantisations/merges).
- **4** are tagged *only* for Edo.
- Including tags inherited from base models: **14**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2026 |       14 | ████████████████████ |

### Largest models tagged for Edo

| model                                                                                                           | parameters   |   # languages tagged |   year | derivative of                    |
|:----------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [lucasjoy88/Gemma-SEA-LION-v3-9B-IT-Cebuano](https://huggingface.co/lucasjoy88/Gemma-SEA-LION-v3-9B-IT-Cebuano) | 9.2B         |                    3 |   2026 | google/gemma-2-9b                |
| [kasramojallal/packi-qwen3-4b-lora-e](https://huggingface.co/kasramojallal/packi-qwen3-4b-lora-e)               | 4.0B         |                    1 |   2026 | Qwen/Qwen3-4B-Instruct-2507      |
| [kasramojallal/packi-llama32-3b-lora-e](https://huggingface.co/kasramojallal/packi-llama32-3b-lora-e)           | 3.0B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |
| [zary0/edo-cutoff-1b](https://huggingface.co/zary0/edo-cutoff-1b)                                               | 1.0B         |                    2 |   2026 | —                                |
| [BeardedMonster/gemma-3-270m-translate-rl2c](https://huggingface.co/BeardedMonster/gemma-3-270m-translate-rl2c) | 270.0M       |                   37 |   2026 | google/gemma-3-270m              |

### Largest models tagged *only* for Edo

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [kasramojallal/packi-qwen3-4b-lora-e](https://huggingface.co/kasramojallal/packi-qwen3-4b-lora-e)     | 4.0B         |                    1 |   2026 | Qwen/Qwen3-4B-Instruct-2507      |
| [kasramojallal/packi-llama32-3b-lora-e](https://huggingface.co/kasramojallal/packi-llama32-3b-lora-e) | 3.0B         |                    1 |   2026 | meta-llama/Llama-3.2-3B-Instruct |

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

**0** benchmark datasets in the survey include Edo.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: none; Knowledge &amp; QA: none; Machine translation: none</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="136.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="310.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

_None found._

### Standard machine translation test sets

Edo isn't in FLORES+, BOUQuET, SMOL, WMT24++ or any WMT translation task (2005–2026).

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Edo datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Edo? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Edo-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 4 of ~18,498 papers (0.02%) (rank 199 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Bini | Edo
- Because 'Bini'; 'Edo' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers published in 2026 that mention Edo. None of the 4 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                        | paper                                                                      | mentioned in   |
|:-------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|:---------------|
| Cultural Awareness is Represented but Not Decoded: Tracing Mythological Knowledge across 18 Open-Source LLMs | [2026.findings-aacl.227](https://aclanthology.org/2026.findings-aacl.227/) | body only      |
| Assessing the Persuasive Effect of AI-Generated Image Support of Arguments                                   | [2026.lrec-1.641](https://aclanthology.org/2026.lrec-1.641/)               | body only      |
| Categorical Emotions or Appraisals - Which Emotion Model Explains Argument Convincingness Better?            | [2026.lrec-1.649](https://aclanthology.org/2026.lrec-1.649/)               | body only      |
| Trust Me, I Can Convince You: The Contextualized Argument Appraisal Framework and the ContArgA Corpus        | [2026.lrec-1.659](https://aclanthology.org/2026.lrec-1.659/)               | body only      |

{% endraw %}
