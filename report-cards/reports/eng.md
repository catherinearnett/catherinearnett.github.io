---
layout: null
nav_exclude: true
search_exclude: true
sitemap: false
permalink: /report-cards/reports/eng.html
---
{% raw %}
# So you want to work on English?

This report is designed to help compile existing resources to give you an idea of where your efforts can be best spent.

**ISO 639-3:** `eng`

**Writing systems:** `Latn`

**Official / recognised in:** Antigua and Barbuda, Australia, Barbados, Belize, Botswana, Burkina Faso, Burundi, Cameroon, Canada, Dominica, Eritrea, Eswatini, Federated States of Micronesia, Fiji, Ghana, Grenada, Guyana, India, Ireland, Jamaica, Kenya, Kingdom of the Netherlands, Kiribati, Lesotho, Liberia, Malawi, Malta, Marshall Islands, Mauritius, Namibia, Nauru, New Zealand, Nigeria, Pakistan, Palau, Papua New Guinea, People's Republic of China, Philippines, Rwanda, Saint Kitts and Nevis, Saint Lucia, Saint Vincent and the Grenadines, Samoa, Seychelles, Sierra Leone, Singapore, Solomon Islands, South Africa, South Sudan, Sudan, Tanzania, The Bahamas, The Gambia, Tonga, Trinidad and Tobago, Tuvalu, Uganda, United Kingdom, United States, Vanuatu, Zambia, Zimbabwe

**Status:** Official language; Official working language; Regional official language; De facto official language


## Training Data

### How much existing data is there?

Let's consider some of the most popular sources of training data:

| Source                 | Amount                                                                                                                                                                                                 |
|:-----------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wikipedia              | 7,546,466 articles in en, simple.wikipedia (rank 1 of 161 in the set) — about the same as English; 270,358 active users                                                                                |
| Common Crawl 2026      | 891,507,483 pages per crawl on average, which is 41.3503% of the crawl. This is about the same amount as English and ranks 1 of 113 official languages in Common Crawl.                                |
| FineWeb                | 53,417.98 GB (fineweb data/); which is equivalent to ≈53,417.98 GB English data after byte-premium scaling. This is about the same amount as English and ranks 1 of 248 official languages in FineWeb. |
| Goldfish training data | 10.71 GB (eng_latn) (rank 8 of 166 in the set)                                                                                                                                                         |

### How good are we at identifying data?

Language identification (LangID or LID) is a classification task that identifies what language a text is in and it remains a challenging task for many languages. We consider a set of 8 popular models and test on samples of 7 common eval datasets. We ask which models can even predict this language (i.e. how many of them have the language code as one of their labels), whether the language is represented in any or all of the eval datasets, and how well the models do.

- **8 of 8** LangID models evaluated have this language code as a label that can be predicted: GlotLID, OpenLID-v2, cld2, commonlingua, fasttext, funlangid, py3langid, pyfranc.
- **Eval datasets (7):** CommonLID (n=300), FLORES (n=300), NTREX (n=300), SmolSent (n=300), Tatoeba (n=300), UDHR-LID (n=58), Wikipedia (n=300)
- **Best model:** GlotLID — F1 0.843 (P 0.769, R 0.989, FPR 4.06e-03) averaged over 7 dataset(s). Runner-up: py3langid (F1 0.802).

**All models (averaged over datasets):**

| model        |   precision |   recall |    f1 |   fpr | supports label   |
|:-------------|------------:|---------:|------:|------:|:-----------------|
| GlotLID      |       0.769 |    0.989 | 0.843 | 0.004 | ✓                |
| py3langid    |       0.730 |    0.976 | 0.802 | 0.007 | ✓                |
| OpenLID-v2   |       0.735 |    0.963 | 0.800 | 0.005 | ✓                |
| pyfranc      |       0.809 |    0.765 | 0.755 | 0.003 | ✓                |
| funlangid    |       0.712 |    0.858 | 0.748 | 0.005 | ✓                |
| commonlingua |       0.685 |    0.917 | 0.745 | 0.006 | ✓                |
| fasttext     |       0.628 |    0.987 | 0.727 | 0.010 | ✓                |
| cld2         |       0.485 |    0.975 | 0.624 | 0.015 | ✓                |

