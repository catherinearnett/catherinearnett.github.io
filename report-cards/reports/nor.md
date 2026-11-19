---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/nor.html
---
{% raw %}
# So you want to work on Norwegian?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `nor`

**Language family:** **Indo-European** › Classical Indo-European › Germanic › … › West Scandinavian ([Glottolog](https://glottolog.org/resource/languoid/id/norw1258))

**Endangerment:** 🟢 not endangered (level 1 of 6 on Glottolog’s scale; source: Ethnologue EGIDS 1 (National))

**Writing systems:** `Latn`

**Speakers:** about 5.5 million first- and second-language speakers ([CLDR](https://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)) · 5.2 million (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q9043#P1098), 2015)

**Official / recognised in:** Norway

**Status:** Official language


## What does Norwegian look and sound like?

**Written ( Bokmål )**, sample text from [Omniglot](https://www.omniglot.com/writing/norwegian.htm):

> Alle mennesker er født frie og med samme menneskeverd og menneskerettigheter. De er utstyrt med fornuft og samvittighet og bør handle mot hverandre i brorskapets ånd.
> A recording of this text by Magne Bergo

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_no.mp3) (Omniglot).

**Written ( Nynorsk )**, Article 1 of the Universal Declaration of Human Rights from [Omniglot](https://www.omniglot.com/writing/norwegian.htm):

> Alle menneske er fødde til fridom og med same menneskeverd og menneskerettar. Dei har fått fornuft og samvit og skal leve med kvarandre som brør.
> A recording of this text by Bard Esteland

*Translation:* All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. (Article 1 of the Universal Declaration of Human Rights) Mange takk to Anders Kvernberg, Haakon Krohn, Hilde Aas Nøst, Karl Sørensen, Heming Welde Thorbjørnsen, Kjell Ødegård, Charles Smith, Hugo Cesar, Knut Larsen, Bard …

[Hear this text read aloud](https://www.omniglot.com/soundfiles/udhr/udhr_ny.mp3) (Omniglot).

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** no Wikitongues video of Norwegian yet ([its Wikitongues page](https://wikitongues.org/languages/nor/) says how to contribute one).


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                               |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 875,865 articles in nn, no.wikipedia; 2,350 active users. NB: counted as `nno` + `nob` together.                                                                     |
| Common Crawl           | 7,130,240 pages per crawl on average, which is 0.3309% of the crawl (2026). This is ~1/125 of English data and ranks 25 of 113 languages in the set in Common Crawl. |
| FineWeb                | **Not in FineWeb / FineWeb-2**                                                                                                                                       |
| Goldfish training data | 1.45 GB (nor_Latn 1.45 GB) (rank 68 of 166 in the set)                                                                                                               |

### Structured and annotated data

Beyond raw text, annotated and lexical resources are useful for training, evaluation and tools: treebanks (syntax, part-of-speech, lemmas, morphology), inflection tables, knowledge-base labels and wordnets.

| Resource               | What exists                                                                                                                                                                                                                                                                                                                                           |
|:-----------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Universal Dependencies | 2 treebanks, 37,619 sentences / 611,574 tokens in total: [UD_Norwegian-Bokmaal](https://github.com/UniversalDependencies/UD_Norwegian-Bokmaal) (20,044 sentences), [UD_Norwegian-Nynorsk](https://github.com/UniversalDependencies/UD_Norwegian-Nynorsk) (17,575 sentences). All have POS tags, dependency syntax, lemmas and morphological features. |
| UniMorph               | 4,689 lemmas, 15,319 inflected forms ([unimorph/nno](https://github.com/unimorph/nno)); 17,930 lemmas, 77,871 inflected forms ([unimorph/nob](https://github.com/unimorph/nob))                                                                                                                                                                       |
| Wikidata labels        | 4,663,868 Wikidata items have a label in Norwegian. (Wikidata codes (labels): nb (4,663,868), nn (3,210,138), no (175,669))                                                                                                                                                                                                                           |
| Wordnets               | Norwegian wordnet (size not listed).                                                                                                                                                                                                                                                                                                                  |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **9 of 10** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, cld3, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (5):** FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=120), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.962 (P 0.957, R 0.967, FPR 3.58e-04) averaged over 5 dataset(s). Runner-up: py3langid (F1 0.923).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.957 |    0.967 | 0.962 | 0.000 | ✓                |
| py3langid    |       0.889 |    0.964 | 0.923 | 0.002 | ✓                |
| fasttext     |       0.872 |    0.979 | 0.919 | 0.002 | ✓                |
| OpenLID-v2   |       0.862 |    0.975 | 0.909 | 0.002 | ✓                |
| cld2         |       0.904 |    0.908 | 0.906 | 0.001 | ✓                |
| cld3         |       0.807 |    0.888 | 0.844 | 0.003 | ✓                |
| commonlingua |       0.755 |    0.898 | 0.819 | 0.003 | ✓                |
| pyfranc      |       0.736 |    0.828 | 0.778 | 0.004 | ✓                |
| funlangid    |       0.638 |    0.834 | 0.721 | 0.005 | ✓                |
| AfroLID      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Tatoeba   | 300 |       0.835 |    0.877 | 0.855 |
| Wikipedia | 300 |       0.974 |    0.987 | 0.980 |
| NTREX     | 300 |       0.990 |    0.980 | 0.985 |
| FLORES    | 300 |       0.993 |    0.990 | 0.992 |
| UDHR-LID  | 120 |       0.992 |    1.000 | 0.996 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Norwegian to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Norwegian *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Norwegian and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Record a speaker:** there's no [Wikitongues](https://wikitongues.org/languages/nor/) video of Norwegian yet. Openly licensed recordings help speech work and show what the language sounds like.


## What models are available for Norwegian?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Norwegian (and whether the model is exclusively tagged for Norwegian or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **967** text-generation models are explicitly tagged for Norwegian (254 original uploads, 713 fine-tunes/quantisations/merges).
- **177** are tagged *only* for Norwegian.
- Including tags inherited from base models: **1,908**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       18 | █                    |
|   2023 |       41 | ██                   |
|   2024 |      140 | ██████               |
|   2025 |      263 | ██████████           |
|   2026 |      505 | ████████████████████ |

### Largest models tagged for Norwegian

| model                                                                                                 | parameters   |   # languages tagged |   year | derivative of                    |
|:------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:---------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                             | 1.9T         |                  143 |   2025 | —                                |
| [anikifoss/Kimi-K2-Instruct-0905-HQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-0905-HQ4_K) | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct-0905 |
| [anikifoss/Kimi-K2-Instruct-DQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-DQ4_K)           | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct      |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                 | 856.0B       |                  143 |   2025 | —                                |
| [anikifoss/DeepSeek-R1-0528-DQ4_K_R4](https://huggingface.co/anikifoss/DeepSeek-R1-0528-DQ4_K_R4)     | 672.0B       |                    2 |   2025 | deepseek-ai/DeepSeek-R1-0528     |

### Largest models tagged *only* for Norwegian

| model                                                                                                                   | parameters   |   # languages tagged |   year | derivative of                       |
|:------------------------------------------------------------------------------------------------------------------------|:-------------|---------------------:|-------:|:------------------------------------|
| [anikifoss/Kimi-K2-Instruct-0905-HQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-0905-HQ4_K)                   | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct-0905    |
| [anikifoss/Kimi-K2-Instruct-DQ4_K](https://huggingface.co/anikifoss/Kimi-K2-Instruct-DQ4_K)                             | 1.0T         |                    1 |   2025 | moonshotai/Kimi-K2-Instruct         |
| [anikifoss/Qwen3-Coder-480B-A35B-Instruct-HQ4_K](https://huggingface.co/anikifoss/Qwen3-Coder-480B-A35B-Instruct-HQ4_K) | 480.2B       |                    1 |   2025 | Qwen/Qwen3-Coder-480B-A35B-Instruct |
| [anikifoss/GLM-4.5-HQ4_K](https://huggingface.co/anikifoss/GLM-4.5-HQ4_K)                                               | 358.3B       |                    1 |   2025 | zai-org/GLM-4.5                     |
| [anikifoss/GLM-4.6-HQ4_K](https://huggingface.co/anikifoss/GLM-4.6-HQ4_K)                                               | 356.8B       |                    1 |   2025 | zai-org/GLM-4.6                     |

_109 tagged models have unknown parameter counts and are not ranked by size._

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

**12** benchmark datasets in the survey include Norwegian.

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
 /         ✅ Machine translation [5]         \
/______________________________________________\
```

### What tasks exist?

| level                         | task                           | dataset                                                                                        | # test items   | construction                                                     |
|:------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 3. Commonsense reasoning      | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                          | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning      | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                         | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 4. Reading comprehension      | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                  | 900            | Human translation (professional)                                 |
| 4. Reading comprehension      | QA – extractive RC             | NorQuAD                                                                                        | —              | Native                                                           |
| 4. Reading comprehension      | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa) (2 varieties/pairs) | 10,000         | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)         | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                       | 10,000         | Human translation                                                |
| Machine translation           | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                    | 854            | Human translation via English pivot                              |
| Machine translation           | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus) (3 varieties/pairs)    | 3,036          | Human translation (professional, from English Wikimedia sources) |
| Machine translation           | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX) (2 varieties/pairs)                  | 3,994          | Human translation (professional, from English)                   |
| Machine translation           | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)           | 5,000          | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation           | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                      | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, PIQA, Physical commonsense, Social commonsense, Temporal reasoning, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Norwegian datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Norwegian? Does it make sense to train one?
  - ~1.29 GB English-equivalent text ≈ 0.32B tokens, enough for a compute-optimal model of ~16.1M parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Norwegian-only model is 1.0T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 174 of ~18,498 papers (0.94%) (rank 36 of 278 in the set); English is mentioned in 8,465.
- Search terms: Norwegian

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 174):

| title                                                                                                                | paper                                                                          |
|:---------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Retrievals Can Be Detrimental: Unveiling the Backdoor Vulnerability of Retrieval-Augmented Diffusion Models          | [2026.acl-long.242](https://aclanthology.org/2026.acl-long.242/)               |
| MuBench: Assessment of Multilingual Capabilities of Large Language Models Across 61 Languages                        | [2026.findings-acl.794](https://aclanthology.org/2026.findings-acl.794/)       |
| Rethinking Research on Stereotypes: An Analysis through Social Psychological and Computational Perspectives          | [2026.findings-acl.85](https://aclanthology.org/2026.findings-acl.85/)         |
| Improving Language Identification for Code-Switched Utterances with Integer Linear Programming                       | [2026.findings-emnlp.1429](https://aclanthology.org/2026.findings-emnlp.1429/) |
| Goldfish: Monolingual Language Models for 350 Languages                                                              | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)                   |
| Towards a Diagnostic and Predictive Evaluation Methodology for Sequence Labeling Tasks                               | [2026.lrec-1.472](https://aclanthology.org/2026.lrec-1.472/)                   |
| TildeOpen LLM: Leveraging Curriculum Learning to Achieve Equitable Language Representation                           | [2026.lrec-1.834](https://aclanthology.org/2026.lrec-1.834/)                   |
| OldBERTur: Named Entity Recognition for Medieval Icelandic                                                           | [2026.lt4hala-1.49](https://aclanthology.org/2026.lt4hala-1.49/)               |
| Disfluencies and ASR Performance on Swedish Spontaneous Speech from the ‘Trip to Stockholm’ Discourse Narrative Task | [2026.rapid-1.3](https://aclanthology.org/2026.rapid-1.3/)                     |
| Stage-Aware Cross-Lingual Transfer for Faroese ASR: When and Which Languages Matter                                  | [2026.speakable-1.17](https://aclanthology.org/2026.speakable-1.17/)           |

{% endraw %}
