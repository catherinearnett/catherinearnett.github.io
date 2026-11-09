---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/por.html
---
{% raw %}
# So you want to work on Portuguese?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `por`

**Writing systems:** `Latn`

**Official / recognised in:** Angola, Brazil, Cape Verde, Equatorial Guinea, Guinea-Bissau, Mozambique, People's Republic of China, Portugal, South Africa, São Tomé and Príncipe, Timor-Leste

**Status:** Official and national language; Official language; Regional official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                                     |
|:-----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 1,187,821 articles in pt.wikipedia (rank 15 of 161 in the set) — ~1/6 of English; 7,482 active users                                                                                                                       |
| Common Crawl 2026      | 53,640,997 pages per crawl on average, which is 2.4892% of the crawl. This is ~1/17 of English data and ranks 7 of 113 official languages in Common Crawl.                                                                 |
| FineWeb                | 275.91 GB (por_Latn (275.91)); which is equivalent to ≈251.32 GB English data after byte-premium scaling; 361.85 GB removed by filtering. This is ~1/194 of English data and ranks 9 of 248 official languages in FineWeb. |
| Goldfish training data | 8.86 GB (por_latn) (rank 20 of 166 in the set)                                                                                                                                                                             |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (6):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), Tatoeba (n=300), UDHR-LID (n=115), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.945 (P 0.916, R 0.981, FPR 7.49e-04) averaged over 6 dataset(s). Runner-up: py3langid (F1 0.900).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.916 |    0.981 | 0.945 | 0.001 | ✓                |
| py3langid    |       0.858 |    0.962 | 0.900 | 0.002 | ✓                |
| fasttext     |       0.812 |    0.981 | 0.876 | 0.003 | ✓                |
| OpenLID-v2   |       0.817 |    0.968 | 0.874 | 0.003 | ✓                |
| cld2         |       0.825 |    0.934 | 0.867 | 0.003 | ✓                |
| commonlingua |       0.844 |    0.857 | 0.848 | 0.002 | ✓                |
| pyfranc      |       0.838 |    0.751 | 0.787 | 0.002 | ✓                |
| funlangid    |       0.808 |    0.760 | 0.777 | 0.002 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| UDHR-LID  | 115 |       0.827 |    1.000 | 0.906 |
| Tatoeba   | 300 |       0.831 |    0.997 | 0.906 |
| CommonLID | 300 |       0.965 |    0.913 | 0.938 |
| Wikipedia | 300 |       0.910 |    0.977 | 0.942 |
| NTREX     | 300 |       0.971 |    0.997 | 0.984 |
| FLORES    | 300 |       0.993 |    1.000 | 0.997 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in Portuguese to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from Portuguese *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in Portuguese and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for Portuguese?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for Portuguese (and whether the model is exclusively tagged for Portuguese or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **7,177** text-generation models are explicitly tagged for Portuguese (1,607 original uploads, 5,570 fine-tunes/quantisations/merges).
- **635** are tagged *only* for Portuguese.
- Including tags inherited from base models: **32,211**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |       54 | █                    |
|   2023 |      115 | █                    |
|   2024 |     2122 | ████████████████     |
|   2025 |     2268 | █████████████████    |
|   2026 |     2618 | ████████████████████ |

### Most popular models tagged for Portuguese

| model                                                                                       | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of           |
|:--------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------------|
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | 193,587,916            | 4,504,499             | 8.0B         |                    8 |   2024 | meta-llama/Llama-3.1-8B |
| [meta-llama/Llama-3.2-1B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct) | 109,758,422            | 1,331,481             | 1.2B         |                    8 |   2024 | —                       |
| [bigscience/bloomz-560m](https://huggingface.co/bigscience/bloomz-560m)                     | 63,206,595             | 599,299               | 559.2M       |                   35 |   2022 | —                       |
| [meta-llama/Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B)                   | 60,177,779             | 477,238               | 1.2B         |                    8 |   2024 | —                       |
| [meta-llama/Llama-3.2-3B-Instruct](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct) | 50,920,320             | 872,223               | 3.2B         |                    8 |   2024 | —                       |

### Most popular models tagged *only* for Portuguese

| model                                                                                                                   | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of         |
|:------------------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------|
| [vabatista/question-generation-t5-small-pt-br-2](https://huggingface.co/vabatista/question-generation-t5-small-pt-br-2) | 646,962                | 9                     | unknown      |                    1 |   2023 | —                     |
| [unicamp-dl/ptt5-base-portuguese-vocab](https://huggingface.co/unicamp-dl/ptt5-base-portuguese-vocab)                   | 480,950                | 1,366                 | 222.9M       |                    1 |   2022 | —                     |
| [pucpr-br/Clinical-BR-LlaMA-2-7B](https://huggingface.co/pucpr-br/Clinical-BR-LlaMA-2-7B)                               | 425,605                | 17                    | 6.7B         |                    1 |   2024 | meta-llama/Llama-2-7b |
| [pierreguillou/gpt2-small-portuguese](https://huggingface.co/pierreguillou/gpt2-small-portuguese)                       | 387,375                | 2,906                 | unknown      |                    1 |   2022 | —                     |
| [maritaca-ai/sabia-7b](https://huggingface.co/maritaca-ai/sabia-7b)                                                     | 46,187                 | 628                   | 6.7B         |                    1 |   2023 | —                     |

### Largest models tagged for Portuguese

| model                                                                                                         | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of                     |
|:--------------------------------------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:----------------------------------|
| [misterlakaz/Midas-1922b](https://huggingface.co/misterlakaz/Midas-1922b)                                     | 0                      | 0                     | 1.9T         |                  140 |   2025 | —                                 |
| [orcarouter/Mistral-Large-4-1T-A52B-GGUF](https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF)     | 1,316                  | 1,316                 | 1.0T         |                   11 |   2026 | mistralai/Mistral-Large-4-1T-A52B |
| [misterlakaz/Ceramic-Base-856b](https://huggingface.co/misterlakaz/Ceramic-Base-856b)                         | 0                      | 0                     | 856.0B       |                  140 |   2025 | —                                 |
| [LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B-DSpark) | 2,057                  | 350                   | 751.4B       |                   10 |   2026 | —                                 |
| [Vanedap/K-EXAONE-2.0-750B-A37B](https://huggingface.co/Vanedap/K-EXAONE-2.0-750B-A37B)                       | 462                    | 43                    | 749.4B       |                   10 |   2026 | —                                 |

### Largest models tagged *only* for Portuguese

| model                                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                        |
|:--------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:-------------------------------------|
| [amadeusai/Amadeus-Verbo-FI-Qwen2.5-72B-PT-BR-Instruct](https://huggingface.co/amadeusai/Amadeus-Verbo-FI-Qwen2.5-72B-PT-BR-Instruct) | 2,032                  |                    48 | 72.7B        |                    1 |   2025 | Qwen/Qwen2.5-72B                     |
| [botbotrobotics/CabraLlama3-70b](https://huggingface.co/botbotrobotics/CabraLlama3-70b)                                               | 2,300                  |                    15 | 70.6B        |                    1 |   2024 | —                                    |
| [rhaymison/Mistral-8x7b-Quantized-portuguese-luana](https://huggingface.co/rhaymison/Mistral-8x7b-Quantized-portuguese-luana)         | 1,693                  |                    17 | 47.4B        |                    1 |   2024 | mistralai/Mixtral-8x7B-Instruct-v0.1 |
| [botbotrobotics/CabraCommand-r-v01-16k](https://huggingface.co/botbotrobotics/CabraCommand-r-v01-16k)                                 | 104                    |                    12 | 35.0B        |                    1 |   2024 | —                                    |
| [notfakerv/mentoria-rv-35b-a3b-preview](https://huggingface.co/notfakerv/mentoria-rv-35b-a3b-preview)                                 | 0                      |                     0 | 34.7B        |                    1 |   2026 | Qwen/Qwen3.6-35B-A3B                 |

_468 tagged models have unknown parameter counts and are not ranked by size._

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

**51** benchmark datasets in the survey include Portuguese.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [20]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [4]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [10]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /   knowledge [3]   |  & discourse [5]   \
  /____________________|_____________________\
 /         ✅ Machine translation [9]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                           | dataset                                                                                                    | # test items   | Construction                                                     |
|:---------------------------------------|:-------------------------------|:-----------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                          | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                       | 3,048          | Treebank-based (automatic, UD + UniMorph)                        |
| 1. Linguistic knowledge                | LAMBADA                        | [LAMBADA-poly (Polygl0t)](https://huggingface.co/datasets/Polygl0t/LAMBADA-poly)                           | 5,153          | Translation (method not stated)                                  |
| 1. Linguistic knowledge                | LAMBADA                        | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)               | 5,153          | Translation (method not stated)                                  |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)              | 1,994          | Native (Reddit/Twitter, native-speaker annotation)               |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms   | [SemEval-2022 Task 2 (idiomaticity)](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity) | 2,555          | Native                                                           |
| 2. Pragmatics, discourse & coreference | WSC                            | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                           | —              | Human translation (collected)                                    |
| 2. Pragmatics, discourse & coreference | WSC                            | Winograd Schemas in Portuguese                                                                             | —              | Human translation                                                |
| 2. Pragmatics, discourse & coreference | WSC                            | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                         | 263            | Human translation (collected)                                    |
| 3. Commonsense reasoning               | HellaSwag                      | [EU20-HellaSwag (HellaSwag-X)](https://huggingface.co/datasets/openGPT-X/hellaswagx)                       | —              | Machine translation (DeepL)                                      |
| 3. Commonsense reasoning               | HellaSwag                      | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                      | 9,088          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | HellaSwag                      | [Okapi HellaSwag (m_hellaswag)](https://huggingface.co/datasets/jon-tow/okapi_hellaswag)                   | 9,229          | Machine translation (GPT-3.5-turbo)                              |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)        | 100            | Native                                                           |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | PIQA                           | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)               | 103            | MT + human post-editing                                          |
| 3. Commonsense reasoning               | Social commonsense             | [SocialIQA-pt](https://huggingface.co/datasets/fabiogr/social_i_qa_pt)                                     | —              | Machine translation (MarianMT) + GEMBA-style LLM quality check   |
| 3. Commonsense reasoning               | StoryCloze                     | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                     | 1,332          | Machine translation (GPT-4o, auto-checked)                       |
| 3. Commonsense reasoning               | Temporal reasoning             | Temporal Reasoning Dataset (TRD)                                                                           | 10,400         | Template-generated with native-curated carrier phrases           |
| 4. Reading comprehension               | QA – MC reading comprehension  | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                              | 900            | Human translation (professional)                                 |
| 4. Reading comprehension               | QA – extractive RC             | FaQuAD                                                                                                     | 900            | Native                                                           |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 4. Reading comprehension               | QA – extractive RC             | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                 | 5,000          | Synthetic (LLM-generated) on native Wikipedia                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | BLUEX                                                                                                      | —              | Native (UNICAMP/USP entrance exams)                              |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | ENEM                                                                                                       | —              | Native (university entrance exam)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                  | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)            | —              | Machine translation (DeepL)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [EXAMS](https://github.com/mhardalov/exams-qa)                                                             | 924            | Native (high-school exams)                                       |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                      | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [INCLUDE (base-44)](https://huggingface.co/datasets/CohereLabs/include-base-44)                            | —              | Native (local exams)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                            | 1,385          | Native (national exams)                                          |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                              | 11,829         | LLM translation + expert review                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [MMMLU (OpenAI)](https://huggingface.co/datasets/openai/MMMLU)                                             | 14,042         | Human translation (professional)                                 |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                 | —              | Native (local exams/publications)                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | OAB Exams                                                                                                  | —              | Native (Brazilian bar exam)                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ        | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                     | —              | Machine translation (GPT-3.5, Okapi)                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                     | 100            | Native (community-written, peer-verified)                        |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MKQA](https://github.com/apple/ml-mkqa)                                                                   | 10,000         | Human translation                                                |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                            | 250            | Native (locally sourced)                                         |
| Machine translation                    | Machine translation            | [BOUQuET](https://huggingface.co/datasets/facebook/bouquet)                                                | 854            | Human translation via English pivot                              |
| Machine translation                    | Machine translation            | [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus)                                    | 1,012          | Human translation (professional, from English Wikimedia sources) |
| Machine translation                    | Machine translation            | [GATITOS (SMOL)](https://huggingface.co/datasets/google/smol)                                              | —              | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [NTREX-128](https://github.com/MicrosoftTranslator/NTREX)                                                  | 1,997          | Human translation (professional, from English)                   |
| Machine translation                    | Machine translation            | [TICO-19](https://github.com/tico-19/tico-19.github.io)                                                    | 2,100          | Human translation (professional/volunteer, from English)         |
| Machine translation                    | Machine translation            | [Tatoeba Challenge (v2023-09-26)](https://github.com/Helsinki-NLP/Tatoeba-Challenge)                       | 23,215         | Native (crowdsourced Tatoeba sentence pairs)                     |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                    |
| Machine translation                    | Machine translation            | [WMT24++](https://huggingface.co/datasets/google/wmt24pp)                                                  | 998            | Human translation (professional) + post-edits                    |

### What tasks are missing?
- **2. Pragmatics, discourse & coreference:** Coherence & discourse, Gender-bias diagnostic (Winograd-format), Implicature & indirect answers, Negation, Presupposition & scalar implicature, Pronoun/coref (WSC-style), WNLI, WinoGrande
- **3. Commonsense reasoning:** COPA, Physical commonsense, World knowledge

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing Portuguese datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for Portuguese? Does it make sense to train one?
  - ~251.32 GB English-equivalent text ≈ 62.83B tokens, enough for a compute-optimal model of ~3.1B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest Portuguese-only model is 72.7B, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 763 of ~18,460 papers (4.13%) (rank 11 of 252 in the set); English is mentioned in 8,441.
- Search terms: Portuguese

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 763):

| title                                                                                                            | paper                                                                          |
|:-----------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
| Beyond the Leaderboard: Rethinking Medical Benchmarks for Large Language Models                                  | [2026.acl-long.1996](https://aclanthology.org/2026.acl-long.1996/)             |
| Parity-Aware Byte-Pair Encoding: Improving Cross-lingual Fairness in Tokenization                                | [2026.acl-long.342](https://aclanthology.org/2026.acl-long.342/)               |
| Worldwide LiveVQA: Real-Time Visual Knowledge Seeking and Updating Across Languages                              | [2026.findings-acl.1984](https://aclanthology.org/2026.findings-acl.1984/)     |
| Proactive for Uncertainty: Cause-Aware Error Diagnosis and Interactive Clarification for Spoken Dialogue Systems | [2026.findings-emnlp.2332](https://aclanthology.org/2026.findings-emnlp.2332/) |
| LuxBorrow: From Pompier to Pompjee, Tracing Borrowing in Luxembourgish                                           | [2026.lrec-1.249](https://aclanthology.org/2026.lrec-1.249/)                   |
| Speak in Context: Multilingual ASR with Speech–Context Alignment via Contrastive Learning                        | [2026.lrec-1.466](https://aclanthology.org/2026.lrec-1.466/)                   |
| Lexicalized Constituency Parsing for Middle Dutch: Low-resource Training and Cross-Domain Generalization         | [2026.lrec-1.807](https://aclanthology.org/2026.lrec-1.807/)                   |
| Evaluating Automated Scoring Models on Official ENEM Essays                                                      | [2026.propor-1.16](https://aclanthology.org/2026.propor-1.16/)                 |
| A Larger Annotated Corpus of Portuguese Coreference                                                              | [2026.propor-2.33](https://aclanthology.org/2026.propor-2.33/)                 |
| Syntax is the Key to Semantics: Combining Universal Dependencies and Abstract Meaning Representation             | [2026.udw-1.27](https://aclanthology.org/2026.udw-1.27/)                       |

{% endraw %}
