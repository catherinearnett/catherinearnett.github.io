--
layout: default
title: Database
nav_order: 5
has_children: false
permalink: /reduplication_database
---

# Reduplication Database

## Geographical Distribution of Languages
<iframe src="/assets/red_database_map.png" height="400" width="600"></iframe>


## Download CSV

<a href="assets/test_reduplication_database.csv">Download File</a>

## Data Sample

| Areal location             | Status     | Productivity      | Type    | Unit     | Length       | Fixed segments          | Fixed segment notes | Copy site                    | Attachment site | Attachment site notes         | Attachment adjacency | Underapplication | Triggering      | Overapplication | Base alternation | Multiple copies | Multiple patterns                                                        | Syntactic category         | Meaning            | Phi features                              |
|----------------------------|------------|-------------------|---------|----------|--------------|-------------------------|---------------------|------------------------------|-----------------|-------------------------------|----------------------|------------------|-----------------|-----------------|------------------|-----------------|--------------------------------------------------------------------------|----------------------------|--------------------|-------------------------------------------|
| micronesia                 | non-creole | productive        |         |          |              |                         |                     |                              |                 |                               |                      |                  |                 |                 |                  |                 |                                                                          |                            |                    |                                           |
| Abkahzia (Rep. of Georgia) | non-creole | productive        | partial | segments | 1 segment    | no                      | -                   | 1st consonant of verbal root | infix           | next to base, gemination-like | yes                  | no               | vowel insertion | no              | no               | no              | no                                                                       | verbs                      | action intensifier | n/a                                       |
| Abkahzia (Rep. of Georgia) | non-creole | productive        | full    | n/a      | -            | no                      | -                   | n/a                          | prefix          |                               | yes                  | no               | no              | no              | no               | no              | yes,  one example has word-final   vowel deleted in copy (or not copied) | nouns, adverbs, adjectives | adverbalization    | n/a                                       |
| Abkahzia (Rep. of Georgia) | non-creole | *not productive | partial | segments | 1-4 segments | à-o, k'-m, l-J̌, x-j | unpredictable       | **                           | **              | infix                         | yes                  | no               | no              | no              | no               | no              | yes                                                                      | ***                        | ***                | *** may have example of number and person |

## Features

| Category name         | Required information                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| language              | Name of the language                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| genus                 | Genus of the language                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Areal location        | Location where the language is primarily spoken. Fill in with one or more of the following categories: [this will be updated soon]                                                                                                                                                                                                                                                                                                                                                                                             |
| Status                | Creole or not?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Productivity          | Fill in with ‘productive’ if this type of reduplication is productive and ‘non-productive’ if this type of reduplication is not productive. If a language has both productive and non-productive reduplication, these should be input as separate entries                                                                                                                                                                                                                                                                      |
| type                  | Type of reduplication (with reference to the size of the reduplicant as compared with the root). Fill in with one or more of the following: full, partial, full+ segments not included in the base, partial+ segments not included in the base                                                                                                                                                                                                                                                                                 |
| unit                  | If looking at a partial reduplication pattern, according to what unit is the reduplicant measured? Fill in with one of the following: Segments, Moras, Syllables, Feet.  If looking at a total reduplication pattern, fill in with N/A                                                                                                                                                                                                                                                                                         |
| length                | If looking at a partial reduplication pattern, how many units long is the reduplicant? Fill in with a roman numeral and the type of unit (e.g. 2 moras)                                                                                                                                                                                                                                                                                                                                                                        |
| Fixed segments        | Does the reduplicant have any fixed (non-copied) segments? Fill in with ‘yes’ or ‘no’                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Fixed segment notes   | If the reduplicant has (a) fixed segment(s), record the segment, its location, and any conditions on its presence (e.g. [i], affix-final, occurs when the initial segment of the base is a consonant)                                                                                                                                                                                                                                                                                                                          |
| Copy site             | What part of the word is copied? Fill in with the edge and the number of units (e.g. leftmost 2 syllables of the base). If the copy does not begin at an edge, record the nearest edge as well as the number of units copied, and the number of units intervening between the copied portion of the word and the nearest edge (e.g. 2 moras preceding the rightmost mora of the base)                                                                                                                                          |
| Attachment site       | Where does the reduplicant attach to the base? Fill in with one or more of the following: prefix, suffix, infix, indeterminate                                                                                                                                                                                                                                                                                                                                                                                                 |
| Attachment site notes | If the reduplicant is an infix, record exactly where it infixes (e.g. between the first and second syllables). Record whether the relevant unit for describing the location of infixing is the same as the relevant unit for describing the size of the reduplicant by filling in ‘unit = same’ or ‘unit = different’. If reduplicants have more than one attachment site, record the conditions for each (e.g. infix if the initial segment of the base is a consonant, prefix if the initial segment of the base is a vowel) |
| Attachment adjacency  | Is the place where the reduplicant attaches to the base adjacent to the part of the word that was copied? Fill in ‘yes’ or ‘no’                                                                                                                                                                                                                                                                                                                                                                                                |
| Underapplication      | Are there phonological processes that apply in the language in general but do not apply in the reduplication context? Fill in ‘yes’ or ‘no’ followed by the name of the process if applicable. (e.g. yes, nasal assimilation)                                                                                                                                                                                                                                                                                                  |
| Triggering            | Are there phonological processes that are triggered by the reduplication process? Fill in ‘yes’ or ‘no’ followed by the name of the process if applicable (e.g. yes, nasal assimilation)                                                                                                                                                                                                                                                                                                                                       |
| Overapplication       | Are there any phonological processes that overapply in the reduplication context? Fill in ‘yes’ or ‘no’ followed by the name of the process if applicable (e.g. yes, nasal assimilation)                                                                                                                                                                                                                                                                                                                                       |
| Base alternation      | Does the base undergo any change(s) when in the context of reduplication? Fill in ‘yes’ or ‘no’ followed by a description of the change if applicable (e.g. yes, final consonant is deleted)                                                                                                                                                                                                                                                                                                                                   |
| Multiple copies       | Are multiple copies allowed? (How) does this affect the meaning? Fill in ‘yes’ or ‘no’ followed by the number of copies, and a description of the effect on the meaning if applicable (e.g. yes, 2 copies, durative meaning). Count the number of copies according to the following system: the form mumu-muto has two copies. The form mu-muto has one copy.                                                                                                                                                                  |
| Multiple patterns     | Can a single word undergo multiple reduplication patterns? Fill in ‘yes’ or ‘no’ followed by a description of the patterns and any restrictions. (e.g. yes, bisyllabic bases may undergo partial or total reduplication).                                                                                                                                                                                                                                                                                                      |
| Syntactic category    | If reduplication only applies to roots from (a) specific syntactic category/ies (e.g. verbs), list the category/ies                                                                                                                                                                                                                                                                                                                                                                                                            |
| Meaning               | State the meaning marked by the reduplication pattern. If a single reduplication pattern can mark more than one meaning, list all of the meanings. If a single meaning can be marked by more than one reduplication pattern, make a separate entry for each pattern.                                                                                                                                                                                                                                                           |
| Phi features          | If the meaning marked by reduplication involves a change in the value of person, number, or gender features of the base, record the change                                                                                                                                                                                                                                                                                                                                                                                     |
| notes                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |