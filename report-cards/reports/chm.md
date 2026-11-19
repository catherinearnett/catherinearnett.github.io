---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/chm.html
---
{% raw %}
# So you want to work on Hill Mari, Meadow Mari?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `chm`

**Language family:** **Uralic** (all 2 member languages of the macrolanguage) (Glottolog)

**Endangerment:** threatened (all 2 member languages; Glottolog)

**Writing systems:** `Cyrl`

**Speakers:** about 521,000 first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html))

**Official / recognised in:** Russia

**Status:** Regional official language


## What does Hill Mari, Meadow Mari look and sound like?

**Written (Mari)**, sample text from [Omniglot](https://www.omniglot.com/writing/mari.htm):

> 1992 ий сентябрь гыч 1993 ий август марте мемнан республикыште Японий
> гыч толшо самырык рвезе Такаси Танака илыш. Тудо Марий кугыжаныш
> университетыште марий да финн-угор филологий отделенийысе
> студент-влаклан англичан йылмым туныктен да шкежат марий йылмым
> тунемын. Кызыт тудо адакат Марий республикыште. Ты гана Такаси шкетын
> огыл, а Токио университетыште финн-угор йылмым шымлыше, …

**Written (Meadow Mari)**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/mari.htm):

> Чыла еҥ шке лӱмнерже да праваже дене эрык да иктӧр шочеш. Нуно уш-акылышт да намысышт дене пойдаралтыныт да ива-шольо шӱлыш дене икте-весе шотышто ыштышаш улыт.

*Transliteration:* Čəla eng ške lümnerže da pravaže dene erək da iktör šočeš. Nuno uš-akələšt da naməsəšt dene pojdaraltənət da iva-šolʹo šüləš dene ikte-vese šotəšto əštəšaš ulət

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood.

<sub>Text © Omniglot / Simon Ager and contributors: Source: http://www.tooyoo.l.u-tokyo.ac.jp/~kmatsum/texts/mari/mari1.html.</sub>

