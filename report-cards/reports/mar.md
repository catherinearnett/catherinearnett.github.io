---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/mar.html
---
{% raw %}
# So you want to work on Marathi?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `mar`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Modern Marathi ([Glottolog](https://glottolog.org/resource/languoid/id/mara1378))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Deva`

**Speakers:** about 98.6 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 83.1 million first-language + 3.0 million second-language ([Wikidata](https://www.wikidata.org/wiki/Q1571#P1098), 2010)

**Official / recognised in:** India

**Status:** Regional official language


## What does Marathi look and sound like?

**Written:** Omniglot has [a page on Marathi](https://www.omniglot.com/writing/marathi.htm) but no sample text.

**Spoken:** [Wikitongues](https://wikitongues.org/languages/mar/) has 2 videos of Marathi speakers. Watch [Devika speaking English, Marwari, Marathi, Hindi](https://wikitongues.org/videos/devika_20141012_eng-rwr-mar-hin/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                    |
|:-----------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 104,027 articles in mr.wikipedia; 297 active users. This is ~1/73 of English data and ranks 56 of 168 languages in the set in Wikipedia.                                                                                  |
| Common Crawl           | 642,705 pages per crawl on average, which is 0.0298% of the crawl (2026). This is ~1/1,387 of English data and ranks 45 of 113 languages in the set in Common Crawl.                                                      |
| FineWeb                | 6.34 GB (mar_Deva 6.34 GB; mar_Latn 0), equivalent to ≈2.56 GB of English after byte-premium scaling; 3.45 GB removed by filtering. This is ~1/8,420 of English data and ranks 47 of 248 languages in the set in FineWeb. |
| Goldfish training data | 8.14 GB (mar_Deva 8.14 GB) (rank 25 of 166 in the set)                                                                                                                                                                    |

**By writing system:**

| Writing system      | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:--------------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Devanagari (`Deva`) | 6.34 GB   | 2.56 GB                       | 8.14 GB      | 3.28 GB                        |
| Latin (`Latn`)      | 0         | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                       |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 10,072 sentences / 121,704 tokens in total: [UD_Marathi-CMUPAN](https://github.com/UniversalDependencies/UD_Marathi-CMUPAN) (9,606 sentences), [UD_Marathi-UFAL](https://github.com/UniversalDependencies/UD_Marathi-UFAL) (466 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | **None found**                                                                                                                                                                                                                                                                                                                    |
| Wikidata labels        | 565,526 Wikidata items have a label in Marathi. (Wikidata codes (labels): mr (565,526))                                                                                                                                                                                                                                           |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY; [Marathi WordNet](http://www.cfilt.iitb.ac.in/wordnet/webmwn/) (size not listed); licence: BROWSE OLINE ONLY.                                                                                                    |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                    |
|:-----------------------------------|:-----------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                        |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([mar](https://ebible.org/details.php?id=mar), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                     |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=59), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.974 (P 0.974, R 0.974, FPR 2.70e-04) averaged over 6 dataset(s). Runner-up: fasttext (F1 0.954).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.974 |    0.974 | 0.974 | 0.000 | ✓                |
| fasttext     |       0.933 |    0.976 | 0.954 | 0.001 | ✓                |
| py3langid    |       0.957 |    0.947 | 0.952 | 0.001 | ✓                |
| commonlingua |       0.972 |    0.908 | 0.936 | 0.000 | ✓                |
| cld2         |       0.761 |    0.972 | 0.837 | 0.005 | ✓                |
| funlangid    |       0.909 |    0.791 | 0.834 | 0.001 | ✓                |
| OpenLID-v2   |       0.742 |    0.973 | 0.820 | 0.006 | ✓                |
| pyfranc      |       0.731 |    0.886 | 0.784 | 0.006 | ✓                |
| cld3         |       0.370 |    0.957 | 0.517 | 0.025 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| CommonLID | 300 |       0.946 |    0.873 | 0.908 |
| Wikipedia | 300 |       0.946 |    0.983 | 0.964 |
| Tatoeba   | 300 |       0.970 |    0.987 | 0.979 |
| FLORES    | 300 |       0.984 |    1.000 | 0.992 |
| NTREX     | 300 |       1.000 |    1.000 | 1.000 |
| UDHR-LID  |  59 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Marathi to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Marathi *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Marathi and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Marathi has no UniMorph data yet. You could contribute inflection tables to [UniMorph](https://unimorph.github.io/).


## What models are available for Marathi?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Marathi (and whether the model is exclusively tagged for Marathi or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **513** text-generation models are explicitly tagged for Marathi (199 original uploads, 314 fine-tunes/quantisations/merges).
- **39** are tagged *only* for Marathi.
- Including tags inherited from base models: **878**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       38 | ███                  |
|   2023 |       33 | ██                   |
|   2024 |       61 | █████                |
|   2025 |      116 | █████████            |
|   2026 |      265 | ████████████████████ |

### Largest models tagged for Marathi

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Marathi

| model                                                                                                   | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [l3cube-pune/marathi-gpt-gemma-7b](https://huggingface.co/l3cube-pune/marathi-gpt-gemma-7b)             | 8.5B         |                    1 |   2024 | —               |
| [Echelon-AI/marathi-mistral-v0.1](https://huggingface.co/Echelon-AI/marathi-mistral-v0.1)               | 7.2B         |                    1 |   2024 | —               |
| [Echelon-AI/marathi-mistral-v0.2](https://huggingface.co/Echelon-AI/marathi-mistral-v0.2)               | 7.2B         |                    1 |   2024 | —               |
| [marathi-llm/MahaMarathi-7B-v24.01-Base](https://huggingface.co/marathi-llm/MahaMarathi-7B-v24.01-Base) | 6.9B         |                    1 |   2024 | —               |
| [smallstepai/Misal-7B-base-v0.1](https://huggingface.co/smallstepai/Misal-7B-base-v0.1)                 | 6.9B         |                    1 |   2024 | —               |

_65 tagged models have unknown parameter counts and are not ranked by size._

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

**26** benchmark datasets in the survey include Marathi.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [6]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [4]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [6]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [1]   |  & discourse [1]   \
  /____________________|_____________________\
 /         ✅ Machine translation [8]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | construction                                                        |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:--------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 460            | Treebank-based (automatic, UD + UniMorph)                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                     | [Winogrande_translated (CognitiveLab)](https://huggingface.co/datasets/CognitiveLab/Winogrande_translated) | —              | Machine translation (method not stated)                             |
| 3. Commonsense reasoning               | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                           | 500            | Human translation                                                   |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                          |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 9,279          | Machine translation (GPT-3.5-turbo)                                 |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                             |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                          |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                    |
| 4. Reading comprehension               | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                                   | 10,805         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii    |
| 4. Reading comprehension               | QA – extractive RC             | [IndicQA (AI4Bharat, IndicXTREME)](https://huggingface.co/datasets/ai4bharat/IndicQA)                      | 1,604          | Native                                                              |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | IndicMMLU-Pro                                                                                              | —              | Machine translation (from MMLU-Pro)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                     | 6,924          | Native (Indian exams; some translated)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                     |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                            | 250            | Native (locally sourced)                                            |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                                 |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources)    |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [SMOL – SmolDoc](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional) of LLM-generated English documents |
| Machine translation                    | Machine translation            | [SMOL – SmolSent](https://huggingface.co/datasets/google/smol)                                             | —              | Human translation (professional, from English)                      |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                    | 2,100          | Human translation (professional/volunteer, from English)            |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 11,026         | Native (crowdsourced Tatoeba sentence pairs)                        |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                       |

### What tasks are missing?
- **1. Linguistic knowledge:** LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC
- **3. Commonsense reasoning:** Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Marathi datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Marathi? Does it make sense to train one?
  - ~3.28 GB English-equivalent text ≈ 0.82B tokens, enough for a compute-optimal model of ~41.0M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Marathi-only model is 8.5B, aim no higher than
  *4. Reading comprehension* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 157 of ~18,498 papers (0.85%) (rank 42 of 278 in the set); English is mentioned in 8,465.
- Search terms: Marathi

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 157):

| title                                                                                                    | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| UPDESH: Synthesizing Grounded Instruction Tuning Data for 13 Indic Languages                             | [2026.acl-long.1763](https://aclanthology.org/2026.acl-long.1763/)             |
| Polyglot Teachers: Evaluating Language Models for Multilingual Synthetic Data Generation                 | [2026.emnlp-main.440](https://aclanthology.org/2026.emnlp-main.440/)           |
| FiNERweb: Datasets and Artifacts for Scalable Multilingual Named Entity Recognition                      | [2026.findings-eacl.121](https://aclanthology.org/2026.findings-eacl.121/)     |
| The Geometry of LLM-as-Judge: Why Inter-LLM Consensus Is Not Human Alignment                             | [2026.findings-emnlp.1696](https://aclanthology.org/2026.findings-emnlp.1696/) |
| Are Small Language Models the Silver Bullet to Low-Resource Languages Machine Translation?               | [2026.loresmt-1.1](https://aclanthology.org/2026.loresmt-1.1/)                 |
| APTFiNER: Annotation Preserving Translation for Fine-grained Named Entity Recognition                    | [2026.lrec-1.608](https://aclanthology.org/2026.lrec-1.608/)                   |
| STAR-IL: A Dataset for Style-Aware Machine Translation of Product Reviews in Indian Languages            | [2026.lrec-1.691](https://aclanthology.org/2026.lrec-1.691/)                   |
| OpenSubtitles2024: A Massively Parallel Dataset of Movie Subtitles for MT Development and Evaluation     | [2026.lrec-1.700](https://aclanthology.org/2026.lrec-1.700/)                   |
| Beyond Accuracy: A Structured Error Analysis of Multilingual LLMs on Marathi Script Variation and Syntax | [2026.mellm-1.11](https://aclanthology.org/2026.mellm-1.11/)                   |
| An improved Code-Switching Detection System for some Indic Languages                                     | [2026.mme-main.3](https://aclanthology.org/2026.mme-main.3/)                   |

{% endraw %}
