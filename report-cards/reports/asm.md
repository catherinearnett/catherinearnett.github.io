---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/asm.html
---
{% raw %}
# So you want to work on Assamese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `asm`

**Language family:** **Indo-European** › Classical Indo-European › Indo-Iranian › … › Eastern Kamrupa ([Glottolog](https://glottolog.org/resource/languoid/id/assa1263))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 2 (Provincial))

**Writing systems:** `Beng`

**Speakers:** about 18.3 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 15.3 million first-language ([Wikidata](https://www.wikidata.org/wiki/Q29401#P1098), 2019)

**Official / recognised in:** India

**Status:** Regional official language


## What does Assamese look and sound like?

**Written (Assamese)**, sample text from [Omniglot](https://www.omniglot.com/writing/assamese.htm):

> জন্মগতভাৱে সকলো মানুহ মৰ্য্যদা আৰু অধিকাৰত সমান আৰু স্বতন্ত্ৰ। তেওঁলোকৰ বিবেক আছে, বুদ্ধি আছে। তেওঁলোকে প্ৰত্যেকে প্ৰেত্যেকক ভ্ৰাতৃভাৱে ব্যৱহাৰ কৰা উচিত।

*Transliteration:* Zonmogotobhawe xokolü manuh moirjjoda aru odhikarot xoman aru sotontro. Teü̃lükor bibek ase, buddhi ase. Teü̃lüke proitteke proittekok bhratribhawe bebohar kora usit.

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/asm/) has 4 videos of Assamese speakers. Watch [Kangkana speaking Assamese, English](https://wikitongues.org/videos/kangkana_20181228_asm-eng/).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                                                                                                                                               |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 26,013 articles in as.wikipedia; 186 active users. This is ~1/290 of English data and ranks 78 of 168 languages in the set in Wikipedia.                                                                                                                                                                                                             |
| Common Crawl           | 71,841 pages per crawl on average, which is 0.0033% of the crawl (2026). This is ~1/12,409 of English data and ranks 71 of 113 languages in the set in Common Crawl.                                                                                                                                                                                 |
| FineWeb                | 0.39 GB (asm_Beng 0.39 GB; asm_Latn 0), equivalent to ≈0.15 GB of English after byte-premium scaling (⚠️ only 100% of the bytes have a byte premium, so this undercounts; re-run `python -m lrc build sizes` to fill the gap); 0.37 GB removed by filtering. This is ~1/136,776 of English data and ranks 84 of 248 languages in the set in FineWeb. |
| Goldfish training data | 0.95 GB (asm_Beng 0.95 GB) (rank 77 of 166 in the set)                                                                                                                                                                                                                                                                                               |

**By writing system:**

| Writing system   | FineWeb   | FineWeb, English-equivalent   | Goldfish     | Goldfish, English-equivalent   |
|:-----------------|:----------|:------------------------------|:-------------|:-------------------------------|
| Bengali (`Beng`) | 0.39 GB   | — (no byte premium yet)       | 0.95 GB      | 0.38 GB                        |
| Latin (`Latn`)   | 0         | — (no byte premium yet)       | not included | —                              |

_Common Crawl and Wikipedia statistics are not broken down by writing system._ _Goldfish ignores a Latin-script file when it looks like romanisation of a language's main script; see `KEEP_LATIN` in `lrc/build/sizes.py`._

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                        |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 1 treebank, 73 sentences / 871 tokens in total: [UD_Assamese-AiW](https://github.com/UniversalDependencies/UD_Assamese-AiW) (73 sentences). It has POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 1,575 lemmas, 94,147 inflected forms ([unimorph/asm](https://github.com/unimorph/asm))                                                                                                                             |
| Wikidata labels        | 592,993 Wikidata items have a label in Assamese. (Wikidata codes (labels): as (592,993))                                                                                                                           |
| Wordnets               | [IndoWordNet](http://www.cfilt.iitb.ac.in/indowordnet/index.jsp) (size not listed); licence: BROWSE ONLINE ONLY.                                                                                                   |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                        |
|:-----------------------------------|:---------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                            |
| Bible translations (eBible corpus) | **Yes** — 1 translation: full Bible ([asmfb](https://ebible.org/details.php?id=asmfb), by-sa 4.0). |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **7 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid.
- **Eval datasets (4):** CommonLID (n=213), FLORES (n=300), Tatoeba (n=300), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.976 (P 0.997, R 0.956, FPR 1.88e-05) averaged over 4 dataset(s). Runner-up: OpenLID-v2 (F1 0.974).

> ⚠️ **These scores are almost certainly an over-estimate.** Scores ≥ 0.99 come from small, clean, mostly single-domain test sets (often parallel data like FLORES that some models were trained on). Real web text is noisier, shorter, code-switched and full of closely related languages, so expect noticeably lower precision in practice.

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.997 |    0.956 | 0.976 | 0.000 | ✓                |
| OpenLID-v2   |       0.994 |    0.956 | 0.974 | 0.000 | ✓                |
| fasttext     |       1.000 |    0.943 | 0.970 | 0.000 | ✓                |
| py3langid    |       0.970 |    0.961 | 0.965 | 0.000 | ✓                |
| commonlingua |       0.997 |    0.895 | 0.940 | 0.000 | ✓                |
| cld2         |       0.999 |    0.878 | 0.931 | 0.000 | ✓                |
| funlangid    |       0.994 |    0.735 | 0.830 | 0.000 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld3         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.996 |    0.927 | 0.960 |
| CommonLID | 213 |       1.000 |    0.934 | 0.966 |
| Tatoeba   | 300 |       0.993 |    0.963 | 0.978 |
| FLORES    | 300 |       1.000 |    1.000 | 1.000 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Assamese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Assamese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Assamese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Assamese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Assamese (and whether the model is exclusively tagged for Assamese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **337** text-generation models are explicitly tagged for Assamese (148 original uploads, 189 fine-tunes/quantisations/merges).
- **28** are tagged *only* for Assamese.
- Including tags inherited from base models: **488**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       29 | ████                 |
|   2023 |       26 | ████                 |
|   2024 |       38 | ██████               |
|   2025 |      131 | ████████████████████ |
|   2026 |      113 | █████████████████    |

### Largest models tagged for Assamese

| model                                                                                 | parameters   |   # languages tagged |   year | derivative of   |
|:--------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:----------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)             | 1.9T         |                  143 |   2025 | —               |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b) | 856.0B       |                  143 |   2025 | —               |
| [0xtest1231/bloom-copy](https://huggingface.co/0xtest1231/bloom-copy)                 | 176.2B       |                   37 |   2026 | —               |
| [AbdulElahGwaith/bloom](https://huggingface.co/AbdulElahGwaith/bloom)                 | 176.2B       |                   37 |   2026 | —               |
| [Methamera/bloomz-mt-fork](https://huggingface.co/Methamera/bloomz-mt-fork)           | 176.2B       |                   37 |   2024 | —               |

### Largest models tagged *only* for Assamese

| model                                                                                                       | parameters   |   # languages tagged |   year | derivative of                 |
|:------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------|
| [alphaedge-ai/Qwen3.5-4B-asm-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-4B-asm-32768)               | 4.0B         |                    1 |   2026 | Qwen3.5-4B                    |
| [alphaedge-ai/gemma-3-4b-it-asm-32768](https://huggingface.co/alphaedge-ai/gemma-3-4b-it-asm-32768)         | 3.7B         |                    1 |   2026 | google/gemma-3-4b-it          |
| [ptrdvn/kakugo-3B-asm](https://huggingface.co/ptrdvn/kakugo-3B-asm)                                         | 3.4B         |                    1 |   2026 | ibm-granite/granite-4.0-micro |
| [alphaedge-ai/Qwen3.5-2B-asm-32768](https://huggingface.co/alphaedge-ai/Qwen3.5-2B-asm-32768)               | 1.8B         |                    1 |   2026 | Qwen3.5-2B                    |
| [dheeyantra/dhee-nxtgen-qwen3-assamese-v2](https://huggingface.co/dheeyantra/dhee-nxtgen-qwen3-assamese-v2) | 1.7B         |                    1 |   2025 | —                             |

_54 tagged models have unknown parameter counts and are not ranked by size._

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

**11** benchmark datasets in the survey include Assamese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /   [2]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            / comprehension [3]  \
           /________________________\
          /    ✅ 3. Commonsense     \
         /      reasoning [2]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [4]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                             | # test items   | construction                                                     |
|:------------------------------|:-------------------------------|:----------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | COPA                           | [IndicCOPA](https://huggingface.co/datasets/ai4bharat/IndicCOPA)                                    | 500            | Human translation                                                |
| 3. Commonsense reasoning      | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel) | 100            | Native                                                           |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                       | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | [Indic QA Benchmark](https://github.com/ayushayush591/IndicQA-Benchmark)                            | 10,778         | Mixed: mostly MT of English/Hindi sources + native IndicQA/chaii |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                          | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                             | 500            | Native (cultural; native-speaker answers)                        |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)              | 100            | Native (community-written, peer-verified)                        |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                         | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                             | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                       | —              | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                | 233            | Native (crowdsourced Tatoeba sentence pairs)                     |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** HellaSwag, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style)

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Assamese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Assamese? Does it make sense to train one?
  - ~0.38 GB English-equivalent text ≈ 0.09B tokens, enough for a compute-optimal model of ~4.7M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Assamese-only model is 4.0B, aim no higher than
  *4. Reading comprehension* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 94 of ~18,498 papers (0.51%) (rank 61 of 278 in the set); English is mentioned in 8,465.
- Search terms: Assamese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 94):

| title                                                                                                                           | paper                                                                          |
|:--------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| How Good is Your Wikipedia? Auditing Data Quality for Low-resource and Multilingual NLP                                         | [2026.acl-long.1373](https://aclanthology.org/2026.acl-long.1373/)             |
| BornoDrishti: Leveraging Vision Encoders and Domain-Adaptive Learning for Bangla OCR on Diverse Documents                       | [2026.eacl-industry.20](https://aclanthology.org/2026.eacl-industry.20/)       |
| NE-MultiSpeech: A Multilingual Speech Corpus and ASR Benchmark for Northeast Indian Languages                                   | [2026.emnlp-main.2471](https://aclanthology.org/2026.emnlp-main.2471/)         |
| Morphological Analysis and Disambiguation of Agglutinative Assamese through Rule-Based Synthesis and Neural Candidate Ranking   | [2026.findings-emnlp.2118](https://aclanthology.org/2026.findings-emnlp.2118/) |
| NE-BERT: A Multilingual Language Model for Nine Northeast Indian Languages                                                      | [2026.loreslm-1.1](https://aclanthology.org/2026.loreslm-1.1/)                 |
| One Vector, Thirty-Eight Languages: Benchmark-Derived Anti-Sycophancy Steering Works Worst Where Sycophancy Is Worst            | [2026.oracle-main.12](https://aclanthology.org/2026.oracle-main.12/)           |
| Models Without Borders at SemEval-2026 Task 7: Bridging Cultural Contexts with Search-Grounded QA                               | [2026.semeval-1.407](https://aclanthology.org/2026.semeval-1.407/)             |
| GUIR at SemEval-2026 Task 7: Probing Cultural Knowledge in LLMs via Multi-Agent Debate                                          | [2026.semeval-1.438](https://aclanthology.org/2026.semeval-1.438/)             |
| TIP-RBG-AI: Overcoming Orthographic Discrepancies via Algorithmic Translinear Pipelines and Phylogenetic Script Mapping         | [2026.wmt-main.152](https://aclanthology.org/2026.wmt-main.152/)               |
| MTG-LIRA: Scaling Neural Machine Translation for Low-Resource Indian Languages through Multilingual Learning and Synthetic Data | [2026.wmt-main.153](https://aclanthology.org/2026.wmt-main.153/)               |

{% endraw %}
