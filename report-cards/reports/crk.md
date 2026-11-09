---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/crk.html
---
{% raw %}
# So you want to work on nēhiyawēwin?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `crk` · macrolanguage `cre`

**Official / recognised in:** Canada

**Status:** Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                             |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | **No Wikipedia edition**                                                                                                                                           |
| Common Crawl 2026      | **Not identified in Common Crawl's language statistics**                                                                                                           |
| FineWeb                | 0.4 MB (crk_Cans (0.00); crk_Latn (0.00)); 1.4 MB removed by filtering. This is ~1/130,280,459 of English data and ranks 214 of 248 official languages in FineWeb. |
| Goldfish training data | **No Goldfish model / data**                                                                                                                                       |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **2 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, funlangid.
- **Eval datasets (2):** Tatoeba (n=52), Wikipedia (n=90)
- **Best model:** GlotLID — F1 0.705 (P 0.984, R 0.550, FPR 1.40e-05) averaged over 2 dataset(s). Runner-up: funlangid (F1 0.059).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.984 |    0.550 | 0.705 | 0.000 | ✓                |
| funlangid    |       0.273 |    0.033 | 0.059 | 0.000 | ✓                |
| OpenLID-v2   |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| cld2         |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| commonlingua |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| fasttext     |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| py3langid    |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |
| pyfranc      |       0.000 |    0.000 | 0.000 | 0.000 | ✗                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia |  90 |       1.000 |    0.522 | 0.686 |
| Tatoeba   |  52 |       0.968 |    0.577 | 0.723 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in nēhiyawēwin to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: current LangID is weak)**: label text from nēhiyawēwin *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in nēhiyawēwin and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for nēhiyawēwin?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for nēhiyawēwin (and whether the model is exclusively tagged for nēhiyawēwin or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **19** text-generation models are explicitly tagged for nēhiyawēwin (7 original uploads, 12 fine-tunes/quantisations/merges).
- **0** are tagged *only* for nēhiyawēwin.
- Including tags inherited from base models: **19**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2023 |        1 | ██                   |
|   2024 |        0 |                      |
|   2025 |       10 | ████████████████████ |
|   2026 |        8 | ████████████████     |

### Most popular models tagged for nēhiyawēwin

| model                                                                                             | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                |
|:--------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-----------------------------|
| [Kirim-ai/Kirim-V1-Base](https://huggingface.co/Kirim-ai/Kirim-V1-Base)                           | 2,102                  |                    32 | 12.3B        |                    3 |   2025 | —                            |
| [ZeppelinCorp/Charm_15](https://huggingface.co/ZeppelinCorp/Charm_15)                             | 962                    |                   307 | unknown      |                   87 |   2025 | mattshumer/mistral-8x7b-chat |
| [Kirim-ai/Kirim-V2](https://huggingface.co/Kirim-ai/Kirim-V2)                                     | 716                    |                    72 | 28.5B        |                   11 |   2026 | —                            |
| [mickymultani/Cree-Llama-3.3-70B](https://huggingface.co/mickymultani/Cree-Llama-3.3-70B)         | 223                    |                    23 | 70.6B        |                    3 |   2026 | meta-llama/Llama-3.1-70B     |
| [Kolyadual/Newton-bot-3-text-mini-8B](https://huggingface.co/Kolyadual/Newton-bot-3-text-mini-8B) | 164                    |                    25 | 8.2B         |                  140 |   2026 | Qwen/Qwen3-8B-Base           |

### Most popular models tagged *only* for nēhiyawēwin

_none_

### Largest models tagged for nēhiyawēwin

| model                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of            |
|:------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                 | 0                      |                     0 | 1.9T         |                  140 |   2025 | —                        |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)     | 0                      |                     0 | 856.0B       |                  140 |   2025 | —                        |
| [mickymultani/Cree-Llama-3.3-70B](https://huggingface.co/mickymultani/Cree-Llama-3.3-70B) | 223                    |                    23 | 70.6B        |                    3 |   2026 | meta-llama/Llama-3.1-70B |
| [Kirim-ai/Kirim-V2](https://huggingface.co/Kirim-ai/Kirim-V2)                             | 716                    |                    72 | 28.5B        |                   11 |   2026 | —                        |
| [Kirim-ai/Kirim-1-Math](https://huggingface.co/Kirim-ai/Kirim-1-Math)                     | 1,738                  |                    24 | 16.2B        |                    3 |   2025 | Kirim-ai/Kirim-V1-Base   |

### Largest models tagged *only* for nēhiyawēwin

_none_

_9 tagged models have unknown parameter counts and are not ranked by size._

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

**2** benchmark datasets in the survey include nēhiyawēwin.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /    [0]     \
                /______________\
               /                \
              /                  \
             /   ❌ 4. Reading    \
            /  comprehension [0]   \
           /________________________\
          /    ❌ 3. Commonsense     \
         /       reasoning [0]        \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ✅ Machine translation [2]         \
/______________________________________________\
```

### What tasks exist?

| level               | task                | dataset                                                     |   # test items | Construction                        |
|:--------------------|:--------------------|:------------------------------------------------------------|---------------:|:------------------------------------|
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) |            854 | Human translation via English pivot |
| Machine translation | Machine translation | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet) |            854 | Human translation via English pivot |

### What tasks are missing?
- **1. Linguistic knowledge:** BLiMP, LAMBADA
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Figurative language & idioms, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WSC, WinoGrande
- **3. Commonsense reasoning:** COPA, HellaSwag, PIQA, Physical commonsense, Social commonsense, StoryCloze, Temporal reasoning, World knowledge
- **4. Reading comprehension:** Multiple-choice reading comprehension (Belebele-style), Extractive reading comprehension (SQuAD-style)
- **5. Knowledge & open-domain QA:** Knowledge/exam MCQ (MMLU-style), Open-domain / closed-book QA

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (❌ not yet — contribute it!): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (❌ not yet — contribute it!): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (❌ not yet — contribute it!): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing nēhiyawēwin datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for nēhiyawēwin? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest tagged (multilingual) model is 1.9T, aim no higher than
  *5. Knowledge & open-domain QA* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 10 of ~18,460 papers (0.05%) (rank 140 of 252 in the set); English is mentioned in 8,441.
- Search terms: nehiyawewin | Plains Cree

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                        | paper                                                                  |
|:---------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
| Neural Text-to-Speech for Myaamia: Speech Synthesis for an Indigenous Algonquian Language    | [2026.americasnlp-6.1](https://aclanthology.org/2026.americasnlp-6.1/) |
| Kelvi: A Morphological Parser to Support Tamil Literacy                                      | [2026.bea-1.21](https://aclanthology.org/2026.bea-1.21/)               |
| Private-Use Area Characters in the Wild: Signal or Noise?                                    | [2026.cawl-1.2](https://aclanthology.org/2026.cawl-1.2/)               |
| Developing A Hawaiian Corpus Toolkit for Data-Driven Language Learning                       | [2026.computel-1.18](https://aclanthology.org/2026.computel-1.18/)     |
| Exploring Cross-Lingual Voice Conversion Methods for Anonymizing Low-Resource Text-to-Speech | [2026.eacl-short.16](https://aclanthology.org/2026.eacl-short.16/)     |
| Goldfish: Monolingual Language Models for 350 Languages                                      | [2026.lrec-1.300](https://aclanthology.org/2026.lrec-1.300/)           |
| Two Ojibwe Constraint Grammars: Morphological Disambiguation and Dependency Parsing          | [2026.lrec-1.766](https://aclanthology.org/2026.lrec-1.766/)           |
| Keyboards for the Endangered Idu Mishmi Language                                             | [2026.sigul-1.5](https://aclanthology.org/2026.sigul-1.5/)             |
| Representation Learning Enables Language Identification in Zero - and Few -Shot Settings     | [2026.tacl-1.118](https://aclanthology.org/2026.tacl-1.118/)           |
| The Crawl Gap: Where Endangered-Language Web Content Is Lost Before It Reaches a Corpus      | [2026.wac-1.21](https://aclanthology.org/2026.wac-1.21/)               |

{% endraw %}
