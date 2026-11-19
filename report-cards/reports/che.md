---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/che.html
---
{% raw %}
# So you want to work on Chechen?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `che`

**Language family:** **Nakh-Daghestanian** › Nakh › Chechen-Ingush ([Glottolog](https://glottolog.org/resource/languoid/id/chec1245))

**Endangerment:** 🟡 threatened (level 2 of 6 on Glottolog’s scale; source: ElCat: Vulnerable)

**Writing systems:** `Cyrl`

**Speakers:** about 929,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Chechen look and sound like?

**Written (Chechen)**, sample text from [Omniglot](https://www.omniglot.com/writing/chechen.htm):

> Ламанах духдуьйлу шал шийла шовданш
> Шиэн бекъачу кийрана Ӏаббалца ца молуш,
> Ӏин кӀоргиэ буьйлш, мела муж муьйлуш,
> Варшан йистиэ йолу маргӀал сийна буц
> Шиэн оьздачу зоьрхана буззалца ца юуш,
> Орцал лахабуьйлуш, сема ладуьйгӀш,
> Иччархочун тоьпуо лацарна, кхоьруш,
> Дехачу диэгана буткъага мотт хьоькхуш,
> Мокхазан бердах куьрана га хьоькхуш,
> Попан орамах торгӀала тӀа детташ,
> Лергаш дуьхьал туьйсуш, кур …

*Translation:* From the depths of the mountains gush the ice-cold springs, But he doesn't fill his lean stomach there. Rather he descends to the depths of the ravine and drinks from a warm puddle. The wooded slope is bordered by rising fresh blue grass, But he doesn't fill his noble belly there. Coming out below the wooded hills, he listens carefully, Anxious to avoid the dreaded hunter's gun. Licking his long …

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/che/) has 2 videos of Chechen speakers. Watch [Movsar speaking Chechen](https://wikitongues.org/videos/movsar_20170713_che/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                               |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 871,420 articles in ce.wikipedia; 95 active users. This is ~1/9 of English data and ranks 17 of the 168 languages in the set with any data in Wikipedia; 164 have none.              |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                                                                                                             |
| FineWeb                | 39.5 MB (che_Cyrl 40.0 MB); 0.13 GB removed by filtering. This is ~1/1,351,620 of English data and ranks 121 of the 248 languages in the set with any data in FineWeb; 84 have none. |
| Goldfish training data | 0.17 GB (che_Cyrl 0.17 GB) (rank 109 of the 166 languages in the set that have any; 166 have none)                                                                                   |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 489 sentences / 3,048 tokens in total: [UD_Chechen-MottDT](https://github.com/UniversalDependencies/UD_Chechen-MottDT) (489 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                             |
| Wikidata labels        | _Not computed yet: run `python -m lrc build structured --resources wikidata`._                                                                                                                                             |
| Wordnets               | **None found**                                                                                                                                                                                                             |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                                                                                 | What exists                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                                                                                                                     |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                                                                                                                                 |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                                                                                                                                  |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | **Not included.**                                                                                                                                                                                                                                                                                                           |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | 1,358 sentences (Cyrl script) — paired with English                                                                                                                                                                                                                                                                         |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ce) en → ce: 3,997 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ru_ce) ru → ce: size not listed; [SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__ru_ce) ru → ce: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **4 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, fasttext, funlangid.
- **Eval datasets (2):** Tatoeba (n=47), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.928 (P 0.938, R 0.918, FPR 1.19e-04) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.572).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.938 |    0.918 | 0.928 | 0.000 | ✓                |
| funlangid    |       0.512 |    0.670 | 0.572 | 0.003 | ✓                |
| commonlingua |       0.527 |    0.611 | 0.537 | 0.003 | ✓                |
| fasttext     |       0.283 |    0.907 | 0.418 | 0.009 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   |  47 |       0.894 |    0.894 | 0.894 |
| Wikipedia | 300 |       0.983 |    0.943 | 0.963 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Chechen to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Chechen *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Chechen and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Chechen has no UniMorph data or wordnet yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Chechen?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Chechen (and whether the model is exclusively tagged for Chechen or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **26** text-generation models are explicitly tagged for Chechen (12 original uploads, 14 fine-tunes/quantisations/merges).
- **6** are tagged *only* for Chechen.
- Including tags inherited from base models: **26**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        4 | ███████              |
|   2024 |        4 | ███████              |
|   2025 |        7 | █████████████        |
|   2026 |       11 | ████████████████████ |

### Largest models tagged for Chechen

| model                                                                                             | parameters   |   # languages tagged |   year | derivative of      |
|:--------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                         | 1.9T         |                  143 |   2025 | —                  |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)             | 856.0B       |                  143 |   2025 | —                  |
| [google/madlad400-8b-lm](https://huggingface.co/google/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [jbochi/madlad400-8b-lm](https://huggingface.co/jbochi/madlad400-8b-lm)                           | 8.6B         |                  189 |   2023 | —                  |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 8.2B         |                  143 |   2026 | Qwen/Qwen3-8B-Base |

### Largest models tagged *only* for Chechen

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of        |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------|
| [alphaedge-ai/gemma-3-4b-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-che-16384)     | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it |
| [alphaedge-ai/gemma-3-1b-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-1b-it-che-16384)     | 716.8M       |                    1 |   2026 | google/gemma-3-1b-pt |
| [alphaedge-ai/gemma-3-270m-it-che-16384](https://huggingface.co/alphaedge-ai/gemma-3-270m-it-che-16384) | 110.8M       |                    1 |   2026 | google/gemma-3-270m  |

_12 tagged models have unknown parameter counts and are not ranked by size._

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

**6** benchmark datasets in the survey include Chechen.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                              |   # test items | construction                                  |
|:-------------------------|:-------------------|:-------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)           |          5,000 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge) |             17 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                            | Direction(s)                      | Size                   | Human reference   |
|:----------------------------------------------------------------------------------------------------|:----------------------------------|:-----------------------|:------------------|
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | ↔ English (and 8 pivot languages) | 1,358 sentences (Cyrl) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_ce) (training data)   | en → ce                           | 3,997 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__ru_ce) (training data)   | ru → ce                           | size not listed        | ✅                |
| [SMOL SmolSent](https://huggingface.co/datasets/google/smol/viewer/smolsent__ru_ce) (training data) | ru → ce                           | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Chechen datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Chechen? Does it make sense to train one?
  - ~99.9 MB English-equivalent text ≈ 0.02B tokens, enough for a compute-optimal model of ~1.2M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Chechen-only model is 3.7B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 7 of ~18,498 papers (0.04%) (rank 172 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Chechen

Here are up to ten papers published in 2026 that mention Chechen. None of the 7 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                            | paper                                                                      |
|:-------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Private-Use Area Characters in the Wild: Signal or Noise?                                        | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)                   |
| Confusable Characters as Endangered Language Markers: The Case of North Caucasus Writing Systems | [2026.cawl-1.5](https://aclanthology.org/2026.cawl-1.5/)                   |
| TIPA: Typologically Informed Parameter Aggregation                                               | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                          | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings         | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)               |
| Expanding Chechen Machine Translation Resources: SMOL, BOUQuET, and WMT24++ Extensions           | [2026.wmt-main.195](https://aclanthology.org/2026.wmt-main.195/)           |
| Findings of the WMT 2026 Shared Task of the Open Language Data Initiative                        | [2026.wmt-main.57](https://aclanthology.org/2026.wmt-main.57/)             |

{% endraw %}