**Spoken:** no Wikitongues video of Hill Mari, Meadow Mari yet ([its Wikitongues page](https://wikitongues.org/languages/chm/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                             |
|:-----------------------|:---------------------------------------------------------------------------------------------------|
| Wikipedia              | 21,765 articles in mhr, mrj.wikipedia; 33 active users. NB: counted as `mhr` + `mrj` together.     |
| Common Crawl           | **Not identified in Common Crawl's language statistics**                                           |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                     |
| Goldfish training data | 96.4 MB (chm_Cyrl 96.0 MB) (rank 121 of the 166 languages in the set that have any; 166 have none) |

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

| Resource                                                                                 | What exists                                                                                                                                                                                                            |
|:-----------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                                                                                     | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                                                                                |
| Bible translations (eBible corpus)                                                       | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist.                                                            |
| Tatoeba                                                                                  | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                                                                             |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                  | 2,009 sentences (Cyrl script) — the same sentences in 200+ languages                                                                                                                                                   |
| [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                              | **Not included.**                                                                                                                                                                                                      |
| [SMOL](https://huggingface.co/datasets/google/smol) (SmolSent, SmolDoc, GATITOS lexicon) | [GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_chm) en → chm: 3,997 lexicon entries; [SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_chm) en → chm: size not listed |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **3 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, commonlingua, funlangid.
- **Eval datasets (3):** FLORES (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.984 (P 0.973, R 0.994, FPR 2.10e-04) averaged over 3 dataset(s). Runner-up: funlangid (F1 0.896).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.973 |    0.994 | 0.984 | 0.000 | ✓                |
| funlangid    |       0.906 |    0.891 | 0.896 | 0.001 | ✓                |
| commonlingua |       0.791 |    0.883 | 0.827 | 0.004 | ✓                |
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
| Tatoeba   | 300 |       0.946 |    0.997 | 0.971 |
| Wikipedia | 300 |       0.974 |    0.987 | 0.980 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Hill Mari, Meadow Mari to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Hill Mari, Meadow Mari *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Hill Mari, Meadow Mari and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Hill Mari, Meadow Mari has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/chm/) video of Hill Mari, Meadow Mari yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Hill Mari, Meadow Mari?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Hill Mari, Meadow Mari (and whether the model is exclusively tagged for Hill Mari, Meadow Mari or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **186** text-generation models are explicitly tagged for Hill Mari, Meadow Mari (155 original uploads, 31 fine-tunes/quantisations/merges).
- **42** are tagged *only* for Hill Mari, Meadow Mari.
- Including tags inherited from base models: **196**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        3 | █                    |
|   2024 |        8 | █                    |
|   2025 |       13 | ██                   |
|   2026 |      162 | ████████████████████ |

### Largest models tagged for Hill Mari, Meadow Mari

| model                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of            |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:-------------------------|
| [open-athena/Marin-Mochi-535B-A23B](https://huggingface.co/open-athena/Marin-Mochi-535B-A23B)                                                     | 535.0B       |                    1 |   2026 | —                        |
| [DSAKAI/llamarine-GGUF](https://huggingface.co/DSAKAI/llamarine-GGUF)                                                                             | 70.6B        |                    2 |   2026 | meta-llama/Llama-3.1-70B |
| [laion/sft-repro-thinking-step630-nemotron-terminal-step1888](https://huggingface.co/laion/sft-repro-thinking-step630-nemotron-terminal-step1888) | 67.1B        |                    1 |   2026 | —                        |
| [laion/snowball-67b-a2b-cooldown-step105149](https://huggingface.co/laion/snowball-67b-a2b-cooldown-step105149)                                   | 67.1B        |                    1 |   2026 | —                        |
| [laion/snowball-67b-a2b-sft-s1-chat-step257](https://huggingface.co/laion/snowball-67b-a2b-sft-s1-chat-step257)                                   | 67.1B        |                    1 |   2026 | —                        |

### Largest models tagged *only* for Hill Mari, Meadow Mari

| model                                                                                                                                             | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [open-athena/Marin-Mochi-535B-A23B](https://huggingface.co/open-athena/Marin-Mochi-535B-A23B)                                                     | 535.0B       |                    1 |   2026 | —               |
| [laion/sft-repro-thinking-step630-nemotron-terminal-step1888](https://huggingface.co/laion/sft-repro-thinking-step630-nemotron-terminal-step1888) | 67.1B        |                    1 |   2026 | —               |
| [laion/snowball-67b-a2b-cooldown-step105149](https://huggingface.co/laion/snowball-67b-a2b-cooldown-step105149)                                   | 67.1B        |                    1 |   2026 | —               |
| [laion/snowball-67b-a2b-sft-s1-chat-step257](https://huggingface.co/laion/snowball-67b-a2b-sft-s1-chat-step257)                                   | 67.1B        |                    1 |   2026 | —               |
| [laion/snowball-67b-a2b-sft-s2-thinking-step630](https://huggingface.co/laion/snowball-67b-a2b-sft-s2-thinking-step630)                           | 67.1B        |                    1 |   2026 | —               |

_16 tagged models have unknown parameter counts and are not ranked by size._

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

**5** benchmark datasets in the survey include Hill Mari, Meadow Mari.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 346" width="100%" style="max-width:600px" role="img" aria-label="Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif" font-size="14"><title>Eval pyramid: Linguistic knowledge: none; Pragmatics &amp; discourse: none; Commonsense reasoning: none; Reading comprehension: 1 dataset; Knowledge &amp; QA: none; Machine translation: 2 datasets</title><polygon points="300.0,8.0 407.1,112.0 192.9,112.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="86.0" text-anchor="middle" fill="#90a4ae" font-size="13"><tspan font-weight="600">5. Knowledge &amp; QA</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="192.9,112.0 407.1,112.0 464.7,168.0 135.3,168.0" fill="#dcedc8" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="136.6" text-anchor="middle" fill="#33691e" font-size="14"><tspan font-weight="600">4. Reading comprehension</tspan><tspan x="300.0" dy="16" font-size="12">1 dataset</tspan></text><polygon points="135.3,168.0 464.7,168.0 522.4,224.0 77.6,224.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="300.0" y="192.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">3. Commonsense reasoning</tspan><tspan x="300.0" dy="16" font-size="12">none</tspan></text><polygon points="77.6,224.0 299.0,224.0 299.0,280.0 20.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="169.8" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">1. Linguistic knowledge</tspan><tspan x="169.8" dy="16" font-size="12">none</tspan></text><polygon points="301.0,224.0 522.4,224.0 580.0,280.0 301.0,280.0" fill="#eceff1" stroke="#b0bec5" stroke-width="1.5" stroke-dasharray="5 4"/><text x="430.2" y="248.6" text-anchor="middle" fill="#90a4ae" font-size="14"><tspan font-weight="600">2. Pragmatics &amp; discourse</tspan><tspan x="430.2" dy="16" font-size="12">none</tspan></text><polygon points="20.0,286.0 580.0,286.0 580.0,342.0 20.0,342.0" fill="#aed581" stroke="#ffffff" stroke-width="1.5"/><text x="300.0" y="310.6" text-anchor="middle" fill="#1b3d0a" font-size="14"><tspan font-weight="600">Machine translation</tspan><tspan x="300.0" dy="16" font-size="12">2 datasets</tspan></text></svg>

<sub>Darker = more datasets; grey with a dashed outline = none yet.</sub>

### What tasks exist?

| level                    | task               | dataset                                                                                        |   # test items | construction                                  |
|:-------------------------|:-------------------|:-----------------------------------------------------------------------------------------------|---------------:|:----------------------------------------------|
| 4. Reading comprehension | QA – extractive RC | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) (2 varieties/pairs) |          9,194 | Synthetic (LLM-generated) on native Wikipedia |
| Machine translation      |                    | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)           |             73 | Native (crowdsourced Tatoeba sentence pairs)  |

### Standard machine translation test sets

| Test set                                                                                           | Direction(s)              | Size                   | Human reference   |
|:---------------------------------------------------------------------------------------------------|:--------------------------|:-----------------------|:------------------|
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                            | multi-way (all languages) | 2,009 sentences (Cyrl) | ✅                |
| [SMOL GATITOS](https://huggingface.co/datasets/google/smol/viewer/gatitos__en_chm) (training data) | en → chm                  | 3,997 lexicon entries  | ✅                |
| [SMOL SmolDoc](https://huggingface.co/datasets/google/smol/viewer/smoldoc__en_chm) (training data) | en → chm                  | size not listed        | ✅                |

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Hill Mari, Meadow Mari datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Hill Mari, Meadow Mari? Does it make sense to train one?
  - ~50.1 MB English-equivalent text ≈ 0.01B tokens, enough for a compute-optimal model of ~626.2K parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Hill Mari, Meadow Mari-only model is 535.0B, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 37 of ~18,498 papers (0.20%) (rank 105 of the 278 languages in the set that have any; 54 have none); English is mentioned in 8,465.
- Search terms: Meadow Mari | Hill Mari | Mari
- Because 'Mari' is also a common word or name, those mentions only count when they appear in a language context (citations and people's names are skipped).

Here are up to ten papers published in 2026 that mention Hill Mari, Meadow Mari. None of the 37 name it in the title or abstract, so these are a random sample of papers that mention it in the body.

| title                                                                                                                                                | paper                                                                      |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| Benchmarking Source-Sensitive Reasoning in Turkish: Humans and LLMs under Evidential Trust Manipulation                                              | [2026.cmcl-1.25](https://aclanthology.org/2026.cmcl-1.25/)                 |
| Adapting Where It Matters: Depth-Aware Adaptation for Efficient Multilingual Speech Recognition in Low-Resource Languages                            | [2026.findings-acl.827](https://aclanthology.org/2026.findings-acl.827/)   |
| TIPA: Typologically Informed Parameter Aggregation                                                                                                   | [2026.findings-eacl.119](https://aclanthology.org/2026.findings-eacl.119/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                                                              | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)               |
| University Speaking for Everyone: Assessing Changes in Italian Higher Education Statutes toward Gender-Inclusive Language                            | [2026.lrec-1.321](https://aclanthology.org/2026.lrec-1.321/)               |
| SciLaD: A Large-Scale, Transparent, Reproducible Dataset for Natural Scientific Language Processing                                                  | [2026.lrec-1.603](https://aclanthology.org/2026.lrec-1.603/)               |
| A Typology of Synthetic Datasets for Dialogue Processing in Clinical Contexts                                                                        | [2026.lrec-1.653](https://aclanthology.org/2026.lrec-1.653/)               |
| Pragmatic Modelling in Language Learning: Caregiver Question-Answer Feedback in Child-Directed Dialogue                                              | [2026.lrec-1.897](https://aclanthology.org/2026.lrec-1.897/)               |
| Do Lexical and Contextual Coreference Resolution Systems Degrade Differently under Mention Noise? An Empirical Study on Scientific Software Mentions | [2026.nslp-1.10](https://aclanthology.org/2026.nslp-1.10/)                 |
| Frequency modulates structural choice in Turkish suspended affixation: a latent-process account                                                      | [2026.scil-main.32](https://aclanthology.org/2026.scil-main.32/)           |

{% endraw %}
