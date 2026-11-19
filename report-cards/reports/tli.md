---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/tli.html
---
{% raw %}
# So you want to work on Tlingit?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `tli`

**Language family:** **Athabaskan-Eyak-Tlingit** ([Glottolog](https://glottolog.org/resource/languoid/id/tlin1245))

**Endangerment:** 🔴 nearly extinct (level 5 of 6 on Glottolog’s scale; source: ElCat: Critically Endangered (80% certain))

**Speakers:** 500 (first/second language not stated) ([Wikidata](https://www.wikidata.org/wiki/Q27792#P1098), 2016)

**Official / recognised in:** United States

**Status:** Regional official language


## What does Tlingit look and sound like?

**Written (Revised Popular orthography)**, sample text from [Omniglot](https://www.omniglot.com/writing/tlingit.htm):

> Chʼa yéi gugénkʼ áwé a kaax̱ shukalisʼúx̱, haa tlagoo ḵwáanxʼi aadé s ḵunoogu yé. Haa léelkʼw hás aadé yéi s jineiyi yé áwé, de áa awtulxaaji át áwé, áa haa waḵkeeyaḵaa. Ách áwé kakawtuwakélʼ. Dei kawtoo.aag̱óon áwé x̱á, haa tláa léelkʼw hás, haa tláa káak hás, hasdu ḵusteeyí, hasdu yoo x̱ʼatángi. Dei áa awtulixaaji át áwé, haa jiyís. Haa jeexʼ kakeeyakélʼ. Ách áwé tsu héide shugax̱tootáan, yá …

**Written (Canadian orthography)**, sample text from [Omniglot](https://www.omniglot.com/writing/tlingit.htm):

> Chʼa yê gugénkʼ áwé a kàxh shukałisʼúxh, hà tłagù khwânxʼi àdé s khunùgu yé. Hà łîłkʼw hás àdé yê s jinèyi yé áwé, de â awtułxàji át áwé, â hà wakhkìyakhà. Ách áwé kakawtuwakéłʼ. Dè kawtù.àghûn áwé xhá, hà tłà łîłkʼw hás, hà tłâ kâk hás, hasdu khustìyí, hasdu yù xhʼatángi. Dè â awtułixàji át áwé, hà jìyís. Hà jìxʼ kakìyakéłʼ. Ách áwé tsu hêde shugaxhtùtân, yá yàkhùsgé dàkèt, hà jìxʼ anákh has …

**Written (Email orthography)**, sample text from [Omniglot](https://www.omniglot.com/writing/tlingit.htm):

> Chʼa yéi gugénkʼ áwé a kaaxh shukalisʼúxh, haa tlagoo khwáanxʼi aadé s khunoogu yé. Haa léelkʼw hás aadé yéi s jineiyi yé áwé, de áa awtulxaaji át áwé, áa haa wakhkeeyakhaa. Ách áwé kakawtuwakélʼ. Dei kawtoo.aaghóon áwé xhá, haa tláa léelkʼw hás, haa tláa káak hás, hasdu khusteeyí, hasdu yoo xhʼatángi. Dei áa awtulixaaji át áwé, haa jiyís. Haa jeexʼ kakeeyakélʼ. Ách áwé tsu héide shugaxhtootáan, …

*Translation:* We have only uncovered a tiny portion of the way our ancient people used to do things. How our grandfathers used to handle things is what we had given up, what you told us to look at. That is why we untied it. We had tried it, you see, our mothersʼ grandfathers, our mothersʼ maternal uncles, their culture, their language. We had given them up for ourselves. You have untied it for us. That is why …

<sub>Text © Omniglot / Simon Ager and contributors.</sub>

**Spoken:** [Wikitongues](https://wikitongues.org/languages/tli/) has 1 video of Tlingit speakers. Watch [Lgeik'i Heather and Naakil.aan Hans speaking Lingit](https://wikitongues.org/videos/lgeikiheather-naakil-aanhans_20170329_tli/).


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

| Resource               | What exists                                                                  |
|:-----------------------|:-----------------------------------------------------------------------------|
| Universal Dependencies | **None found**                                                               |
| UniMorph               | **None found**                                                               |
| Wikidata labels        | 1 Wikidata items have a label in Tlingit. (Wikidata codes (labels): tli (1)) |
| Wordnets               | **None found**                                                               |

### Parallel data (for machine translation)

Text aligned with translations in other languages, mostly English: the basis for training and adapting translation systems.

| Resource                           | What exists                                                                                                                                                 |
|:-----------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OPUS                               | _Not computed yet: run `python -m lrc build parallel --parallel opus`._                                                                                     |
| Bible translations (eBible corpus) | **None in the eBible corpus.** It only includes openly licensed translations from [ebible.org](https://ebible.org), so a Bible translation may still exist. |
| Tatoeba                            | _Not computed yet: run `python -m lrc build parallel --parallel tatoeba`._                                                                                  |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 10 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **0 of 10** LangID models evaluated have this language code as a label that can be predicted.
- **No labelled LangID eval data** for this language — creating some is a high-value contribution.
- No model performance numbers are available.

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Tlingit to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data** **(priority: no eval data exists yet)**: label text from Tlingit *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Tlingit and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.
- **Create structured data:** Tlingit has no UD treebank, UniMorph data or wordnet yet. You could start a [Universal Dependencies treebank](https://universaldependencies.org/contributing/); contribute inflection tables to [UniMorph](https://unimorph.github.io/); build or link a wordnet via the [Open Multilingual Wordnet](https://omwn.org/).


## What models are available for Tlingit?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Tlingit (and whether the model is exclusively tagged for Tlingit or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

**No text-generation models on the Hugging Face Hub are tagged for Tlingit.**

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

**0** benchmark datasets in the survey include Tlingit.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ❌ 5. QA \
                 /   [0]    \
                /______________\
               /                \
              /                  \
             /   ❌ 4. Reading    \
            / comprehension [0]  \
           /________________________\
          /    ❌ 3. Commonsense     \
         /      reasoning [0]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ❌ 1. Linguistic | ❌ 2. Pragmatics  \
   /   knowledge [0]   |  & discourse [0]   \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

_None found._

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

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Tlingit datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Tlingit? Does it make sense to train one?
  - There is too little measured data (no FineWeb/Goldfish English-equivalent size) to say; data collection comes first.
- **Create new evals.** Start from the bottom of the pyramid. Since no tagged model with a known size exists, aim no higher than
  *1. Linguistic knowledge* for now; the first gap to fill is **1. Linguistic knowledge**.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 2 of ~18,498 papers (0.01%) (rank 227 of 278 in the set); English is mentioned in 8,465.
- Search terms: Tlingit

Here are up to ten papers that were published mentioning this language in 2026:

| title                                                                                                                       | paper                                                              |
|:----------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------|
| ChiKhaPo: A Large-Scale Multilingual Benchmark for Evaluating Lexical Comprehension and Generation in Large Language Models | [2026.acl-long.1555](https://aclanthology.org/2026.acl-long.1555/) |
| Communicating with the Entire Population: Machine Translation of Emergency Alerts and Warnings                              | [2026.lt4cpr-1.6](https://aclanthology.org/2026.lt4cpr-1.6/)       |

{% endraw %}