**Best model (GlotLID) by dataset**:

| dataset   |   n |   precision |   recall |    f1 |
|:----------|----:|------------:|---------:|------:|
| Wikipedia | 300 |       0.269 |    0.993 | 0.423 |
| CommonLID | 300 |       0.698 |    0.933 | 0.799 |
| UDHR-LID  |  58 |       0.744 |    1.000 | 0.853 |
| Tatoeba   | 300 |       0.842 |    0.997 | 0.913 |
| NTREX     | 300 |       0.895 |    0.997 | 0.943 |
| SmolSent  | 300 |       0.965 |    1.000 | 0.982 |
| FLORES    | 300 |       0.971 |    1.000 | 0.985 |

### What can you do?

- To help make more data appear in Common Crawl, you can help **seed the crawl:** add URLs of sites written in English to [commoncrawl/web-languages](https://github.com/commoncrawl/web-languages).
- **Create LangID data**: label text from English *and* from closely related languages that might be confused with it.
- **Gather data from new sources:**
  - Look for datasets built for other purposes (UD treebanks, ASR transcripts, etc.) that contain high-quality text reliably in English and compile them ready for training data.
  - Find books or other materials that can be digitised, OCRed, or otherwise made available (check the license!).
  - Make them available on Hugging Face and tag them for the language.


## What models are available for English?

We scraped all `text-generation` models on Hugging Face and analyzed the metadata. We counted how many models are explicitly tagged for English (and whether the model is exclusively tagged for English or tagged for multiple languages). We note which models are fine-tunes or have been derived from other (most likely massively multilingual) models.

- **127,004** text-generation models are explicitly tagged for English (34,929 original uploads, 92,075 fine-tunes/quantisations/merges).
- **97,226** are tagged *only* for English.
- Including tags inherited from base models: **191,228**.

**Uploads by year**

|   year |   models |                      |
|-------:|---------:|:---------------------|
|   2022 |     4175 | ██                   |
|   2023 |     6963 | ███                  |
|   2024 |    25746 | █████████            |
|   2025 |    34636 | ████████████         |
|   2026 |    55484 | ████████████████████ |

### Most popular models tagged for English

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------|
| [openai-community/gpt2](https://huggingface.co/openai-community/gpt2)           | 969,147,969            | 31,775,505            | 137.0M       |                    1 |   2022 | —                 |
| [distilbert/distilgpt2](https://huggingface.co/distilbert/distilgpt2)           | 259,087,343            | 1,481,788             | 88.2M        |                    1 |   2022 | —                 |
| [Qwen/Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct) | 227,862,317            | 5,017,129             | 1.5B         |                    1 |   2024 | Qwen/Qwen2.5-1.5B |
| [facebook/opt-125m](https://huggingface.co/facebook/opt-125m)                   | 222,917,610            | 4,677,401             | 125.0M       |                    1 |   2022 | —                 |
| [Qwen/Qwen2.5-7B-Instruct](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct)     | 193,979,285            | 6,037,480             | 7.6B         |                    1 |   2024 | Qwen/Qwen2.5-7B   |

### Most popular models tagged *only* for English

| model                                                                           | downloads (all time)   | downloads (30 days)   | parameters   |   # languages tagged |   year | derivative of     |
|:--------------------------------------------------------------------------------|:-----------------------|:----------------------|:-------------|---------------------:|-------:|:------------------|
| [openai-community/gpt2](https://huggingface.co/openai-community/gpt2)           | 969,147,969            | 31,775,505            | 137.0M       |                    1 |   2022 | —                 |
| [distilbert/distilgpt2](https://huggingface.co/distilbert/distilgpt2)           | 259,087,343            | 1,481,788             | 88.2M        |                    1 |   2022 | —                 |
| [Qwen/Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct) | 227,862,317            | 5,017,129             | 1.5B         |                    1 |   2024 | Qwen/Qwen2.5-1.5B |
| [facebook/opt-125m](https://huggingface.co/facebook/opt-125m)                   | 222,917,610            | 4,677,401             | 125.0M       |                    1 |   2022 | —                 |
| [Qwen/Qwen2.5-7B-Instruct](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct)     | 193,979,285            | 6,037,480             | 7.6B         |                    1 |   2024 | Qwen/Qwen2.5-7B   |

### Largest models tagged for English

| model                                                                                                                 | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of                   |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:--------------------------------|
| [Blackfrost-Research/KIMI-K3-MXFP4-DERISKED-V2](https://huggingface.co/Blackfrost-Research/KIMI-K3-MXFP4-DERISKED-V2) | 40                     |                     2 | 2.8T         |                    2 |   2026 | moonshotai/Kimi-K3              |
| [GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF](https://huggingface.co/GrEarl/Kimi-K3-Abliterated-V1-Q2_K-GGUF)             | 291                    |                    72 | 2.8T         |                    3 |   2026 | Uniboshi/Kimi-K3-Abliterated-V1 |
| [MUSTJAB-KING/QUEEN-PRO](https://huggingface.co/MUSTJAB-KING/QUEEN-PRO)                                               | 149                    |                    43 | 2.4T         |                    1 |   2026 | —                               |
| [MUSTJAB-KING/QUEEN-FP8](https://huggingface.co/MUSTJAB-KING/QUEEN-FP8)                                               | 54                     |                    14 | 2.4T         |                    1 |   2026 | —                               |
| [kernelpool/Qwen3.8-2.4T-A95B-3bit-UVMAX](https://huggingface.co/kernelpool/Qwen3.8-2.4T-A95B-3bit-UVMAX)             | 2,156                  |                   221 | 2.4T         |                    1 |   2026 | Qwen/Qwen3.8-2.4T-A95B          |

### Largest models tagged *only* for English

| model                                                                                                     | downloads (all time)   |   downloads (30 days) | parameters   |   # languages tagged |   year | derivative of               |
|:----------------------------------------------------------------------------------------------------------|:-----------------------|----------------------:|:-------------|---------------------:|-------:|:----------------------------|
| [MUSTJAB-KING/QUEEN-PRO](https://huggingface.co/MUSTJAB-KING/QUEEN-PRO)                                   | 149                    |                    43 | 2.4T         |                    1 |   2026 | —                           |
| [MUSTJAB-KING/QUEEN-FP8](https://huggingface.co/MUSTJAB-KING/QUEEN-FP8)                                   | 54                     |                    14 | 2.4T         |                    1 |   2026 | —                           |
| [kernelpool/Qwen3.8-2.4T-A95B-3bit-UVMAX](https://huggingface.co/kernelpool/Qwen3.8-2.4T-A95B-3bit-UVMAX) | 2,156                  |                   221 | 2.4T         |                    1 |   2026 | Qwen/Qwen3.8-2.4T-A95B      |
| [ISTA-DASLab/Kimi-K3-P48NVFP4-MoESQ](https://huggingface.co/ISTA-DASLab/Kimi-K3-P48NVFP4-MoESQ)           | 717                    |                   443 | 1.8T         |                    1 |   2026 | moonshotai/Kimi-K3          |
| [kernelpool/LongCat-2.0-3bit-UVMAX](https://huggingface.co/kernelpool/LongCat-2.0-3bit-UVMAX)             | 1,025                  |                    65 | 1.6T         |                    1 |   2026 | meituan-longcat/LongCat-2.0 |

_16,782 tagged models have unknown parameter counts and are not ranked by size._

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

**101** benchmark datasets in the survey include English.

### The pyramid (bottom = basic linguistic competence, top = knowledge-heavy tasks)

```
                       /\
                      /  \
                     /    \
                    /      \
                   /        \
                  / ✅ 5. QA \
                 /    [23]    \
                /______________\
               /                \
              /                  \
             /   ✅ 4. Reading    \
            /  comprehension [2]   \
           /________________________\
          /    ✅ 3. Commonsense     \
         /       reasoning [20]       \
        /______________________________\
       /               |                \
      /                |                 \
     /                 |                  \
    / ✅ 1. Linguistic | ✅ 2. Pragmatics  \
   /  knowledge [24]   |  & discourse [32]  \
  /____________________|_____________________\
 /         ❌ Machine translation [0]         \
/______________________________________________\
```

### What tasks exist?

| level                                  | task                                     | dataset                                                                                                           | # test items   | Construction                                                                       |
|:---------------------------------------|:-----------------------------------------|:------------------------------------------------------------------------------------------------------------------|:---------------|:-----------------------------------------------------------------------------------|
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 860            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 330            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 1,000          | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 760            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 553            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [ACS](https://github.com/igorsterner/acs)                                                                         | 201            | Corpus-extracted + automatic manipulation                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [BLiMP](https://huggingface.co/datasets/nyu-mll/blimp)                                                            | 67,000         | Template-based                                                                     |
| 1. Linguistic knowledge                | BLiMP                                    | [BLiMPPI](https://github.com/arzuburcuguven/blimppi-data)                                                         | 212            | Treebank-based (automatic)                                                         |
| 1. Linguistic knowledge                | BLiMP                                    | [CLAMS](https://github.com/aaronmueller/clams)                                                                    | 157,000        | Template-based (Marvin & Linzen grammars, translated)                              |
| 1. Linguistic knowledge                | BLiMP                                    | [CausalGym](https://huggingface.co/datasets/aryaman/causalgym)                                                    | 2,900          | Template-based (from SyntaxGym)                                                    |
| 1. Linguistic knowledge                | BLiMP                                    | [Colorless green (Gulordava et al.)](https://github.com/facebookresearch/colorlessgreenRNNs)                      | 410            | Treebank-extracted (+ nonce variants)                                              |
| 1. Linguistic knowledge                | BLiMP                                    | CxMP                                                                                                              | 43,000         | LLM-generated from templates (+ human validation)                                  |
| 1. Linguistic knowledge                | BLiMP                                    | [Linzen et al. agreement](http://tallinzen.net/projects/lstm_agreement)                                           | 1,210,000      | Corpus-extracted (Wikipedia)                                                       |
| 1. Linguistic knowledge                | BLiMP                                    | [Marvin & Linzen](https://github.com/BeckyMarvin/LM_syneval)                                                      | 337,072        | Template-based                                                                     |
| 1. Linguistic knowledge                | BLiMP                                    | [MultiBLiMP 1.0](https://huggingface.co/datasets/jumelet/multiblimp)                                              | 770            | Treebank-based (automatic, UD + UniMorph)                                          |
| 1. Linguistic knowledge                | BLiMP                                    | [SyntaxGym](https://github.com/cpllab/syntaxgym-core)                                                             | 799            | Existing material (psycholinguistic test suites)                                   |
| 1. Linguistic knowledge                | BLiMP                                    | [Zorro](https://github.com/phueb/Zorro)                                                                           | 46,000         | Template-based                                                                     |
| 1. Linguistic knowledge                | LAMBADA                                  | [LAMBADA](https://huggingface.co/datasets/cimec/lambada)                                                          | 5,153          | Original                                                                           |
| 1. Linguistic knowledge                | LAMBADA                                  | [LAMBADA (OpenAI version)](https://huggingface.co/datasets/EleutherAI/lambada_openai)                             | 5,153          | Original (detokenized/preprocessed by OpenAI)                                      |
| 1. Linguistic knowledge                | LAMBADA                                  | [lambada_multilingual (marcob)](https://huggingface.co/datasets/marcob/lambada_multilingual)                      | 5,153          | Original                                                                           |
| 2. Pragmatics, discourse & coreference | Coherence & discourse                    | [DiscoEval](https://github.com/ZeweiChu/DiscoEval)                                                                | —              | Original                                                                           |
| 2. Pragmatics, discourse & coreference | Coherence & discourse                    | [Multilingual DiscoEval-style probing (Godunova & Voloshina)](https://github.com/mashagodunova/discource_probing) | —              | Automatically derived from UD treebanks                                            |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms             | [Fig-QA](https://huggingface.co/datasets/nightingal3/fig-qa)                                                      | —              | Original (crowd-written)                                                           |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms             | [MAPS (proverbs)](https://github.com/UKPLab/maps)                                                                 | 394            | Native (Wikiquote/Wiktionary proverbs; GPT-3.5 seed contexts rewritten by natives) |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms             | MIDAS                                                                                                             | —              | Native (dictionaries; LLM-refined meanings checked by natives)                     |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms             | [MultiPICo (irony)](https://huggingface.co/datasets/Multilingual-Perspectivist-NLU/MultiPICo)                     | 2,999          | Native (Reddit/Twitter, native-speaker annotation)                                 |
| 2. Pragmatics, discourse & coreference | Figurative language & idioms             | [SemEval-2022 Task 2 (idiomaticity)](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity)        | 5,352          | Native                                                                             |
| 2. Pragmatics, discourse & coreference | Gender-bias diagnostic (Winograd-format) | [WinoBias](https://github.com/uclanlp/corefBias)                                                                  | 1,580          | Original (template-based)                                                          |
| 2. Pragmatics, discourse & coreference | Gender-bias diagnostic (Winograd-format) | [WinoGender](https://github.com/rudinger/winogender-schemas)                                                      | 720            | Original (template-based)                                                          |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers           | [InQA+](https://github.com/mainlp/Multilingual-IQA)                                                               | 438            | Original (subtitles)                                                               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers           | [IndirectQA](https://github.com/mainlp/indirectQA)                                                                | 62             | Original (subtitles)                                                               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers           | [MultiPragEval](https://github.com/DojunPark/MultiPragEval)                                                       | 300            | Translation from Korean (DeepL + human verification)                               |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers           | [PUB](https://github.com/meetdoshi90/PUB)                                                                         | —              | Original (compiled from existing datasets)                                         |
| 2. Pragmatics, discourse & coreference | Implicature & indirect answers           | [Ruis et al. implicature benchmark](https://github.com/LauraRuis/do-pigs-fly)                                     | 600            | Original (from Circa-style annotations)                                            |
| 2. Pragmatics, discourse & coreference | Negation                                 | Multilingual negation minimal pairs (Hartmann et al.)                                                             | —              | Derived from XNLI (human-translated) + manual editing                              |
| 2. Pragmatics, discourse & coreference | Negation                                 | [Negated LAMA](https://github.com/norakassner/LAMA_primed_negated)                                                | —              | Original (template negation of LAMA)                                               |
| 2. Pragmatics, discourse & coreference | Negation                                 | [NoFEVER-ML](https://github.com/MIR-MU/negation)                                                                  | 2,600          | Original (rule-based negation + manual check)                                      |
| 2. Pragmatics, discourse & coreference | Negation                                 | [NoSNLI-ML](https://github.com/MIR-MU/negation)                                                                   | 6,261          | Original (rule-based negation + manual check)                                      |
| 2. Pragmatics, discourse & coreference | Negation                                 | [This is not a Dataset](https://huggingface.co/datasets/HiTZ/This-is-not-a-dataset)                               | —              | Original (semi-automatic)                                                          |
| 2. Pragmatics, discourse & coreference | Negation                                 | Thunder-NUBench                                                                                                   | —              | Original                                                                           |
| 2. Pragmatics, discourse & coreference | Presupposition & scalar implicature      | [IMPPRES](https://github.com/facebookresearch/Imppres)                                                            | 25,500         | Original (template-generated)                                                      |
| 2. Pragmatics, discourse & coreference | Presupposition & scalar implicature      | [ImplicaTR](https://github.com/kursathalat/ImplicaTR)                                                             | 3,888          | Parallel English version (from repo)                                               |
| 2. Pragmatics, discourse & coreference | Pronoun/coref (WSC-style)                | DPR (WSCR)                                                                                                        | 564            | Original (crowd-written, easier)                                                   |
| 2. Pragmatics, discourse & coreference | WNLI                                     | [WNLI (GLUE)](https://huggingface.co/datasets/nyu-mll/glue)                                                       | 71             | Original (recast)                                                                  |
| 2. Pragmatics, discourse & coreference | WSC                                      | PDP                                                                                                               | 122            | Original (collected)                                                               |
| 2. Pragmatics, discourse & coreference | WSC                                      | [PWS (Parallel Winograd Schemata)](https://github.com/nytud/PWS)                                                  | —              | Original                                                                           |
| 2. Pragmatics, discourse & coreference | WSC                                      | [SuperGLUE WSC](https://huggingface.co/datasets/aps/super_glue)                                                   | 146            | Original (recast)                                                                  |
| 2. Pragmatics, discourse & coreference | WSC                                      | [WSC273](https://huggingface.co/datasets/ErnestSDavis/winograd_wsc)                                               | 273            | Original                                                                           |
| 2. Pragmatics, discourse & coreference | WSC                                      | [WSC285](https://huggingface.co/datasets/ErnestSDavis/winograd_wsc)                                               | 285            | Original                                                                           |
| 2. Pragmatics, discourse & coreference | WSC                                      | [XWinograd](https://huggingface.co/datasets/Muennighoff/xwinograd)                                                | 2,325          | Original                                                                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                               | [AraDiCE-WinoGrande](https://huggingface.co/datasets/QCRI/AraDiCE-WinoGrande)                                     | 1,267          | Original                                                                           |
| 2. Pragmatics, discourse & coreference | WinoGrande                               | [WinoGrande](https://huggingface.co/datasets/allenai/winogrande)                                                  | 1,267          | Original (crowdsourced + adversarial filtering)                                    |
| 3. Commonsense reasoning               | COPA                                     | [Balanced COPA](https://huggingface.co/datasets/pkavumba/balanced-copa)                                           | 1,000          | Original (adapted)                                                                 |
| 3. Commonsense reasoning               | COPA                                     | [COPA](https://people.ict.usc.edu/~gordon/copa.html)                                                              | 500            | Original                                                                           |
| 3. Commonsense reasoning               | HellaSwag                                | GoldenSwag                                                                                                        | —              | Original (filtered)                                                                |
| 3. Commonsense reasoning               | HellaSwag                                | [HellaSwag](https://huggingface.co/datasets/Rowan/hellaswag)                                                      | 10,042         | Original                                                                           |
| 3. Commonsense reasoning               | HellaSwag                                | HellaSwag-Pro                                                                                                     | —              | Original (adapted: 7 robustness variants)                                          |
| 3. Commonsense reasoning               | HellaSwag                                | [MuBench HellaSwag](https://github.com/aialt/MuBench)                                                             | 9,088          | Original (filtered)                                                                |
| 3. Commonsense reasoning               | HellaSwag                                | [SWAG](https://huggingface.co/datasets/allenai/swag)                                                              | 20,006         | Original                                                                           |
| 3. Commonsense reasoning               | PIQA                                     | [Global PIQA (non-parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)               | 100            | Native                                                                             |
| 3. Commonsense reasoning               | PIQA                                     | [Global PIQA (parallel)](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-parallel)                      | 103            | Original                                                                           |
| 3. Commonsense reasoning               | PIQA                                     | [PIQA](https://huggingface.co/datasets/ybisk/piqa)                                                                | 1,838          | Original                                                                           |
| 3. Commonsense reasoning               | Physical commonsense                     | [PIQA](https://huggingface.co/datasets/ybisk/piqa)                                                                | 1,838          | Original (crowd-written)                                                           |
| 3. Commonsense reasoning               | Physical commonsense                     | [PROST](https://github.com/nala-cub/prost)                                                                        | 18,736         | Original (template-generated)                                                      |
| 3. Commonsense reasoning               | Social commonsense                       | [Social IQa](https://huggingface.co/datasets/allenai/social_i_qa)                                                 | 1,954          | Original (crowd-written)                                                           |
| 3. Commonsense reasoning               | StoryCloze                               | [MuBench StoryCloze](https://github.com/aialt/MuBench)                                                            | 1,332          | Original (filtered)                                                                |
| 3. Commonsense reasoning               | StoryCloze                               | [Story Cloze Test (Spring 2016)](https://www.cs.rochester.edu/nlp/rocstories/)                                    | 1,871          | Original                                                                           |
| 3. Commonsense reasoning               | StoryCloze                               | [Story Cloze Test (Winter 2018, SCT-v1.5)](https://www.cs.rochester.edu/nlp/rocstories/)                          | 1,571          | Original (adapted)                                                                 |
| 3. Commonsense reasoning               | StoryCloze                               | [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze)                                             | 1,511          | Original                                                                           |
| 3. Commonsense reasoning               | Temporal reasoning                       | [TRAM](https://github.com/EternityYW/TRAM-Benchmark)                                                              | —              | Original (existing datasets + templates + program generation)                      |
| 3. Commonsense reasoning               | Temporal reasoning                       | Temporal Reasoning Dataset (TRD)                                                                                  | 10,400         | Template-generated with native-curated carrier phrases                             |
| 3. Commonsense reasoning               | World knowledge                          | [EWoK-core-1.0](https://huggingface.co/datasets/ewok-core/ewok-core-1.0)                                          | 4,374          | Original (template-generated minimal pairs)                                        |
| 4. Reading comprehension               | QA – MC reading comprehension            | [Belebele](https://huggingface.co/datasets/facebook/belebele)                                                     | 900            | Original                                                                           |
| 4. Reading comprehension               | QA – extractive RC                       | [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa)                                        | 5,000          | Synthetic (LLM-generated) on native Wikipedia                                      |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [AfriMMLU (IrokoBench)](https://huggingface.co/datasets/masakhane/afrimmlu)                                       | 500            | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [BLEnD (MCQ)](https://huggingface.co/datasets/nayeon212/BLEnD)                                                    | 37,557         | Native (cultural, 16 countries)                                                    |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [EU20-ARC](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                          | —              | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [EU20-MMLU](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                         | —              | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [EU20-TruthfulQA](https://hf.co/collections/openGPT-X/eu20-benchmarks-67093b13db8ff192dc39312d)                   | —              | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [Global-MMLU](https://huggingface.co/datasets/CohereLabs/Global-MMLU)                                             | 14,042         | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | LAG-MMLU                                                                                                          | 112            | Original (MMLU sample)                                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [M3Exam](https://github.com/DAMO-NLP-SG/M3Exam)                                                                   | 2,738          | Native (national exams)                                                            |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [MILU](https://huggingface.co/datasets/ai4bharat/MILU)                                                            | 13,536         | Native (Indian exams; some translated)                                             |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [MMLU](https://huggingface.co/datasets/cais/mmlu)                                                                 | 14,042         | Original                                                                           |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [MMLU-ProX](https://huggingface.co/datasets/li-lab/MMLU-ProX)                                                     | 11,829         | Original (MMLU-Pro)                                                                |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [NOVA-63](https://huggingface.co/datasets/zjy1298/NOVA-63)                                                        | —              | Native (local exams/publications)                                                  |
| 5. Knowledge & open-domain QA          | QA – knowledge/exam MCQ                  | [m_MMLU (Okapi / alexandrainst)](https://huggingface.co/datasets/alexandrainst/m_mmlu)                            | —              | Machine translation (GPT-3.5, Okapi)                                               |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [BLEnD (short-answer)](https://huggingface.co/datasets/nayeon212/BLEnD)                                           | 8,000          | Native (cultural; native-speaker answers)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [CulturalRiddles](https://huggingface.co/datasets/CohereLabsCommunity/CulturalRiddles)                            | 100            | Native (community-written, peer-verified)                                          |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [French Trivia (FrenchBench)](https://huggingface.co/datasets/manu/french-trivia)                                 | —              | Native                                                                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [MKQA](https://github.com/apple/ml-mkqa)                                                                          | 10,000         | Original (NQ questions)                                                            |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [MultiLoKo](https://huggingface.co/datasets/facebook/multiloko)                                                   | 250            | Native (locally sourced)                                                           |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [Natural Questions (NQ-Open)](https://huggingface.co/datasets/google-research-datasets/nq_open)                   | 3,610          | Native                                                                             |
| 5. Knowledge & open-domain QA          | QA – open-domain / closed-book           | [TriviaQA](https://huggingface.co/datasets/mandarjoshi/trivia_qa)                                                 | —              | Native                                                                             |

### What tasks are missing?
- **Machine translation:** Machine translation

### Community benchmarks you can contribute to

- **[Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel)** (✅ included): Physical-commonsense questions written by native speakers about their own culture.
- **[Last Translation Benchmark](https://github.com/zouharvi/last-translation-benchmark)** (✅ included): Live benchmark of hard-to-translate inputs: submit a source, reference translation and verification rules that current MT systems fail; 10 accepted examples earns co-authorship.
- **[Cultural Riddles](https://culturalriddles.ai/)** (✅ included): Human-written, culturally grounded riddles (Cohere Labs Community); open contribution process.

### What can you do?

- **Implement tasks on the [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)** for the existing English datasets listed above, if they're not there already.
- **Make a leaderboard.** What is the best available model for English? Does it make sense to train one?
  - ~53,417.98 GB English-equivalent text ≈ 13,354.50B tokens, enough for a compute-optimal model of ~667.7B parameters trained from scratch (rule of thumb: 20 tokens/parameter, 4 bytes/token). Existing tagged models are already at least this size; evaluating and adapting them is likely a better use of effort than training from scratch.
- **Create new evals.** Start from the bottom of the pyramid. Since the largest English-only model is 2.4T, aim no higher than
  *5. Knowledge & open-domain QA* for now; every level up to there already has at least one dataset, so prioritise the missing task types listed above and natively-written (not translated) data.
  (If the only model is ~100M parameters, don't build QA tasks: the models probably can't do them.)
- **Translate existing evals, and contribute to the community benchmarks above** (Global PIQA, Last Translation Benchmark, Cultural Riddles).


## How much research is being done on this language?

- **Mentions in ACL papers in 2026:** 8,441 of ~18,460 papers (45.69%) (rank 1 of 252 in the set).
- Search terms: English

Here are up to ten papers that were published mentioning this language in 2026 (randomly sampled from 8,441):

| title                                                                                                                     | paper                                                                        |
|:--------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| Composing Within Constraints: A Benchmark for Thai Classical Poetry in Large Language Models                              | [2026.aacl-short.16](https://aclanthology.org/2026.aacl-short.16/)           |
| TONY: an open-source TOolkit for Nlp in psYchology                                                                        | [2026.acl-demo.65](https://aclanthology.org/2026.acl-demo.65/)               |
| Claim Verification in the Age of Large Language Models: A Survey                                                          | [2026.acl-srw.2](https://aclanthology.org/2026.acl-srw.2/)                   |
| TeleTables: A Benchmark for Evaluating LLM Understanding of Tables in Technical Standards                                 | [2026.emnlp-industry.103](https://aclanthology.org/2026.emnlp-industry.103/) |
| Probing Cultural Signals in Large Language Models through Author Profiling                                                | [2026.emnlp-main.316](https://aclanthology.org/2026.emnlp-main.316/)         |
| Mitigating Coordinate Prediction Bias from Positional Encoding Failures                                                   | [2026.findings-acl.1034](https://aclanthology.org/2026.findings-acl.1034/)   |
| RiddleBench: A New Generative Reasoning Benchmark for LLMs                                                                | [2026.findings-eacl.228](https://aclanthology.org/2026.findings-eacl.228/)   |
| Consistency Training Along the Transformer Stack                                                                          | [2026.findings-emnlp.472](https://aclanthology.org/2026.findings-emnlp.472/) |
| Incorporating Multiword Expressions in Galician Neural Machine Translation: Compositionality, Efficiency, and Performance | [2026.mwe-1.9](https://aclanthology.org/2026.mwe-1.9/)                       |
| Beyond Fine-Tuning: Procrustes Alignment of Multilingual Embeddings for Low-Resource Cross-Lingual Retrieval              | [2026.sigul-1.23](https://aclanthology.org/2026.sigul-1.23/)                 |

{% endraw %}
